---
title: Enregistrement de réunion cloud Teams
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: Comment activer et gérer l’enregistrement de la réunion dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f358a0099da3f759e50f02b7bb7a5226069fcd28
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780333"
---
# <a name="teams-cloud-meeting-recording"></a>Enregistrement de réunion cloud Teams

Dans Microsoft Teams, les utilisateurs peuvent enregistrer leurs réunions et appels de groupe Teams pour capturer les activités audio, vidéo et de partage d’écran. Il existe également une option pour les enregistrements qui permet une transcription automatique, afin que les utilisateurs puissent regarder les enregistrements de réunion avec des sous-titres et rechercher des éléments de discussion importants dans la transcription. L’enregistrement se fait dans le cloud et est sauvegardé dans [Microsoft Stream](https://docs.microsoft.com/stream/) pour permettre aux utilisateurs de le partager en toute sécurité au sein de leur organisation.

En relation avec la [Réunion Teams de qui enregistre la documentation de l’utilisateur final](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Conditions préalables pour l’enregistrement de réunion cloud Teams

Microsoft Stream doit être activé pour que les réunions d’un utilisateur Teams soient enregistrées pour le locataire. De plus, les conditions préalables suivantes sont requises pour l’organisateur de la réunion et la personne qui lance l’enregistrement :

- L’utilisateur a Office 365 E1, E3, E5, A1, A3, A5, M365 Business, Business Premium ou Business Essentials
- L’utilisateur doit disposer d’une licence Microsoft Stream <sup>1</sup> 
- L’utilisateur doit disposer des autorisations nécessaires au chargement des vidéos Microsoft Stream
- L’utilisateur doit avoir accepté les directives de l’entreprise configurées par l’administrateur, le cas échéant.
- L’utilisateur doit disposer de l’espace de stockage suffisant dans Microsoft Stream pour sauvegarder les enregistrements
- L’utilisateur a le paramètre TeamsMeetingPolicy-AllowCloudRecording défini sur true
- L’utilisateur ne doit pas être un utilisateur anonyme, invité ou fédéré de la réunion

> [!NOTE]
> De plus, pour permettre à la personne qui a initié l’enregistrement de choisir de transcrire automatiquement l’enregistrement, le paramètre TeamsMeetingPolicy-AllowTranscription de l’utilisateur doit être défini sur true

<sup>1</sup>utilisateur doit être titulaire d’une licence pour charger ou télécharger les réunions vers ou à partir de Microsoft Stream, mais il n’a pas besoin de la licence pour enregistrer une réunion. Si vous souhaitez empêcher un utilisateur d’enregistrer une réunion Microsoft Teams, vous devez accorder une TeamsMeetingPolicy dont AllowCloudRecording a la valeur $False.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurer l’Enregistrement de réunion cloud Teams pour les utilisateurs de votre organisation

Cette section vous explique comment configurer et planifier l'enregistrement des réunions Teams.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>Activer Microsoft Stream pour les utilisateurs de l’Organisation

Microsoft Stream est disponible dans le cadre des abonnements Microsoft 365 et Office 365 admissibles ou en tant que service autonome.  Pour plus d’informations, consultez la [Vue d’ensemble des licences Stream](https://docs.microsoft.com/stream/license-overview).  Microsoft Stream est désormais inclus dans Microsoft 365 entreprise, Microsoft 365 Business standard et Microsoft 365 entreprise Basic.

En savoir plus sur la façon dont vous pouvez [affecter des licences aux utilisateurs dans Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) afin que les utilisateurs puissent accéder à Microsoft Stream. Assurez-vous que Microsoft Stream n’est pas bloqué pour les utilisateurs, comme défini dans [cet article](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>S’assurer que les utilisateurs ont des autorisations de téléchargement de vidéo dans Microsoft Stream

Par défaut, tous les membres de l’entreprise peuvent créer du contenu dans Stream, une fois Stream activé et la licence affectée à l’utilisateur. Un administrateur Microsoft Stream peut [restreindre les employés à créer du contenu](https://docs.microsoft.com/stream/restrict-uploaders) en continu. Les utilisateurs figurant dans cette liste restreinte ne pourront pas enregistrer de réunions.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Informez les employés pour qu’ils acceptent les instructions de la société dans Microsoft Stream

Si un administrateur Microsoft Stream a [configuré la stratégie de la société](https://docs.microsoft.com/stream/company-policy-and-consent) et nécessite que les employés acceptent cette stratégie avant d’enregistrer le contenu, les utilisateurs doivent le faire avant de procéder à l’enregistrement dans Microsoft Teams. Avant de déployer la fonctionnalité d’enregistrement dans l’organisation, assurez-vous que les utilisateurs ont reçu une invitation à la stratégie.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Activer ou désactiver l’enregistrement dans le cloud

Vous pouvez utiliser le Centre d’administration Microsoft Teams ou PowerShell pour définir une stratégie de réunion Teams afin de contrôler si les réunions des utilisateurs peuvent être enregistrées.

Dans le Centre d’administration Microsoft Teams, activez ou désactivez le paramètre **Autoriser l’enregistrement dans le cloud** dans la stratégie de réunion. Pour plus d’informations, voir [Gérer les stratégies de réunion Teams](meeting-policies-in-teams.md#allow-cloud-recording).

À l’aide de PowerShell, vous configurez le paramètre AllowCloudRecording dans TeamsMeetingPolicy. Pour en savoir plus, consultez[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) et [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Notez que l’organisateur de la réunion et l’initiateur de l’enregistrement doivent avoir les autorisations d’enregistrement pour enregistrer la réunion. Sauf si vous avez affecté une stratégie personnalisée aux utilisateurs, les utilisateurs reçoivent la stratégie globale, laquelle AllowCloudRecording est désactivée par défaut.

Pour qu’un utilisateur renvoie la stratégie globale, utilisez l’applet de commande suivante pour supprimer une affectation de stratégie spécifique pour un utilisateur :

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante :

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Scénario                                                                 |                                                                                                                                                                         Étapes                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Je souhaite que tous les utilisateurs de mon entreprise puissent enregistrer leurs réunions                                    |                                                                     <ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowCloudRecording = Vrai<li>Tous les utilisateurs ont la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Vrai </ol>                                                                     |
| Je veux que la plupart des utilisateurs puissent enregistrer leurs réunions, mais désactiver de façon sélective des utilisateurs spécifiques qui ne sont pas autorisés à enregistrer |        <ol><li>Confirmer que la stratégie GlobalCsTeamsMeeting a AllowCloudRecording = Vrai<li>La plupart des utilisateurs ont la stratégie CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Vrai<li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowCloudRecording = Faux</ol>         |
|                                                   Je souhaite que l’enregistrement soit 100% désactivé                                                   |                                                                <ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowCloudRecording = Faux<li>Tous les utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Faux                                                                 |
|      Je souhaite que l’enregistrement soit désactivé pour la plupart des utilisateurs, mais il autorise sélectivement les utilisateurs spécifiques autorisés à enregistrer       | <ol><li>Confirmer que la stratégie globale CsTeamsMeeting a AllowCloudRecording = Faux<li>La plupart des utilisateurs ont reçu la stratégie globale CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = Faux<li>Tous les autres utilisateurs ont reçu une des stratégies de CsTeamsMeetingPolicy avec AllowCloudRecording = Vrai <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>Où sont stockées vos Enregistrements de réunions

Les enregistrements de réunion sont stockés dans le stockage cloud Microsoft Stream. Une fois que vous avez enregistré une réunion, Microsoft Stream la conserve définitivement (ou jusqu’à ce que le propriétaire de l’enregistrement le supprime). Si l’enregistrement n’est pas transféré en flux, il est stocké dans le stockage cloud Teams, où il est disponible en téléchargement pendant 20 jours. Pour l’instant, la fonctionnalité d’enregistrement de la réunion est désactivée pour les clients dont les données d’équipe sont stockées dans le pays si Microsoft Stream n’est pas disponible dans la zone de résidence des données dans le pays où sont stockées les données.

Pour rechercher la région dans laquelle vos données Microsoft Stream sont stockées, dans Microsoft Stream, cliquez sur **?** dans le coin supérieur droit, cliquez sur **À propos de Microsoft Stream**, puis sur **Vos données sont stockées dans**.  Pour en savoir plus sur les régions dans lesquelles Microsoft Stream stocke les données, consultez la rubrique [FAQ Microsoft Stream](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

Pour en savoir plus sur l’emplacement de stockage des données au sein des services dans Office 365, consultez [Où se trouvent vos données ?](https://products.office.com/where-is-your-data-located?rtc=1)

### <a name="turn-on-or-turn-off-recording-transcription"></a>Activer ou désactiver la transcription de l’enregistrement

Lorsque les utilisateurs enregistrent leurs réunions Teams, ils peuvent vérifier qu’une transcription doit être générée automatiquement une fois la réunion enregistrée. Si vous avez désactivé la fonctionnalité de transcription pour l’organisateur de la réunion et l’initiateur de l’enregistrement, l’initiateur d’enregistrement n’a pas la possibilité de transcrire les enregistrements de réunion.

Vous pouvez utiliser le Centre d’administration Microsoft Teams ou PowerShell pour définir une stratégie de réunion Teams afin de contrôler si l’initiateur d’enregistrement peut transcrire le choix de transcrire l’enregistrement de la réunion.

Dans le Centre d’administration Microsoft Teams, activez ou désactivez le paramètre **Autoriser la transcription** dans la stratégie de réunion. Pour plus d’informations, voir [Gérer les stratégies de réunion Teams](meeting-policies-in-teams.md#allow-transcription).

À l’aide de PowerShell, vous configurez le paramètre AllowTranscription dans TeamsMeetingPolicy. Pour en savoir plus, consultez[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) et [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Sauf si vous avez affecté une stratégie personnalisée aux utilisateurs, les utilisateurs reçoivent la stratégie globale, laquelle AllowTranscription est désactivée par défaut.

Pour qu’un utilisateur renvoie la stratégie globale, utilisez l’applet de commande suivante pour supprimer une affectation de stratégie spécifique pour un utilisateur :

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante :

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
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

La taille d’un enregistrement de 1 heure est de 400 Mo. Assurez-vous que vous comprenez la capacité requise pour les fichiers enregistrés et disposez d’un espace de stockage suffisant disponible dans Microsoft Stream.  Consultez [cet article](https://docs.microsoft.com/stream/license-overview) pour comprendre le stockage de base inclus dans l’abonnement et comment acheter de l’espace de stockage supplémentaire.

## <a name="manage-meeting-recordings"></a>Gérer les enregistrements de réunions

Les enregistrements de réunion sont considérés comme du contenu appartenant au locataire. Si le propriétaire de l’enregistrement quitte l’entreprise, l’administrateur peut ouvrir l’URL de la vidéo d’enregistrement dans Microsoft Stream en mode administrateur. L’administrateur peut supprimer l’enregistrement, mettre à jour les métadonnées d’enregistrement ou modifier les autorisations de la vidéo d’enregistrement. En savoir plus sur les [fonctionnalités d’administration de dans Stream](https://docs.microsoft.com/stream/manage-content-permissions).

> [!NOTE]
> Pour plus d’informations sur la gestion des enregistrements et l’accès utilisateur, consultez [Gérer les données utilisateur dans Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data) et [Autorisations et confidentialité dans Microsoft Stream](https://docs.microsoft.com/stream/portal-permissions).


## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Conformité et eDiscovery pour les enregistrements de réunions

Les enregistrements des réunions sont stockés dans Microsoft Stream, qui est conforme à la norme Office 365 Tier-C. Pour prendre en charge les demandes d’e-Discovery pour les administrateurs de conformité qui sont intéressés par les enregistrements de réunion ou d’appels pour Microsoft Streams, le message enregistrement terminé est disponible dans la fonctionnalité de recherche de contenu de conformité pour Microsoft Teams. Les administrateurs de conformité peuvent rechercher le mot clé « enregistrement » dans la ligne d’objet de l’élément dans le cadre de la recherche de contenu de conformité et découvrir les enregistrements de réunions et d’appels au sein de l’organisation. Une condition préalable pour qu’elles puissent afficher tous les enregistrements est qu’ils doivent être configurés dans Microsoft Stream avec accès administrateur. En savoir plus sur les [affectations d’autorisations d’administrateur dans Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
