---
title: Présentation des équipes et des canaux dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
ms.reviewer: ''
manager: serdars
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
description: Découvrez la variété d'équipes, de canaux et d'applications disponibles pour des exigences très variées, telles que les opérations financières, la planification d'événements, les ventes, etc.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.teamschannel.overview
- ms.teamsadmincenter.teamssettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04a7366c9b4f09fa9c06b7d7f4cd40a24892f840
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2019
ms.locfileid: "35804675"
---
> [!NOTE]
> Passez en revue les informations suivantes pour mieux comprendre la conversation, les équipes, les canaux et les applications dans Teams. Ensuite, accédez à la fenêtre de [conversation, d’équipes, de canaux & les applications dans teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) pour parcourir la liste des décisions importantes pour le déploiement d’équipes.

<a name="overview-of-teams-and-channels-in-microsoft-teams"></a>Présentation des équipes et des canaux dans Microsoft Teams
=================================================

Commençons par nous pencher sur la façon dont Microsoft Teams permet aux équipes individuelles de s’auto-organiser et de collaborer dans différents scénarios d’entreprise.

- **Teams** regroupe des personnes, du contenu et des outils autour d'un projet ou d'une tâche spécifique au sein d'une organisation.

    - Teams peut être créé pour être privé, accessible uniquement aux utilisateurs invités.

    - Teams peut également être créé pour être publique et ouvert à tous les utilisateurs d’une organisation (jusqu'à 5000 membres).
    
    Une équipe est conçue pour réunir un groupe de personnes qui travaillent étroitement ensemble pour atteindre leurs objectifs. Les équipes peuvent être dynamiques pour un travail de projet (lancer un produit ou créer un centre de crise numérique par exemple) et être courantes, pour refléter la structure interne de votre organisation (services et bureaux par exemple). Les conversations, les fichiers et les notes ne sont visibles que pour les membres de l’équipe.

- Les **canaux** sont des sections dédiées dans une équipe pour stocker des conversations organisées par sujets, projets et disciplines spécifiques ; à votre équipe de décider ! Les fichiers que vous partagez dans un canal (sous l’onglet fichiers) sont stockés dans SharePoint. Pour en savoir plus, voir [comment SharePoint Online et OneDrive entreprise interagissent avec teams](SharePoint-OneDrive-interact.md).

    - Les canaux d’équipe sont des lieux où tous les membres de l’équipe peuvent avoir des conversations. Les discussions privées ne sont visibles que par les membres de la discussion (et les fichiers que vous partagez dans une discussion sont stockés dans OneDrive entreprise). 

    - Les canaux sont particulièrement utiles lorsque des applications incluant des onglets, des connecteurs et des robots y sont ajoutés, qui apportent une valeur ajoutée pour les membres de l’équipe. Pour en savoir plus, reportez-vous à la rubrique [applications, robots, & connecteurs dans teams](deploy-apps-microsoft-teams-landing-page.md).

Affichez cette courte vidéo pour en savoir plus sur les meilleures pratiques pour la création d’équipes et canaux.

   > [!VIDEO https://www.youtube.com/embed/hjJWtoaRJeE]

<a name="membership-roles-and-settings"></a>Appartenance, rôles et paramètres
------------------------------

**Appartenance à une équipe**

Lorsque Microsoft teams est activé pour l’ensemble de votre organisation, les propriétaires d’équipe désignés peuvent inviter les employés avec lesquels ils travaillent pour rejoindre leur équipe. Microsoft Teams permet aux propriétaires d’équipe d’ajouter facilement des personnes de l’organisation selon leur nom. En fonction des paramètres de votre organisation, des invités qui sont membres d’une équipe mais externes à votre organisation peuvent également être ajoutés à vos équipes. Reportez-vous à la rubrique [Accès invité dans Microsoft Teams](guest-access.md) pour plus d’informations. 

Les propriétaires d’équipe peuvent également créer une équipe basée sur un groupe Office 365 existant. Les modifications apportées au groupe seront synchronisées automatiquement avec Microsoft Teams. Créer une équipe basée sur un groupe Office 365 existant simplifie non seulement le processus d’invitation et de gestion des membres, mais synchronise également les fichiers du groupe au sein de Microsoft Teams.

**Rôles d’équipe**

Il existe deux rôles principaux dans Microsoft teams: 

- **Propriétaire** de l’équipe-personne qui crée l’équipe. Les propriétaires d’équipe peuvent définir n’importe quel membre de leur équipe comme copropriétaire lorsqu'ils 'l’invitent à rejoindre l'équipe ou à n’importe quel moment une fois qu'il a rejoint l’équipe. La présence de plusieurs propriétaires d’équipes vous permet de partager les responsabilités liées à la gestion des paramètres et de l’appartenance, y compris aux invitations.
- **Membres** d’une équipe: les personnes que les propriétaires peuvent inviter à rejoindre leur équipe.

De plus, si la modération est configurée, les propriétaires d’équipe et les membres peuvent disposer de capacités de modérateur pour un canal. Les modérateurs peuvent commencer de nouvelles publications dans le canal et contrôler si les membres d’une équipe peuvent répondre à des messages de canal existants. Les propriétaires d’équipe peuvent affecter des modérateurs au sein d’un canal. (Les propriétaires d’équipe disposent de fonctionnalités de modérateur par défaut). Les modérateurs au sein d’un canal peuvent ajouter ou supprimer d’autres modérateurs dans ce canal. Pour plus d’informations, reportez-vous à [configurer et gérer la modération de canal dans Microsoft teams](manage-channel-moderation-in-teams.md).

**Paramètres d’équipe** 

Les propriétaires d’équipe peuvent gérer les paramètres à l’échelle de l’équipe directement dans Microsoft Teams. Les paramètres incluent la possibilité d’ajouter une image de l’équipe, de définir les autorisations entre les membres pour créer des canaux, ajouter des onglets et connecteurs, @mentionner toute l’équipe ou le canal et l’utilisation de fichiers GIF, autocollants et mèmes. 

Prenez trois minutes à examiner cette vidéo guide de déplacement pour les propriétaires d’équipe : 

   > [!VIDEO https://www.youtube.com/embed/7XcDSuw6NR4]

Si vous êtes un administrateur de Microsoft Teams dans Office 365, vous avez accès aux paramètres à l’échelle du système dans le centre d’administration Microsoft Teams. Ces paramètres peuvent avoir une incidence sur les options et valeurs par défaut que les propriétaires d'équipe voient sous les paramètres de l’équipe. Par exemple, vous pouvez activer un canal par défaut (général) pour les annonces, les discussions et les ressources à l’échelle de l’équipe, qui s’afficheront dans toutes les équipes.

Par défaut, tous les utilisateurs sont autorisés à créer une équipe dans Microsoft Teams. (Pour modifier ces autorisations, consultez la rubrique [Attribuer des rôles et des autorisations dans Teams](assign-roles-permissions.md).) Les utilisateurs d’un groupe Office 365 existant peuvent également améliorer leurs autorisations grâce aux fonctionnalités d’équipe.

L’une des principales activités de planification initiale pour engager des utilisateurs auprès de Microsoft teams est d’aider les utilisateurs à réfléchir et à comprendre la façon dont les équipes peuvent améliorer la collaboration au quotidien. Discutez avec les utilisateurs et aidez-les à sélectionner les scénarios d’entreprise dans lesquels ils collaborent actuellement de manière fragmentée. Rassemblez-les dans un canal grâce aux onglets appropriés qui vous aideront à accomplir leurs tâches. Un des cas d’utilisation les plus puissants de Teams est un processus inter-organisationnel. 

<a name="example-teams"></a>Exemple Teams
--------------

Vous trouverez ci-dessous un exemple de la façon dont les différents types d’utilisateur peuvent aborder la configuration de leurs équipes, canaux et applications (onglets/connecteurs/robots). Il est possible que cela soit utile pour lancer une conversation sur Microsoft teams avec votre communauté d’utilisateurs. Dans le cadre de la mise en œuvre de Microsoft teams au sein de votre organisation, n’oubliez pas que vous pouvez fournir des recommandations sur la structure de ses équipes. Toutefois, les utilisateurs contrôlent la manière dont ils peuvent s’organiser eux-mêmes. Voici quelques exemples pour aider les équipes à réfléchir aux possibilités.

Microsoft teams est idéal pour fractionner les silos d’organisations et promouvoir les équipes de grande fonction, de sorte que vos utilisateurs pensent aux équipes fonctionnelles plutôt qu’aux limites de l’organisation.

|Types d'équipes  |Canaux potentiels  |Applications (Onglets ![Icône représentant un dossier avec un onglet](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image2.png)/Connecteurs ![Icône de représentation de blocs de connexion](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image3.png)/Bots ![Icône représentant un petit robot](media/Overview_of_teams_and_channels_in_Microsoft_Teams_image4.png))  |
|---------|---------|---------|
|Ventes     |Réunion annuelles sur les ventes<br></br> Évaluation trimestrielle des activités<br></br> Évaluation mensuelle de la pipeline des ventes<br></br> Registre des ventes |Power BI<br></br>Trello<br></br>CRM<br></br>Bot récapitulatif         |
|Relations publiques     |Communiqués de presse<br></br>Actualité et mises à jour<br></br>Vérification des faits         |Flux RSS<br></br>Twitter         |
|Planification d'événements     |Marketing<br></br>Logistique et planification<br></br>Salle<br></br>Budget         |Twitter<br></br>Facebook<br></br>Planificateur<br></br>fichier PDF ;         |
|Marketing/Commercialisation   |Recherche de marché<br></br>Piliers de messagerie<br></br>Plan de communications<br></br>Nomenclature Marketing        |YouTube<br></br>Microsoft Stream<br></br>Twitter<br></br>MailChimp         |
|Opérations techniques    |Gestion des incidents<br></br>Planification d'itération<br></br>Éléments de travail<br></br>Infrastructure et opérations         |Services d'équipe<br></br>Jira<br></br>AzureBot         |
|Équipe de produit      |Stratégie<br></br>Marketing<br></br>Ventes<br></br>Opérations<br></br>Informations<br></br>Services et support technique         |Power BI<br></br>Services d'équipe         |
|Finances    |Exercice fiscal en cours<br></br>Planificiatin de l'excercice fiscal<br></br>Prévisions<br></br>Comptes débiteurs<br></br>Comptes payables         |Power BI<br></br>Google Analytics         |
|Logistique     |Opérations d'entrepôt<br></br>Maintenance des véhicules<br></br>Registre des conducteurs         |Service météo<br></br>Perturbations de déplacement / trafic<br></br>Planificateur<br></br>Tubot<br></br>UPS Bot         |
|HR     |Gestion des compétences<br></br>Recrutement<br></br>Planification de l'évaluation des performances<br></br>Éthique         |Outil de RH<br></br>Sites d'offres d'emploi externes<br></br>Growbot         |
|Inter-organisationnel <br></br>Équipe virtuelle |Stratégie<br></br>Développement des effectifs<br></br>Concurrence et recherche         |Power BI<br></br>Microsoft Stream         |

Il est possible de créer des équipes qui s’alignent sur la structure de l’organisation. C’est le meilleur moyen pour les leaders qui souhaitent faire des bonnes moeurs, d’apporter des commentaires spécifiques à une équipe, de clarifier les processus d’intégration d’employés, de discuter des plans de main-d’œuvre et de rendre le niveau de visibilité accru.  

![Diagramme hiérarchique des équipes et des canaux organisés dans Microsoft Teams.](media/overview-of-teams-and-channels-image1.png)

## <a name="org-wide-teams"></a>Équipes à l’échelle de l’organisation

Si votre organisation a pas plus de 5 000 utilisateurs, vous pouvez créer une équipe de l’échelle de l’organisation. Les équipes à l’échelle de l’organisation fournissent un moyen automatique pour tous les membres d’une organisation de faire partie d’une équipe unique pour la collaboration. Pour plus d’informations, notamment les meilleures pratiques pour créer et gérer une équipe l’échelle de l’organisation, voir [Créer une équipe de l’échelle de l’organisation dans Microsoft Teams](create-an-org-wide-team.md).
