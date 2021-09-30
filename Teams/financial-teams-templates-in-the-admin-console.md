---
title: Utiliser des modèles d’équipe financière
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Découvrez comment gérer et utiliser les modèles d’équipe financière dans le Centre d’administration Teams et avec Microsoft Graph pour créer rapidement et facilement des équipes pour votre organisation de services financiers.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9273f8519fd7aeea90ff35f49ca0d6986afa2d59
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991103"
---
# <a name="use-financial-team-templates"></a>Utiliser des modèles d’équipe financière

Les modèles Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d'applications préinstallées.

Pour les organisations de services financiers, les modèles d’équipe peuvent être particulièrement puissants, car ils vous aident à déployer rapidement des équipes cohérentes au sein de votre organisation. Les modèles aident également le personnel à s’orienter dans l’utilisation efficace de Teams.

Teams comprend des modèles conçus pour les organisations de services financiers. Utilisez ces modèles pré-conçus pour créer rapidement des équipes de communication et de collaboration entre les membres du personnel. Cet article présente chacun des modèles Teams et vous explique comment les utiliser.

La façon dont vous gérez et travaillez avec les modèles d’équipe dépend de votre rôle d’administrateur ou de développeur.

|Si vous êtes : | Alors, vous : |
| ---- | --------- |
| Un administrateur ou un professionnel de l’informatique |[Gérez les modèles d’équipe dans le Centre d'administration Teams](#manage-team-templates-in-the-teams-admin-center). Affichez les modèles d’équipe et appliquez des stratégies de modèles pour contrôler les modèles que les membres du personnel peuvent utiliser Teams pour créer des équipes. |
| Un développeur | [Utilisez Microsoft Graph](#use-team-templates-with-microsoft-graph) pour créer des équipes à partir de modèles d’équipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gérer les modèles d’équipe dans le Centre d’administration Teams

En tant qu’administrateur, vous pouvez créer et gérer des équipes et des canaux dans le client Teams ou avec le centre d’administration de Microsoft Teams. Ici, vous pouvez afficher des détails sur chaque modèle. Vous pouvez également [créer et attribuer des stratégies de modèles](templates-policies.md) à votre personnel afin de contrôler les modèles qu’il voit dans Teams pour [créer des équipes.](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)

Pour en savoir plus sur les modèles d’équipe en général, consultez [Commencer à utiliser les modèles d’équipe dans le Centre d'administration Teams](get-started-with-teams-templates-in-the-admin-console.md).

Nous proposons actuellement les modèles d’équipe pré-intégrés suivants pour les organisations de services financiers. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **Modèles d’équipes** > **Teams**.

### <a name="collaborate-within-a-bank-branch"></a>Collaborer au sein d’une filiale bancaire

Centralisez la collaboration pour les employés de votre agence bancaire dans le cadre de réunions, de rencontres avec les clients et de processus commerciaux tels que la collaboration en matière de prêts, et tenez tout le monde au courant par des annonces et des félicitations.

| Type de modèle |TemplateId| Propriétés fournies avec ce modèle |
| ------------------ |--|----------------------------------------------------- |
|Agence bancaire| `CollaborateWithinABankBranch`|Canaux : <ul><li>Général<li>Annonces</li><li>Blotti</li><li>Réunions avec les clients</li><li>Demande d’approbation </li><li>Accompagnement</li><li>Développement de compétences</li><li>Traitement des emprunts</li><li>Réclamations des clients</li><li>Félicitations</li><li>Outils amusants</li><li>Conformité</li></ul>Applications :<ul><li>Compliment </li><li>Signalement de problèmes</li><li>Page Wiki</li><li>Calendrier</li><li>Approbations</li><li>Bulletins</li><li>Idées</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>Utiliser les modèles Teams avec Microsoft Graph

Les développeurs peuvent utiliser Microsoft Graph pour créer des équipes à partir de modèles d’équipe pré-conçus. Pour en savoir plus sur l’utilisation de modèles d’équipe avec Microsoft Graph, consultez [Démarrage avec des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md), [Vue d’ensemble de l’API Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0)et [type de ressource teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

### <a name="bank-branch"></a>Agence bancaire

Centralisez la collaboration pour les employés de votre agence bancaire dans le cadre de réunions, de rencontres avec les clients et de processus commerciaux tels que la collaboration en matière de prêts, et tenez tout le monde au courant par des annonces et des félicitations.

| Type de modèle |TemplateId| Canaux de modèle |
| ------------------ |--|----------------------------------------------------- |
|Agence bancaire|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|Général<br>Annonces<br>Blotti<br>Réunions avec les clients<br>Demande d’approbation<br>Accompagnement<br>Développement de compétences<br>Traitement des emprunts<br>Réclamations des clients<br>Félicitations<br>Outils amusants<br>Conformité|
||||

> [!NOTE]
> Pour obtenir des modèles supplémentaires qui s’appliquent aux organisations de services financiers, consultez [Modèles d’équipe intégrés à Microsoft Graph pour les petites et moyennes entreprises](smb-templates.md).