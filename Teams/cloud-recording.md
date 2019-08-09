---
title: Enregistrement de réunion cloud Teams
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
ms.reviewer: sonua
search.appverid: MET150
description: Guide pratique pour le déploiement de la fonctionnalité vocale cloud dans Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88f043bec273cb19745e9800fc9cdb85f64c8e7a
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271396"
---
# <a name="teams-cloud-meeting-recording"></a>Enregistrement de réunion cloud Teams

Microsoft teams permet aux utilisateurs d’enregistrer les réunions et les appels de groupe de leurs équipes pour capter les activités de partage audio, vidéo et de partage d’écran. Il existe également une option pour les enregistrements qui permet une transcription automatique, afin que les utilisateurs puissent regarder les enregistrements de réunion avec des sous-titres et rechercher des éléments de discussion importants dans la transcription. L’enregistrement intervient dans le Cloud et est enregistré dans [Microsoft Stream](https://docs.microsoft.com/stream/), de sorte que les utilisateurs puissent le partager en toute sécurité au sein de leur organisation.

Associé: [la documentation sur l’enregistrement de la réunion teams](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Conditions préalables à l’enregistrement d’une réunion Cloud teams

Pour que les réunions d’un utilisateur d’équipes puissent être enregistrées, Microsoft Stream doit être activé pour le client. De plus, les conditions préalables suivantes sont requises pour l’organisateur de la réunion et la personne qui initialise l’enregistrement:

- L’utilisateur possède un bureau 365 E1, E3, E5, a1, a3, a5, M365 entreprise, Business Premium ou Business Essentials
- L’utilisateur doit avoir une licence pour Microsoft Stream<sup>1</sup> 
- L’utilisateur dispose des autorisations de la vidéo de téléchargement de Microsoft Stream
- L’utilisateur s’est inscrit aux recommandations de la société, si elle a été configurée par l’administrateur.
- L’utilisateur dispose d’un espace de stockage suffisant dans Microsoft Stream pour enregistrer les enregistrements
- L’utilisateur dispose du paramètre TeamsMeetingPolicy-AllowCloudRecording défini sur true
- L’utilisateur n’est pas un utilisateur anonyme, d’invité ou fédéré dans la réunion

> [!NOTE]
> Par ailleurs, pour permettre à la personne chargée de l’enregistrement d’indiquer la transcription automatique de l’enregistrement, le paramètre TeamsMeetingPolicy-AllowTranscription de l’utilisateur doit être défini sur true.

<sup>1</sup> L’utilisateur doit être titulaire d’une licence pour télécharger et télécharger des réunions dans/à partir de Microsoft Stream, mais il n’est pas nécessaire d’enregistrer une réunion. Si vous souhaitez empêcher un utilisateur d’enregistrer une réunion Microsoft Teams, vous devez lui accorder une TeamsMeetingPolicy dont AllowCloudRecording a la valeur $False.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurer l’enregistrement de réunion Cloud teams pour les utilisateurs de votre organisation

Cette section explique comment vous pouvez configurer et planifier des réunions d’équipes.

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Activer Microsoft Stream pour les utilisateurs au sein de l’Organisation

Microsoft Stream est disponible dans le cadre des abonnements Office 365 éligibles ou d’un service autonome.  Pour plus d’informations, consultez la [vue d’ensemble des licences de flux](https://docs.microsoft.com/stream/license-overview) .  Microsoft Stream est désormais inclus dans Microsoft 365 entreprise, Office 365 Business Premium et Office 365 Business Essentials.

Apprenez-en davantage sur la façon dont vous pouvez [attribuer des licences aux utilisateurs dans Office 365 de](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) sorte que les utilisateurs puissent accéder à Microsoft Stream. Assurez-vous que Microsoft Stream n’est pas bloqué pour les utilisateurs, tel que défini dans [cet article](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>S’assurer que les utilisateurs ont des autorisations de téléchargement de vidéo dans Microsoft Stream

Par défaut, tous les membres de l’entreprise peuvent créer du contenu dans le flux, une fois que le flux est activé et que la licence est affectée à l’utilisateur. Un administrateur de flux Microsoft peut [limiter les employés pour la création de contenu](https://docs.microsoft.com/stream/restrict-uploaders) dans le flux. Les utilisateurs figurant dans cette liste restreinte ne peuvent pas enregistrer des réunions.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Notification aux employés d’accepter les directives de la société dans Microsoft Stream

Si un administrateur de Microsoft Stream a [configuré la politique d’instructions](https://docs.microsoft.com/stream/company-policy-and-consent) de la société et nécessite que les employés acceptent cette politique avant d’enregistrer le contenu, les utilisateurs doivent le faire avant d’enregistrer dans Microsoft Teams. Avant de déployer la fonctionnalité d’enregistrement au sein de l’organisation, assurez-vous que les utilisateurs ont reçu cette politique.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Activer ou désactiver l’enregistrement dans le Cloud

Utilisez le paramètre AllowCloudRecording dans TeamsMeetingPolicy dans teams PowerShell pour contrôler si les réunions d’un utilisateur peuvent être enregistrées ou non. Pour en savoir plus sur la gestion de TeamsMeetingPolicy avec Office 365 PowerShell, procédez comme [suit](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Notez que l’organisateur de la réunion et l’initiateur du Registre doivent disposer de l’autorisation d’enregistrement pour enregistrer la réunion. À moins que vous n’ayez affecté une stratégie personnalisée aux utilisateurs, les utilisateurs obtiennent une stratégie globale qui a désactivé par défaut AllowTranscription.

Pour qu’un utilisateur revient à la stratégie globale, utilisez l’applet de commande suivante pour supprimer une affectation de stratégie spécifique pour un utilisateur:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Scénario                                                                 |                                                                                                                                                                         Étapes                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Je souhaite que tous les utilisateurs de mon entreprise puissent enregistrer leurs réunions                                    |                                                                     <ol><li>Confirmer le CsTeamsMeetingPolicy global est AllowCloudRecording = true<li>Tous les utilisateurs ont le CsTeamsMeetingPolicy global ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = true </ol>                                                                     |
| Je veux que la plupart des utilisateurs puissent enregistrer leurs réunions, mais désactiver de manière sélective des utilisateurs spécifiques qui ne sont pas autorisés à enregistrer |        <ol><li>Vérifiez que GlobalCsTeamsMeetingPolicy a AllowCloudRecording = true<li>La plupart des utilisateurs ont le CsTeamsMeetingPolicy global ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = true<li>Les autres utilisateurs ont reçu l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = false.</ol>         |
|                                                   Je souhaite que l’enregistrement soit de 100% désactivé                                                   |                                                                <ol><li>Confirmer le CsTeamsMeetingPolicy global est AllowCloudRecording = false.<li>Tous les utilisateurs ont reçu l’CsTeamsMeetingPolicy global ou l’une des politiques CsTeamsMeetingPolicy avec AllowCloudRecording = false.                                                                 |
|      Je souhaite que l’enregistrement soit désactivé pour la plupart des utilisateurs, mais qu’il autorise sélectivement des utilisateurs spécifiques autorisés à enregistrer       | <ol><li>Confirmer le CsTeamsMeetingPolicy global est AllowCloudRecording = false.<li>La plupart des utilisateurs ont reçu l’CsTeamsMeetingPolicy global ou l’une des politiques CsTeamsMeetingPolicy avec AllowCloudRecording = false.<li>Les autres utilisateurs ont reçu l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = true <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                        |

### <a name="turn-on-or-turn-off-recording-transcription"></a>Activer ou désactiver la transcription d’enregistrement

Lorsque les utilisateurs enregistrent leurs réunions d’équipe, ils peuvent vérifier qu’une transcription doit être générée automatiquement une fois que la réunion est enregistrée. Si les administrateurs ont désactivé la fonctionnalité de transcription pour l’organisateur de la réunion et l’initiateur de l’enregistrement, l’initiateur d’enregistrement n’aura aucun choix pour transcrire les enregistrements de la réunion.

Utilisez le paramètre AllowTranscription dans TeamsMeetingPolicy dans teams PowerShell pour contrôler si un initiateur d’enregistrement peut choisir de transcrire l’enregistrement de la réunion. Pour en savoir plus sur la gestion de TeamsMeetingPolicy avec Office 365 PowerShell, procédez comme [suit](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

À moins que vous n’ayez affecté une stratégie personnalisée aux utilisateurs, ils obtiennent une stratégie globale qui a AllowTranscription désactivée par défaut.

Pour qu’un utilisateur revient à la stratégie globale, utilisez l’applet de commande suivante pour supprimer une affectation de stratégie spécifique pour un utilisateur:

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante:

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Scénario|Étapes |
|---|---|
|Je veux que tous les utilisateurs de mon entreprise puissent transcrire lors du lancement de l’enregistrement d’une réunion |<ol><li>Confirmer le CsTeamsMeetingPolicy global est AllowTranscription = true <li>Tous les utilisateurs ont le csTeamsMeetingPolicy global ou l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = true. </ol>|
|La plupart des utilisateurs doivent être en mesure de transcrire les enregistrements de la réunion, mais les utilisateurs spécifiques qui ne sont pas autorisés à transcrire |<ol><li>Confirmer le CsTeamsMeetingPolicy global est AllowTranscription = true <li>La plupart des utilisateurs ont le CsTeamsMeetingPolicy global ou l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = true <li>Les autres utilisateurs ont reçu l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = false. </ol>|
|Je veux que la transcription de l’enregistrement soit de 100% désactivé |<ol><li>Confirmer le CsTeamsMeetingPolicy global est AllowTranscription = false. <li>Tous les utilisateurs ont reçu l’CsTeamsMeetingPolicy global ou l’une des politiques CsTeamsMeetingPolicy avec AllowTranscription = false. </ol>|
|Je veux que la transcription soit désactivée pour la plupart des utilisateurs, mais elle autorise sélectivement des utilisateurs spécifiques qui sont autorisés à transcrire |<ol><li>Confirmer le CsTeamsMeetingPolicy global est AllowCloudRecording = false. <li>La plupart des utilisateurs ont reçu l’CsTeamsMeetingPolicy global ou l’une des politiques CsTeamsMeetingPolicy avec AllowCloudRecording = false. <li>Les autres utilisateurs ont reçu l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = true </ol>|
|||

### <a name="planning-for-storage"></a>Planification du stockage

La taille d’un enregistrement d'1 heure est de 400 Mo. Assurez-vous de connaître la capacité requise pour les fichiers enregistrés et disposer d’un espace de stockage suffisant disponible dans Microsoft Stream.  Lisez [cet article](https://docs.microsoft.com/stream/license-overview) pour connaître le stockage de base inclus dans l’abonnement et l’achat d’un espace de stockage supplémentaire.

## <a name="manage-meeting-recordings"></a>Gérer les enregistrements de réunion
Les enregistrements de réunion sont considérés comme du contenu appartenant au client. Si le propriétaire de l’enregistrement quitte l’entreprise, l’administrateur peut ouvrir l’URL de la vidéo d’enregistrement dans Microsoft Stream en mode admin. L’administrateur est en mesure de supprimer l’enregistrement, de mettre à jour les métadonnées d’enregistrement ou de modifier les autorisations de la vidéo d’enregistrement. En savoir plus sur les [fonctionnalités d’administration dans Stream](https://docs.microsoft.com/stream/manage-content-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Conformité et découverte électronique pour les enregistrements de réunion
Les enregistrements de la réunion sont stockés dans Microsoft Stream, conforme à la norme Office 365 Tier-C. Pour prendre en charge les demandes de e-Discovery destinées aux administrateurs de la conformité qui sont intéressés par les enregistrements de réunion ou d’appel pour les flux Microsoft, le message enregistrement Completed est disponible dans la fonctionnalité de recherche de contenu de conformité pour Microsoft Teams. Les administrateurs de la conformité peuvent rechercher le mot clé «enregistrement» dans la ligne d’objet de l’élément dans l’aperçu de la recherche de contenu de conformité et découvrir les enregistrements de réunion et d’appel au sein de l’organisation. Pour qu’ils puissent voir tous les enregistrements, il doit être configuré dans Microsoft Stream avec l’accès administrateur. En savoir plus sur [l’attribution des autorisations d’administrateur dans Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Configurer votre ordinateur pour Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525038)

