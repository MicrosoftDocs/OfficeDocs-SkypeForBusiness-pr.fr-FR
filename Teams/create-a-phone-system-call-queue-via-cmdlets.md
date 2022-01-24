---
title: Créer une file d’attente d’appels via des cmdlets
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
description: Découvrir comment configurer les files d’attente d’appels via des cmdlets
ms.openlocfilehash: a8f24f11cb19f448fc897043c7cb046a08c32341
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2022
ms.locfileid: "62181107"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Créer une file d’attente d’appels via des cmdlets

## <a name="assumptions"></a>Hypothèses
1)  PowerShell est installé sur votre ordinateur
- Configurer votre ordinateur pour [l’Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
- Module MSTeams installé ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- Module MSOnline installé ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  Vous avez des droits d’administration des locataires
3)  Vous avez acheté des Microsoft Teams Téléphone
4)  Les agents, listes de distribution et canaux Teams ci-dessous ont déjà été créés.

Remarque : la cmdlet Teams canal utilisé ci-dessous fait partie de la version d’aperçu public Teams module PowerShell.  Pour plus d’informations, [voir installer Teams prévisualisation publique de PowerShell,](teams-powershell-install.md) ainsi que les Microsoft Teams de publication [de PowerShell.](teams-powershell-release-notes.md)

Les utilisateurs qui ont déjà installé le module MicrosoftTeams doivent s’assurer que la version la plus récente ````Update-Module MicrosoftTeams```` est installée.


## <a name="scenario"></a>Scénario

Les trois files d’attente d’appels suivantes sont créées :

Informations de la file d’attente des appels commerciaux :
- Fronted by Standard automatique: Yes
- Appels directs à partir du PSTN : Non
- Langue : Anglais (États-Unis)
- Message d’accueil : Aucun
- Musique attente : lire un fichier audio
- - Nom du fichier : sales-hold-in-queue-music.wav
- Réponse à un appel : Utilisateurs
- - Bill@contoso.com
- - Mary@contoso.com
- Mode conférence : sous
- Méthode de routage : Attendant
- Routage en fonction de la présence : non
- Les agents d’appel peuvent refuser de prendre des appels : Oui
- Heure d’alerte de l’agent d’appel : 15
- Gestion des dépassements d’appel : 200
- - Rediriger vers : Adele@contoso.com
- Traitement du délai d’appel : 120 secondes
- - Rediriger vers : Adele@contoso.com

Informations de la file d’attente d’appels du support :
- Fronted by Standard automatique: Yes
- Appels directs à partir du PSTN : Non
-   Langue : Anglais (Royaume-Uni)
-   Salutations : Lire un fichier audio
-   - Nom de fichier : support-greeting.wav
-   Musique attente : lire un fichier audio
-   - Nom du fichier : support-hold-in-queue-music.wav
-   Réponse à un appel : liste de distribution du support
-   - Support@contoso.com
-   Mode conférence : sous
-   Méthode de routage : Idle la plus longue
-   Routage basé sur la présence : N/A – sur par défaut en raison d’Idle la plus longue
-   Les agents d’appel peuvent refuser de prendre des appels : Non
-   Heure d’alerte de l’agent d’appel : 15
-   Gestion des dépassements d’appel : 200
-   - Redirection : Prise en charge de la messagerie vocale partagée
- - -   Lire un fichier audio (support-shared-voicemail-greeting.wav)
- - -   Transcription activée
-   Traitement du délai d’appel : 45 minutes
-   - Redirection : Prise en charge de la messagerie vocale partagée
- - - TTS : « Nous sommes désolés de vous avoir attendu et de transférer votre appel vers la messagerie vocale. »
- - - Transcription activée


Informations de la file d’attente d’appels en collaboration sur les installations :
- Fronted by Standard automatique: No
- Appels directs depuis PSTN : Non (appels internes uniquement)
-   Langue : Français (FR)
-   Message d’accueil : Aucun
-   Musique attente : par défaut
-   Réponse à un appel : Équipe : installations
-   Call Answering Channel: Help Desk
-   - Propriétaire du canal : Fred@contoso.com
-   Mode conférence : sous
-   Méthode de routage : Rond Rond
-   Routage en fonction de la présence : sur
-   Les agents d’appel peuvent refuser de prendre des appels : Non
-   Heure d’alerte de l’agent d’appel : 15
-   Gestion des dépassements d’appel : 200
-   - Déconnexion
-   Traitement du délai d’appel : 45 minutes
-   - Déconnexion


## <a name="login"></a>Connexion
Vous êtes invité à entrer vos informations d’identification d Teams administrateur.
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>File d’attente des ventes
### <a name="create-audio-files"></a>Créer des fichiers audio
Remplacez « d: \\ » par le chemin d’accès à l’endroit où les fichiers wav sont stockés sur votre ordinateur.

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>Obtenir l’ID d’utilisateur
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).ObectID
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).ObjectID
````

### <a name="get-list-of-supported-languages"></a>Obtenir la liste des langues prise en charge
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Créer une file d’attente d’appels
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>Obtenir les types de licences
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Créer et affecter un compte de ressource
Remarque : Téléphone numéro non requis ici, car la file d’attente d’appels est avant terminée par un Standard automatique
- ApplicationID
- - Standard automatique : ce933385-9390-45d1-9512-c8d228074e07
- - File d’attente d’appels : 11cd3e2e-fccb-42ad-ad00-878b93575e07

Remarque : le type de licence indiqué ci-dessous (PHONESYSTEM_VIRTUALUSER) doit être répertorié par l'Get-MsolAccountSku cmdlet ci-dessus.

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>File d’attente du support
### <a name="create-audio-files"></a>Créer des fichiers audio
Remplacez « d: \\ » par le chemin d’accès à l’endroit où les fichiers wav sont stockés sur votre ordinateur.

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>Obtenir l’ID du groupe d’équipe de support
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>Obtenir la liste des langues prise en charge
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Créer une file d’attente d’appels
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>Obtenir les types de licences
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Créer et affecter un compte de ressource
Remarque : Téléphone numéro non requis ici, car la file d’attente d’appels est frontale par un Standard automatique
- ApplicationID
- - Standard automatique : ce933385-9390-45d1-9512-c8d228074e07
- - File d’attente d’appels : 11cd3e2e-fccb-42ad-ad00-878b93575e07

Remarque : le type de licence indiqué ci-dessous (PHONESYSTEM_VIRTUALUSER) doit être répertorié par l'Get-MsolAccountSku cmdlet ci-dessus.

````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>File d’attente d’appels de collaboration d’installations
### <a name="get-facilities-team-group-id"></a>Obtenir l’ID du groupe d’équipe Installations
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>Obtenir l’ID de canal de l’équipe du service d’aide sur les installations
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-ower-user-id"></a>Obtenir l’ID utilisateur du canal du service d’aide sur les installations
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Obtenir de la part de l’ID de compte de ressource d’appel
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").ObjectID
````

### <a name="get-list-of-supported-languages"></a>Obtenir la liste des langues prise en charge
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Créer une file d’attente d’appels
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>Obtenir les types de licences
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Créer et affecter un compte de ressource
Remarque : Téléphone numéro non requis ici, car la file d’attente d’appels est frontale par un Standard automatique
- ApplicationID
- - Standard automatique : ce933385-9390-45d1-9512-c8d228074e07
- - File d’attente d’appels : 11cd3e2e-fccb-42ad-ad00-878b93575e07

Remarque : le type de licence indiqué ci-dessous (PHONESYSTEM_VIRTUALUSER) doit être répertorié par l'Get-MsolAccountSku cmdlet ci-dessus.

````
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````
