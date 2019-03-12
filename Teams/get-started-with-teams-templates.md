---
title: Prise en main des modèles Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Découvrez comment utiliser les modèles d’équipe pour créer une équipe avec des canaux prédéfinis.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: f16b851641de64813212bf67a83dbf9d7a05c043
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2019
ms.locfileid: "30541639"
---
# <a name="get-started-with-teams-templates"></a>Prise en main des modèles Teams 

Définitions de structure d’une équipe conçu autour d’un projet ou les besoins de l’entreprise, les modèles d’équipe sont prédéfinies. Vous pouvez utiliser les modèles d’équipe pour créer rapidement des espaces de collaboration riche avec des canaux pour les différentes rubriques et préinstaller les applications pour extraire des services et contenu critique. Les modèles d’équipe fournissent une structure de l’équipe prédéfinies qui peut vous aider à créer facilement des équipes cohérentes au sein de votre organisation. 

Dans cet article, nous expliquerons les propriétés qui peuvent être définies dans des modèles, le modèle de base sont de types, et comment vous pouvez utiliser quelques exemples de demandes pour créer une équipe à partir d’un modèle.
 
Cet article est pour vous si vous êtes :

- Responsable de la planification, le déploiement et la gestion de plusieurs équipes au sein de votre organisation.<br>
- Un pour les développeurs souhaitant créer par programme une équipe avec les applications et les canaux prédéfinis 

## <a name="teams-template-capabilities"></a>Fonctionnalités de modèle d’équipes

La plupart des propriétés dans une équipe sont inclus et pris en charge par les modèles. Mais il existe quelques propriétés et les fonctionnalités qui ne sont pas actuellement pris en charge. Le tableau suivant fournit un résumé rapide de contenu, et ce qui n’est pas inclus dans les modèles d’équipe.

| **Propriétés de l’équipe pris en charge par les modèles d’équipe** | **Propriétés de l’équipe n’est pas encore pris en charge par les modèles d’équipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Type de modèle de base | Appartenance de l’équipe |
| Nom de l'équipe | Image de l’équipe |
| Description de l’équipe | Paramètres de canal |
| Visibilité de l’équipe (publique ou privée) | Connecteurs |
| Paramètres d’équipe (par exemple, membre, invité, @ mentions) | Fichiers et contenu |
| Canal automatique-favoris | |
| Application installée | |
| Onglets affichés | | 

> [!NOTE]
> Nous allons ajouter davantage de fonctionnalités de modèle dans les versions futures de Microsoft Teams, donc vérifier les informations les plus récentes sur les propriétés prises en charge.

## <a name="what-are-base-template-types"></a>Quels sont les types de modèle de base ?

Types de modèle de base des modèles spéciales créé par Microsoft pour industries spécifiques. Ces modèles de base contiennent souvent des applications qui ne sont pas disponibles dans les propriétés du magasin et l’équipe pas encore pris en charge individuellement dans les modèles d’équipe.

Une fois qu’un type de modèle de base est défini, vous pouvez étendre ou remplacer ces modèles spéciaux avec les propriétés supplémentaires que vous souhaitez spécifier. Mais certains types de modèle de base contiennent des propriétés qui ne peut pas être remplacées. 

Par défaut, le modèle de base est défini à **Standard** qui ne contient pas les applications propriétaires supplémentaires ou des propriétés spéciales. Voici la liste actuelle des types de modèle de base disponibles.

| Type de modèle de base | baseTemplateId | Propriétés liées à ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | Aucune propriétés et applications supplémentaires |
| Formation-<br>Équipe de classe | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | Applications :<ul><li>Bloc-notes OneNote de classe (épinglés sur l’onglet **Général** ) </li><li>Application des affectations (épinglée sur l’onglet **Général** )</li></ul> Propriétés de l’équipe :<ul><li>Visibilité de l’équipe définie sur **HiddenMembership** (ne peut pas être modifiée)</li></ul> |
| Formation-<br>Équipe du personnel | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | Applications :<ul><li>Bloc-notes OneNote de personnel (épinglés sur l’onglet **Général** )</li></ul> |
|Formation-<br>Équipe PLC |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | Applications :<ul><li>Bloc-notes OneNote de PLC (épinglés sur l’onglet **Général** )</ul></li>|
| Vente au détail-<br>boutique | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailStore` | Canaux :<ul><li>Remise MAJ</li><li>Formation</li></ul>Propriétés de l’équipe<ul><li>Visibilité de l’équipe définie sur Public</li></ul>Autorisations de membre<ul><li>Empêcher les membres de création, mise à jour ou suppression de chaînes</li><li>Empêcher les membres d’ajouter ou supprimer des applications</li><li>Empêcher les membres de création, mise à jour ou suppression des connecteurs</li></ul> |
| Vente au détail-<br>Collaboration de gestionnaire | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailManagerCollaboration` | Canaux :<ul><li>Remise MAJ</li><li>Formation</li></ul>Propriétés de l’équipe :<ul><li>Visibilité de l’équipe privée</li></ul>Autorisations de membre :<ul><li>Empêcher les membres de création, mise à jour ou suppression de chaînes</li><li>Empêcher les membres d’ajouter ou supprimer des applications</li><li>Empêcher les membres de création, mise à jour ou suppression des connecteurs</li></ul>|
| Prestataires-<br>Comté |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`healthcareWard` |Canaux : <ul><li>Annonces\*</li><li>Huddles\*</li><li>Arrondit</li><li>Personnel\*</li><li>Formation\*</li></ul>\*Canaux auto-favorited |
|Prestataires-<br>Hôpital | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`healthcareHospital` |Canaux :<ul><li>Annonces\*</li><li>Conformité\*</li><li>Garde</li><li>Ressources humaines</li></li><li>Pharmacie</li></ul>\*Canal auto-favorited|
|||

> [!NOTE]
> Nous allons ajouter d’autres modèle de base de types dans les futures versions de Microsoft Teams, afin de rechercher dans les informations les plus récentes sur les propriétés prises en charge.


## <a name="related-topics"></a>Rubriques connexes

- [Équipe de création](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en aperçu)
- [Nouvelle équipe](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Formation à Microsoft Teams pour les administrateurs](itadmin-readiness.md)
- [Prise en main des modèles Équipes de vente au détail](get-started-with-retail-teams-templates.md)
- [Commencer avec les modèles d’équipe de santé](healthcare/healthcare-templates.md)
