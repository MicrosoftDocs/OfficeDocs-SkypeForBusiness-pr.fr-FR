---
title: Modèles d’organisations de santé
author: kenwith
ms.author: kenwith
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Utilisez les modèles de Microsoft teams pour créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: db6475c3d7c4be6242c1befb988b240b9efcab42
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904726"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Démarrage avec les modèles Teams pour les organismes de santé

Les modèles Microsoft teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications préinstallées.

Pour les entreprises de santé, les modèles peuvent être particulièrement puissants, car ils permettent aux utilisateurs de se familiariser avec l’utilisation des équipes efficacement. Les modèles permettent également aux administrateurs de déployer des équipes cohérentes au sein de leurs organisations. Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de santé.

Nous proposons actuellement deux modèles de soins de santé que vous pouvez utiliser pour différentes situations. Pour en savoir plus sur les modèles d’équipe en général, voir [prendre en main les modèles](../../get-started-with-teams-templates.md)Teams.

## <a name="ward-template"></a>Modèle vers le haut

Le modèle à l’envers est destiné à la communication et à la collaboration dans une direction, une pod ou un service. Le modèle peut être utilisé pour faciliter la gestion du patient, ainsi que pour les besoins de fonctionnement de a à l’envers. Par exemple, les annonces à l’envers peuvent être publiées dans le canal *annonces* et les équipes peuvent être gérées en *équipe*. Si vous cherchez à rationaliser vos opérations à l’envers, ce modèle vous appartient.

|Type de modèle de base |baseTemplateId |Canaux de modèles de base|
|:--- |:---|:---|
|Soins de santé-au | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Annonces\* <br> Huddles\* <br> Négative\* <br> Spécifient\* <br> Formation\* |
|     | |         |

\*Favoris automatique

## <a name="hospital-template"></a>Modèle d’hôpital

Le modèle d’hôpital est destiné à la communication et à la collaboration entre divers services, modules et services d’un hôpital. Il s’agit de nombreux canaux opérationnels, y compris les *annonces*, la *privative*d’emploi et la *pharmacie*, mais nous proposons également un script ci-dessous qui étend le modèle à un large éventail de canaux centrés sur des services ou des spécialisations, que vous pouvez ajouter, supprimer ou modifier selon vos souhaits. Par exemple, si vous avez un service *Endocrinology* , mais que vous n’avez pas besoin d’un canal pour *Ophthalmology*, le script peut être adapté pour inclure un canal *Endocrinology* et supprimer le canal *Ophthalmology* . Nous vous conseillons de ne pas ajouter de favoris automatique pour ces canaux spécialisés ou les canaux à l’envers. En général, les utilisateurs favoris sont les canaux qu’ils recherchent.

|Type de modèle de base |baseTemplateId |Canaux de modèles de base|
|:--- |:---|:---|
|Healthcare-hôpital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Annonces\* <br> Conformément\* <br> Privatives de Troie <br> Ressources humaines <br> Pharmaceutiques |
| | |  |

\*Favoris automatique 

## <a name="how-to-use-first-party-templates"></a>Utilisation de modèles de première partie

Pour utiliser ces modèles, il vous suffit de changer la propriété « template@odata. bind » dans le corps de la requête de « standard » vers le TemplateIDs ci-dessus.  Pour plus d’informations sur le déploiement de modèles d’équipe, voir l’article Microsoft Graph sur la [création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Les canaux du modèle sont automatiquement créés sous l’onglet général.

### <a name="example-hospital-template-extension-script"></a>Exemple : script d’extension de modèle d’hôpital

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

## <a name="related-topics"></a>Sujets associés

[Prise en main des modèles Teams](../../get-started-with-teams-templates.md)

[Prise en main de Teams pour les organismes de santé](teams-in-hc.md)
