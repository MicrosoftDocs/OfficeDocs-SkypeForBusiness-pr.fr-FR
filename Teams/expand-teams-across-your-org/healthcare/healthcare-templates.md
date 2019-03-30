---
title: Démarrage avec les modèles Teams pour les organismes de santé
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Démarrage avec les modèles Teams pour les organismes de santé
ms.openlocfilehash: 282c28661de3d2678f7b4b29129de4f80dece491
ms.sourcegitcommit: 89b866a3c383555f6f89dc77bebd74cddf9e40fb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013216"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Démarrage avec les modèles Teams pour les organismes de santé

Modèles Microsoft Teams permettent de rapidement et facilement créer des équipes en fournissant un modèle prédéfini de paramètres, les canaux et applications préinstallées.

Pour les organisations de santé, les modèles peuvent être particulièrement puissantes, comme leur fournissent une structure pour les utilisateurs de devenir orienté avec comment exploiter au mieux les équipes efficacement. Les modèles permettent également aux administrateurs de déployer des équipes cohérentes entre leurs organisations. Si vous êtes responsable de la planification, le déploiement et la gestion de plusieurs équipes au sein de votre organisation prestataires, cet article est pour vous.

Nous actuellement offre deux première partie prestataires modèles que vous pouvez exploiter pour de nombreuses situations. Pour en savoir plus sur l’équipe modèles en général, consultez [mise en route les modèles d’équipe](../../get-started-with-teams-templates.md).

## <a name="ward-template"></a>Modèle comté

Le modèle comté est destiné à la communication et de collaboration au sein d’un comté, module ou par service. Le modèle peut être utilisé afin de faciliter la gestion des patients, ainsi que des besoins opérationnels d’une comté. Par exemple, annonces comté peuvent être publiés dans le canal *annonces* et équipes peuvent être gérés dans *personnel*. Si vous avez besoin pour simplifier vos opérations comté, ce modèle est pour vous.

|Type de modèle de base |baseTemplateId |Canaux de modèle de base|
|:--- |:---|:---|
|Prestataires - comté | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Annonces\* <br> Huddles\* <br> Arrondit\* <br> Personnel\* <br> Formation\* |
|     | |         |

\*Auto-favorited

## <a name="hospital-template"></a>Modèle hôpital

Le modèle hôpital est destiné à la communication et la collaboration entre plusieurs départements au sein d’un hôpital, modules et longtemps. Inclus dans ce modèle sont plusieurs chaînes opérationnelles notamment *annonces*, *Custodial*et *pharmacie*, mais nous fournissons également un script ci-dessous qui étend le modèle avec une variété de service supplémentaires ou canaux centrées spécialisés que vous pouvez ajouter, supprimer ou modifier à votre convenance. Par exemple, si vous avez un service *Endocrinology* , mais que vous n’avez pas besoin un canal pour *ophtalmologie*, le script peut être adapté pour inclure une couche *Endocrinology* et de supprimer le canal *ophtalmologie* . Nous recommandons que ces spécialisés ou des canaux modélisés comté ne pas favorited automatique pour éviter la saturation de la notification. Utilisateurs sont généralement Favoris les canaux qu’ils rencontrent pertinentes.

|Type de modèle de base |baseTemplateId |Canaux de modèle de base|
|:--- |:---|:---|
|Prestataires - hôpital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Annonces\* <br> Conformité\* <br> Garde <br> Ressources humaines <br> Pharmacie |
| | |  |

\*Auto-favorited 

## <a name="how-to-use-first-party-templates"></a>Comment utiliser des modèles de première partie

Pour utiliser ces modèles, modifiez simplement la propriété 'template@odata.bind' dans le corps de la demande à partir de « standard » pour la TemplateIDs ci-dessus.  Pour plus d’informations sur la façon de déployer les modèles d’équipe, voir [l’article sur la création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)Microsoft Graph.

### <a name="example-hospital-template-extension-script"></a>Exemple : Script d’extension hôpital modèle

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
              "displayName": "Women’s Health",
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
