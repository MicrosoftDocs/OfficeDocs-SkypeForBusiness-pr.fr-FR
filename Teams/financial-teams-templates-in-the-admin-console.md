---
title: Utiliser des modèles d’équipe financiers
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
ms.openlocfilehash: 51ec855bc9065bb65c0f6eae14a3e41683cfbc6f
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046130"
---
# <a name="use-financial-team-templates"></a>Utiliser des modèles d’équipe financiers

Les modèles d’équipe Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d'applications préinstallées.

Pour les organisations de services financiers, les modèles d’équipe peuvent être particulièrement puissants, car ils vous aident à déployer rapidement des équipes cohérentes au sein de votre organisation. Les modèles aident également le personnel à s’orienter dans l’utilisation efficace de Teams.

Teams comprend des modèles conçus pour les organisations de services financiers. Utilisez ces modèles pré-conçus pour créer rapidement des équipes de communication et de collaboration entre les membres du personnel. Dans cet article, nous vous présenterons chacun de ces modèles et vous expliquerons comment les utiliser.

La façon dont vous gérez et travaillez avec les modèles d’équipe dépend de votre rôle d’administrateur ou de développeur.

|Si vous êtes : | Ensuite, vous : |
| ---- | --------- |
| Un administrateur ou un professionnel de l’informatique |[Gérez les modèles d’équipe dans le Centre d'administration Teams](#manage-team-templates-in-the-teams-admin-center). Affichez les modèles d’équipe et appliquez des stratégies de modèles pour contrôler les modèles que les membres de votre personnel peuvent utiliser dans Teams pour créer des équipes. |
| Un développeur | [Utilisez Microsoft Graph](#use-team-templates-with-microsoft-graph) pour créer des équipes à partir de modèles d’équipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gérer les modèles d’équipe dans le Centre d’administration Teams

En tant qu’administrateur, vous pouvez gérer des modèles d’équipe dans le Centre d’administration de Microsoft Teams. Ici, vous pouvez afficher des détails sur chaque modèle. Vous pouvez également [créer et attribuer des stratégies de modèles](templates-policies.md) à votre personnel afin de contrôler les modèles qu’ils voient dans Teams pour [la création d’équipes](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Pour en savoir plus sur les modèles d’équipe en général, consultez [ Commencer à utiliser les modèles d’équipe dans le centre d’administration Teams](get-started-with-teams-templates-in-the-admin-console.md).

Nous proposons actuellement les modèles d’équipe pré-intégrés suivants pour les organisations de services financiers. Pour les afficher, dans le volet de navigation gauche du centre d'administration Teams, accédez à **Modèles d’équipes** >  **Teams**.

### <a name="collaborate-within-a-bank-branch"></a>Collaborer au sein d’une filiale bancaire

Centralisez la collaboration pour les employés de votre agence bancaire lors de réunions, de rencontres de clients, de processus commerciaux tels que la collaboration sur le crédit, et gardez tout le monde au courant par des annonces et des félicitations.

| Type de modèle |TemplateId| Propriétés fournies avec ce modèle de base |
| ------------------ |--|----------------------------------------------------- |
|Agence bancaire| `CollaborateWithinABankBranch`|Canaux : <ul><li>Général<li>Annonces</li><li>Blotti</li><li>Réunions avec des clients</li><li>Demande d’approbation </li><li>Accompagnement</li><li>Développement de compétences</li><li>Traitement des emprunts</li><li>Réclamations des clients</li><li>Félicitations</li><li>Outils amusants</li><li>Conformité</li></ul>Applications :<ul><li>Compliment </li><li>Signalement de problèmes</li><li>Page Wiki</li><li>Calendrier</li><li>Approbations</li><li>Bulletins</li><li>Idées</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>Utiliser les modèles Teams avec Microsoft Graph

Les développeurs peuvent utiliser Microsoft Graph pour créer des équipes à partir de modèles d’équipe prédéfinis. Pour en savoir plus sur l’utilisation des modèles d’équipe avec Microsoft Graph, consultez [Démarrage des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md), [Vue d’ensemble de l’API Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0) et [Type de ressource de modèles Teams](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

### <a name="bank-branch"></a>Agence bancaire

Centralisez la collaboration pour les employés de votre agence bancaire lors de réunions, de rencontres de clients, de processus commerciaux tels que la collaboration sur le crédit, et gardez tout le monde au courant par des annonces et des félicitations.

| Type de modèle |TemplateId| Canaux de modèles |
| ------------------ |--|----------------------------------------------------- |
|Agence bancaire|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|Général<br>Annonces<br>Blotti<br>Réunions avec des clients<br>Demande d’approbation<br>Accompagnement<br>Développement de compétences<br>Traitement des emprunts<br>Réclamations des clients<br>Félicitations<br>Outils amusants<br>Conformité|
||||

> [!NOTE]
> Pour obtenir des modèles d’équipe supplémentaires qui s’appliquent aux organisations, consultez [modèles d’équipe intégrés à Microsoft Graph pour les petites moyennes entreprises](smb-templates.md).

## <a name="related-articles"></a>Articles connexes

- [Utiliser des modèles d’équipe dans le Centre d’administration Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Créer une équipe à partir d’un modèle](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Utiliser des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md)