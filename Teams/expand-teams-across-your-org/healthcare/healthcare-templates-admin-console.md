---
title: Créer une équipe à l’aide de modèles Médicaux Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Utilisez les modèles Microsoft Teams dans le Centre d’administration ou avec Microsoft Graph pour créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260306"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>Créer une équipe à l’aide de modèles médicaux Teams

Les modèles Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications préinstallées.

Pour les organisations de santé, les modèles peuvent être particulièrement puissants, car ils structurent les utilisateurs pour s’orienter dans l’utilisation efficace de Teams. Les modèles permettent également aux administrateurs de déployer des équipes cohérentes au sein de leur organisation. Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de soins de santé.

Choisissez une méthode de création d’équipes avec les modèles Médicaux Teams :

| Qui | Méthode à utiliser : |
| ---- | --------- |
| Administrateurs et professionnels de l’informatique | [Utilisez le Centre d’administration Teams pour](#use-the-teams-templates-in-the-teams-admin-center) créer des équipes basées sur les modèles Teams médicaux.|
| Développeurs et intégrateurs de systèmes | [Utilisez Microsoft Graph pour créer des](#use-the-teams-templates-with-the-microsoft-graph) équipes basées sur les modèles Healthcare Teams. |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Utiliser les modèles Teams dans le Centre d’administration Teams

Les administrateurs Microsoft Teams peuvent utiliser le Centre d’administration Teams pour créer des équipes à l’aide des modèles Teams. Nous proposons actuellement deux modèles de soins de santé à usage unique, que vous pouvez utiliser dans différentes situations. Pour en savoir plus sur les modèles d’équipe en général, voir Commencer à utiliser les [modèles Teams dans le Centre d’administration.](../../get-started-with-teams-templates-in-the-admin-console.md)

### <a name="collaborate-on-patient-care"></a>Collaborer sur les soins des patients

 Simplifiez la communication et la collaboration au sein d’un service, d’une équipe ou d’un service. Le modèle peut être utilisé pour faciliter la gestion des patients et les besoins opérationnels d’une base de données.

| Type de modèle de base |baseTemplateId| Propriétés de ce modèle de base |
| ------------------ |---|----------------------------------------------------- |
| Collaborer sur les soins des patients |`healthcareWard` | Canaux :<ul><li>Général</li><li>Annonces</li><li>Bldles</li><li>Arrondit</li><li>Personnel</li><li>Formation</li></ul> Applications : <ul><li>Wiki</li><li>Listes</li></ul>|
||||

### <a name="hospital"></a>Hôpital

Simplifiez la communication et la collaboration entre plusieurs productions, ainsi que des services au sein d’un hôpital. Ce modèle inclut un ensemble de canaux de base pour les opérations en hôpital et peut être étendu eux-mêmes de manière à inclure les tâches spéciales, ad hoc.

| Type de modèle de base |baseTemplateId | Propriétés de ce modèle de base |
| ------------------|-- |----------------------------------------------------- |
|Hôpital|`healthcareHospital`|Canaux : <ul><li>Général</li><li>Annonces</li><li>Conformité</li><li>Adess</li><li>Ressources humaines</li><li>Desse</li></ul> Applications : <ul><li>Wiki</li><li>Listes </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Utiliser les modèles Teams avec Microsoft Graph

Les développeurs peuvent utiliser Microsoft Graph pour créer des équipes avec les modèles Teams. Nous proposons actuellement deux modèles de soins de santé à usage unique, que vous pouvez utiliser dans différentes situations. Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles Teams.](../../get-started-with-teams-templates.md) Pour plus d’informations sur les modèles Teams et Microsoft Graph, consultez la vue d’ensemble de [l’API Microsoft Teams](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) et le type de ressource [teamsTemplate.](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)

### <a name="ward-template"></a>Modèle Template

Le modèle sont conçus pour la communication et la collaboration au sein d’un service, d’un groupe ou d’un service. Le modèle peut être utilisé pour faciliter la gestion des patients, ainsi que pour répondre aux besoins opérationnels d’une équipe. Par exemple, les annonces de groupe peuvent être publiées dans le canal *Annonces* et les shifts peuvent être gérés dans *staffing.* Si vous cherchez à simplifier vos opérations de simplification, ce modèle est pour vous.

|Type de modèle de base |baseTemplateId |Canaux de modèle de référence|
|:--- |:---|:---|
|Soins de santé - Unité | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Annonces\* <br> Bldles\* <br> Arrondit\* <br> Personnel\* <br> Formation\* |
|     | |         |

\* Favoris automatiques

### <a name="hospital-template"></a>Modèle d’hôpital

Le modèle de l’hôpital est destiné à la communication et à la collaboration entre plusieurs gardiens, pods et services au sein d’un hôpital. Plusieurs canaux opérationnels sont inclus dans ce modèle, notamment *Annonces,* Film et Précédez, mais nous fournissons également un script ci-dessous qui étend le modèle avec toute une série de canaux supplémentaires ou spécialisés que vous pouvez ajouter, supprimer ou modifier à votre convenance. Par exemple, si  vous avez un service de Quézy, mais que vous n’avez pas besoin d’un canal pour *Acécé,* le script peut être adapté afin d’inclure un canal *#A0* et de supprimer le canal acédant.  Nous recommandons que ces canaux spécialisés ou modelés ne soient pas marqués automatiquement pour éviter une saturation des notifications. Généralement, les utilisateurs préfèrent les canaux qu’ils trouvent pertinents.

|Type de modèle de base |baseTemplateId |Canaux de modèle de référence|
|:--- |:---|:---|
|Soins de santé - Hôpital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Annonces\* <br> Conformité\* <br> Adess <br> Ressources humaines <br> Desse |
| | |  |

\* Favoris automatiques 

### <a name="how-to-use-first-party-templates"></a>Comment utiliser des modèles tiers

Pour utiliser ces modèles, modifiez simplement la propriété « template@odata.bind » dans le corps de la demande de « standard » à la propriété TemplateIDs ci-dessus.  Pour plus d’informations sur le déploiement de modèles Teams, voir l’article Microsoft Graph sur la création [d’une équipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Les canaux du modèle sont automatiquement créés sous l’onglet Général.

#### <a name="example-hospital-template-extension-script"></a>Exemple : Script d’extension de modèle d’hôpital

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-topics"></a>Voir aussi

[Prise en main des modèles Teams](../../get-started-with-teams-templates.md)

[Prise en main de Teams pour les organismes de santé](teams-in-hc.md)
