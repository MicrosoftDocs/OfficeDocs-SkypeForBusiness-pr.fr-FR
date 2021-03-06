---
title: Utiliser des modèles Teams dans le Centre d’administration
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser les modèles Teams pour créer des espaces de collaboration avec des canaux pour différentes rubriques à l’aide de modèles préinstallés.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 62bee9c494cc6155a84b30d75ae71528656133be
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508007"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>Utiliser les modèles Teams dans le Centre d’administration

**La possibilité de créer des modèles personnalisés n’est pas encore prise en charge pour les clients EDU.**

> [!NOTE]
> Pour le moment, les modèles Teams ne supportent pas la création de canaux privés. La création de canaux privés n’est pas incluse dans les définitions de modèle.

Les modèles Teams sont des définitions pré-intégrées de la structure d’une équipe conçue autour d’un besoin ou d’un projet d’entreprise. Utilisez des modèles pré-intégrés ou créez votre propre modèle. Les modèles Teams vous permettent de créer rapidement des espaces de collaboration enrichis avec des canaux pour différents sujets et des applications de préinstallation qui permettent d’obtenir du contenu et des services essentiels. Les modèles Teams fournissent une structure d’équipe prédéfinée qui peut vous aider à créer facilement des équipes cohérentes au sein de votre organisation. Vous pouvez actuellement créer une équipe à partir d’un modèle dans Teams ou à l’aide [de Microsoft Graph.](get-started-with-teams-templates.md)

Cet article décrit les propriétés qui peuvent être définies dans les modèles, les types de modèles de base et la façon dont vous pouvez utiliser quelques exemples de demandes pour créer une équipe à partir d’un modèle.

Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation

## <a name="teams-template-capabilities"></a>Fonctionnalités des modèles Teams

La plupart des propriétés d’une équipe sont incluses et prise en charge par les modèles. Certaines propriétés et fonctionnalités ne sont actuellement pas pris en charge. Le tableau suivant récapitule rapidement ce qui est inclus et ce qui n’est pas inclus dans les modèles Teams.

| **Propriétés d’équipe pris en charge par les modèles Teams** | **Propriétés d’équipe non encore pris en charge par les modèles Teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Type de modèle de base | Appartenance à une équipe |
| Nom de l’équipe | Image de l’équipe |
| Description de l’équipe | Paramètres du canal |
| Visibilité de l’équipe (publique ou privée) | Connecteurs |
| Paramètres de l’équipe (par exemple, membre, invité, @mentions) | Fichiers et contenu |
| Canal Des masons automatiques | |
| Application installée | |
| Onglets épinglés | |

> [!NOTE]
> Nous ajouterons d’autres fonctionnalités de modèle dans les prochaines version de Microsoft Teams. Vérifiez donc si vous avez besoin des informations les plus à jour sur les propriétés prise en charge.

## <a name="what-are-base-template-types"></a>Présentation des types de modèles de base

Les types de modèles de base sont des modèles spéciaux que Microsoft a créés pour des secteurs spécifiques. Ces modèles de base contiennent souvent des applications exclusives qui ne sont pas disponibles dans le magasin d’applications.

Une fois le type de modèle de base défini, vous pouvez étendre ou remplacer ces modèles spéciaux par des propriétés supplémentaires que vous souhaitez spécifier. Certains types de modèles de base contiennent des propriétés qui ne peuvent pas être surchargées.

> [!NOTE]
> Les modèles de base prédéfinés fournis dans Microsoft Teams peuvent être dupliqués, mais pas modifiés.

| Type de modèle de base | baseTemplateId | Propriétés de ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adopter Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Coin Champions</li> <li>Formulaires d’équipe</li></ul> Applications : <ul><li>Wiki</li>  <li>Calendrier</li> |
| Gérer un projet |`com.microsoft.teams.template.ManageAProject`| Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Ressources</li> <li>Planification</li></ul> Applications :<ul><li>Wiki</li><li>OneNote</li><li>Planificateur</li><li>Listes</li>  </ul> |
| Gérer un événement|`com.microsoft.teams.template.ManageAnEvent` | Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Budget</li> <li>Contenu</li><li>Logistique</li> <li>Planification</li> <li> Marketing et relations publiques</li></ul> Applications :<ul><li>Wiki</li><li>Site web</li> <li>YouTube</li> <li>Planificateur</li> <li>OneNote</li></ul> |
|Intégrer des employés|`com.microsoft.teams.template.OnboardEmployees` | Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Conversation employé</li> <li>Formation</li></ul>Applications :<ul><li>Wiki</li><li>Communautés</li><li>Planificateur</li></ul>|
|Organiser le service d’aide| `com.microsoft.teams.template.OrganizeHelpDesk`|Canaux :<ul><li>Général</li><li>Annonces</li><li>FAQ</li></ul>Applications :<ul><li>Wiki</li><li>OneNote</li><li>Planificateur </li><li>Compliment</li></ul> |
| Collaborer sur les soins des patients| `healthcareWard`| Canaux :<ul><li>Général</li><li>Annonces</li><li>Bldles</li><li>Arrondit</li><li>Personnel</li><li>Formation</li></ul> Applications : <ul><li>Wiki</li><li>Listes  </li></ul>|
| Collaborer sur la crise ou l’événement global |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canaux : <ul><li>Général<li>Annonces</li><li>Actualités mondiales</li><li>Continuité de l’activité</li><li>Travail à distance</li><li>Communications internes</li><li>Comms externes</li><li>Demande d’approbation</li><li>Réclamations des clients</li><li>Kudos</li><li>Mise à jour pour la direction</li></ul>Applications : <ul><li>Compliment</li><li>Wiki</li><li>Site web</li><li>Planificateur</li></ul>|
|Collaborer au sein d’une banque| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canaux : <ul><li>Général<li>Annonces</li><li>Bldles</li><li>Réunions avec les clients</li><li>Demande d’approbation </li><li>Desso</li><li>Développement de compétences</li><li>Traitement des emprunts</li><li>Réclamations des clients</li><li>Kudos</li><li>Amusant</li><li>Conformité</li></ul>Applications :<ul><li>Compliment </li></ul>|
|Coordonner la réponse à un incident| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canaux : <ul><li>Général<li>Annonces</li><li>Logistique</li><li>Planification</li><li>Récupération</li><li>Urgent</li></ul> Applications : <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planificateur</li></ul>|
|Hôpital| `healthcareHospital` |Canaux : <ul><li>Général</li><li>Annonces</li><li>Conformité</li><li>Adess</li><li>Ressources humaines</li><li>Desse</li></ul> Applications : <ul><li>Wiki</li><li>Listes  </li></ul>|
|Organiser un magasin| `retailStore` |Canaux : <ul><li>Général<li>Transfert des shifts</li><li>Formation</li></ul> Applications : <ul><li>Wiki</li><li>Planificateur</li></ul>|
|Qualité et sécurité |`com.microsoft.teams.template.QualitySafety`|Canaux : <ul><li>Général<li>Annonces</li><li>Ligne 1</li><li>Ligne 2</li><li>Ligne 3</li><li>Sécurité</li><li>Formation</li><li>Maintenance</li><li>Amusant</li></ul> Applications : <ul><li>Wiki</li><li>Planificateur</li></ul>|
|Vente au détail - Collaboration avec les responsables| `retailManagerCollaboration` |Canaux : <ul><li>Général<li>Opérations</li><li>Formation</li></ul> Applications : <ul><li>Wiki</li><li>Planificateur</li></ul>|
||||

Pour plus d’informations sur les catégories de modèles, voir les catégories suivantes :

- [Modèles financiers](financial-teams-templates-in-the-admin-console.md)
- [Modèles généraux](general-teams-templates-in-the-admin-console.md)
- [Modèles pour le gouvernement](government-teams-templates-in-the-admin-console.md)
- [Modèles médicaux](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Modèles de fabrication](manufacturing-teams-templates-in-the-admin-console.md)
- [Modèles commerciaux](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Limites de taille des modèles

Les modèles sont limités à un nombre spécifique de canaux, d’onglets et d’applications.

 > [!Note]
 > Vous pouvez ajouter des canaux, des onglets et des applications à l’équipe après sa création à partir d’un modèle.

|Fonctionnalité | Limite|
|-|-|
|Canaux par modèle | 15 |
|Onglets par canal dans un modèle | 20 |
|Applications par modèle | 50|
|||

Pour [plus d’informations, voir Limites](limits-specifications-teams.md) et spécifications de Teams.

## <a name="related-topics"></a>Sujets associés

- [Créer un modèle d’équipe personnalisé](create-a-team-template.md)
- [Créer un modèle d’équipe à partir d’un modèle d’équipe existant](create-template-from-existing-template.md)
- [Créer un modèle à partir d’une équipe existante](create-template-from-existing-team.md)
