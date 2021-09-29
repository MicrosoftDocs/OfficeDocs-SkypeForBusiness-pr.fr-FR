---
title: Utiliser des modèles d’équipe à l’aide de Microsoft Graph
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
description: En savoir plus sur les modèles d’équipe qui sont disponibles uniquement avec Microsoft Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e570faff4ec7138457f7cd52e101a0a3632d64d2
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991113"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Utiliser des modèles d’équipe à l’aide de Microsoft Graph

> [!NOTE]
> Pour le moment, les modèles d’équipe ne prisent pas en charge la création de canaux privés. La création de canaux privés n’est pas incluse dans les définitions de modèle.

Un modèle d’équipe Microsoft Teams est une définition de la structure d’une équipe conçue autour d’un besoin ou d’un projet d’entreprise. Les modèles d’équipe vous permettent de créer rapidement et facilement des espaces de collaboration enrichis avec des paramètres, des canaux et des applications prédéfinés. Les modèles d’équipe peuvent vous aider à déployer des équipes cohérentes au sein de votre organisation.

Avec Microsoft Graph, vous utilisez les modèles d’équipe pré-intégrés inclus dans Teams pour créer des équipes. Cet article présente les propriétés qui peuvent être définies dans les modèles et les modèles disponibles uniquement avec Microsoft Graph.

Cet article est pour vous si vous êtes :

- Responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation<br>
- Développeur désireux de créer par programme une équipe avec des canaux et applications prédéfinfinés

## <a name="team-template-capabilities"></a>Fonctionnalités des modèles d’équipe

La plupart des propriétés d’une équipe sont incluses et prise en charge par les modèles. Certaines propriétés et fonctionnalités ne sont actuellement pas pris en charge. Voici un bref résumé de ce qui est inclus et de ce qui n’est pas inclus dans les modèles d’équipe.

| **Propriétés d’équipe pris en charge par les modèles d’équipe** | **Propriétés de l’équipe non encore pris en charge par les modèles d’équipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Type de modèle | Appartenance à une équipe |
| Nom de l’équipe | Image de l’équipe |
| Description de l’équipe | Paramètres du canal |
| Visibilité de l’équipe (publique ou privée) | Connecteurs |
| Paramètres de l’équipe (par exemple, membre, invité, @mentions) | Fichiers et contenu |
| Canal favoris automatique | |
| Application installée | |
| Onglets épinglés | |

> [!NOTE]
> Nous ajouterons d’autres fonctionnalités de modèle dans les prochaines version de Microsoft Teams. Vérifiez donc que vous avez besoin des informations les plus à jour sur les propriétés prise en charge.

## <a name="pre-built-templates"></a>Modèles pré-intégrés

Les modèles d’équipe pré-créés sont des modèles que nous avons créés pour des secteurs spécifiques. Voici les modèles pré-conçus qui sont disponibles uniquement avec Microsoft Graph.

| Type de modèle | TemplateId | Propriétés de ce modèle |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | Aucune application et propriété supplémentaire |
| Éducation -<br>Équipe de classe | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | Applications :<ul><li>OneNote Bloc-notes Pour la classe (épinglé à **l’onglet** Général) </li><li>Application Devoirs (épinglée à **l’onglet** Général)</li></ul> Propriétés de l’équipe :<ul><li>Visibilité de l’équipe définie **sur HiddenMembership** (ne peut pas être masquée)</li></ul> |
| Éducation -<br>Équipe de membres du personnel enseignant | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | Applications :<ul><li>OneNote Bloc-notes pour le personnel enseignant (épinglé à **l’onglet** Général)</li></ul> |
|Éducation -<br>Équipe PLC |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Applications :<ul><li>OneNote Bloc-notes PLC (épinglé à **l’onglet** Général)</ul></li>|

> [!NOTE]
> Pour obtenir la liste des modèles pré-conçus que vous pouvez utiliser dans le client Teams et avec Microsoft Graph, voir Commencer à utiliser des modèles d’équipe dans le Centre d’administration [Teams.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="related-articles"></a>Articles connexes

- [Utiliser des modèles d’équipe dans le Centre d’administration Teams’équipe](get-started-with-teams-templates-in-the-admin-console.md)
- [Créer une équipe](/graph/api/team-post?view=graph-rest-beta) (en prévisualisation)
- [Nouvelle équipe](/powershell/module/teams/New-Team?view=teams-ps)
