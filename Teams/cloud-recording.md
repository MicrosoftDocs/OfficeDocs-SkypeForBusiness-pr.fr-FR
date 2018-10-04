---
title: Enregistrement de la réunion équipes sur le nuage
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Guide pratique pour le déploiement de la fonctionnalité vocale cloud dans Microsoft Teams.
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: e78abdbe7d0cc2680917f2aae7920883837a2ac9
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375978"
---
# <a name="teams-cloud-meeting-recording"></a>Enregistrement de la réunion équipes sur le nuage

> [!Note]
> [!INCLUDE [preview-feature](includes/preview-feature.md)]

Dans Microsoft Teams, les utilisateurs peuvent enregistrer leurs réunions d’équipes et les appels de groupe de capture audio, vidéo et partage d’activité de l’écran. Il existe également une option pour les enregistrements d’avoir une transcription automatique, afin que les utilisateurs peuvent lire des enregistrements de réunions avec légendes et rechercher des éléments de discussion important dans la transcription. L’enregistrement se produit dans le nuage et est enregistré dans le [Flux de Microsoft](https://docs.microsoft.com/stream/), afin que les utilisateurs peuvent partager en toute sécurité au sein de leur organisation.

Connexes : [Enregistrement de documentation de l’utilisateur final de la réunion équipes](https://aka.ms/recordmeeting)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Conditions requises pour l’enregistrement de la réunion équipes sur le nuage

Pour les réunions d’un utilisateur d’équipes à enregistrer, Stream Microsoft doit être activé pour le client. En outre, les conditions préalables suivantes sont requises pour l’organisateur de la réunion et de la personne qui lance l’enregistrement :

- Utilisateur possède une licence Office 365 entreprise E1, E3 ou E5
- L’utilisateur doit être autorisé pour Microsoft Stream
- Utilisateur a Microsoft Stream télécharger autorisations vidéo
- Utilisateur a accepté les instructions de la société, si définie par l’administrateur
- L’utilisateur a un espace suffisant dans Stream Microsoft pour les enregistrements d’être enregistrées
- Utilisateur a TeamsMeetingPolicy-AllowCloudRecording paramètre défini sur true
- Utilisateur a TeamsMeetingPolicy-AllowTranscription paramètre défini sur true, afin que l’utilisateur peut choisir s’il faut transcrire automatiquement les enregistrements
- Utilisateur n’est pas anonyme, invité ou utilisateur fédéré de la réunion

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configuration d’enregistrement de réunion équipes cloud pour les utilisateurs de votre organisation

Cette section explique comment vous pouvez configurer et planifier des réunions d’équipes d’enregistrement.

### <a name="enable-microsoft-stream-for-users-in-the-organization"></a>Activer Microsoft Stream pour les utilisateurs dans l’organisation

Stream Microsoft est disponible dans le cadre des abonnements Office 365 éligibles ou en tant que service autonome.  Voir la [Présentation des flux de licences](https://docs.microsoft.com/stream/license-overview) pour plus d’informations.  Notez que Microsoft Stream n’est pas inclus dans Business Essentials ou entreprise Premium plans.

Pour plus d’informations sur la façon dont vous pouvez [attribuer des licences aux utilisateurs dans Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) afin que les utilisateurs peuvent accéder à Microsoft Stream. Assurez-vous que Microsoft Stream n’est pas bloqué pour les utilisateurs, comme défini dans [cet article](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="ensure-that-users-have-upload-video-permissions-in-microsoft-stream"></a>Assurez-vous que les utilisateurs ont télécharger autorisations vidéo dans Microsoft Stream

Par défaut, tout le monde peut créer du contenu dans le flux de données, une fois que le flux est activée et que la licence est attribuée à l’utilisateur. Un administrateur de Microsoft Stream peut [empêcher les employés pour la création de contenu](https://docs.microsoft.com/stream/restrict-uploaders) dans le flux. Les utilisateurs qui figurent dans cette liste restreinte ne sera pas en mesure d’enregistrer les réunions.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Notifier les employés à consentez aux instructions de la société dans Microsoft Stream

Si un administrateur de Microsoft Stream a [configurer la stratégie de règle d’entreprise](https://docs.microsoft.com/stream/company-policy-and-consent) et exige que les employés accepter cette stratégie avant d’enregistrer le contenu, les utilisateurs doivent le faire avant l’enregistrement dans Microsoft Teams. Avant de déployer la fonctionnalité d’enregistrement dans l’organisation, assurez-vous que les utilisateurs ont accepté à la stratégie.

### <a name="enabledisable-cloud-recording-for-users"></a>Activer/désactiver l’enregistrement pour les utilisateurs de nuage

Utiliser le paramètre AllowCloudRecording de TeamsMeetingPolicy dans PowerShell équipes pour contrôler si les réunions d’un utilisateur sont autorisées à être enregistrée ou non. Vous pouvez en savoir plus sur la gestion des TeamsMeetingPolicy avec Office 365 PowerShell [ici](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Notez que l’organisateur de la réunion et de l’initiateur d’enregistrement doivent disposer des autorisations d’enregistrement à enregistrer la réunion. Sauf si vous avez assigné une stratégie personnalisée pour les utilisateurs, les utilisateurs obtiennent la stratégie globale, qui a AllowTranscription désactivée par défaut.

Pour un utilisateur de revenir à la stratégie globale, utilisez l’applet de commande suivante pour supprimer l’affectation d’une stratégie spécifique pour un utilisateur :

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante :

`Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false`
</br>
</br>


|                                                                 Scénario                                                                 |                                                                                                                                                                         Étapes                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Je veux tous les utilisateurs de votre société pour être en mesure d’enregistrer des réunions                                    |                                                                     <ol><li>Confirmer Global CsTeamsMeetingPolicy a AllowCloudRecording = True<li>Tous les utilisateurs ont la globale ou CsTeamsMeetingPolicy l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = True </ol>                                                                     |
| Je souhaite la majorité des utilisateurs à être en mesure d’enregistrer des réunions, mais désactiver des utilisateurs spécifiques qui ne sont pas autorisés à enregistrer |        <ol><li>Vérifiez GlobalCsTeamsMeetingPolicy a AllowCloudRecording = True<li>Majorité des utilisateurs ont le Global CsTeamsMeetingPolicy ou une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = True<li>Tous les autres utilisateurs ont été accordées à l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = False</ol>         |
|                                                   Je veux enregistrement pour qu’il soit désactivé 100 %                                                   |                                                                <ol><li>Confirmer Global CsTeamsMeetingPolicy a AllowCloudRecording = False<li>Tous les utilisateurs ont été accordées le Global CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = False                                                                 |
|      Je veux enregistrement pour être désactivée pour la plupart des utilisateurs sans activer des utilisateurs spécifiques qui sont autorisés à enregistrer       | <ol><li>Confirmer Global CsTeamsMeetingPolicy a AllowCloudRecording = False<li>La majorité des utilisateurs ont été accordées le Global CsTeamsMeetingPolicy ou une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = False<li>Tous les autres utilisateurs ont été accordées à l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = True <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                        |

### <a name="enabledisable-recording-transcription-for-users"></a>Activer/désactiver l’enregistrement transcription pour les utilisateurs

Lorsque les utilisateurs enregistrement leurs réunions d’équipes, ils peuvent confirmer si une transcription doit être générée automatiquement après l’enregistrement de la réunion. Si admins avez désactivé fonctionnalité transcription pour l’organisateur de la réunion et l’initiateur d’enregistrement, l’initiateur d’enregistrement ne recevra pas un choix transcrire les enregistrements de la réunion.

Utilisez le paramètre AllowTranscription dans TeamsMeetingPolicy dans PowerShell équipes pour contrôler si un initiateur enregistrement Obtient la possibilité d’effectuer une transcription de l’enregistrement de la réunion. Vous pouvez en savoir plus sur la gestion des TeamsMeetingPolicy avec Office 365 PowerShell [ici](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Sauf si vous avez assigné une stratégie personnalisée pour les utilisateurs, ils obtiennent stratégie globale, qui est désactivé par défaut.

Pour un utilisateur de revenir à la stratégie globale, utilisez l’applet de commande suivante pour supprimer l’affectation d’une stratégie spécifique pour un utilisateur :

`Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose`

Pour modifier la valeur de AllowCloudRecording dans la stratégie globale, utilisez l’applet de commande suivante :

`Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false`
</br>
</br>

|Scénario|Étapes |
|---|---|
|Je veux tous les utilisateurs de votre société pour être en mesure de transcrire lors du passage d’enregistrement d’une réunion |<ol><li>Confirmer Global CsTeamsMeetingPolicy a AllowTranscription = True <li>Tous les utilisateurs ont le csTeamsMeetingPolicy globale ou une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = True. </ol>|
|Je souhaite la majorité des utilisateurs puissent transcrire les enregistrements de réunions, mais désactiver des utilisateurs spécifiques qui ne sont pas autorisés à transcrire |<ol><li>Confirmer Global CsTeamsMeetingPolicy a AllowTranscription = True <li>Majorité des utilisateurs ont le Global CsTeamsMeetingPolicy ou une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = True <li>Tous les autres utilisateurs ont été accordées à l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = False </ol>|
|Je veux transcription de l’enregistrement à 100 % désactivé |<ol><li>Confirmer Global CsTeamsMeetingPolicy a AllowTranscription = False <li>Tous les utilisateurs ont été accordées le Global CsTeamsMeetingPolicy ou l’une des stratégies CsTeamsMeetingPolicy avec AllowTranscription = False </ol>|
|Je veux transcription à désactivé pour la majorité des utilisateurs, mais activer des utilisateurs spécifiques qui sont autorisés à transcrire |<ol><li>Confirmer Global CsTeamsMeetingPolicy a AllowCloudRecording = False <li>La majorité des utilisateurs ont été accordées le Global CsTeamsMeetingPolicy ou une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = False <li>Tous les autres utilisateurs ont été accordées à l’une des stratégies CsTeamsMeetingPolicy avec AllowCloudRecording = True </ol>|
|||

### <a name="planning-for-storage"></a>Planification du stockage

La taille d’un enregistrement de 1 heure est 400 Mo. Assurez-vous que vous comprenez la capacité requise pour les fichiers enregistrés et disposez de suffisamment de stockage dans Microsoft Stream.  Lecture de [cet article](https://docs.microsoft.com/stream/license-overview) pour comprendre le stockage de base inclus dans l’abonnement et sur l’achat de stockage supplémentaire.

## <a name="manage-meeting-recordings"></a>Gérer les enregistrements de réunions
Les enregistrements de réunion sont considérées comme appartenant à un client de contenu. Si le propriétaire de l’enregistrement quitte l’entreprise, l’administrateur peut ouvrir le URL d’enregistrement de la vidéo dans Microsoft Stream en mode administrateur. L’administrateur peut supprimer l’enregistrement, mettre à jour les métadonnées de l’enregistrement ou modifier les autorisations pour l’enregistrement vidéo. Pour plus d’informations sur les [fonctionnalités d’administration dans le flux](https://docs.microsoft.com/stream/manage-content-permissions).

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Conformité et eDiscovery pour les enregistrements de réunions
Les enregistrements de réunion sont stockés dans Microsoft Stream, Office 365 couche-c conforme. Pour prendre en charge les demandes d’e-Discovery pour les administrateurs de conformité qui souhaitent enregistrements de réunion ou un appel de Microsoft Streams, le message terminé d’enregistrement est disponible dans la fonctionnalité de recherche de contenu de la conformité pour Microsoft Teams. Les administrateurs de conformité peuvent rechercher le mot clé « enregistrer » dans la ligne d’objet de l’élément dans l’aperçu de recherche de contenu de la conformité et découvrir la réunion et les enregistrements des appels dans l’organisation. Il est indispensable pour pouvoir afficher tous les enregistrements qu’ils devront être définis dans Microsoft Stream avec un accès d’administration. Pour plus d’informations sur [l’affectation d’autorisations d’administration dans le flux](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
- [Configurer votre ordinateur pour Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525038)

