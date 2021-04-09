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
localization_priority: Priority
f1.keywords:
- NOCSH
description: Conseil pratique pour le déploiement de fonctionnalités vocales cloud dans Teams pour enregistrer des réunions et des appels de groupe Teams pour capturer l’activité audio, vidéo, et le partage d'écran.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e5c23c362d9d425c163a46dde93c6daa3c593a92
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617776"
---
# <a name="teams-cloud-meeting-recording"></a>Enregistrement de réunion cloud Teams

Dans Microsoft Teams, les utilisateurs peuvent enregistrer leurs réunions et appels de groupe Teams pour capturer les activités audio, vidéo et de partage d’écran. Il existe également une option pour les enregistrements qui permet une transcription automatique, afin que les utilisateurs puissent regarder les enregistrements de réunion avec des sous-titres et rechercher des éléments de discussion importants dans la transcription. L’enregistrement se fait dans le cloud et est sauvegardé dans [Microsoft Stream](/stream/) pour permettre aux utilisateurs de le partager en toute sécurité au sein de leur organisation.

En relation avec la [Réunion Teams de qui enregistre la documentation de l’utilisateur final](https://aka.ms/recordmeeting)

>[!Note]
> Le passage de l’utilisation de Microsoft Stream à OneDrive Entreprise et SharePoint pour les enregistrements de réunion se fera progressivement. Si vous souhaitez en savoir plus sur chaque phase, consultez l’article [Utiliser OneDrive Entreprise et SharePoint ou Stream pour les enregistrements de réunion](tmr-meeting-recording-change.md).

> [!NOTE]
> Si vous souhaitez en savoir plus sur l’utilisation des rôles dans les réunions Teams et la méthode pour modifier les rôles des utilisateurs, consultez l’article [Rôles dans une réunion Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us). Pour les options d’enregistrement d’événements en direct, consultez l’article [Stratégies d’enregistrement des événements en direct dans Teams. ](teams-live-events/live-events-recording-policies.md).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Conditions préalables pour l’enregistrement de réunion cloud Teams

Microsoft Stream doit être activé pour que les réunions d’un utilisateur Teams soient enregistrées pour le locataire. De plus, les conditions préalables suivantes sont requises pour l’organisateur de la réunion et la personne qui lance l’enregistrement :

- L’utilisateur possède Office 365 E1, E3, E5, A1, A3, A5, Microsoft 365 Business Premium, Business Standard ou Business Basic<sup>1</sup>
- L’utilisateur doit avoir accepté les directives de l’entreprise configurées par l’administrateur, le cas échéant.
- L’utilisateur doit disposer de l’espace de stockage suffisant dans Microsoft Stream pour sauvegarder les enregistrements
- L’utilisateur a défini le paramètre CsTeamsMeetingPolicy -AllowCloudRecording sur true afin d’enregistrer les réunions et les appels de groupe
- L’utilisateur a défini le paramètre CsTeamsCallingPolicy -AllowCloudRecordingForCalls sur true afin d’enregistrer les réunions et les appels individuels
- L’utilisateur ne doit pas être un utilisateur anonyme, invité ou fédéré de la réunion
- Pour activer la transcription pour la réunion d’un utilisateur, la stratégie de réunion Teams à laquelle il est affecté doit disposer du paramètre Autoriser la transcription définie sur True.

<sup>1</sup> À compter du 20 aout 2020, l’accès au fichier d’enregistrement d’une réunion arrive à expiration après 21 jours pour les utilisateurs disposant de A1. Pour plus d'informations, voir [Télécharger l'enregistrement d'une réunion de Microsoft Teams vers Stream](/stream/portal-upload-teams-meeting-recording).

> [!IMPORTANT] 
>
> Les utilisateurs n’ont pas besoin d’une attribution de licence Microsoft Stream si vous souhaitez qu’ils puissent uniquement enregistrer et télécharger les enregistrements. Cela signifie que les enregistrements ne sont pas stockés dans Microsoft Stream, mais dans Teams Async Media Services (AMS) avec une limite de 21 jours avant leur suppression. À ce stade, un administrateur n’est pas habilité à contrôler, gérer, et même supprimer un enregistrement.
>
> Pour les enregistrements sur AMS, la rétention des enregistrements est affectée par le message de conversation lui-même. De ce fait, la suppression de l’enregistrement du message de conversation AMS d’origine empêchera les utilisateurs d’accéder à l’enregistrement. Il existe deux scénarios qui peuvent affecter cela :
> 
> - L’utilisateur supprime manuellement le message de conversation
> 
>   Dans ce scénario, le message d’origine ayant disparu, les utilisateurs ne pourront plus accéder à l’enregistrement et aucun autre téléchargement ne sera possible. Cependant, l’enregistrement lui-même peut toujours être conservé dans les systèmes internes de Microsoft pendant un certain temps (ne dépassant pas la période initiale de 21 jours).
> 
> - L’enregistrement du message de conversation est supprimé par la stratégie de rétention de conversation 
> 
>   Les enregistrements AMS sont directement liés à la stratégie de rétention de conversation. De ce fait, bien que les enregistrements sur AMS soient par défaut conservés pendant 21 jours avant d’être supprimés, si le message de conversation est supprimé avant la fin de la période de 21 jours, l’enregistrement sera également supprimé en raison des stratégies de rétention des messages de conversation. Une fois l’enregistrement supprimé, il est impossible de le récupérer.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurer l’Enregistrement de réunion cloud Teams pour les utilisateurs de votre organisation

Cette section vous explique comment configurer et planifier l'enregistrement des réunions Teams.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>Activer Microsoft Stream pour les utilisateurs de l’organisation

Microsoft Stream est disponible dans le cadre d’abonnements Microsoft 365 et Office 365 éligibles ou en tant que service autonome.  Pour plus d’informations, consultez la [Vue d’ensemble des licences Stream](/stream/license-overview).  Microsoft Stream est désormais inclus dans Microsoft 365 Business, Office 365 Business Premium et Microsoft 365 Business Essentials.

En savoir plus sur la façon dont vous pouvez [affecter des licences aux utilisateurs dans Microsoft 365 ou Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) afin que les utilisateurs puissent accéder à Microsoft Stream. Assurez-vous que Microsoft Stream n’est pas bloqué pour les utilisateurs, comme défini dans [Bloquer les abonnements pour Microsoft Stream](/stream/disable-user-organization).

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>Vérifier que les utilisateurs ont des autorisations de chargement de vidéo dans Microsoft Stream

Par défaut, tous les membres de l’entreprise peuvent créer du contenu dans Stream, une fois Stream activé et la licence affectée à l’utilisateur. Un administrateur Microsoft Stream peut [restreindre les employés à créer du contenu](https://docs.microsoft.com/stream/restrict-uploaders) en continu. Les utilisateurs figurant sur cette liste restreinte pourront toujours enregistrer des réunions, mais leurs enregistrements ne seront pas envoyés à Stream. À la place, ces enregistrements seront stockés temporairement sur AMS pendant 21 jours. Pendant cette période, l’enregistrement doit être téléchargé avant d’être supprimé à la fin de cette période de 21 jours.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Informez les employés pour qu’ils acceptent les instructions de la société dans Microsoft Stream

Si un administrateur Microsoft Stream a [configuré la stratégie de la société](/stream/company-policy-and-consent) et nécessite que les employés acceptent cette stratégie avant d’enregistrer le contenu, les utilisateurs doivent le faire avant de procéder à l’enregistrement dans Microsoft Teams. Avant de déployer la fonctionnalité d’enregistrement dans l’organisation, assurez-vous que les utilisateurs ont reçu une invitation à la stratégie.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Activer ou désactiver l’enregistrement dans le cloud

Vous pouvez utiliser le Centre d’administration Microsoft Teams ou PowerShell pour définir une stratégie de réunion Teams afin de contrôler si les réunions des utilisateurs peuvent être enregistrées.

Dans le Centre d’administration Microsoft Teams, activez ou désactivez le paramètre **Autoriser l’enregistrement dans le cloud** dans la stratégie de réunion. Si vous souhaitez en savoir plus, consultez l’article [Paramètres de stratégie de réunion pour l’audio et la vidéo](meeting-policies-audio-and-video.md#allow-cloud-recording).

À l’aide de PowerShell, vous configurez le paramètre AllowCloudRecording dans TeamsMeetingPolicy. Pour en savoir plus, consultez[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et [CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

Notez que l’organisateur de la réunion et l’initiateur de l’enregistrement doivent avoir les autorisations d’enregistrement pour enregistrer la réunion. Sauf si vous avez affecté une stratégie personnalisée aux utilisateurs, les utilisateurs reçoivent la stratégie globale, laquelle AllowCloudRecording est activée par défaut.

> [!NOTE]
> Pour plus d’informations sur l’utilisation des rôles Teams pour configurer les utilisateurs autorisés à enregistrer une réunion, consultez [Rôles dans une réunion Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Pour qu’un utilisateur renvoie la stratégie globale, utilisez l’applet de commande suivante pour supprimer une affectation de stratégie spécifique pour un utilisateur :

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false
```

</br>
</br>


|                                                                 Scénario                                                                 |                                                                                                                                                                         Étapes                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Je souhaite que tous les utilisateurs de mon entreprise puissent enregistrer leurs réunions                                    |                                                                     <ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowCloudRecording = Vrai<li>Tous les utilisateurs ont la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Vrai </ol>                                                                     |
| Je veux que la plupart des utilisateurs puissent enregistrer leurs réunions, mais désactiver de façon sélective des utilisateurs spécifiques qui ne sont pas autorisés à enregistrer |        <ol><li>Confirmer que la stratégie GlobalCsTeamsMeeting a AllowCloudRecording = Vrai<li>La plupart des utilisateurs ont la stratégie CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Vrai<li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowCloudRecording = Faux</ol>         |
|                                                   Je souhaite que l’enregistrement soit 100% désactivé                                                   |                                                                <ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowCloudRecording = Faux<li>Tous les utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Faux                                                                 |
|      Je souhaite que l’enregistrement soit désactivé pour la plupart des utilisateurs, mais qu’il autorise de façon sélective les utilisateurs autorisés à enregistrer       | <ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowCloudRecording = Faux<li>La plupart des utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Faux<li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowCloudRecording = Vrai <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |

#### <a name="where-your-meeting-recordings-are-stored"></a>Où sont stockées vos Enregistrements de réunions

Les enregistrements de réunion sont stockés dans le stockage cloud Microsoft Stream. Pour l’instant, la fonctionnalité d’enregistrement de la réunion est désactivée pour les clients dont les données d’équipe sont stockées dans le pays si Microsoft Stream n’est pas disponible dans la zone de résidence des données dans le pays où sont stockées les données. La fonctionnalité d’enregistrement de réunions Teams peut être activée pour les clients dont les données sont censées être stockées dans le pays, même si Microsoft Stream n’est pas disponible dans la région de résidence des données du pays. Vous pouvez faire cela en autorisant le stockage des enregistrements dans la région géographique la plus proche pour Microsoft Stream. 

Si vos données Teams sont stockées dans le pays et que vous préférez stocker les enregistrements de réunions dans le pays, nous vous conseillons de désactiver la fonctionnalité, puis de les activer une fois Microsoft Stream déployé sur votre pays ou région de résidence dans le pays. Pour désactiver la fonctionnalité pour tous les utilisateurs de votre organisation, désactivez le paramètre **Autoriser l’enregistrement dans le cloud** dans la stratégie de réunion globale Teams qui se trouve dans le Centre d’administration Microsoft Teams. Si, toutefois, vous souhaitez encore activer le stockage des enregistrement dans la région géographique la plus proche pour Microsoft Stream, vous devez activer **Autoriser l'enregistrement dans le cloud** et **Autoriser le stockage d’enregistrement en dehors de la région** avant que cette modification intervienne.

Pour activer les enregistrements existants dans une région dans la stratégie globale, utilisez la cmdlet suivante :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true
```

Voici un résumé de ce qui se produit lorsque vous activez l’enregistrement de la réunion lorsque cette modification prend effet :

|Si vous activez l’enregistrement de la réunion...|Les enregistrements de réunion sont stockés... |
|---|---|
|Avant que Microsoft Stream soit disponible dans votre région de résidence de données dans le pays |Dans la zone Microsoft Stream la plus proche|
|Après que Microsoft Stream soit disponible dans votre région de résidence de données dans le pays |Dans la région de résidence de données dans le pays|

Pour les clients nouveaux et existants qui n’ont pas encore activé l’enregistrement de la réunion, les nouveaux enregistrements sont stockés dans le pays une fois Microsoft Stream disponible dans la zone de résidence des données dans le pays. Cependant, les locataires qui activent l’enregistrement de réunions avant Microsoft Stream sont disponibles dans la zone de résidence des données dans le pays continuera à utiliser le stockage Microsoft Stream pour les enregistrements existants et nouveaux, même si Microsoft Stream est disponible dans le région de résidence des données dans le pays.

Pour rechercher la région dans laquelle vos données Microsoft Stream sont stockées, dans Microsoft Stream, cliquez sur **?** dans le coin supérieur droit, cliquez sur **À propos de Microsoft Stream**, puis sur **Vos données sont stockées dans**.  Pour en savoir plus sur les régions dans lesquelles Microsoft Stream stocke les données, consultez la rubrique [FAQ Microsoft Stream](/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

Pour en savoir plus sur l’emplacement de stockage des données au sein des services dans Microsoft 365 ou Office 365, consultez [Où se trouvent vos données ?](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>Activer ou désactiver la transcription de l’enregistrement

Ce paramètre détermine si les fonctionnalités de légende et de transcription sont disponibles lors de la lecture des enregistrements de réunion. Si vous désactivez cette option, les options **Recherche** et **CC** ne sont pas disponibles pendant la lecture d’un enregistrement de réunion. La personne qui a démarré l’enregistrement a besoin de ce paramètre activé de sorte que l’enregistrement inclut également la transcription.

> [!NOTE]
> Cette transcription pour les réunions enregistrées est pour l’instant prise en charge uniquement pour les utilisateurs dont la langue est définie sur anglais dans Teams et lorsque l’anglais est parlé pendant la réunion. Ils sont stockés avec les enregistrements de réunion dans le stockage cloud Microsoft Stream.

Vous pouvez utiliser le Centre d’administration Microsoft Teams ou PowerShell pour définir une stratégie de réunion Teams afin de contrôler si l’initiateur d’enregistrement peut transcrire le choix de transcrire l’enregistrement de la réunion.

Dans le Centre d’administration Microsoft Teams, activez ou désactivez le paramètre **Autoriser la transcription** dans la stratégie de réunion. Si vous souhaitez en savoir plus, consultez l’article [Paramètres de stratégie de réunion pour l’audio et la vidéo](meeting-policies-audio-and-video.md#allow-transcription).

À l’aide de PowerShell, vous configurez le paramètre AllowTranscription dans TeamsMeetingPolicy. Pour en savoir plus, consultez[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et [CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

Sauf si vous avez affecté une stratégie personnalisée aux utilisateurs, les utilisateurs reçoivent la stratégie globale, laquelle AllowTranscription est désactivée par défaut.

Pour qu’un utilisateur renvoie la stratégie globale, utilisez l’applet de commande suivante pour supprimer une affectation de stratégie spécifique pour un utilisateur :

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```

</br>
</br>

|Scénario|Étapes |
|---|---|
|Je souhaite que tous les utilisateurs de ma société soient en mesure de transcrire lors du lancement de l’enregistrement d’une réunion |<ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowTranscription = Vrai <li>Tous les utilisateurs ont la stratégie globale csTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = Vrai. </ol>|
|Je veux que la plupart des utilisateurs puissent transcrire les enregistrements de réunion, mais désactiver de façon sélective des utilisateurs spécifiques qui ne sont pas autorisés à transcrire |<ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowTranscription = Vrai <li>La plupart des utilisateurs ont la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = Vrai. <li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowTranscription = Faux </ol>|
|Je souhaite que la transcription de l’enregistrement soit 100 % désactivée |<ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowTranscription = Faux <li>Tous les utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = Faux </ol>|
|Je souhaite que la transcription soit désactivé pour la plupart des utilisateurs, mais qu’il autorise de façon sélective les utilisateurs autorisés à transcrire |<ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowCloudRecording = Faux <li>La plupart des utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Faux <li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowCloudRecording = Vrai </ol>|
|||

### <a name="planning-for-storage"></a>Planification pour stockage

La taille d’un enregistrement de 1 heure est de 400 Mo. Assurez-vous que vous comprenez la capacité requise pour les fichiers enregistrés et disposez d’un espace de stockage suffisant disponible dans Microsoft Stream.  Consultez [Vue d’ensemble des licences Microsoft Stream](/stream/license-overview) pour comprendre le stockage de base inclus dans l’abonnement et comment acheter de l’espace de stockage supplémentaire.

## <a name="manage-meeting-recordings"></a>Gérer les enregistrements de réunions

Les enregistrements de réunion sont considérés comme du contenu appartenant au locataire. Si le propriétaire de l’enregistrement quitte l’entreprise, l’administrateur peut ouvrir l’URL de la vidéo d’enregistrement dans Microsoft Stream en mode administrateur. L’administrateur peut supprimer l’enregistrement, mettre à jour les métadonnées d’enregistrement ou modifier les autorisations de la vidéo d’enregistrement. En savoir plus sur les [fonctionnalités d’administration de dans Stream](/stream/manage-content-permissions).

> [!NOTE]
> Pour plus d’informations sur la gestion des enregistrements et l’accès utilisateur, consultez [Gérer les données utilisateur dans Microsoft Stream](/stream/managing-user-data) et [Autorisations et confidentialité dans Microsoft Stream](/stream/portal-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Conformité et eDiscovery pour les enregistrements de réunions

Les enregistrements des réunions sont stockés dans Microsoft Stream, qui est conforme à la norme Microsoft 365 et Office 365 Tier-C. Pour prendre en charge les demandes d’e-Discovery pour les administrateurs de conformité qui sont intéressés par les enregistrements de réunion ou d’appels pour Microsoft Streams, le message enregistrement terminé est disponible dans la fonctionnalité de recherche de contenu de conformité pour Microsoft Teams. Les administrateurs de conformité peuvent rechercher le mot clé « enregistrement » dans la ligne d’objet de l’élément dans le cadre de la recherche de contenu de conformité et découvrir les enregistrements de réunions et d’appels au sein de l’organisation. Une condition préalable pour qu’elles puissent afficher tous les enregistrements est qu’ils doivent être configurés dans Microsoft Stream avec accès administrateur. En savoir plus sur les [affectations d’autorisations d’administrateur dans Stream](/stream/assign-administrator-user-role).

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)