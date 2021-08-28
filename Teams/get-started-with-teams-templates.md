---
title: Utiliser les modèles d’équipe à l’aide de Microsoft Graph
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser des modèles d’équipe dans Microsoft Graph pour créer des espaces de collaboration avec des canaux pour différentes rubriques et des applications de préinstallation pour fournir du contenu et des services.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8005d17debce7a0187ac8411a8054071c754566
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599739"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Utiliser les modèles d’équipe à l’aide de Microsoft Graph

> [!NOTE]
> Pour le moment, les modèles d’équipe ne prisent pas en charge la création de canaux privés. La création de canaux privés n’est pas incluse dans les définitions de modèle.

Les modèles d’équipe sont des définitions pré-pré-précodentes de la structure d’une équipe conçue autour d’un besoin ou d’un projet d’entreprise. Vous pouvez [créer votre propre modèle dans la console d’administration.](get-started-with-teams-templates-in-the-admin-console.md) Avec Microsoft Graph, vous utilisez les modèles pré-intégrés. Vous pouvez utiliser les modèles d’équipe pour créer rapidement des espaces de collaboration enrichis avec des canaux pour différents sujets et des applications de préinstallation pour télécharger du contenu et des services essentiels pour l’entreprise. Les modèles d’équipe fournissent une structure d’équipe prédéfinée qui peut vous aider à créer facilement des équipes cohérentes au sein de votre organisation.

Cet article explique les propriétés qui peuvent être définies dans les modèles, ce que sont les types de modèles de base et comment utiliser quelques exemples de demandes pour créer une équipe à partir d’un modèle.

Cet article est pour vous si vous êtes :

- Responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation<br>
- Développeur désireux de créer par programme une équipe avec des canaux et applications prédéfinfinés

## <a name="team-template-capabilities"></a>Fonctionnalités des modèles d’équipe

La plupart des propriétés d’une équipe sont incluses et prise en charge par les modèles. Certaines propriétés et fonctionnalités ne sont actuellement pas pris en charge. Le tableau suivant récapitule rapidement ce qui est inclus et ce qui n’est pas inclus dans les modèles d’équipe.

| **Propriétés d’équipe pris en charge par les modèles d’équipe** | **Propriétés de l’équipe non encore pris en charge par les modèles d’équipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Type de modèle de base | Appartenance à une équipe |
| Nom de l’équipe | Image de l’équipe |
| Description de l’équipe | Paramètres du canal |
| Visibilité de l’équipe (publique ou privée) | Connecteurs |
| Paramètres de l’équipe (par exemple, membre, invité, @mentions) | Fichiers et contenu |
| Canal favoris automatique | |
| Application installée | |
| Onglets épinglés | |

> [!NOTE]
> Nous ajouterons d’autres fonctionnalités de modèle dans les prochaines version de Microsoft Teams. Vérifiez donc que vous avez besoin des informations les plus à jour sur les propriétés prise en charge.

## <a name="what-are-base-template-types"></a>Présentation des types de modèles de base

Les types de modèles de base sont des modèles spéciaux que Microsoft a créés pour des secteurs spécifiques. Ces modèles de base contiennent souvent des applications exclusives qui ne sont pas disponibles dans le Store. De plus, les modèles de base contiennent souvent des propriétés d’équipe qui ne sont pas encore pris en charge individuellement dans les modèles d’équipe. Découvrez comment utiliser les [modèles d’équipe dans Microsoft Graph.](get-started-with-teams-templates.md)

Une fois le type de modèle de base défini, vous pouvez étendre ou remplacer ces modèles spéciaux par des propriétés supplémentaires que vous souhaitez spécifier. Certains types de modèles de base contiennent des propriétés qui ne peuvent pas être surchargées.

Par défaut, le modèle de base est **standard,** qui ne contient pas d’autres applications propriétaires ou propriétés spéciales. Vous trouverez ci-dessous la liste actuelle des types de modèles de base disponibles.

| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | Aucune application et propriété supplémentaire |
| Éducation -<br>Équipe de classe | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | Applications :<ul><li>OneNote Bloc-notes Pour la classe (épinglé à **l’onglet** Général) </li><li>Application Devoirs (épinglée à **l’onglet** Général)</li></ul> Propriétés de l’équipe :<ul><li>Visibilité de l’équipe définie **sur HiddenMembership** (ne peut pas être masquée)</li></ul> |
| Éducation -<br>Équipe de membres du personnel | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | Applications :<ul><li>OneNote Bloc-notes pour le personnel enseignant (épinglé à **l’onglet** Général)</li></ul> |
|Éducation -<br>Équipe PLC |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Applications :<ul><li>OneNote Bloc-notes PLC (épinglé à **l’onglet** Général)</ul></li>|
| Commerce -<br>Magasin | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailStore')` | Canaux :<ul><li>Transfert de shift</li><li>Apprentissage</li></ul>Propriétés de l’équipe<ul><li>Visibilité de l’équipe définie sur Public</li></ul>Autorisations de membre<ul><li>Empêcher les membres de créer, mettre à jour ou supprimer des canaux</li><li>Empêcher les membres d’ajouter ou de supprimer des applications</li><li>Empêcher les membres de créer, mettre à jour ou supprimer des connecteurs</li></ul> |
| Commerce -<br>Collaboration avec les responsables | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailManagerCollaboration')` | Canaux :<ul><li>Apprentissage</li><li>Opérations</li></ul>Propriétés de l’équipe :<ul><li>Visibilité de l’équipe définie sur Privé</li></ul>Autorisations des membres :<ul><li>Empêcher les membres de créer, mettre à jour ou supprimer des canaux</li><li>Empêcher les membres d’ajouter ou de supprimer des applications</li><li>Empêcher les membres de créer, mettre à jour ou supprimer des connecteurs</li></ul>|
| Soins de santé -<br>Desso |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareWard')` |Canaux : <ul><li>Annonces\*</li><li>Blotti\*</li><li>Rondes</li><li>Personnel\*</li><li>Formation\*</li></ul>\*Canaux ajoutés automatiquement aux favoris |
|Soins de santé -<br>Hôpital | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareHospital')` |Canaux :<ul><li>Annonces\*</li><li>Conformité\*</li><li>Consignataires</li><li>Ressources humaines</li></li><li>Pharmacie</li></ul>\*Canal avec favoris automatiques|
|||


Utilisez les modèles suivants pour créer des équipes à la fois dans le client Teams et dans Microsoft Graph.


| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adopter une Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Coin Champions</li> <li>Formulaires d’équipe</li></ul> Applications : <ul><li>Wiki</li>  <li>Calendrier</li> |
| Gérer un projet |`com.microsoft.teams.template.`<br>`ManageAProject`| Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Ressources</li> <li>Planification</li></ul> Applications :<ul><li>Wiki</li><li>OneNote</li></ul> |
| Gérer un événement|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Budget</li> <li>Contenu</li><li>Logistique</li> <li>Planification</li> <li> Marketing et relations publiques</li></ul> Applications :<ul><li>Wiki</li><li>Site web</li> <li>YouTube</li> <li>Planificateur</li> <li>OneNote</li></ul> |
|Intégrer des employés|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Conversation employé</li> <li>Formation</li></ul>Applications :<ul><li>Wiki</li><li>Communautés</li></ul>|
|Organiser le service d’aide| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Canaux :<ul><li>Général</li><li>Annonces</li><li>FAQ</li></ul>Applications :<ul><li>Wiki</li><li>OneNote</li></ul> |
| Collaborer sur les soins aux patients| `healthcareWard `| Canaux :<ul><li>Général</li><li>Annonces</li><li>Blotti</li><li>Rondes</li><li>Personnel</li><li>Formation</li></ul> Applications : <ul><li>Wiki</li>|
| Collaborer sur la crise ou l’événement global |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Canaux : <ul><li>Général<li>Annonces</li><li>Actualités mondiales</li><li>Continuité de l’activité</li><li>Travail à distance</li><li>Communications internes</li><li>Comms externe</li><li>Réclamations des clients</li><li>Kudos</li><li>Mise à jour pour la direction</li></ul>Applications : <ul><li>Compliment</li><li>Wiki</li><li>Site web</li></ul>|
|Collaborer au sein d’une banque| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Canaux : <ul><li>Général<li>Annonces</li><li>Blotti</li><li>Réunions avec les clients</li><li>Desso</li><li>Développement de compétences</li><li>Traitement des emprunts</li><li>Réclamations des clients</li><li>Kudos</li><li>Amusant</li><li>Conformité</li></ul>|
|Coordonner la réponse à un incident| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Canaux : <ul><li>Général<li>Annonces</li><li>Logistique</li><li>Planification</li><li>Récupération</li><li>Urgent</li></ul> Applications : <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planificateur</li></ul>|
|Hôpital| `healthcareHospita`l |Canaux : <ul><li>Général<li>Annonces</li><li>Conformité</li><li>Consignataires</li><li>Ressources humaines</li><li>Pharmacie</li></ul> Applications : <ul><li>Wiki</li></ul>|
|Organiser un magasin| `retailStore` |Canaux : <ul><li>Général<li>Transfert de shift</li><li>Apprentissage</li></ul> Applications : <ul><li>Wiki</li></ul>|
|Qualité et sécurité |`com.microsoft.teams.`<br>`template.QualitySafety`|Canaux : <ul><li>Général<li>Annonces</li><li>Ligne 1</li><li>Ligne 2</li><li>Ligne 3</li><li>Sécurité</li><li>Formation</li><li>Maintenance</li><li>Amusant</li></ul> Applications : <ul><li>Wiki</li></ul>|
|Vente au détail : collaboration entre responsables| `retailManagerCollaboration` |Canaux : <ul><li>Général<li>Opérations</li><li>Apprentissage</li></ul> Applications : <ul><li>Wiki</li></ul>|
||||

Pour [plus d’informations, voir Commencer à utiliser les modèles d’équipe](get-started-with-teams-templates-in-the-admin-console.md) dans le Centre d’administration.

## <a name="related-topics"></a>Rubriques connexes

- [Utiliser des modèles d’équipe dans la console d’administration](get-started-with-teams-templates-in-the-admin-console.md)
- [Créer une équipe](/graph/api/team-post?view=graph-rest-beta) (en prévisualisation)
- [Nouvelle équipe](/powershell/module/teams/New-Team?view=teams-ps)
- [Formation à Microsoft Teams pour les administrateurs](itadmin-readiness.md)
