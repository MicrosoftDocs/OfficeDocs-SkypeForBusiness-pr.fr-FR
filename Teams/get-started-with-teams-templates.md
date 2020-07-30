---
title: Découvrir les modèles teams à l’aide de Microsoft Graph
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser les modèles teams dans Microsoft Graph pour créer des espaces de collaboration avec des canaux pour différentes rubriques et des applications de préinstallation pour fournir du contenu et des services.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 18459b8350326d1af50fa8da4046b8987dd336dd
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506185"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Découvrir les modèles teams à l’aide de Microsoft Graph

> [!NOTE]
> Pour l’instant, les modèles Teams ne prennent pas en charge la création de canaux privés. La création d’un canal privé n’est pas incluse dans les définitions de modèle.

Les modèles teams sont des définitions prédéfinies d’une structure d’équipe conçue pour un projet ou une entreprise. Vous ne pouvez pas créer votre propre modèle. À la place, vous utilisez les modèles prédéfinis de Microsoft Graph. Vous pouvez utiliser les modèles teams pour créer rapidement des espaces de collaboration riches avec des canaux pour différentes rubriques et des applications de préinstallation pour extraire du contenu et des services critiques. Les modèles teams fournissent une structure d’équipe prédéfinie qui peut vous aider à créer facilement des équipes cohérentes au sein de votre organisation.

Dans cet article, nous allons expliquer les propriétés qui peuvent être définies dans les modèles, les types de modèles de base et la façon dont vous pouvez utiliser quelques exemples de requête pour créer une équipe à partir d’un modèle.

Cet article est pour vous si vous êtes :

- Responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation<br>
- Développeur souhaitant créer par programme une équipe avec des canaux et applications prédéfinis.

## <a name="teams-template-capabilities"></a>Fonctionnalités du modèle équipes

La plupart des propriétés d’une équipe sont incluses et prises en charge par les modèles. Toutefois, certaines propriétés et fonctionnalités ne sont pas prises en charge pour le moment. Le tableau suivant décrit brièvement ce qui est inclus et ce qui n’est pas inclus dans les modèles d’équipe.

| **Propriétés d’équipe prises en charge par les modèles teams** | **Propriétés d’équipe non encore prises en charge par les modèles teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Type de modèle de base | Appartenance à une équipe |
| Nom de l’équipe | Image d’équipe |
| Description de l’équipe | Paramètres du canal |
| Visibilité de l’équipe (publique ou privée) | Connecteurs |
| Paramètres d’équipe (par exemple, membre, invité, @ mentions) | Fichiers et contenu |
| Canal de favoris automatique | |
| Application installée | |
| Onglets épinglés | |

> [!NOTE]
> Dans la prochaine version de Microsoft Teams, nous ajouterons de nouvelles fonctionnalités de modèles, vous retrouverez donc les informations les plus récentes sur les propriétés prises en charge.

## <a name="what-are-base-template-types"></a>Présentation des types de modèles de base

Les types de modèles de base sont des modèles spécifiques créés par Microsoft pour des industries spécifiques. Les modèles de base contiennent souvent des applications propriétaires qui ne sont pas encore prises en charge individuellement dans les modèles d’équipe. Découvrez comment utiliser les [modèles d’équipe dans la console d’administration](get-started-with-teams-templates.md).

Une fois qu’un type de modèle de base est défini, vous pouvez étendre ou remplacer ces modèles spéciaux par d’autres propriétés que vous souhaitez spécifier. Toutefois, certains types de modèles de base contiennent des propriétés qui ne peuvent pas être remplacées.

Par défaut, le modèle de base est défini sur **standard** , qui ne contient pas d’applications propriétaires ou de propriétés spéciales supplémentaires. Vous trouverez ci-dessous la liste actuelle des types de modèles de base disponibles.

| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Aucune application et aucune propriété supplémentaires |
| Expliquer<br>Équipe de classe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Logiciels<ul><li>Bloc-notes OneNote pour la classe (épinglé à l’onglet **général** ) </li><li>Application devoirs (épinglée à l’onglet **général** )</li></ul> Propriétés d’équipe :<ul><li>Visibilité de l’équipe définie sur **HiddenMembership** (ne peut pas être substitué)</li></ul> |
| Expliquer<br>Équipe du personnel enseignant | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Logiciels<ul><li>Carnet de notes OneNote du personnel enseignant (ajouté à l’onglet **général** )</li></ul> |
|Expliquer<br>Équipe PLC |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Logiciels<ul><li>Bloc-notes OneNote PLC (épinglé à l’onglet **général** )</ul></li>|
| Revendeur<br>Magasin | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canaux<ul><li>Remise du Shift</li><li>LMS</li></ul>Propriétés d’équipe<ul><li>Visibilité de l’équipe définie sur publique</li></ul>Autorisations des membres<ul><li>Empêcher les membres de créer, de mettre à jour ou de supprimer des canaux</li><li>Empêcher les membres d’ajouter ou de supprimer des applications</li><li>Empêcher les membres de créer, de mettre à jour ou de supprimer des connecteurs</li></ul> |
| Revendeur<br>Collaboration avec les responsables | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canaux<ul><li>Remise du Shift</li><li>LMS</li></ul>Propriétés d’équipe :<ul><li>Visibilité de l’équipe définie sur privée</li></ul>Autorisations des membres :<ul><li>Empêcher les membres de créer, de mettre à jour ou de supprimer des canaux</li><li>Empêcher les membres d’ajouter ou de supprimer des applications</li><li>Empêcher les membres de créer, de mettre à jour ou de supprimer des connecteurs</li></ul>|
| Organisme<br>Rétrocompatibles |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canaux <ul><li>Annonces\*</li><li>Huddles\*</li><li>Négative</li><li>Spécifient\*</li><li>Formation\*</li></ul>\*Canaux favoris automatiquement |
|Organisme<br>Hôpital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canaux<ul><li>Annonces\*</li><li>Conformité\*</li><li>Privatives de Troie</li><li>Ressources humaines</li></li><li>Pharmaceutiques</li></ul>\*Canal avec favoris automatique|
|||

## <a name="related-topics"></a>Voir aussi

- [Créer une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en Preview)
- [Nouvelle équipe](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Formation à Microsoft Teams pour les administrateurs](itadmin-readiness.md)
- [Démarrage avec les modèles Teams pour la vente au détail](get-started-with-retail-teams-templates.md)
- [Démarrage avec les modèles Teams pour les organismes de santé](expand-teams-across-your-org/healthcare/healthcare-templates.md)
