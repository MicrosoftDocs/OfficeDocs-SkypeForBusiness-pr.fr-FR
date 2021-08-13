---
title: Créer une équipe à l’aide de modèles médicaux
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
description: Utilisez des modèles d’équipe dans le Centre d’administration ou avec Microsoft Graph pour créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 050ddd4e9efabe3433257f0497081758767e1cfa38c16aa1102ff17554ce3391
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336254"
---
# <a name="use-a-healthcare-team-templates"></a>Utiliser des modèles d’équipe de santé

Les modèles vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications préinstallées.

Pour les organisations de soins de santé, les modèles peuvent être particulièrement puissants, car ils fournissent aux utilisateurs une structure qui leur permet de s’orienter dans l’utilisation efficace d’Microsoft Teams. Les modèles permettent également aux administrateurs de déployer des équipes cohérentes au sein de leur organisation. Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de soin de santé.

Choisissez une méthode de création d’équipes avec les modèles médicaux d’équipe :

| Qui | Méthode à utiliser : |
| ---- | --------- |
| Administrateurs et professionnels de l’informatique | [Utilisez le centre Teams d’administration](#use-the-team-templates-in-the-admin-center) pour créer des équipes basées sur les modèles de l’équipe de santé.|
| Développeurs et intégrateurs de systèmes | [Utilisez le site Web Graph](#use-the-team-templates-with-the-microsoft-graph) Microsoft pour créer une équipe basée sur les modèles de l’équipe médicale. |

## <a name="use-the-team-templates-in-the-admin-center"></a>Utiliser les modèles d’équipe dans le Centre d’administration

Microsoft Teams administrateurs peuvent utiliser le centre Teams’administration pour créer des équipes à l’grâce aux modèles d’équipe. Nous proposons actuellement deux modèles de soins de santé pour un large éventail de situations. Pour en savoir plus sur les modèles d’équipe en général, voir Commencer à utiliser les [modèles d’équipe dans le Centre d’administration.](../../get-started-with-teams-templates-in-the-admin-console.md)

### <a name="collaborate-on-patient-care"></a>Collaborer sur les soins aux patients

 Simplifiez la communication et la collaboration en matière de soins de santé au sein d'un service, d'une unité ou d'un département. Ce modèle peut être utilisé pour faciliter la gestion des patients et les besoins opérationnels d'un service.

| Type de modèle de base |baseTemplateId| Propriétés fournies avec ce modèle de base |
| ------------------ |---|----------------------------------------------------- |
| Collaborer sur les soins aux patients |`healthcareWard` | Canaux :<ul><li>Général</li><li>Annonces</li><li>Blotti</li><li>Rondes</li><li>Personnel</li><li>Formation</li></ul> Applications : <ul><li>Wiki</li><li>Listes</li></ul>|
||||

### <a name="hospital"></a>Hôpital

Simplifiez la communication et la collaboration entre plusieurs salles, services et départements d'un hôpital. Ce modèle comprend un ensemble de canaux de base pour les opérations hospitalières, et peut être auto-étendu pour inclure des spécialités, ad-hoc.

| Type de modèle de base |baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------|-- |----------------------------------------------------- |
|Hôpital|`healthcareHospital`|Canaux : <ul><li>Général</li><li>Annonces</li><li>Conformité</li><li>Consignataires</li><li>Ressources humaines</li><li>Pharmacie</li></ul> Applications : <ul><li>Wiki</li><li>Listes </li></ul>|
||||


## <a name="use-the-team-templates-with-the-microsoft-graph"></a>Utiliser les modèles d’équipe avec l’Graph

Les développeurs peuvent utiliser le programme Microsoft Graph pour créer des équipes à l’aide des modèles d’équipe. Nous proposons actuellement deux modèles de soins de santé pour un large éventail de situations. Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles d’équipe.](../../get-started-with-teams-templates.md) Pour plus d’informations sur les modèles d’équipe et le modèle Microsoft Graph, voir Microsoft Teams vue d’ensemble de [l’API](/graph/teams-concept-overview?view=graph-rest-1.0) et le type de ressource [teamsTemplate.](/graph/api/resources/teamstemplate?view=graph-rest-1.0)

### <a name="ward-template"></a>Modèle de pavillon

Le modèle de salle est destiné à la communication et à la collaboration au sein d'un pavillon, d'un service ou d'un département. Ce modèle peut être utilisé pour faciliter la gestion des patients et les besoins opérationnels d'un service. Par exemple, les annonces de recherche peuvent être publiées dans le canal *Annonces* et les Plannings peuvent être gérés dans *Staffing*. Si vous cherchez à simplifier les opérations de présentation, ce modèle est fait pour vous.

|Type de modèle de base |baseTemplateId |Canaux modèles de référence|
|:--- |:---|:---|
|Soins de santé : pavillon | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Annonces\* <br> Blotti\* <br> Rondes\* <br> Personnel\* <br> Formation\* |
|     | |         |

\* Favoris automatiques

### <a name="hospital-template"></a>Modèle d’hôpital

Le modèle d'hôpital est destiné à la communication et à la collaboration entre les différents services et départements d'un hôpital. Ce modèle inclut plusieurs canaux opérationnels, notamment *Annonces*, *Consignataires* et *Pharmacie*, mais nous fournissons également un script ci-dessous qui étend le modèle avec de nombreux canaux supplémentaires de service ou spécialisés que vous pouvez ajouter, supprimer ou modifier à votre convenance. Par exemple, si vous avez un service *Endocrinologie* , mais que vous n’avez pas besoin d’un canal pour *Ophtalmologie*, le script peut être adapté pour inclure un canal *Endocrinologie* et supprimer le canal *Ophtalmologie* . Nous vous recommandons de ne pas faire attention à ces canaux de spécialité ou à modélisation automatique afin d’éviter une saturation des notifications. Les utilisateurs préfèrent généralement tous les canaux qu’ils trouvent pertinents.

|Type de modèle de base |baseTemplateId |Canaux modèles de référence|
|:--- |:---|:---|
|Soins de santé : hôpital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Annonces\* <br> Conformité\* <br> Consignataires <br> Ressources humaines <br> Pharmacie |
| | |  |

\* Favoris automatiques 

### <a name="how-to-use-first-party-templates"></a>Comment utiliser les modèles de premier groupe

Pour utiliser ces modèles, modifiez simplement la propriété « template@odata.bind » dans le corps de la demande de « standard » en valeurs TemplateID ci-dessus.  Pour plus d’informations sur le déploiement de modèles d’équipe, consultez l’article Graph Microsoft sur la création [d’une équipe.](/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Les canaux dans le modèle seront automatiquement créés sous l’onglet Général.

#### <a name="example-hospital-template-extension-script"></a>Exemple : script d’extension de modèle d’hôpital

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

### <a name="related-topics"></a>Rubriques connexes

[Utiliser les modèles d’équipe](../../get-started-with-teams-templates.md)

[Commencer à travailler avec l’équipe pour les organisations du secteur des soins de santé](teams-in-hc.md)