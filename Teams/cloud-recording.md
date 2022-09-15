---
title: Enregistrement de réunion cloud Teams
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
ms.localizationpriority: high
f1.keywords:
- NOCSH
description: Conseil pratique pour le déploiement de fonctionnalités vocales cloud dans Teams pour enregistrer des réunions et des appels de groupe Teams pour capturer l’activité audio, vidéo, et le partage d'écran.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1360847f187d98118d0b5468638cf1d6eb215fb8
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706861"
---
# <a name="teams-cloud-meeting-recording"></a>Enregistrement de réunion cloud Teams

Dans Microsoft Teams, les utilisateurs peuvent enregistrer leurs réunions et appels de groupe Teams pour capturer les activités audio, vidéo et de partage d’écran. Il existe également une option de transcription automatique des enregistrements qui permet aux utilisateurs de regarder les enregistrements des réunions avec des sous-titres et de rechercher des éléments de discussion importants dans la transcription. L’enregistrement se produit dans le cloud et est réalisé dans OneDrive et SharePoint, afin que les utilisateurs puissent le partager en toute sécurité au sein de leur organisation.

Lorsqu’une réunion est enregistrée, elle est automatiquement :

- Chargé sur OneDrive Entreprise ou SharePoint Online
- Autorisations accordées aux personnes invitées à la réunion
- Lié dans la conversation pour la réunion
- Affiché sous l’onglet Enregistrements et transcriptions de la réunion dans le calendrier Teams
- Ajouté à différentes listes de fichiers dans Microsoft 365 : Partagé avec moi, office.com, Recommandé, Récent, etc.
- Indexé pour la recherche Microsoft 365

Connexe : [documentation de l’utilisateur final sur l’enregistrement de la réunion Teams](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> Le passage de l’utilisation de Microsoft Stream (classique) à OneDrive et SharePoint pour les enregistrements de réunion aura lieu automatiquement en août 2021. Pour plus d’informations, consultez [Utiliser OneDrive et SharePoint ou Stream pour les enregistrements de réunion](tmr-meeting-recording-change.md).

> [!NOTE]
> Si vous souhaitez en savoir plus sur l’utilisation des rôles dans les réunions Teams et la méthode pour modifier les rôles des utilisateurs, consultez l’article [Rôles dans une réunion Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019). Pour les options d’enregistrement d’événements en direct, consultez l’article [Stratégies d’enregistrement des événements en direct dans Teams. ](teams-live-events/live-events-recording-policies.md).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Conditions préalables pour l’enregistrement de réunion cloud Teams

Pour que les réunions d’un utilisateur Teams soient enregistrées, OneDrive et SharePoint doivent être activés pour le client. De plus, les conditions préalables suivantes sont requises pour l’organisateur de la réunion et la personne qui lance l’enregistrement :

- L’utilisateur dispose d’un espace de stockage suffisant dans OneDrive pour enregistrer les sauvegardes de réunion hors canal.

- Le canal Teams dispose d’un espace de stockage suffisant dans SharePoint pour que les enregistrements des réunions de canal soient enregistrés.

- L’utilisateur a `CsTeamsMeetingPolicy -AllowCloudRecording` défini le paramètre sur true pour enregistrer les réunions et les appels de groupe.

- L’utilisateur a `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` défini le paramètre sur true pour enregistrer les appels 1:1.

- L’utilisateur ne doit pas être un utilisateur anonyme, invité ou fédéré de la réunion.

- Pour activer la transcription pour la réunion d’un utilisateur, la stratégie de réunion Teams à laquelle il est affecté doit avoir`-AllowTranscription` défini le paramètre sur true.

- Pour permettre l’enregistrement des enregistrements de réunion de canal afin que les membres du canal ne puissent pas modifier ou télécharger les enregistrements, le paramètre `CSTeamsMeetingPolicy -ChannelRecordingDownload` doit être défini sur Bloquer.

> [!IMPORTANT]
>
> Les utilisateurs n’ont pas besoin que OneDrive ou SharePoint soit activé si vous souhaitez que les utilisateurs enregistrent et téléchargent uniquement les enregistrements. Cela signifie que les enregistrements ne sont pas stockés dans OneDrive ou SharePoint, mais qu’ils sont stockés dans un stockage Teams temporaire avec une limite de 21 jours avant leur suppression. Il ne s’agit pas d’un élément qu’un administrateur peut contrôler, gérer ou supprimer pour l’instant.
>
> Pour plus [d’informations sur le fonctionnement du stockage d’enregistrement de réunion temporaire](#temp-storage), voir ci-dessous.  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurer l’enregistrement de réunions cloud Teams pour les utilisateurs de votre organisation

Cette section explique comment configurer et planifier l’enregistrement des réunions Teams via [stratégies de réunion Teams](policy-assignment-overview.md).

### <a name="turn-on-or-turn-off-cloud-recording"></a>Activer ou désactiver l’enregistrement dans le cloud

Vous pouvez utiliser le Centre d’administration Microsoft Teams ou PowerShell pour définir une stratégie de réunion Teams afin de contrôler si les réunions des utilisateurs peuvent être enregistrées.

Dans le Centre d’administration Microsoft Teams, activer ou désactiver le paramètre d’enregistrement **sur le nuage** dans la stratégie de réunion. Si vous souhaitez en savoir plus, consultez l’article [Paramètres de stratégie de réunion pour l’audio et la vidéo](meetings-policies-recording-and-transcription.md#cloud-recording).

À l’aide de PowerShell, vous configurez le paramètre AllowCloudRecording dans TeamsMeetingPolicy. Pour en savoir plus, consultez[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et [CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

L’organisateur de la réunion et l’initiateur d’enregistrement doivent disposer des autorisations d’enregistrement pour enregistrer la réunion. Sauf si vous avez affecté une stratégie personnalisée aux utilisateurs, les utilisateurs reçoivent la stratégie globale, laquelle AllowCloudRecording est activée par défaut.

> [!NOTE]
> Pour plus d’informations sur l’utilisation des rôles Teams pour configurer les utilisateurs autorisés à enregistrer une réunion, consultez [Rôles dans une réunion Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Pour qu’un utilisateur renvoie la stratégie globale, utilisez l’applet de commande suivante pour supprimer une affectation de stratégie spécifique pour un utilisateur :

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true
```

|Scénario|Étapes|
|--|--|
| Je souhaite que tous les utilisateurs de mon entreprise puissent enregistrer leurs réunions. | <ol><li>Vérifiez que la stratégie globale CsTeamsMeetingPolicy a AllowCloudRecording = True.<li>Tous les utilisateurs ont la stratégie globale CsTeamsMeetingPolicy OU l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = True.</ol> |
| Je souhaite que la plupart de mes utilisateurs puissent enregistrer leurs réunions, mais désactiver de manière sélective des utilisateurs spécifiques qui ne sont pas autorisés à enregistrer. | <ol><li>Vérifiez que la stratégie globale CsTeamsMeetingPolicy a AllowCloudRecording = True.<li>La plupart des utilisateurs ont la stratégie CsTeamsMeetingPolicy globale OU l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = True.<li>Tous les autres utilisateurs ont reçu l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = False.</ol> |
| Je souhaite que l’enregistrement soit 100 % désactivé. | <ol><li>Vérifiez que la stratégie globale CsTeamsMeetingPolicy a AllowCloudRecording = False.<li>Tous les utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy OU l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = False. |
| Je souhaite désactiver l’enregistrement pour la majorité des utilisateurs, mais activer de manière sélective des utilisateurs spécifiques autorisés à enregistrer. | <ol><li>Vérifiez que la stratégie globale CsTeamsMeetingPolicy a AllowCloudRecording = False.<li>La plupart des utilisateurs ont reçu la stratégie CsTeamsMeetingPolicy globale ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = False.<li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowCloudRecording = True. <ol> |

<a name="bd-channel"></a>

### <a name="block-or-allow-download-of-channel-meeting-recordings"></a>Bloquer ou autoriser le téléchargement des enregistrements de réunion de canal

Ce paramètre contrôle si les réunions de canal sont enregistrées dans un dossier « Recordings » ou un dossier « Recordings\View only » dans le canal. Le paramètre s’applique à la stratégie de l’utilisateur qui sélectionne l’enregistrement pour la réunion de canal.

Les deux valeurs de ce paramètre sont les suivantes :

- **Autoriser** (par défaut) : enregistre les enregistrements de réunion de canal dans un dossier « Recordings » dans le canal. Les autorisations sur les fichiers d’enregistrement sont basées sur les autorisations SharePoint du canal. Il s’agit du même fichier que n’importe quel autre fichier chargé pour le canal.

- **Bloquer**: enregistre les enregistrements de réunion de canal dans un dossier « Recordings\View only » dans le canal. Les propriétaires de canaux disposeront de droits complets sur les enregistrements de ce dossier, mais les membres du canal disposeront d’un accès en lecture sans possibilité de téléchargement.

À l’aide de PowerShell, vous configurez le paramètre ChannelRecordingDownload dans TeamsMeetingPolicy. Pour en savoir plus, consultez[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et [CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

Sauf si vous avez affecté une stratégie personnalisée aux utilisateurs, les utilisateurs obtiennent la stratégie globale, dont ChannelRecordingDownload est défini sur Autoriser par défaut.

Pour qu’un utilisateur renvoie la stratégie globale, utilisez l’applet de commande suivante pour supprimer une affectation de stratégie spécifique pour un utilisateur :

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Pour modifier la valeur de ChannelRecordingDownload dans la stratégie globale, utilisez l’applet de commande suivante :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -ChannelRecordingDownload Block
```

> [!NOTE]
> Le paramètre ChannelRecordingDownload est disponible uniquement dans le module Teams PowerShell version 2.4.1-preview ou ultérieure. Pour télécharger la dernière préversion du module, utilisez la commande suivante :
>
>```powershell
>Install-Module -Name MicrosoftTeams -Force -AllowClobber -AllowPrerelease
>```

### <a name="turn-on-or-turn-off-recording-transcription"></a>Activer ou désactiver la transcription de l’enregistrement

Ce paramètre détermine si les fonctionnalités de légende et de transcription sont disponibles lors de la lecture des enregistrements de réunion. La personne qui a lancé l'enregistrement doit activer ce paramètre pour que ces fonctionnalités fonctionnent avec son enregistrement.
  
L’activation de ce paramètre crée une copie de la transcription stockée avec l’enregistrement de la réunion, ce qui active **Recherche**, **CC** et **Transcriptions** sur l’enregistrement de réunion.

> [!NOTE]
> Cette transcription pour les réunions enregistrées est actuellement prise en charge uniquement pour l’anglais (États-Unis), l’anglais (Canada), l’anglais (Inde), l’anglais (Royaume-Uni), l’anglais (Australie), l’anglais (Nouvelle-Zélande), l’arabe (Émirats arabes unis) , l’arabe (Arabie saoudite), le chinois (simplifié, Chine), chinois (traditionnel, Hong Kong SAR), chinois (traditionnel, Taïwan), tchèque (Tchèque), danois (Danemark), néerlandais (Belgique), néerlandais (Pays-Bas), Français (Canada), Français (France), finnois (Finlande), allemand (Allemagne), Grec (Grèce), hébreu (Israël), hindi (Inde), hongrois (Hongrie), italien (Italie), japonais (Japon), coréen (Corée), norvégien (Norvège), polonais (Pologne), portugais (Brésil), portugais (Portugal), roumain (Romanie), russe (Russie), slovaque (Pologne), espagnol (Mexique), espagnol (Espagne), suédois (Suède), thaï (Thaïlande), turc (Turquie), ukrainien (Ukraine), vietnamien (Vietnam). Ils sont stockés avec les enregistrements de réunion dans OneDrive et le stockage cloud SharePoint.

Vous pouvez utiliser le Centre d’administration Microsoft Teams ou PowerShell pour définir une stratégie de réunion Teams afin de contrôler si l’initiateur d’enregistrement peut transcrire le choix de transcrire l’enregistrement de la réunion.

Dans le Centre d’administration Microsoft Teams, activez ou désactivez le paramètre **Autoriser la transcription** dans la stratégie de réunion. Si vous souhaitez en savoir plus, consultez l’article [Paramètres de stratégie de réunion pour l’audio et la vidéo](meetings-policies-recording-and-transcription.md#transcription).

À l’aide de PowerShell, vous configurez le paramètre AllowTranscription dans TeamsMeetingPolicy. Pour en savoir plus, consultez[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et [CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

Sauf si vous avez affecté une stratégie personnalisée aux utilisateurs, les utilisateurs reçoivent la stratégie globale, laquelle AllowTranscription est désactivée par défaut.

Pour qu’un utilisateur renvoie la stratégie globale, utilisez l’applet de commande suivante pour supprimer une affectation de stratégie spécifique pour un utilisateur :

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```

|Scénario|Étapes |
|---|---|
|Je souhaite que tous les utilisateurs de ma société soient en mesure de transcrire lors du lancement de l’enregistrement d’une réunion. |<ol><li>Confirmer que la stratégie globale CsTeamsMeetingPolicy a AllowTranscription = True. <li>Tous les utilisateurs ont la stratégie globale CsTeamsMeetingPolicy OU l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = True. </ol>|
|Je souhaite que la plupart de mes utilisateurs puissent transcrire les enregistrements de réunion, mais désactiver de manière sélective des utilisateurs spécifiques qui ne sont pas autorisés à transcrire. |<ol><li>Confirmer que la stratégie globale CsTeamsMeetingPolicy a AllowTranscription = True. <li>La plupart des utilisateurs ont la stratégie globale CsTeamsMeetingPolicy OU l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = True. <li>Tous les autres utilisateurs ont reçu l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = False. </ol>|
|Je souhaite que la transcription de l’enregistrement soit 100 % désactivée. |<ol><li>Confirmer que la stratégie globale CsTeamsMeetingPolicy a AllowTranscription = False. <li>Tous les utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy OU l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = False. </ol>|
|Je souhaite que la transcription soit désactivée pour la majorité des utilisateurs, mais activer de manière sélective des utilisateurs spécifiques qui sont autorisés à transcrire. |<ol><li>Vérifiez que la stratégie globale CsTeamsMeetingPolicy a AllowCloudRecording = False. <li>La majorité des utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy OU l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = False. <li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowCloudRecording = True. </ol>|

### <a name="terms-of-use-acceptance"></a>Acceptation des Conditions d’utilisation

Si votre organisation dispose d’une stratégie d’enregistrement des réunions que vous souhaitez que vos utilisateurs acceptent avant d’enregistrer une réunion, utiliser la fonctionnalité [Conditions d’utilisation Azure Active Directory](/azure/active-directory/conditional-access/terms-of-use). Cette fonctionnalité permet à vos utilisateurs d’accepter les conditions de la stratégie utilisateur de votre organisation avant d’accéder à Microsoft Teams. Cette fonctionnalité ne s’applique pas spécifiquement au clic sur le bouton Enregistrer. Elle est associée à l’utilisation de Teams ou d’autres applications Microsoft 365 en général. Notre suggestion est d’ajouter votre information d’enregistrement de la réunion aux conditions d'utilisation générales pour l’utilisateur de Teams ou de Microsoft 365.

### <a name="set-a-custom-privacy-policy-url"></a>Définir une URL de stratégie de confidentialité personnalisée

En tant qu'administrateur, vous pouvez mettre à jour l'URL de la stratégie de confidentialité de l'enregistrement et de la transcription de Teams avec un lien personnalisé pour votre organisation. Vous pouvez le faire dans le [Centre d’administration Azure AD](https://aad.portal.azure.com) en procédant comme suit :

1. Connectez-vous au centre d’administration Azure AD.
1. Accédez à **Azure Active Directory** > **Propriétés**.
1. Mettez à jour le champ de l’**URL de la déclaration de confidentialité** avec le lien vers votre stratégie de confidentialité.

> [!NOTE]
> Si vous avez déjà mis à jour ce champ pour votre organisation, vous n’avez pas besoin d’effectuer de modifications.

Après avoir ajouté l'URL de votre stratégie de confidentialité, la déclaration de confidentialité par défaut de l'enregistrement et de la transcription des réunions Teams sera remplacée par la nouvelle URL fournie par votre organisation.

> [!NOTE]
> Les utilisateurs anonymes, invités et fédérés qui participent à des réunions Teams hébergées par votre organisation seront toujours soumis à la stratégie de confidentialité par défaut en matière d'enregistrement et de transcription des réunions Teams.

## <a name="permissions-and-storage"></a>Autorisations et stockage

Les enregistrements de réunion sont stockés dans Le Stockage Cloud OneDrive et SharePoint. L’emplacement et les autorisations dépendent du type de réunion et du rôle de l’utilisateur dans la réunion. Les autorisations par défaut appliquées à l’enregistrement sont répertoriées ci-dessous. Les utilisateurs qui disposent de droits d’édition complets sur le fichier d’enregistrement vidéo peuvent modifier les autorisations et les partager ultérieurement avec d’autres personnes si nécessaire.

### <a name="non-channel-meetings"></a>Réunions hors canal

- L’enregistrement est stocké dans un dossier nommé **Enregistrements** dans le OneDrive de l’utilisateur qui a cliqué sur l’enregistrement. 

  Exemple :**enregistrements** OneDrive /*de l’enregistreur*

- Les personnes invitées à la réunion, à l’exception des participants externes, bénéficient automatiquement de l’autorisation d’accès au fichier d’enregistrement avec un accès en affichage sans possibilité de téléchargement.

- Le propriétaire de la réunion et la personne qui a cliqué sur l’enregistrement bénéficieront d’un accès de modification complet avec la possibilité de modifier les autorisations et de partager avec d’autres personnes.

### <a name="channel-meetings"></a>Réunions de canal

Si `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` est défini sur Autoriser (valeur par défaut) :

- L’enregistrement est stocké dans la bibliothèque de documentation du site Teams dans un dossier nommé **Recordings**.

   Exemple : *Nom teams - Enregistrements***documents**/ de nom / de canal

- Le membre qui a cliqué sur l’enregistrement dispose des droits de modification pour l’enregistrement.

- Les autorisations de tous les autres membres sont basées sur les autorisations canal SharePoint.

Si `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` est défini sur Bloquer :

- L’enregistrement est stocké dans la bibliothèque de documentation du site Teams dans un dossier nommé **Recordings/View only**. 

  Exemple : *Nom Teams - Nom*/ de canal **Documents/Enregistrements/Affichage uniquement**

- Les propriétaires de canaux disposeront de droits complets de modification et de téléchargement sur les enregistrements de ce dossier.

- Les membres du canal disposeront d’un accès en lecture seule sans possibilité de téléchargement.

Pour plus d’informations sur des types de réunions spécifiques, consultez le tableau suivant :

| Type de réunion  | Qui a cliqué sur Enregistrement ?| Où arrive l’enregistrement ? | Qui a accès ? En lecture et en écriture, lecture seule ou partage  |
|-------------|-----------------------|------------------------|------------------------|
|Appel individuel avec des parties internes             |Appelant                 |Compte OneDrive de l’appelant                        |L’appelant est propriétaire et dispose de tous les droits. <br /><br />L’appelé (si dans le même client) dispose d’un accès en lecture seule. Aucun accès de partage. <br /><br /> Le destinataire de l’appel (s’il est dans un client différent) ne dispose d’aucun accès. L’appelant doit partager le document avec le destinataire de l’appel.|
|Appel individuel avec des parties internes             |Destinataire de l’appel                 |Compte OneDrive de l’appelé                        |Le destinataire de l’appel est propriétaire et dispose de tous les droits. <br /><br />Appelant (si dans le même client) dispose d’un accès en lecture seule. Aucun accès de partage. <br /><br />L’appelant (s’il est dans un client différent) ne dispose d’aucun accès. Le destinataire de l’appel doit partager le document avec l’appelant.|
|Appel individuel avec des parties externes             |Appelant                 |Compte OneDrive de l’appelant                        |L’appelant est propriétaire et dispose de tous les droits.<br /> <br />Le destinataire de l’appel ne dispose d’aucun accès. L’appelant doit partager le document avec le destinataire de l’appel.|
|Appel individuel avec des parties externes             |Destinataire de l’appel                 |Compte OneDrive de l’appelé                        |Le destinataire de l’appel est propriétaire et dispose de tous les droits.<br /><br />L’appelant ne dispose d’aucun accès. Le destinataire de l’appel doit partager le document avec l’appelant.|
|Appel de groupe                                 |Tout membre de l’appel |Membre du groupe qui a cliqué sur le compte OneDrive de l’enregistrement  |Le membre qui a cliqué sur Enregistrement dispose de tous les droits. <br /><br /> Les autres membres du même client disposent de droits en lecture. <br /><br /> Les autres membres du groupe de différent clients n’y ont aucun droit.|
|Réunion ad hoc/planifiée                    |Organisateur              |Compte OneDrive de l’organisateur                     |L’organisateur dispose de droits complets sur l’enregistrement. <br /><br /> Tous les autres membres de la réunion disposent d’un accès en lecture sans possibilité de téléchargement.|
|Réunion ad hoc/planifiée                    |Autre membre de la réunion   |Membre de réunion qui a cliqué sur Enregistrer                                  |Le membre qui a cliqué sur Enregistrement dispose de tous les droits d’accès à l’enregistrement. <br /><br />L’organisateur dispose de droits de modification et de partage.<br /><br /> Tous les autres membres de la réunion disposent d’un accès en lecture sans possibilité de téléchargement.|
|Réunion ad hoc/planifiée avec des participants externes|Organisateur              |Compte OneDrive de l’organisateur                     |L’organisateur dispose de droits complets sur l’enregistrement.<br /> <br /> Tous les autres membres de la réunion du même client que l’organisateur disposent d’un accès en lecture sans possibilité de téléchargement. <br /><br /> Tous les autres membres externes n’ont pas d’accès, et l’organisateur doit le partager avec eux.|
|Réunion ad hoc/planifiée avec des participants externes|Autre membre de la réunion   |Membre qui a cliqué sur Enregistrement                                  |Le membre qui a cliqué sur Enregistrement dispose de tous les droits d’accès à l’enregistrement. L’organisateur dispose de droits de modification et de partage. <br /><br /> Tous les autres membres de la réunion du même client que l’organisateur disposent d’un accès en lecture sans possibilité de téléchargement. <br /><br />Tous les autres membres externes n’ont pas d’accès, et l’organisateur doit le partager avec eux.|
|Réunion de canal                            |Membre du canal         |Emplacement SharePoint de Teams pour ce canal                   |Si Set-CsTeamsMeetingPolicy -ChannelRecordingDownload est défini sur Autoriser (par défaut), le membre qui a cliqué sur Enregistrement dispose des droits de modification pour l’enregistrement. Les autorisations de tous les autres membres sont basées sur les autorisations canal SharePoint.<Br><Br>Si Set-CsTeamsMeetingPolicy -ChannelRecordingDownload est défini sur Bloquer, les propriétaires de canaux disposeront des droits complets sur l’enregistrement, mais les membres du canal disposeront d’un accès en lecture sans possibilité de téléchargement.|

<a name="temp-storage"></a>

### <a name="temporary-storage-when-unable-to-upload-to-onedrive-and-sharepoint"></a>Stockage temporaire en cas d’impossibilité de chargement vers OneDrive et SharePoint

Si un enregistrement de réunion ne peut pas être chargé sur OneDrive et SharePoint, il sera temporairement disponible en téléchargement à partir de Teams pendant 21 jours avant sa suppression. À ce stade, ce n’est pas quelque chose qu’un administrateur peut contrôler ou gérer pour inclure la possibilité de le supprimer.

Les enregistrements de réunion peuvent se retrouver dans ce stockage temporaire pour les raisons suivantes :

- Pour les réunions hors canal si l’utilisateur qui enregistre n’a pas OneDrive ou si son OneDrive a atteint son quota de stockage
- Pour une réunion de canal si le site SharePoint a atteint son quota de stockage ou si le site n’a pas encore été approvisionné
- Si des stratégies OneDrive et SharePoint spécifiques sont activées, empêchant les utilisateurs de charger des fichiers lorsqu’ils ne se trouvent pas sur des plages d’adresses IP spécifiques, etc.

La rétention d’enregistrement pour ce stockage temporaire est affectée par le message de conversation lui-même. Par conséquent, toute suppression du message de conversation d’origine pour l’enregistrement empêchera les utilisateurs d’accéder à l’enregistrement. Il existe deux scénarios qui peuvent affecter ceci :

- **L’utilisateur supprime manuellement le message de conversation**: dans ce scénario, à mesure que le message d’origine a disparu, les utilisateurs ne pourront plus accéder à l’enregistrement et aucun téléchargement supplémentaire ne sera possible. Toutefois, l’enregistrement lui-même peut toujours être conservé dans les systèmes internes de Microsoft pendant un certain temps (sans dépasser la période d’origine de 21 jours).

- **L’enregistrement du message de conversation est supprimé par la stratégie de rétention de conversation**: les enregistrements de stockage temporaires sont directement liés à la stratégie de rétention des conversations. Par conséquent, bien que les enregistrements sur le stockage temporaire Teams soient conservés par défaut pendant 21 jours avant d’être supprimés, si le message de conversation est supprimé avant la période de 21 jours, en raison des stratégies de rétention des messages de conversation, l’enregistrement est également supprimé. Il n’existe aucun moyen de récupérer l’enregistrement après cela.

### <a name="planning-for-storage"></a>Planification pour stockage

La taille d’un enregistrement de 1 heure est de 400 Mo. Veillez à bien comprendre la capacité requise pour les fichiers enregistrés et à disposer d’un espace de stockage suffisant dans OneDrive et SharePoint.  Lisez [Définir l’espace de stockage par défaut pour OneDrive](/onedrive/set-default-storage-space) et [gérer les limites de stockage de site SharePoint](/sharepoint/manage-site-collection-storage-limits) pour comprendre le stockage de base inclus dans l’abonnement et comment acheter du stockage supplémentaire.
  
## <a name="manage-meeting-recordings"></a>Gérer les enregistrements de réunion

Les enregistrements de réunion sont stockés sous forme de fichiers vidéo dans OneDrive et SharePoint et suivent les options de gestion et de gouvernance disponibles sur ces plateformes. Pour plus d’informations, consultez [la vue d’ensemble de la gouvernance SharePoint](/sharepoint/governance-overview) .

Pour les réunions hors canal, les enregistrements sont stockés dans l’espace OneDrive de l’enregistreur. Ainsi, la gestion de la propriété et de la rétention après le départ d’un employé suit le [processus OneDrive et SharePoint](/onedrive/retention-and-deletion#the-onedrive-deletion-process)normal.

Les enregistrements de réunion ont un délai d’expiration par défaut de 120 jours. Vous pouvez désactiver le paramètre d’expiration automatique des réunions ou modifier l’heure d’expiration par défaut. En savoir plus sur [l’expiration automatique des enregistrements de réunion](meetings-policies-recording-and-transcription.md#meetings-automatically-expire).

## <a name="closed-captions-for-recordings"></a>Sous-titres pour les enregistrements

Les sous-titres des enregistrements de réunion Teams ne seront disponibles pendant la lecture que si la transcription de l’utilisateur était activée au moment de l’enregistrement. Les administrateurs doivent [activer l’enregistrement de la transcription via la stratégie](#turn-on-or-turn-off-recording-transcription) pour s’assurer que leurs utilisateurs ont la possibilité d’enregistrer des réunions avec la transcription.

Les légendes permettent de créer du contenu inclusif pour les visiteurs de tous niveaux. En tant que propriétaire, vous pouvez masquer les sous-titres de l’enregistrement de la réunion, bien que la transcription de la réunion soit toujours disponible sur Teams, sauf si vous l’avez supprimé de cet emplacement.

Aujourd’hui, les sous-titres du fichier vidéo d’enregistrement sont liés à la transcription de la réunion Teams. Ce lien restera pendant la durée de vie du fichier dans la plupart des cas, mais il peut être rompu si le fichier vidéo est copié dans le même site OneDrive ou SharePoint, ce qui entraînerait l’inversion des sous-titres sur le fichier vidéo copié.

Les modifications futures apportées au lien entre la transcription dans Teams et l’enregistrement seront précisées ici et dans les notifications du centre de messages. Si nous apportons des modifications à l'avenir, nous veillerons à ce que les fichiers d'enregistrement datant de moins de 60 jours affichent la transcription de la réunion sous forme de sous-titres.

> [!NOTE]
> La transcription de réunion n’est pas encore disponible dans le Cloud de la communauté du secteur public.

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>eDiscovery et conformité pour les enregistrements de réunion

### <a name="ediscovery"></a>eDiscovery

Les enregistrements de réunion sont stockés dans OneDrive et SharePoint, qui est Microsoft 365 et office 365 de niveau D. Pour prendre en charge les demandes e-Discovery pour les administrateurs de conformité qui sont intéressés par les enregistrements de réunions ou d’appels, le message d’enregistrement terminé est disponible dans la fonctionnalité de recherche de contenu de conformité pour Microsoft Teams. Les administrateurs de conformité peuvent rechercher le mot clé « enregistrement » dans la ligne d’objet de l’élément dans le cadre de la recherche de contenu de conformité et découvrir les enregistrements de réunions et d’appels au sein de l’organisation.

En outre, le fichier vidéo d’enregistrement de réunion est disponible via des recherches eDiscovery pour les fichiers sur SharePoint et OneDrive.

Pour en savoir plus sur eDiscovery, consultez l’article [solutions eDiscovery pour Microsoft 365](/microsoft-365/compliance/ediscovery)

### <a name="retention-policies"></a>Stratégies de rétention

Vous pouvez appliquer des étiquettes de rétention automatiques pour cibler uniquement les fichiers vidéo d’enregistrement de réunion Teams via la propriété ProgID. Pour plus d’informations, consultez [Comment appliquer automatiquement une étiquette de rétention pour les enregistrements de réunion Teams](/microsoft-365/compliance/apply-retention-labels-automatically#microsoft-teams-meeting-recordings).

### <a name="microsoft-purview-data-loss-prevention-dlp-policies"></a>Conseils de stratégie de protection contre la perte de données (DLP) Microsoft Purview

Vous pouvez appliquer des stratégies DLP aux fichiers d’enregistrement de réunion également par la propriété ProgID. Dans la règle DLP pour les fichiers dans SharePoint et OneDrive, définissez les conditions suivantes :

- Propriété du document = *ProgID*
- Valeur = *Media.Meeting*

Pour en savoir plus sur la protection contre la perte de données, consultez l’article [En savoir plus sur la protection contre la perte de données](/microsoft-365/compliance/dlp-learn-about-dlp)

## <a name="meeting-recording-diagnostic-tools"></a>Outils de diagnostic d'enregistrement de réunion

### <a name="user-cannot-record-meetings"></a>L'utilisateur ne peut pas enregistrer les réunions

Si vous êtes administrateur, vous pouvez utiliser l'outil de diagnostic suivant pour valider que l'utilisateur est correctement configuré pour enregistrer une réunion dans Teams :

1. Sélectionnez **Exécuter les tests** ci-dessous, qui remplira le diagnostic dans le Centre d'Administration Microsoft 365.

   > [!div class="nextstepaction"]
   > [Exécuter des tests : enregistrement de réunion](https://aka.ms/MeetingRecordingDiag)

2. Dans le volet Exécuter le diagnostic, saisissez l'e-mail de l'utilisateur qui ne peut pas enregistrer de réunions dans le **champ Nom d'utilisateur ou E-mail**, puis sélectionnez **Exécuter les tests**.

3. Les tests renverront les meilleures étapes suivantes pour traiter les configurations de locataire ou de stratégie afin de valider que l'utilisateur est correctement configuré pour enregistrer une réunion dans Teams.
  
### <a name="meeting-record-is-missing"></a>L'enregistrement de la réunion est manquant

Si vous êtes un administrateur, vous pouvez utiliser l'outil de diagnostic suivant pour valider que l'enregistrement de la réunion s'est terminé avec succès et qu'il a été téléchargé sur Stream ou OneDrive, en fonction de l'ID de la réunion et de l'heure de début de l'enregistrement :

1. Sélectionnez **Exécuter les tests** ci-dessous, qui remplira le diagnostic dans le Centre d'Administration Microsoft 365.

   > [!div class="nextstepaction"]
   > [Exécuter des tests : enregistrement de réunion manquant](https://aka.ms/MissingRecordingDiag)

2. Dans le volet De diagnostic d’exécution, entrez l’URL de la réunion dans **l’URL de la réunion enregistrée** (généralement trouvée dans l’invitation à la réunion) ainsi que la date de la réunion dans le champ **Quand la réunion a-t-elle été enregistrée ?** puis sélectionnez **Exécuter les tests**.

3. Les tests valideront que l'enregistrement de la réunion s'est terminé avec succès et qu'il a été téléchargé sur Stream ou OneDrive.

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
