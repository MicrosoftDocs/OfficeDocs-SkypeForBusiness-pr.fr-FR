---
title: Enregistrement de réunion cloud Teams
author: tonysmit
ms.author: tonysmit
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
ms.openlocfilehash: 37d7c3999986373e7ad72176cfc0182f09144e3a
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2021
ms.locfileid: "61205414"
---
# <a name="teams-cloud-meeting-recording"></a>Enregistrement de réunion cloud Teams

Dans Microsoft Teams, les utilisateurs peuvent enregistrer leurs réunions et appels de groupe Teams pour capturer les activités audio, vidéo et de partage d’écran. Il existe également une option de transcription automatique des enregistrements qui permet aux utilisateurs de regarder les enregistrements des réunions avec des sous-titres et de rechercher des éléments de discussion importants dans la transcription. L’enregistrement se produit dans le cloud et est enregistré dans Microsoft OneDrive Entreprise et Microsoft SharePoint Online, afin que les utilisateurs puissent le partager en toute sécurité au sein de leur organisation.

Lorsqu’une réunion est enregistrée, elle est automatiquement :

- Chargé sur OneDrive Entreprise ou SharePoint Online
- Autorisations accordées aux personnes invitées à la réunion
- Lié dans la conversation pour la réunion
- Affiché sous l’onglet Enregistrements et transcriptions de la réunion dans le calendrier Teams
- Ajouté à différentes listes de fichiers dans Microsoft 365 : Partagé avec moi, office.com, Recommandé, Récent, etc.
- Indexé pour la recherche Microsoft 365

Connexe : [documentation de l’utilisateur final sur l’enregistrement de la réunion Teams](https://support.microsoft.com/en-us/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24)

>[!Note]
> Le passage de l’utilisation de Microsoft Stream (classique) à OneDrive Entreprise et SharePoint Online pour les enregistrements de réunions aura lieu automatiquement en août 2021. Pour plus d’informations, consultez [Utiliser OneDrive Entreprise et SharePoint Online ou Stream pour les enregistrements de réunion](tmr-meeting-recording-change.md).

> [!NOTE]
> Si vous souhaitez en savoir plus sur l’utilisation des rôles dans les réunions Teams et la méthode pour modifier les rôles des utilisateurs, consultez l’article [Rôles dans une réunion Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019). Pour les options d’enregistrement d’événements en direct, consultez l’article [Stratégies d’enregistrement des événements en direct dans Teams. ](teams-live-events/live-events-recording-policies.md).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Conditions préalables pour l’enregistrement de réunion cloud Teams

Pour que les réunions d’un utilisateur Teams soient enregistrées, OneDrive Entreprise et SharePoint Online doivent être activés pour le client. De plus, les conditions préalables suivantes sont requises pour l’organisateur de la réunion et la personne qui lance l’enregistrement :

- L’utilisateur dispose d’un espace de stockage suffisant dans OneDrive Entreprise pour enregistrer les enregistrements de réunions hors canal.

- Le canal Teams dispose d’un stockage suffisant dans SharePoint Online pour enregistrer les enregistrements des réunions de canal.

- L’utilisateur a `CsTeamsMeetingPolicy -AllowCloudRecording` défini le paramètre sur true pour enregistrer les réunions et les appels de groupe.

- L’utilisateur a `CsTeamsCallingPolicy -AllowCloudRecordingForCalls` défini le paramètre sur true pour enregistrer les appels 1:1.

- L’utilisateur ne doit pas être un utilisateur anonyme, invité ou fédéré de la réunion.

- Pour activer la transcription pour la réunion d’un utilisateur, la stratégie de réunion Teams à laquelle il est affecté doit avoir`-AllowTranscription` défini le paramètre sur true.

- Pour permettre l’enregistrement des enregistrements de réunion de canal afin que les membres du canal ne puissent pas modifier ou télécharger les enregistrements, le paramètre `CSTeamsMeetingPolicy -ChannelRecordingDownload` doit être défini sur Bloquer.

> [!IMPORTANT]
>
> Les utilisateurs n’ont pas besoin d’activer OneDrive Entreprise ou SharePoint Online si vous souhaitez que les utilisateurs puissent uniquement enregistrer et télécharger les enregistrements. Cela signifie que les enregistrements ne sont pas stockés dans OneDrive Entreprise ou SharePoint Online, mais qu’ils sont stockés dans un stockage Teams temporaire avec une limite de 21 jours avant leur suppression. Il ne s’agit pas d’un élément qu’un administrateur peut contrôler, gérer ou supprimer pour l’instant.
>
> Pour plus [d’informations sur le fonctionnement du stockage d’enregistrement de réunion temporaire](#temp-storage), voir ci-dessous.  

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurer l’enregistrement de réunions cloud Teams pour les utilisateurs de votre organisation

Cette section explique comment configurer et planifier l’enregistrement des réunions Teams via [stratégies de réunion Teams](policy-assignment-overview.md).

### <a name="turn-on-or-turn-off-cloud-recording"></a>Activer ou désactiver l’enregistrement dans le cloud

Vous pouvez utiliser le Centre d’administration Microsoft Teams ou PowerShell pour définir une stratégie de réunion Teams afin de contrôler si les réunions des utilisateurs peuvent être enregistrées.

Dans le Centre d’administration Microsoft Teams, activer ou désactiver le paramètre d’enregistrement **sur le nuage** dans la stratégie de réunion. Si vous souhaitez en savoir plus, consultez l’article [Paramètres de stratégie de réunion pour l’audio et la vidéo](meetings-policies-recording-and-transcription.md#allow-cloud-recording).

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

- **Autoriser** (par défaut) : enregistre les enregistrements de réunion de canal dans un dossier « Recordings » dans le canal. Les autorisations sur les fichiers d’enregistrement sont basées sur les autorisations Channel SharePoint Online. Il s’agit du même fichier que n’importe quel autre fichier chargé pour le canal.

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

Ce paramètre détermine si les fonctionnalités de légende et de transcription sont disponibles lors de la lecture des enregistrements de réunion. Si vous désactivez cette option, les options **Recherche** et **CC** ne sont pas disponibles pendant la lecture d’un enregistrement de réunion. La personne qui a démarré l’enregistrement a besoin de ce paramètre activé de sorte que l’enregistrement inclut également la transcription.

> [!NOTE]
> Cette transcription pour les réunions enregistrées n'est actuellement prise en charge que pour l'anglais (États-Unis), l'anglais (Canada), l'anglais (Inde), l'anglais (Royaume-Uni), l'anglais (Australie), l'anglais (Nouvelle-Zélande), l'allemand (Allemagne), le portugais (Brésil), néerlandais (Pays-Bas), néerlandais (Belgique), français (France), espagnol (Espagne), japonais (Japon), français (Canada), chinois (cantonais, traditionnel), chinois (mandarin, simplifié), hindi (Inde) , italien (Italie), coréen (Corée), espagnol (Mexique), suédois (Suède), polonais (Pologne), arabe (Émirats arabes unis), arabe (Arabie saoudite), danois (Danemark), finnois (Finlande), norvégien (Norvège) et russe (Russie). Ils sont stockés avec les enregistrements de réunion dans OneDrive Entreprise et le stockage cloud SharePoint Online.

Vous pouvez utiliser le Centre d’administration Microsoft Teams ou PowerShell pour définir une stratégie de réunion Teams afin de contrôler si l’initiateur d’enregistrement peut transcrire le choix de transcrire l’enregistrement de la réunion.

Dans le Centre d’administration Microsoft Teams, activez ou désactivez le paramètre **Autoriser la transcription** dans la stratégie de réunion. Si vous souhaitez en savoir plus, consultez l’article [Paramètres de stratégie de réunion pour l’audio et la vidéo](meetings-policies-recording-and-transcription.md#allow-transcription).

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

</br>
</br>

|Scénario|Étapes |
|---|---|
|Je souhaite que tous les utilisateurs de ma société soient en mesure de transcrire lors du lancement de l’enregistrement d’une réunion. |<ol><li>Confirmer que la stratégie globale CsTeamsMeetingPolicy a AllowTranscription = True. <li>Tous les utilisateurs ont la stratégie globale CsTeamsMeetingPolicy OU l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = True. </ol>|
|Je souhaite que la plupart de mes utilisateurs puissent transcrire les enregistrements de réunion, mais désactiver de manière sélective des utilisateurs spécifiques qui ne sont pas autorisés à transcrire. |<ol><li>Confirmer que la stratégie globale CsTeamsMeetingPolicy a AllowTranscription = True. <li>La plupart des utilisateurs ont la stratégie globale CsTeamsMeetingPolicy OU l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = True. <li>Tous les autres utilisateurs ont reçu l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = False. </ol>|
|Je souhaite que la transcription de l’enregistrement soit 100 % désactivée. |<ol><li>Confirmer que la stratégie globale CsTeamsMeetingPolicy a AllowTranscription = False. <li>Tous les utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy OU l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = False. </ol>|
|Je souhaite que la transcription soit désactivée pour la majorité des utilisateurs, mais activer de manière sélective des utilisateurs spécifiques qui sont autorisés à transcrire. |<ol><li>Vérifiez que la stratégie globale CsTeamsMeetingPolicy a AllowCloudRecording = False. <li>La majorité des utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy OU l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = False. <li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowCloudRecording = True. </ol>|

### <a name="terms-of-use-acceptance"></a>Acceptation des Conditions d’utilisation
Si votre organisation dispose d’une stratégie d’enregistrement des réunions que vous souhaitez que vos utilisateurs acceptent avant d’enregistrer une réunion, utiliser la fonctionnalité [Conditions d’utilisation Azure Active Directory](/azure/active-directory/conditional-access/terms-of-use). Cette fonctionnalité permet à vos utilisateurs d’accepter les conditions de la stratégie utilisateur de votre organisation avant d’accéder à Microsoft Teams. Cette fonctionnalité ne s’applique pas spécifiquement au clic sur le bouton Enregistrer. Elle est associée à l’utilisation de Teams ou d’autres applications Microsoft 365 en général. Notre suggestion est d’ajouter votre information d’enregistrement de la réunion aux conditions d'utilisation générales pour l’utilisateur de Teams ou de Microsoft 365. 

## <a name="permissions-and-storage"></a>Autorisations et stockage

Les enregistrements de réunion sont stockés dans OneDrive Entreprise et le stockage cloud SharePoint Online. L’emplacement et les autorisations dépendent du type de réunion et du rôle de l’utilisateur dans la réunion. Les autorisations par défaut appliquées à l’enregistrement sont répertoriées ci-dessous. Les utilisateurs qui disposent de droits d’édition complets sur le fichier d’enregistrement vidéo peuvent modifier les autorisations et les partager ultérieurement avec d’autres personnes si nécessaire.

### <a name="non-channel-meetings"></a>Réunions hors canal

- L’enregistrement est stocké dans un dossier nommé **Recordings** dans le OneDrive Entreprise de l’utilisateur qui a cliqué sur l’enregistrement. 

  Exemple : <i>Enregistrements OneDrive Entreprise</i>/**Recordings**

- Les personnes invitées à la réunion, à l’exception des utilisateurs externes, bénéficient automatiquement de l’autorisation d’accès au fichier d’enregistrement avec accès en affichage sans possibilité de téléchargement.

- Le propriétaire de la réunion et la personne qui a cliqué sur l’enregistrement bénéficieront d’un accès de modification complet avec la possibilité de modifier les autorisations et de partager avec d’autres personnes.

### <a name="channel-meetings"></a>Réunions de canal

Si `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` est défini sur Autoriser (valeur par défaut) :

- L’enregistrement est stocké dans la bibliothèque de documentation du site Teams dans un dossier nommé **Recordings**.

  Exemple : <i> nom Teams – Nom du canal</i>/**Documents**/**Recordings**

- Le membre qui a cliqué sur l’enregistrement dispose des droits de modification pour l’enregistrement.

- Les autorisations de tous les autres membres sont basées sur les autorisations Channel SharePoint Online.

Si `Set-CsTeamsMeetingPolicy -ChannelRecordingDownload` est défini sur Bloquer :

- L’enregistrement est stocké dans la bibliothèque de documentation du site Teams dans un dossier nommé **Recordings/View only**. 

  Exemple : <i>nom Teams – Nom du canal</i>/**Documents/Recordings/View only**

- Les propriétaires de canaux disposeront de droits complets de modification et de téléchargement sur les enregistrements de ce dossier.

- Les membres du canal disposeront d’un accès en lecture seule sans possibilité de téléchargement.

Pour plus d’informations sur des types de réunions spécifiques, consultez le tableau suivant :

| Type de réunion  | Qui a cliqué sur Enregistrement ?| Où arrive l’enregistrement ? | Qui a accès ? En lecture et en écriture, lecture seule ou partage  |
|-------------|-----------------------|------------------------|------------------------|
|Appel individuel avec des parties internes             |Appelant                 |Compte OneDrive Entreprise de l’appelant                        |L’appelant est propriétaire et dispose de tous les droits. <br /><br />L’appelé (si dans le même client) dispose d’un accès en lecture seule. Aucun accès de partage. <br /><br /> Le destinataire de l’appel (s’il est dans un client différent) ne dispose d’aucun accès. L’appelant doit partager le document avec le destinataire de l’appel.|
|Appel individuel avec des parties internes             |Destinataire de l’appel                 |Compte OneDrive Entreprise du destinataire de l’appel                        |Le destinataire de l’appel est propriétaire et dispose de tous les droits. <br /><br />Appelant (si dans le même client) dispose d’un accès en lecture seule. Aucun accès de partage. <br /><br />L’appelant (s’il est dans un client différent) ne dispose d’aucun accès. Le destinataire de l’appel doit partager le document avec l’appelant.|
|Appel individuel avec des parties externes             |Appelant                 |Compte OneDrive Entreprise de l’appelant                        |L’appelant est propriétaire et dispose de tous les droits.<br /> <br />Le destinataire de l’appel ne dispose d’aucun accès. L’appelant doit partager le document avec le destinataire de l’appel.|
|Appel individuel avec des parties externes             |Destinataire de l’appel                 |Compte OneDrive Entreprise du destinataire de l’appel                        |Le destinataire de l’appel est propriétaire et dispose de tous les droits.<br /><br />L’appelant ne dispose d’aucun accès. Le destinataire de l’appel doit partager le document avec l’appelant.|
|Appel de groupe                                 |Tout membre de l’appel |Membre ayant cliqué sur le compte OneDrive Entreprise de l’enregistrement  |Le membre qui a cliqué sur Enregistrement dispose de tous les droits. <br /><br /> Les autres membres du même client disposent de droits en lecture. <br /><br /> Les autres membres du groupe de différent clients n’y ont aucun droit.|
|Réunion ad hoc/planifiée                    |Organisateur              |Compte OneDrive Entreprise de l’organisateur                     |L’organisateur dispose de droits complets sur l’enregistrement. <br /><br /> Tous les autres membres de la réunion disposent d’un accès en lecture sans possibilité de téléchargement.|
|Réunion ad hoc/planifiée                    |Autre membre de la réunion   |Membre de réunion qui a cliqué sur Enregistrer                                  |Le membre qui a cliqué sur Enregistrement dispose de tous les droits d’accès à l’enregistrement. <br /><br />L’organisateur dispose de droits de modification et de partage.<br /><br /> Tous les autres membres de la réunion disposent d’un accès en lecture sans possibilité de téléchargement.|
|Réunion ad hoc/planifiée avec des utilisateurs externes|Organisateur              |Compte OneDrive Entreprise de l’organisateur                     |L’organisateur dispose de droits complets sur l’enregistrement.<br /> <br /> Tous les autres membres de la réunion du même client que l’organisateur disposent d’un accès en lecture sans possibilité de téléchargement. <br /><br /> Tous les autres membres externes n’ont pas d’accès, et l’organisateur doit le partager avec eux.|
|Réunion ad hoc/planifiée avec des utilisateurs externes|Autre membre de la réunion   |Membre qui a cliqué sur Enregistrement                                  |Le membre qui a cliqué sur Enregistrement dispose de tous les droits d’accès à l’enregistrement. L’organisateur dispose de droits de modification et de partage. <br /><br /> Tous les autres membres de la réunion du même client que l’organisateur disposent d’un accès en lecture sans possibilité de téléchargement. <br /><br />Tous les autres membres externes n’ont pas d’accès, et l’organisateur doit le partager avec eux.|
|Réunion de canal                            |Membre du canal         |Emplacement SharePoint de Teams pour ce canal                   |Si Set-CsTeamsMeetingPolicy -ChannelRecordingDownload est défini sur Autoriser (par défaut), le membre qui a cliqué sur Enregistrement dispose des droits de modification pour l’enregistrement. Les autorisations de tous les autres membres sont basées sur les autorisations Channel SharePoint Online.<Br><Br>Si Set-CsTeamsMeetingPolicy -ChannelRecordingDownload est défini sur Bloquer, les propriétaires de canaux disposeront des droits complets sur l’enregistrement, mais les membres du canal disposeront d’un accès en lecture sans possibilité de téléchargement.|

<a name="temp-storage"></a>
### <a name="temporary-storage-when-unable-to-upload-to-onedrive-for-business-and-sharepoint-online"></a>Stockage temporaire en cas d’impossibilité de chargement vers OneDrive Entreprise et SharePoint Online

Si un enregistrement de réunion ne peut pas être chargé sur OneDrive Entreprise et SharePoint Online, il sera temporairement disponible en téléchargement à partir de Teams pendant 21 jours avant sa suppression. À ce stade, ce n’est pas quelque chose qu’un administrateur peut contrôler ou gérer pour inclure la possibilité de le supprimer.

Les enregistrements de réunion peuvent se retrouver dans ce stockage temporaire pour les raisons suivantes :

- Pour les réunions hors canal si l’enregistrement de l’utilisateur n’a pas de configuration OneDrive Entreprise ou si OneDrive Entreprise a atteint son quota de stockage
- Pour une réunion de canal si le site SharePoint Online a atteint son quota de stockage ou si le site n’a pas encore été approvisionné
- Si des stratégies OneDrive Entreprise et SharePoint Online spécifiques sont activées, cela empêche les utilisateurs de charger des fichiers lorsqu’ils ne se trouvent pas sur des plages d’adresses IP spécifiques, etc.

La rétention d’enregistrement pour ce stockage temporaire est affectée par le message de conversation lui-même. Par conséquent, toute suppression du message de conversation d’origine pour l’enregistrement empêchera les utilisateurs d’accéder à l’enregistrement. Il existe deux scénarios qui peuvent affecter ceci :

- **L’utilisateur supprime manuellement le message de conversation**: dans ce scénario, à mesure que le message d’origine a disparu, les utilisateurs ne pourront plus accéder à l’enregistrement et aucun téléchargement supplémentaire ne sera possible. Toutefois, l’enregistrement lui-même peut toujours être conservé dans les systèmes internes de Microsoft pendant un certain temps (sans dépasser la période d’origine de 21 jours).

- **L’enregistrement du message de conversation est supprimé par la stratégie de rétention de conversation**: les enregistrements de stockage temporaires sont directement liés à la stratégie de rétention des conversations. Par conséquent, bien que les enregistrements sur le stockage temporaire Teams soient conservés par défaut pendant 21 jours avant d’être supprimés, si le message de conversation est supprimé avant la période de 21 jours, en raison des stratégies de rétention des messages de conversation, l’enregistrement est également supprimé. Il n’existe aucun moyen de récupérer l’enregistrement après cela.

### <a name="planning-for-storage"></a>Planification pour stockage

La taille d’un enregistrement de 1 heure est de 400 Mo. Veillez à bien comprendre la capacité requise pour les fichiers enregistrés et à disposer d’un espace de stockage suffisant dans OneDrive Entreprise et SharePoint Online.  Lisez [Définissez l’espace de stockage par défaut pour OneDrive Entreprise](/onedrive/set-default-storage-space) et [Gérer les limites de stockage de site SharePoint Online](/sharepoint/manage-site-collection-storage-limits) pour comprendre le stockage de base inclus dans l’abonnement et comment acheter du stockage supplémentaire.

 <a name="auto-expiration"></a>
### <a name="auto-expiration-of-teams-meeting-recordings"></a>Expiration automatique des enregistrements de réunion Teams : 

> [!IMPORTANT]
>
> La fonctionnalité d’expiration automatique décrite dans cet article n’est pas encore lancée. Veuillez-vous référer à [la feuille de route (ID de fonctionnalité : 84580)](https://www.microsoft.com/microsoft-365/roadmap?searchterms=82057&filters=&searchterms=84580) pour plus d’informations sur sa date de livraison.
> 
> Nous fournissons des informations sur le futur fonctionnement de cette fonctionnalité dans l’avenir, afin que vous puissiez planifier cette modification et modifier les paramètres de stratégie Teams à l’avance.
>
> La commande qui modifie de façon préventive le paramètre d’expiration par défaut dans Teams est en cours de déploiement, mais vous pouvez peut-être voir l’attribut dans PowerShell. Le paramètre n’est actuellement pas disponible dans les Centres d’administration Teams. Ces paramètres seront disponibles et communiqués dans un billet du centre de messages au moins 30 jours avant le lancement de la fonctionnalité.
>
>

Consultez les questions fréquemment posées aux administrateurs et aux utilisateurs finaux pour recueillir des informations sur le fonctionnement de l’expiration automatique des enregistrements de réunion Teams, les actions que vous pouvez effectuer maintenant et les actions que vous pouvez effectuer après le lancement de la fonctionnalité.
  
## <a name="frequently-asked-questions"></a>Questions fréquentes (FAQ)

**Quelle est la modification ?**
  
Nous ’ introduisons un paramètre d’expiration par défaut de 60 jours pour tous les enregistrements de réunion Teams nouvellement créés. Cela signifie que, par défaut, tous les TMR créés après l’activation de cette fonctionnalité seront supprimés 60 jours après leur date de création. Si les administrateurs souhaitent que les enregistrements de réunion expirent plus tôt ou plus tard que la valeur par défaut, ils peuvent modifier le paramètre d’expiration. Les systèmes OneDrive et SharePoint surveillent la date d’expiration définie sur tous les enregistrements de réunion et les déplacent automatiquement vers la Corbeille à leur date d’expiration.

**Qui est concerné ?**
  
Toute personne stockant un enregistrement de réunion Teams (sans canal, canal ou réunion ad hoc) dans OneDrive ou SharePoint.

**Pourquoi dois-je utiliser cette fonctionnalité ?**
  
Vous devez utiliser cette fonctionnalité pour limiter le stockage OneDrive ou SharePoint consommé par les enregistrements de réunion Teams (remarque : ils utilisent généralement environ 400 Mo par heure d’enregistrement).
  
**Pourquoi introduisons-nous ce changement ?**
  
Les clients ont envoyé des commentaires excessifs indiquant qu’ils souhaitent davantage de contrôles pour réduire l’encombrement du stockage créé à partir des enregistrements de réunion Teams, dont 99 % en moyenne ne sont jamais revus après 60 jours.
  
**Pourquoi cette option est-elle activée par défaut ?**
  
Nous pensons que presque tous les clients tireront parti de la charge de stockage réduite sur leur locataire en supprimant les enregistrements qui ne seront probablement jamais revus après 60 jours. Notre objectif est de fournir une expérience aussi propre que possible à tous les clients par défaut.
  
**Sera-t-il automatiquement supprimé même si les données sont accessibles ou téléchargées ?**
  
L’accès au fichier ne modifie pas la date d’expiration.
  
**La date d’expiration est-elle visible sous forme de colonne dans la liste ?**

Les utilisateurs ayant un accès visuel à l'enregistrement verront une icône rouge en regard du fichier dans le dossier OneDrive ou SharePoint 14 jours avant l'expiration du fichier. Il n’existe actuellement aucun moyen d’ajouter une colonne à une liste avec une date d’expiration.
  
**Comment la date d’expiration est-elle calculée ?**
  
La date d’expiration est calculée en tant que jour de création de l’enregistrement de réunion, plus le nombre de jours par défaut défini dans le paramètre Teams par l’administrateur.
  
**La date d'expiration peut-elle être modifiée pour chaque TMR, par exemple la date d'expiration des données A est de 30 jours et celle des données B de 60 jours ?**

Oui, la date d’expiration est définie par fichier. Les utilisateurs peuvent modifier la date d’expiration dans le volet d’informations des détails d’un fichier sélectionné dans OneDrive ou SharePoint.

**Comment un administrateur peut-il modifier la date d’expiration ?**
  
Les administrateurs peuvent modifier le paramètre d’expiration par défaut dans PowerShell ou le Centre d’administration Teams des utilisateurs avant la publication de la fonctionnalité. La modification des paramètres d’expiration aura uniquement un impact sur les TMRs nouvellement créés à partir de ce point. Cela n’aura aucun impact sur les enregistrements effectués avant cette date. Les nouveaux enregistrements n’expireront pas automatiquement jusqu’à la publication de la fonctionnalité, même si vous pouvez définir l’attribut de stratégie avant sa publication.

La valeur de jours d’expiration peut être définie comme suit :
  
- La valeur peut être de 1 à 9 999.
- La valeur peut également être -1 pour que le TMR n’expire jamais. 
 
Les administrateurs ne peuvent pas modifier la date d’expiration des TMRs existants déjà chargés sur OneDrive ou SharePoint avant la publication de cette fonctionnalité. Cela protège l’intention de l’utilisateur propriétaire du TMR.
  
Pour modifier le comportement d’expiration automatique par défaut de votre client, modifiez l’attribut suivant dans PowerShell. Dans cet exemple, la valeur par défaut est remplacée par 50 jours.
 
Set-CsTeamsMeetingPolicy -Identity Global -**New** MeetingRecordingExpirationDays 50

La possibilité de modifier le paramètre par défaut dans le Centre d’administration Teams sera déployée ultérieurement, au moins 30 jours avant notre activation de la fonctionnalité d’expiration automatique par défaut.
  
**Un administrateur peut-il définir les TMR pour qu’ils n’expirent jamais ?**
  
 Oui, les administrateurs peuvent configurer les TMR pour qu’ils n’expirent jamais.
  
**La lecture de l’enregistrement modifie-t-elle la date d’expiration ?**

Non, la lecture n’a pas d’impact sur la date d’expiration.
  
**Que se passe-t-il à la date d’expiration si le TMR est téléchargé et chargé à nouveau ?**

La date d'expiration sera effacée lors du nouveau chargement, indépendamment de la référence (SKU) de l'utilisateur.
  
**Que se passe-t-il si je copie ou déplace le TMR vers un autre emplacement ou site ?**

La date est conservée uniquement pour un fichier TMR déplacé. Un fichier copié n'aura pas de date d'expiration, tout comme un TMR rechargé.
  

**Quelle est l’étendue du contrôle de la stratégie d’administration ?**
  
Les réunions et les appels sont contrôlés par le même `CsTeamsMeetingPolicy`paramètre,`MeetingRecordingExpirationDays`. 
  
**Comment les utilisateurs finaux peuvent-ils modifier la date d’expiration sur un fichier TMR spécifique ?**
  
Toute personne disposant d’autorisations de modification et de suppression sur un TMR peut modifier la date d’expiration dans le ’ volet d’informations du fichier dans OneDrive ou SharePoint.

L’utilisateur peut différer l’expiration 14, 30 ou 60 jours, ou choisir une date spécifique à l’avenir, ou il peut sélectionner que le fichier n’a jamais expiré.
  
**Les administrateurs doivent-ils s’appuyer sur cette fonctionnalité pour un respect strict de la sécurité et de la conformité ?**
  
Non, les administrateurs ne doivent pas s’appuyer sur cette fonctionnalité pour bénéficier d’une protection légale, car les utilisateurs finaux peuvent modifier la date d’expiration de tous les enregistrements qu’ils contrôlent.
  
**Cette fonctionnalité appliquera-t-elle la rétention des fichiers ?**
  
Non, les fichiers ne seront pas conservés en raison de cette fonctionnalité ou de ses paramètres. Si un utilisateur disposant d’autorisations de suppression tente de supprimer un TMR dont le paramètre d’expiration est défini, l’action de suppression de cet utilisateur ’ est exécutée.

**Une stratégie de rétention et/ou de suppression que j’ai définie dans le centre de sécurité et conformité (S+C) remplacera-t-elle le paramètre d’expiration TMR ?**
  
Oui, toutes les stratégies que vous avez définies dans le centre S+C sont prioritaires. Par exemple :
  
- Si vous avez une stratégie qui indique que tous les fichiers d’un site doivent être conservés pendant 100 jours et que le paramètre d’expiration d’un TMR est de 30 jours, le fichier d’enregistrement est conservé pendant les 100 jours complets.  
- Si vous avez une stratégie de suppression qui indique que tous les tmrs seront supprimés après 5 jours et que vous avez un paramètre d’expiration sur un fichier d’enregistrement de 30 jours, ce fichier sera supprimé au bout de cinq jours.

**Que se passe-t-il lorsqu’un TMR « expire » ?**
  
À la date d’expiration, le TMR est déplacé dans la Corbeille OneDrive ou SharePoint et le champ date d’expiration est effacé. Cette action du système est exactement la même que si un utilisateur a supprimé le fichier. Le cycle de vie de la corbeille suit ensuite le chemin d’accès normal. Si l’utilisateur récupère le TMR à partir de la Corbeille, le TMR ne sera plus supprimé par cette fonctionnalité depuis que la date d’expiration a été effacée, sauf si l’utilisateur final définit une nouvelle date d’expiration sur le fichier.
  
**Comment être averti de l’expiration d’un fichier ?**
  
Toutes les personnes disposant d’un accès à l’affichage verront une notification concernant la date d’expiration dans l’applet de commande d’enregistrement dans la fenêtre de conversation Teams.
  
Toutes les personnes ayant accès à l’affichage verront une icône rouge en regard du fichier dans votre dossier OneDrive ou SharePoint 14 jours avant l’expiration du fichier.
  
Le propriétaire du fichier reçoit une notification par e-mail lorsque le TMR expire et est dirigé vers la Corbeille pour récupérer le TMR s’il le souhaite.
  
**Quelles sont les références SKU requises pour cette fonctionnalité ?**
  
Toutes les références SKU auront cette fonctionnalité par défaut. Les utilisateurs A1 ont par défaut une période d’expiration de 30 jours.
  
**L’expiration du fichier est-elle un événement audité et puis-je le voir dans mes journaux d’audit ?**
  
Oui, les expirations de fichiers s’affichent en tant qu’événements de suppression du système dans le journal d’audit.
  
**Que se passe-t-il si je souhaite que l’administrateur ait un contrôle total sur le cycle de vie des tmrs et ne ’ souhaite pas donner aux utilisateurs finaux la possibilité de remplacer la date d’expiration ?**
  
Nous vous recommandons d’utiliser les stratégies de rétention et/ou de suppression S+C disponibles dans le cadre de la référence SKU de conformité E5. Cette offre vise à résoudre des problèmes juridiques d’administration complexes basés sur des stratégies et des contrats SLA.

Cette fonctionnalité est uniquement conçue comme un mécanisme léger de nettoyage pour réduire l’encombrement du stockage créé à partir de TMR froids.
  
**Quand le fichier sera-t-il supprimé ?**
  
Le fichier sera supprimé dans les 5 jours suivant la date d’expiration, bien qu’il ne s’agit pas d’une garantie stricte.
  
**L’expiration automatique sera-t-elle également appliquée aux futures tmrs migrées à partir de Classic Stream après la publication de cette fonctionnalité ?**
  
Non, les tmrs migrés ne sont pas fournis avec un délai d’expiration défini sur eux. Au lieu de cela, nous encourageons les administrateurs à migrer uniquement les TMR qu’ils souhaitent conserver. Vous trouverez plus de détails dans la documentation de migration.
  
## <a name="manage-meeting-recordings"></a>Gérer les enregistrements de réunion

Les enregistrements de réunion sont stockés sous forme de fichiers vidéo dans OneDrive Entreprise et SharePoint Online, et suivent les options de gestion et de gouvernance disponibles sur ces plateformes. Pour plus d’informations, consultez [vue d’ensemble de la gouvernance SharePoint Online](/sharepoint/governance-overview), [OneDrive Entreprise guide pour les entreprises](/onedrive/plan-onedrive-enterprise)ou [OneDrive Entreprise guide pour les petites entreprises](/onedrive/one-drive-quickstart-small-business) .

Pour les réunions hors canal, les enregistrements sont stockés dans le OneDrive Entreprise de l’enregistreur, ce qui permet de gérer la propriété et la rétention après le départ d’un employé suivront la [OneDrive Entreprise normale et le processus SharePoint Online](/onedrive/retention-and-deletion#the-onedrive-deletion-process).

## <a name="closed-captions-for-recordings"></a>Sous-titres pour les enregistrements

Les sous-titres des enregistrements de réunion Teams ne seront disponibles pendant la lecture que si la transcription de l’utilisateur était activée au moment de l’enregistrement. Les administrateurs doivent [activer l’enregistrement de la transcription via la stratégie](#turn-on-or-turn-off-recording-transcription) pour s’assurer que leurs utilisateurs ont la possibilité d’enregistrer des réunions avec la transcription.

Les légendes permettent de créer du contenu inclusif pour les visiteurs de tous niveaux. En tant que propriétaire, vous pouvez masquer les sous-titres de l’enregistrement de la réunion, bien que la transcription de la réunion soit toujours disponible sur Teams, sauf si vous l’avez supprimé de cet emplacement.

Les sous-titres pour le fichier vidéo de l’enregistrement sont aujourd’hui liés à la transcription de la réunion Teams. Ce lien restera pendant la durée de vie du fichier dans la plupart des cas, mais il peut être corrompu si le fichier vidéo est copié dans le même OneDrive Entreprise ou le même site SharePoint Online, ce qui empêcherait aux sous-titres d’être copiés sur le fichier vidéo.

Les modifications futures apportées au lien entre la transcription dans Teams et l’enregistrement seront précisées ici et dans les notifications du centre de messages. Si nous apportons des modifications à l’avenir, nous nous assurerons que les fichiers d’enregistrement datant de moins de 60 jours affichent la transcription de la réunion sous forme de sous-titre.

> [!NOTE]
> La transcription de réunion n’est pas encore disponible dans le Cloud de la communauté du secteur public.

## <a name="ediscovery-and-compliance-for-meeting-recordings"></a>eDiscovery et conformité pour les enregistrements de réunion

### <a name="ediscovery"></a>eDiscovery

Les enregistrements de réunion sont stockés dans OneDrive Entreprise et SharePoint Online, qui appartiennent à Microsoft 365 et sont conformes à la norme de niveau D d’Office 365. Pour prendre en charge les demandes e-Discovery pour les administrateurs de conformité qui sont intéressés par les enregistrements de réunions ou d’appels, le message d’enregistrement terminé est disponible dans la fonctionnalité de recherche de contenu de conformité pour Microsoft Teams. Les administrateurs de conformité peuvent rechercher le mot clé « enregistrement » dans la ligne d’objet de l’élément dans le cadre de la recherche de contenu de conformité et découvrir les enregistrements de réunions et d’appels au sein de l’organisation.

En outre, le fichier vidéo d’enregistrement de réunion est disponible via des recherches eDiscovery pour les fichiers sur SharePoint Online et OneDrive Entreprise.

Pour en savoir plus sur eDiscovery, consultez l’article [solutions eDiscovery pour Microsoft 365](/microsoft-365/compliance/ediscovery)

### <a name="retention-policies"></a>Stratégies de rétention

Vous pouvez appliquer des étiquettes de rétention automatiques pour cibler uniquement les fichiers vidéo d’enregistrement de réunion Teams via la propriété ProgID. Pour plus d’informations, consultez [Comment appliquer automatiquement une étiquette de rétention pour les enregistrements de réunion Teams](/microsoft-365/compliance/apply-retention-labels-automatically#microsoft-teams-meeting-recordings).

### <a name="data-loss-prevention-dlp-policies"></a>Stratégie de prévention des pertes de données (DLP)

Vous pouvez appliquer des stratégies DLP aux fichiers d’enregistrement de réunion également par la propriété ProgID. Dans la règle DLP pour les fichiers dans SharePoint Online et OneDrive Entreprise définissez les conditions comme suivantes :

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

2. Dans le volet Exécuter le diagnostic, saisissez l'URL de la réunion dans le champ **URL de la réunion qui a été enregistrée** (généralement trouvée dans l'invitation à la réunion), ainsi que la date de la réunion dans le champ **Quand la réunion a-t-elle été enregistrée ?**, puis sélectionnez **Exécuter les tests**.

3. Les tests valideront que l'enregistrement de la réunion s'est terminé avec succès et qu'il a été téléchargé sur Stream ou OneDrive.

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
