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
- microsoftcloud-healthcare
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: Découvrez comment gérer et utiliser les modèles d’équipe médicale dans le Centre d’administration Teams et avec Microsoft Graph pour créer rapidement et facilement des équipes pour votre organisation de services de santé.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 17f5ce2774dd163f5f244bea0e685623f64ed59f
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778964"
---
# <a name="use-healthcare-team-templates"></a>Utiliser des modèles d’équipe médicale

Les modèles d’équipe dans Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant une structure d’équipe prédéfinie de paramètres, de canaux et d'applications préinstallées.

Pour les organisations de santé, les modèles d’équipe peuvent être particulièrement puissants, car ils vous aident à déployer rapidement des équipes cohérentes au sein de votre organisation. Les modèles aident également le personnel à s’orienter dans l’utilisation efficace de Teams.

Teams inclut des modèles conçus spécifiquement pour les organisations de services de santé. Utilisez ces modèles pré-conçus pour créer rapidement des équipes pour la communication et la collaboration du personnel sur les soins aux patients ou les besoins opérationnels. Cet article présente chacun des modèles Teams et vous explique comment les utiliser.

La façon dont vous gérez et travaillez avec les modèles d’équipe dépend de votre rôle d’administrateur ou de développeur.

|Si vous êtes : | Ensuite, vous : |
| ---- | --------- |
| Un administrateur ou un professionnel de l’informatique |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| Un développeur | [Utilisez Microsoft Graph](#use-team-templates-with-microsoft-graph) pour créer des équipes à partir des modèles d’équipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gérer les modèles d’équipe dans le Centre d’administration Teams

En tant qu’administrateur, vous pouvez gérer des modèles d’équipe dans le Centre d’administration de Microsoft Teams. Ici, vous pouvez afficher des détails sur chaque modèle. Vous pouvez également [créer et attribuer des stratégies de modèles](../../templates-policies.md) à votre personnel afin de contrôler les modèles qu’ils voient dans Teams pour [la création d’équipes](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles d’équipe dans le Centre d'administration Teams](../../get-started-with-teams-templates-in-the-admin-console.md).

Nous proposons actuellement les modèles pré-intégrés d’équipe de services de santé suivants. Pour les afficher, dans le navigation gauche du Centre d'administration Teams, accédez à **Modèles d’équipe** > **Teams**.

### <a name="patient-care"></a>Soins aux patients

Simplifiez la communication et la collaboration en matière de soins de santé au sein d'un service, d'une unité ou d'un département. Utilisez ce modèle pour faciliter la gestion des patients et les besoins opérationnels d’un service. Par exemple, publiez des annonces d’unité dans le canal *Annonces* et gérez les shifts dans le canal *Personnel*.

>[!div class="mx-tdBreakAll"]
>| Type de modèle |TemplateId| Propriétés fournies avec ce modèle de base |
>| ------------------ |---|----------------------------------------------------- |
>| Soins aux patients |`healthcareWard` | Canaux :<ul><li>Général</li><li>Annonces</li><li>Blotti</li><li>Rondes</li><li>Personnel</li><li>Formation</li></ul> Applications : <ul><li>Approbations</li><li>Bulletins</li><li>Inspection</li><li>Listes</li><li>Shifts</li><li>Tâches par planificateur et à faire</li><li>Wiki</li></ul>|

### <a name="hospital"></a>Hôpital

Simplifiez la communication et la collaboration entre plusieurs salles, services et départements d'un hôpital. Ce modèle comprend un ensemble de canaux pour les opérations hospitalières et peut être étendu pour inclure des spécialités.

>[!div class="mx-tdBreakAll"]
>| Type de modèle |TemplateId | Propriétés fournies avec ce modèle de base |
>| ------------------|-- |----------------------------------------------------- |
>|Hôpital|`healthcareHospital`|Canaux : <ul><li>Général</li><li>Annonces</li><li>Conformité</li></li><li>Consignataires</li><li>Ressources humaines</li><li>Pharmacie</li></ul>  Applications : <ul><li>Approbations</li><li>Bulletins</li><li>Idées des employés</li><li>Inspection</li><li>Listes</li><li>Shifts</li><li>Tâches par planificateur et à faire</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Utiliser les modèles Teams avec Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](../../get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview), and [teamsTemplate resource type](/graph/api/resources/teamstemplate).

Voici les modèles pré-intégrés de l’équipe de santé.

### <a name="patient-care"></a>Soins aux patients

Ce modèle est destiné à la communication et à la collaboration au sein d'une unité, d'un service ou d'un département. Utilisez ce modèle pour faciliter la gestion des patients et les besoins opérationnels d’un service. Par exemple, les annonces de recherche peuvent être publiées dans le canal *Annonces* et les Plannings peuvent être gérés dans *Staffing*. Si vous cherchez à simplifier les opérations de présentation, ce modèle est fait pour vous.

>[!div class="mx-tdBreakAll"]
>|Type de modèle |TemplateId |Canaux modèles|
>|:--- |:---|:---|
>|Services de santé : unité | `https://graph.microsoft.com/beta/teamsTemplates('healthcareWard')`   | Général<br>Annonces&sup2; <br> Comités restreints&sup2; <br> Rondes&sup2; <br> Personnel&sup2; <br> Formation&sup2; |

&sup2; Canaux favoris automatiques

### <a name="hospital"></a>Hôpital

Ce modèle est destiné à la communication et à la collaboration entre les différents services, unités et départements d'un hôpital. Il comprend plusieurs canaux opérationnels tels que *les annonces*, *la garde* et la *pharmacie*. Nous fournissons également un script que vous pouvez utiliser pour étendre le modèle à d’autres services ou canaux spécialisés. Vous pouvez le modifier selon vos besoins.

Par exemple, si vous avez un service *d’endocrinologie* , mais que vous n’avez pas besoin d’un canal pour *l’ophtalmologie*, vous pouvez adapter le script pour inclure un canal *d’endocrinologie* et supprimer le canal *Ophtalmologie* . Nous vous recommandons de ne pas faire attention à ces canaux de spécialité ou à modélisation automatique afin d’éviter une saturation des notifications. Les utilisateurs préfèrent généralement tous les canaux qu’ils trouvent pertinents.

>[!div class="mx-tdBreakAll"]
>|Type de modèle |TemplateId |Canaux modèles|
>|:--- |:---|:---|
>|Services de santé : hôpital | `https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')`   | Général<br>Annonces&sup2; <br> Conformité&sup2; <br> Consignataires <br> Ressources humaines <br> Pharmacie |

&sup2; Canaux favoris automatiques

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Comment utiliser des modèles d’équipe avec Microsoft Graph

Pour utiliser ces modèles, modifiez la propriété « template@odata.bind » dans le corps de la demande de « standard » en valeurs TemplateID ci-dessus. Pour plus d’informations sur le déploiement de modèles d’équipe, consultez l’article Graph Microsoft sur la [création d’une équipe](/graph/api/team-post?view=graph-rest-beta).

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

- [Créer une équipe à partir d’un modèle](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Utiliser des modèles d’équipe dans le Centre d’administration Teams](../../get-started-with-teams-templates-in-the-admin-console.md)
- [Prise en main des modèles d’équipe à l’aide de Microsoft Graph](../../get-started-with-teams-templates.md)
- [Prise en main de Teams pour les organismes de santé](/microsoft-365/frontline/teams-in-hc?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)