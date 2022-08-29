---
title: Prise en main des modèles d’équipe à l’aide de Microsoft Graph
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
description: Découvrez les modèles d’équipe disponibles uniquement avec Microsoft Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4251aa0293665b6fd41c66e352ca9c595378259
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397235"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Prise en main des modèles d’équipe à l’aide de Microsoft Graph

> [!NOTE]
> Actuellement, les modèles d’équipe ne prennent pas en charge la création de canaux privés. La création de canaux privés n’est pas incluse dans les définitions de modèle.

Un modèle d’équipe dans Microsoft Teams est une définition de la structure d’une équipe conçue autour d’un besoin ou d’un projet métier. Avec les modèles d’équipe, vous pouvez créer rapidement et facilement des espaces de collaboration riches avec des paramètres, des canaux et des applications prédéfinis. Les modèles d’équipe peuvent vous aider à déployer des équipes cohérentes au sein de votre organisation.

Avec Microsoft Graph, vous pouvez [créer vos propres modèles](/graph/api/resources/teamtemplate?view=graph-rest-beta) ou utiliser les modèles d’équipe prédéfinifiés inclus dans Teams pour créer des équipes. Dans cet article, vous allez découvrir les propriétés qui peuvent être définies dans les modèles et les modèles prédéfinis qui sont disponibles uniquement avec Microsoft Graph.

Cet article est destiné à vous si vous êtes :

- Responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation<br>
- Un développeur souhaitant créer par programmation une équipe avec des canaux et des applications prédéfinis

## <a name="team-template-capabilities"></a>Fonctionnalités de modèle d’équipe

La plupart des propriétés d’une équipe sont incluses et prises en charge par les modèles. Mais il existe quelques propriétés et fonctionnalités qui ne sont pas prises en charge actuellement. Voici un résumé rapide de ce qui est inclus et de ce qui n’est pas inclus dans les modèles d’équipe.

| **Propriétés d’équipe prises en charge par les modèles d’équipe** | **Propriétés d’équipe non encore prises en charge par les modèles d’équipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Type de modèle | Appartenance à une équipe |
| Nom de l’équipe | Image de l’équipe |
| Description de l’équipe | Paramètres de canal |
| Visibilité de l’équipe (publique ou privée) | Connecteurs |
| Paramètres d’équipe (par exemple, membre, invité, @ mentions) | Fichiers et contenu |
| Canal favori automatique | |
| Application installée | |
| Onglets épinglés | |

> [!NOTE]
> Nous ajouterons d’autres fonctionnalités de modèle dans les prochaines versions de Microsoft Teams. Par conséquent, consultez les informations les plus récentes sur les propriétés prises en charge.

## <a name="pre-built-templates"></a>Modèles prédéfinifiés

Les modèles d’équipe prédéfinifiés sont des modèles que nous avons créés pour des secteurs spécifiques. Voici les modèles prédéfinifiés qui sont disponibles uniquement avec Microsoft Graph.

| Type de modèle | TemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | Aucune application et propriété supplémentaire |
| Éducation -<br>Équipe de classes | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | Applications :<ul><li>Bloc-notes OneNote pour la classe (épinglé à l’onglet **Général** ) </li><li>Application Affectations (épinglée à l’onglet **Général** )</li></ul> Propriétés de l’équipe :<ul><li>Visibilité de l’équipe définie sur **HiddenMembership** (ne peut pas être remplacée)</li></ul> |
| Éducation -<br>Équipe du personnel | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | Applications :<ul><li>Bloc-notes OneNote pour le personnel enseignant (épinglé à l’onglet **Général** )</li></ul> |
|Éducation -<br>Équipe PLC |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Applications :<ul><li>Bloc-notes OneNote PLC (épinglé à l’onglet **Général** )</ul></li>|

> [!NOTE]
> Pour obtenir la liste des modèles prédéfinifiés que vous pouvez utiliser dans le client Teams et avec Microsoft Graph, consultez [Prise en main des modèles d’équipe dans le Centre d’administration Teams](get-started-with-teams-templates-in-the-admin-console.md).

## <a name="related-articles"></a>Articles connexes

- [Utiliser des modèles d’équipe dans le Centre d’administration Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Créer une équipe](/graph/api/team-post?view=graph-rest-beta) (en préversion)
- [Nouvelle équipe](/powershell/module/teams/New-Team?view=teams-ps)
