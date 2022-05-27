---
title: Créer une file d’attente d’appels via des applets de commande
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Découvrez comment configurer des files d’attente d’appels via des applets de commande
ms.openlocfilehash: 8d62d3648d35cc302e333c2efa552bb2094cb14d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674576"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Créer une file d’attente d’appels via des applets de commande

## <a name="assumptions"></a>Hypothèses

1. PowerShell est installé sur votre ordinateur
   - Configurer votre ordinateur pour [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
   - Module MSTeams installé

     ```powershell
     Install-Module -Name MicrosoftTeams -Force -AllowClobber
     ```

   - Module MSOnline installé

     ```powershell
     Install-Module -Name MSOnline -Force -AllowClobber
     ```

2. Vous disposez de droits d’administration de locataire
3. Vous avez acheté Téléphonie Microsoft Teams
4. Les agents, listes de distribution et canaux Teams mentionnés ci-dessous ont déjà été créés

Remarque : l’applet de commande Teams Channel utilisée ci-dessous fait partie de la préversion publique de Teams module PowerShell.  Pour plus d’informations, consultez [Installer Teams préversion publique de PowerShell](teams-powershell-install.md) et consultez également [Microsoft Teams notes de publication powershell](teams-powershell-release-notes.md).

Les utilisateurs qui ont déjà installé le module MicrosoftTeams doivent `Update-Module MicrosoftTeams` s’assurer que la version la plus à jour est installée.

## <a name="scenario"></a>Scénario

Les trois files d’attente d’appels suivantes seront créées :

Informations sur la file d’attente des appels de ventes :

- Fronted by Auto Attendant: Yes
- Appel direct à partir de PSTN : Non
- Langue : Anglais US
- Message d’accueil : Aucun
- Musique en attente : Lire un fichier audio
  - Nom de fichier : sales-hold-in-queue-music.wav
- Réponse aux appels : Utilisateurs
  - Bill@contoso.com
  - Mary@contoso.com
- Mode conférence : activé
- Méthode de routage : Attendant
- Routage basé sur la présence : désactivé
- Les agents d’appel peuvent refuser de passer des appels : Oui
- Heure d’alerte de l’agent d’appel : 15
- Gestion du dépassement de capacité des appels : 200
  - Rediriger vers : Adele@contoso.com
- Gestion du délai d’expiration des appels : 120 secondes
  - Rediriger vers : Adele@contoso.com

Prise en charge des informations de file d’attente d’appels :

- Fronted by Auto Attendant: Yes
- Appel direct à partir de PSTN : Non
- Langue : Anglais Royaume-Uni
- Message d’accueil : Lire un fichier audio
  - Nom de fichier : support-greeting.wav
- Musique en attente : Lire un fichier audio
  - Nom de fichier : support-hold-in-queue-music.wav
- Réponse aux appels : liste de distribution du support
  - Support@contoso.com
- Mode conférence : activé
- Méthode de routage : idle le plus long
- Routage basé sur la présence : N/A – activé par défaut en raison de l’inactivité la plus longue
- Les agents d’appel peuvent refuser de passer des appels : Non
- Heure d’alerte de l’agent d’appel : 15
- Gestion du dépassement de capacité des appels : 200
  - Redirection : prise en charge de la messagerie vocale partagée
    - Lire un fichier audio (support-shared-voicemail-greeting.wav)
    - Transcription activée
- Gestion du délai d’expiration des appels : 45 minutes
  - Redirection : prise en charge de la messagerie vocale partagée
    - TTS : « Nous sommes désolés de vous avoir fait attendre et transférons maintenant votre appel à la messagerie vocale. »
    - Transcription activée

Informations sur la file d’attente d’appels collaboratifs d’installations :

- Fronted by Auto Attendant: No
- Appel direct à partir de PSTN : Non (appel interne uniquement)
- Langue : Français FR
- Message d’accueil : Aucun
- Musique en attente : valeur par défaut
- Répondeur d’appel : Équipe : Installations
- Canal de réponse aux appels : Support technique
  - Propriétaire du canal : Fred@contoso.com
- Mode conférence : activé
- Méthode de routage : Round Robin
- Routage basé sur la présence : activé
- Les agents d’appel peuvent refuser de passer des appels : Non
- Heure d’alerte de l’agent d’appel : 15
- Gestion du dépassement de capacité des appels : 200
  - Déconnexion
- Gestion du délai d’expiration des appels : 45 minutes
  - Déconnexion

## <a name="login"></a>Connexion

Vous serez invité à entrer vos informations d’identification d’administrateur Teams.

```powershell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
```

## <a name="sales-queue"></a>File d’attente des ventes

### <a name="create-audio-files"></a>Créer des fichiers audio

Remplacez « d:\\ » par le chemin d’accès à l’emplacement où les fichiers wav sont stockés sur votre ordinateur.

```powershell
$content = Get-Content "d:\sales-hold-in-queue-music.wav" -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
```

### <a name="get-users-id"></a>Obtenir l’ID d’utilisateur

```powershell
$userAdeleID = (Get-CsOnlineUser -Identity "sip:adele@contoso.com").Identity
$userSalesBillID = (Get-CsOnlineUser -Identity "sip:bill@contoso.com").Identity
$userSalesMaryID = (Get-CsOnlineUser -Identity "sip:mary@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>Obtenir la liste des langues prises en charge

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Créer une file d’attente d’appels

```powershell
New-CsCallQueue -Name "Sales" -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID "en-US"
```

### <a name="get-license-types"></a>Obtenir les types de licences

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Créer et attribuer un compte de ressource

Remarque : Téléphone numéro n’est pas obligatoire ici, car la file d’attente d’appels est terminée par un standard automatique

- ID d’application
  - Standard automatique : ce933385-9390-45d1-9512-c8d228074e07
  - File d’attente d’appels : 11cd3e2e-fccb-42ad-ad00-878b93575e07

Remarque : le type de licence indiqué ci-dessous (PHONESYSTEM_VIRTUALUSER) doit être répertorié par l’applet de commande Get-MsolAccountSku ci-dessus.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Sales-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="support-queue"></a>File d’attente de support

### <a name="create-audio-files"></a>Créer des fichiers audio

Remplacez « d:\\ » par le chemin d’accès à l’emplacement où les fichiers wav sont stockés sur votre ordinateur.

```powershell
$content = Get-Content "d:\support-greeting.wav" -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content "d:\support-hold-in-queue-music.wav" -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content "d:\support-shared-voicemail-greeting.wav" -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
```

### <a name="get-support-team-group-id"></a>Obtenir l’ID du groupe d’équipe de support

```powershell
$teamSupportID = (Get-Team -displayname "Support").GroupID
```

### <a name="get-list-of-supported-languages"></a>Obtenir la liste des langues prises en charge

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Créer une file d’attente d’appels

```powershell
New-CsCallQueue -Name "Support" -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID "en-US"
```

### <a name="get-license-types"></a>Obtenir les types de licences

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Créer et attribuer un compte de ressource

Remarque : Téléphone numéro n’est pas obligatoire ici, car la file d’attente d’appels est frontale par un standard automatique

- ID d’application
  - Standard automatique : ce933385-9390-45d1-9512-c8d228074e07
  - File d’attente d’appels : 11cd3e2e-fccb-42ad-ad00-878b93575e07

Remarque : le type de licence indiqué ci-dessous (PHONESYSTEM_VIRTUALUSER) doit être répertorié par l’applet de commande Get-MsolAccountSku ci-dessus.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Support-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="facilities-collaborative-calling-queue"></a>File d’attente d’appels collaboratifs d’installations

### <a name="get-facilities-team-group-id"></a>Obtenir l’ID du groupe d’équipe Facilities

```powershell
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
```

### <a name="get-facilities-help-desk-team-channel-id"></a>Obtenir l’ID de canal d’équipe du support technique d’installation

```powershell
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
```

### <a name="get-facilities-help-desk-channel-owner-user-id"></a>Obtenir l’ID d’utilisateur du propriétaire du canal Help Desk Facilities

```powershell
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
```

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Obtenir au nom de l’ID de compte de ressource d’appel

```powershell
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>Obtenir la liste des langues prises en charge

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Créer une file d’attente d’appels

```powershell
New-CsCallQueue -Name "Facilities" -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID "fr-FR" -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
```

### <a name="get-license-types"></a>Obtenir les types de licences

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Créer et attribuer un compte de ressource

**Remarque** : Téléphone numéro n’est pas obligatoire ici, car la file d’attente d’appels est frontale par un standard automatique

- ID d’application
  - Standard automatique : ce933385-9390-45d1-9512-c8d228074e07
  - File d’attente d’appels : 11cd3e2e-fccb-42ad-ad00-878b93575e07

Remarque : le type de licence indiqué ci-dessous (PHONESYSTEM_VIRTUALUSER) doit être répertorié par l’applet de commande Get-MsolAccountSku ci-dessus.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Facilities-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```
