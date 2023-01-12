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
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ea67bec0fd8750e32ebb5f65d0258fa7c172a46
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778944"
---
# <a name="use-financial-team-templates"></a>Utiliser des modèles d’équipe financiers

Les modèles d’équipe Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d'applications préinstallées.

Pour les organisations de services financiers, les modèles d’équipe peuvent être particulièrement puissants, car ils vous aident à déployer rapidement des équipes cohérentes au sein de votre organisation. Les modèles aident également le personnel à s’orienter dans l’utilisation efficace de Teams.

Teams comprend des modèles conçus pour les organisations de services financiers. Utilisez ces modèles pré-conçus pour créer rapidement des équipes de communication et de collaboration entre les membres du personnel. Cet article présente chacun des modèles Teams et vous explique comment les utiliser.

La façon dont vous gérez et travaillez avec les modèles d’équipe dépend de votre rôle d’administrateur ou de développeur.

|Si vous êtes : | Ensuite, vous : |
| ---- | --------- |
| Un administrateur ou un professionnel de l’informatique |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| Un développeur | [Utilisez Microsoft Graph](#use-team-templates-with-microsoft-graph) pour créer des équipes à partir de modèles d’équipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gérer les modèles d’équipe dans le Centre d’administration Teams

En tant qu’administrateur, vous pouvez gérer des modèles d’équipe dans le Centre d’administration de Microsoft Teams. Ici, vous pouvez afficher des détails sur chaque modèle. Vous pouvez également [créer et attribuer des stratégies de modèles](templates-policies.md) à votre personnel afin de contrôler les modèles qu’ils voient dans Teams pour [la création d’équipes](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles d’équipe dans le Centre d'administration Teams](get-started-with-teams-templates-in-the-admin-console.md).

Nous proposons actuellement les modèles d’équipe pré-intégrés suivants pour les organisations de services financiers. Pour les afficher, dans le volet de navigation gauche du centre d'administration Teams, accédez à **Modèles d’équipes** >  **Teams**.

### <a name="bank-branch"></a>Succursale bancaire

Centralisez la collaboration pour les employés de votre agence bancaire lors de réunions, de rencontres de clients, de processus commerciaux tels que la collaboration sur le crédit, et gardez tout le monde au courant par des annonces et des félicitations.

>[!div class="mx-tdBreakAll"]
>| Type de modèle |TemplateId| Propriétés fournies avec ce modèle de base |
>| ------------------ |--|----------------------------------------------------- |
>|Succursale bancaire| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canaux : <ul><li>Général<li>Annonces</li><li>Blotti</li><li>Réunions client</li><li>Demande d’approbations </li><li>Accompagnement</li><li>Développement des compétences</li><li>Traitement des prêts</li><li>Plaintes des clients</li><li>Félicitations</li><li>Trucs amusants</li><li>Conformité</li></ul>Applications :<ul><li>Approbations</li><li>Bulletins</li><li>Calendrier du canal</li><li>Idées des employés</li><li>Signalement des problèmes</li><li>Compliment</li><li>Shifts</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Utiliser les modèles Teams avec Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0&preserve-view=true), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0&preserve-view=true).

### <a name="bank-branch"></a>Succursale bancaire

Centralisez la collaboration pour les employés de votre agence bancaire lors de réunions, de rencontres de clients, de processus commerciaux tels que la collaboration sur le crédit, et gardez tout le monde au courant par des annonces et des félicitations.

>[!div class="mx-tdBreakAll"]
>| Type de modèle |TemplateId| Canaux modèles |
>| ------------------ |--|----------------------------------------------------- |
>|Succursale bancaire|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|Général<br>Annonces<br>Blotti<br>Réunions client<br>Demande d’approbations<br>Accompagnement<br>Développement des compétences<br>Traitement des prêts<br>Plaintes des clients<br>Félicitations<br>Trucs amusants<br>Conformité|

> [!NOTE]
> Pour obtenir des modèles d’équipe supplémentaires qui s’appliquent aux organisations, consultez [modèles d’équipe intégrés à Microsoft Graph pour les petites moyennes entreprises](smb-templates.md).

## <a name="related-articles"></a>Articles connexes

- [Utiliser des modèles d’équipe dans le Centre d’administration Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Créer une équipe à partir d’un modèle](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Utiliser des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md)