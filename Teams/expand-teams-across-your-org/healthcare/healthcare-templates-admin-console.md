---
title: Utiliser des modèles d’équipe médicale
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: Découvrez comment gérer et utiliser les modèles d’équipe médicale dans le Centre d’administration Teams et avec Microsoft Graph pour créer rapidement et facilement des équipes pour votre organisation de services de santé.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5345f5e9886bbcb9e4a2274d21d2aabb0be373c6
ms.sourcegitcommit: 5eb5acd7910724f7f4a598ecc28b003e5bbe5ea5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "60007804"
---
# <a name="use-healthcare-team-templates"></a>Utiliser des modèles d’équipe médicale

Les modèles d’équipe dans Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant une structure d’équipe prédéfinie de paramètres, de canaux et d'applications préinstallées.

Pour les organisations de santé, les modèles d’équipe peuvent être particulièrement puissants, car ils vous aident à déployer rapidement des équipes cohérentes au sein de votre organisation. Les modèles aident également le personnel à s’orienter pour utiliser efficacement Teams.

Teams inclut des modèles conçus spécifiquement pour les organisations de services de santé. Utilisez ces modèles pré-conçus pour créer rapidement des équipes pour la communication et la collaboration du personnel sur les soins aux patients ou les besoins opérationnels. Cet article présente chacun des modèles Teams et vous explique comment les utiliser.

La façon dont vous gérez et travaillez avec les modèles d’équipe dépend si vous avez un rôle d’administrateur ou de développeur.

|Si vous êtes : | Vous êtes alors : |
| ---- | --------- |
| Un administrateur ou un professionnel de l’informatique |[Gérez les modèles d’équipe dans le Centre d’administration Teams](#manage-team-templates-in-the-teams-admin-center). Affichez les modèles d’équipe et appliquez des stratégies de modèles pour contrôler les modèles que les membres du personnel peuvent utiliser dans Teams pour créer des équipes. |
| Développeur | [Utilisez Microsoft Graph](#use-team-templates-with-microsoft-graph) pour créer des équipes à partir des modèles d’équipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gérer les modèles d’équipe dans le Centre d’administration Teams

En tant qu’administrateur, vous pouvez gérer les modèles d’équipe dans le Centre d’administration Microsoft Teams. Ici, vous pouvez afficher des détails sur chaque modèle. Vous pouvez également [créer et attribuer des stratégies de modèles](../../templates-policies.md) à votre personnel afin de contrôler les modèles qu’il voit dans Teams pour [créer des équipes](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c). 

Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles d’équipe dans le Centre d'administration Teams](../../get-started-with-teams-templates-in-the-admin-console.md).

Nous proposons actuellement les modèles pré-intégrés d’équipe de services de santé suivants. Pour les afficher, dans le navigation gauche du Centre d'administration Teams, accédez à **Modèles d’équipe** > **Teams**.
### <a name="patient-care"></a>Soins du patient

 Ce modèle est destiné à la communication et à la collaboration au sein d'une unité, d'un service ou d'un département. Vous pouvez utiliser ce modèle pour faciliter la gestion des patients et les besoins opérationnels d’une unité. Par exemple, publiez des annonces d’unité dans le canal *Annonces* et gérez les shifts dans le canal *Personnel*.

| Type de modèle |TemplateId| Propriétés fournies avec ce modèle de base |
| ------------------ |---|----------------------------------------------------- |
| Soins du patient |`healthcareWard` | Canaux :<ul><li>Général</li><li>Annonces<ul><li>Bulletins&sup1;</li></ul></li><li>Comités restreints<ul><li>Listes (liste des patients) &sup1;</li></ul></li><li>Rondes<ul><li>Inspection&sup1;</li></ul></li><li>Personnel</li><li>Formation</li></ul> Applications : <ul><li>Wiki</li><li>Listes</li><li>Tâches</li><li>Approbations</li><li>Plannings</li><li>Bulletins</li><li>Inspection</li></ul>|
||||

&sup1; Application ajoutée au canal en tant qu’onglet
### <a name="hospital"></a>Hôpital

Ce modèle est destiné à la communication et à la collaboration entre les différents services, unités et départements d'un hôpital. Ce modèle comprend un ensemble de canaux pour les opérations hospitalières et peut être étendu pour inclure des spécialités.

| Type de modèle |TemplateId | Propriétés fournies avec ce modèle de base |
| ------------------|-- |----------------------------------------------------- |
|Hôpital|`healthcareHospital`|Canaux : <ul><li>Général<ul><li>Listes&sup1;</li></ul></li><li>Annonces<ul><li>Bulletins&sup1;</li></ul></li><li>Conformité</li><ul><li>Inspection&sup1;</li></ul></li><li>Consignataires</li><li>Ressources humaines<ul><li>Idées&sup1;</li></ul></li><li>Pharmacie</li></ul> Applications : <ul><li>Wiki</li><li>Tâches</li><li>Listes</li><li>Approbations</li><li>Plannings</li><li>Bulletins</li><li>Inspection</li><li>Idées</li></ul>|
||||

&sup1; Application ajoutée au canal en tant qu’onglet
## <a name="use-team-templates-with-microsoft-graph"></a>Utiliser les modèles d’équipe avec Microsoft Graph

Les développeurs peuvent utiliser Microsoft Graph pour créer des équipes à partir de modèles d’équipe pré-conçus. Pour en savoir plus sur l’utilisation des modèles d’équipe avec Microsoft Graph, voir [Mise en place des modèles d’équipe à l’aide de Microsoft Graph](../../get-started-with-teams-templates.md), [Vue d’ensemble de l’API Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0)et [Type de ressources teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Voici les modèles pré-intégrés de l’équipe de santé.
### <a name="ward"></a>Unité

Le modèle d’unité est destiné à la communication et à la collaboration au sein d'une unité, d'un service ou d'un département. Ce modèle peut être utilisé pour faciliter la gestion des patients et les besoins opérationnels d'un service. Par exemple, les annonces de recherche peuvent être publiées dans le canal *Annonces* et les Plannings peuvent être gérés dans *Staffing*. Si vous cherchez à simplifier les opérations de présentation, ce modèle est fait pour vous.

|Type de modèle |TemplateId |Canaux modèles|
|:--- |:---|:---|
|Services de santé : unité | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Général<br>Annonces&sup2; <br> Comités restreints&sup2; <br> Rondes&sup2; <br> Personnel&sup2; <br> Formation&sup2; |
|     | |         |

&sup2; Canaux favoris automatiques

### <a name="hospital"></a>Hôpital

Le modèle d'hôpital est destiné à la communication et à la collaboration entre les différents services, unités et départements au sein d'un hôpital. Ce modèle inclut plusieurs canaux opérationnels tels que *Annonces*, *Gardes* et *Pharmacie*. Nous fournissons également un script que vous pouvez utiliser pour étendre le modèle à d’autres services ou canaux de spécialisation. Vous pouvez le modifier selon vos besoins.

Par exemple, si vous avez un service *Endocrinologie*, mais que vous n’avez pas besoin d’un canal pour *Ophtalmologie*, le script peut être adapté afin d’inclure un canal *Endocrinologie* et de supprimer le canal *Ophtalmologie*. Nous vous recommandons de ne pas faire attention à ces canaux de spécialité ou à modélisation automatique afin d’éviter une saturation des notifications. Les utilisateurs préfèrent généralement tous les canaux qu’ils trouvent pertinents.

|Type de modèle |TemplateId |Canaux modèles|
|:--- |:---|:---|
|Services de santé : hôpital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Général<br>Annonces&sup2; <br> Conformité&sup2; <br> Consignataires <br> Ressources humaines <br> Pharmacie |
| | |  |

&sup2; Canaux favoris automatiques

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Utiliser des modèles d’équipe avec Microsoft Graph

Pour utiliser ces modèles, modifiez la propriété « template@odata.bind » dans le corps de la demande de « standard » en valeurs TemplateIds ci-dessus. Pour plus d’informations sur le déploiement de modèles d’équipe, consultez l’article Graph Microsoft sur la [création d’une équipe](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Les canaux du modèle sont automatiquement créés sous l’onglet **Général**.

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

### <a name="related-articles"></a>Articles connexes

[Prise en main des modèles d’équipe dans le Centre d’administration Teams](../../get-started-with-teams-templates-in-the-admin-console.md)

[Prise en main des modèles d’équipe à l’aide de Microsoft Graph](../../get-started-with-teams-templates.md)

[Prise en main de Teams pour les organismes de santé](teams-in-hc.md)