---
title: Présentation des équipes et des canaux dans Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: Découvrez la variété d'équipes, de canaux et d'applications disponibles pour des exigences très variées, telles que les opérations financières, la planification d'événements, les ventes, etc.
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.msteamsfiles
- ms.teamsadmincenter.dashboard.helparticle.teamsandchannels
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
- okr_smb
- intro-overview
- chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1cfbda5204e9294dd202440bbcd53b343cafe96f
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198706"
---
# <a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Présentation des équipes et des canaux dans Microsoft Teams

Commençons par nous pencher sur la façon dont Microsoft Teams permet aux équipes individuelles de s’auto-organiser et de collaborer dans différents scénarios d’entreprise :

- **Teams** regroupe des personnes, du contenu et des outils autour d'un projet ou d'une tâche spécifique au sein d'une organisation.

    - Teams peut être créé pour être privé, accessible uniquement aux utilisateurs invités.
    - Teams peut également être créé pour être publique et ouvert à tous les utilisateurs d’une organisation (jusqu'à 10 000 membres).
    
    Une équipe est conçue pour réunir un groupe de personnes qui travaillent en étroite collaboration pour atteindre leurs objectifs. Les équipes peuvent être dynamiques pour le travail basé sur un projet (par exemple, le lancement d’un produit, la création d’une salle d’expédition numérique), ainsi que l’exécution continue, pour refléter la structure interne de votre organisation (par exemple, les services et les emplacements de bureau). Les conversations, les fichiers et les notes ne sont visibles que pour les membres de l’équipe.

- Les **canaux** sont des sections dédiées dans une équipe pour stocker des conversations organisées par sujets, projets et disciplines spécifiques : à votre équipe de décider. Les fichiers que vous partagez dans un canal (sous l’onglet Fichiers) sont stockés dans SharePoint. Si vous souhaitez en savoir plus, consultez l’article [Interaction entre SharePoint Online et OneDrive Entreprise  et Teams](SharePoint-OneDrive-interact.md).

    - Les canaux sont les endroits où les conversations ont lieu et où le travail se fait réellement. Les canaux peuvent être ouverts à tous les membres de l’équipe (canaux standard), aux membres d’équipe sélectionnés ([canaux privés](private-channels.md)) ou aux personnes sélectionnées à l’intérieur et à l’extérieur de l’équipe ([canaux partagés](shared-channels.md)).
    - Les canaux sont particulièrement utiles lorsque des applications incluant des onglets, des connecteurs et des robots y sont ajoutés, qui apportent une valeur ajoutée pour les membres de l’équipe. Pour plus [d’informations, consultez Vue d’ensemble des applications Teams](deploy-apps-microsoft-teams-landing-page.md).
    
Pour obtenir de l’aide sur l’utilisation des équipes et des canaux, consultez l’article [Teams and les canaux](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499).

Pour plus d’informations sur les limites associées à l’utilisation de Teams, consultez [Limites et spécifications de Microsoft Teams](/microsoftteams/limits-specifications-teams) .

## <a name="membership-roles-and-settings"></a>Appartenance, rôles et paramètres

**Appartenance à une équipe**

Lorsque Microsoft Teams est activé pour l'ensemble de votre organisation, les propriétaires d'équipe désignés peuvent inviter les employés avec lesquels ils travaillent à rejoindre leur équipe. Teams permet aux propriétaires d’équipe d’ajouter facilement des personnes dans l’organisation en fonction de leur nom. Selon les paramètres de votre organisation, les personnes extérieures à votre organisation peuvent être ajoutées à vos équipes en tant qu’invités ou en tant que participants externes dans des canaux partagés. Reportez-vous à la rubrique [Accès invité dans Microsoft Teams](guest-access.md) pour plus d’informations. 

Les propriétaires d’équipe peuvent également créer une équipe basée sur un groupe Microsoft 365 existant. Toutes les modifications apportées à l’appartenance au groupe sont synchronisées automatiquement avec Teams.

**Rôles de l’équipe**

Il existe deux rôles principaux dans Microsoft Teams : 

- **Propriétaire d’équipe** : la personne qui crée l’équipe. Les propriétaires d’équipe peuvent faire de n’importe quel membre de leur équipe un copropriétaire lorsqu’ils les invitent à rejoindre l’équipe ou à tout moment après avoir rejoint l’équipe. Avoir plusieurs propriétaires pour une équipe vous permet de partager les responsabilités de gestion des paramètres et d’appartenance, y compris les invitations.
- **Membres d’une équipe** : les personnes que les propriétaires peuvent inviter à rejoindre leur équipe.

De plus, si la modération est mise en place, les propriétaires et les membres de l'équipe peuvent avoir les capacités de modérateur pour un canal. Les modérateurs peuvent commencer de nouvelles publications dans un canal et contrôler si les membres d’une équipe peuvent répondre aux messages existants. Les propriétaires d’équipe peuvent affecter des modérateurs au sein d’un canal. (Les propriétaires d'équipe ont des capacités de modérateur par défaut.) Les modérateurs d'un canal peuvent ajouter ou supprimer d'autres modérateurs de ce canal. Si vous souhaitez en savoir plus, consultez l’article [Configurer et gérer la modération des canaux dans Microsoft Teams](manage-channel-moderation-in-teams.md).

> [!NOTE]
> Lorsque vous ajoutez un propriétaire d’équipe, il est également ajouté en tant que membre, sauf lorsque l’équipe est créée dans le Centre d’administration Teams ou lorsqu’une équipe est ajoutée à un groupe Microsoft 365 nouveau ou existant.

**Paramètres de l’équipe** 

Team owners can manage team-wide settings directly in Teams. Settings include the ability to add a team picture, set permissions across team members for creating standard, private, and shared channels, adding tabs and connectors, @mentioning the entire team or channel, and the usage of GIFs, stickers, and memes.

Si vous êtes administrateur Teams dans Microsoft 365, vous avez accès aux paramètres à l’échelle du système dans le Centre d’administration Teams. Ces paramètres peuvent avoir une incidence sur les options et valeurs par défaut que les propriétaires d'équipe voient sous les paramètres de l’équipe. Par exemple, vous pouvez activer un canal « Général » par défaut, pour les annonces, discussions et ressources de l’équipe, qui s’afficheront pour toutes les équipes.

Par défaut, tous les utilisateurs sont autorisés à créer une équipe dans Microsoft Teams. Pour modifier cela, consultez [Attribuer des rôles et des autorisations dans Teams](assign-roles-permissions.md).

L’une des principales activités de planification pour impliquer les utilisateurs dans Teams consiste à aider les utilisateurs à réfléchir et à comprendre comment Teams peut améliorer la collaboration dans leur vie quotidienne. Discutez avec les utilisateurs et aidez-les à sélectionner les scénarios d’entreprise dans lesquels ils collaborent actuellement de manière fragmentée. Rassemblez-les dans un canal avec les onglets pertinents qui les aideront à effectuer leur travail. Un des cas d’utilisation les plus puissants de Teams est un processus inter-organisationnel.

> [!NOTE]
> Lorsque vous créez une équipe ou un canal privé ou partagé dans Teams, un site d’équipe dans SharePoint est automatiquement créé. Pour modifier la description ou la classification du site d’équipe, accédez aux [paramètres du canal correspondant dans Microsoft Teams](https://support.microsoft.com/office/bf39798f-90d2-44fb-a750-55fa05a56f1d).
>
> En savoir plus sur la gestion [sites d’équipes connectées Microsoft Teams](/SharePoint/teams-connected-sites).

Cette vidéo montre les étapes à suivre pour afficher et gérer l’appartenance à l’équipe d’un utilisateur.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE53x1L?autoplay=false]

## <a name="channel-feature-comparison"></a>Comparaison des fonctionnalités de canal

Le tableau suivant présente une comparaison des fonctionnalités Teams pour chaque type de canal.

|Fonctionnalités|Canal standard|Canal privé|Canal partagé|
|:-------|:---------------|:--------------|:-------------|
|Les personnes peuvent être ajoutées au canal sans les ajouter à l’équipe.|Non|Non|Oui|
|L’appartenance au canal peut être limitée à un sous-ensemble de l’équipe.|Non|Oui|Oui|
|Le canal peut être partagé directement avec d’autres équipes.|Non|Non|Oui|
|Le canal peut être partagé directement avec son équipe parente.|N/A|Non|Oui|
|Les invités peuvent participer au canal.|Oui|Oui|Non|
|Les participants externes (B2B Direct Connect) peuvent participer au canal.|Non|Non|Oui|
|Modération|Oui|Non|Non|
|Salles de réunion|Oui|Non|Non|
|Copier un lien vers le canal|Oui|Non|Non|
|Chaque canal a un site SharePoint dédié.|Non|Oui|Oui|
|Réunions planifiées|Oui|Non|Oui|
|Planificateur|Oui|Non|Non|
|Bots, connecteurs et extensions de messagerie|Oui|Non|Non|
|Pris en charge dans les équipes de classe|Oui|Oui|Non|
|Balises|Oui|Non|Non|
|Analyse|Oui|Oui|Non|

## <a name="org-wide-teams"></a>Équipes à l’échelle de l’organisation

Si votre organisation a pas plus de 10 000 utilisateurs, vous pouvez créer une équipe à l’échelle de l’organisation. Les équipes à l’échelle de l’organisation fournissent un moyen automatique pour tous les membres d’une organisation de faire partie d’une équipe unique pour la collaboration. Pour plus d’informations, notamment les meilleures pratiques pour créer et gérer une équipe l’échelle de l’organisation, voir [Créer une équipe de l’échelle de l’organisation dans Microsoft Teams](create-an-org-wide-team.md).

## <a name="next-steps"></a>Étapes suivantes

Lisez [Conversation, équipes, canaux et applications dans Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) pour parcourir la liste des décisions importantes pour votre déploiement Teams.
