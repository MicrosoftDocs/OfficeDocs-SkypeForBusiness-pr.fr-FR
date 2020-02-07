---
title: Découvrir les modèles teams pour les petites et moyennes entreprises
author: kenwith
ms.author: kenwith
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Découvrir les modèles teams pour les petites et moyennes entreprises
ms.openlocfilehash: be42728387189f2281f892e5cc608f9e6f557b02
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837934"
---
# <a name="get-started-with-teams-templates-for-small-and-medium-businesses"></a>Découvrir les modèles teams pour les petites et moyennes entreprises

Les modèles Microsoft teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications préinstallées.

Pour les petites et moyennes entreprises, les modèles peuvent être particulièrement puissants, car ils permettent aux administrateurs de déployer rapidement des équipes au sein de leur organisation. Les modèles permettent également d’orienter les utilisateurs et de commencer à utiliser les équipes efficacement. Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation.

Pour l’instant, nous offrons trois modèles SMB de première partie que vous pouvez utiliser dans diverses situations. Tous les modèles créent une équipe *privée* . Une fois que vous avez créé les équipes et que vous êtes prêt à déployer votre organisation, vous pouvez définir le *niveau* de confidentialité en fonction de l’organisation ou du *public*, selon le cas. Pour en savoir plus sur les modèles d’équipe en général, voir [prendre en main les modèles](get-started-with-teams-templates.md)Teams.

## <a name="company-wide-template"></a>Modèle à l’échelle de l’entreprise
Le modèle à l’échelle de l’entreprise est destiné aux communications et à la collaboration pertinentes pour l’ensemble de la société. Vous pouvez utiliser le canal général pour les annonces à l’échelle de l’entreprise, les actualités du secteur ou les billets d’encadrement. Le canal de ressources humaines est l’endroit idéal pour consolider toutes les activités liées aux ressources humaines, telles que les billets de poste, l’intégration de nouveaux employés, la formation et le développement. Le canal amusant est une plate-forme de mise en place pour toutes les publications aléatoires et amusantes.

| Type de modèle de base  | baseTemplateId | Propriétés fournies avec ce modèle de base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| Secteur <br>À l’échelle de l’entreprise | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canaux <ul><li>Général\*</li><li>Ressources humaines\*</li><li>Outils amusants\*</li></ul><br> Applications<ul><li>Portail d’entreprise (site Web épinglé au canal **ressources humaines** ) </li> </UL><br>Propriétés d’équipe <ul><li>Visibilité de l’équipe définie sur privée</li></ul> |

* Canaux avec favoris automatique 

Pour créer une équipe à l’échelle de la société en utilisant les valeurs par défaut du modèle prédéfini, fournissez la représentation JSON de l’objet d’équipe dans le corps de la requête. Pour en savoir plus sur le déploiement de modèles d’équipes, voir l' [article Microsoft Graph sur la création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Demande 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a>Modèle d’équipe exécutive

Le modèle d’équipe exécutive est idéal pour créer une équipe destinée aux responsables de la société afin de communiquer et de collaborer sur des initiatives de société telles que des priorités annuelles, des budgets fiscaux, des initiatives stratégiques, des clients principaux, etc. Ce modèle est fourni avec un canal *privé* pour inviter des utilisateurs à sélectionner des rubriques spécifiques.

| Type de modèle de base  | baseTemplateId | Propriétés fournies avec ce modèle de base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| Secteur <br>Équipe de direction | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canaux <ul><li>Général\*</li><li>Vulnérabilité\*</li></ul> Applications<ul><li>OneNote (épinglé au canal **privé** )</li> <li>Planificateur (épinglé au canal **privé** ) </li></ul><br>Propriétés d’équipe <ul><li>Visibilité de l’équipe définie sur privée</li></ul> | 

* Canaux avec favoris automatique<br>

Pour créer l’équipe direction en prédéfinissant les valeurs par défaut du modèle prédéfini, fournissez la représentation JSON de l’objet équipe dans le corps de la requête. Pour en savoir plus sur le déploiement de modèles d’équipes, voir l' [article Microsoft Graph sur la création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Demande 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company’s leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>Modèle d’équipe département

Vous pouvez utiliser le modèle d’équipe départemental pour créer une équipe pour des services individuels ou pour des projets. Le modèle d’équipe Finance est idéal pour tous les billets, annonces, collaboration quotidienne et communication au sein des membres de l’équipe finance (et membres de l’équipe de direction, le cas échéant). Le modèle est fourni avec un canal *privé* pour inviter des utilisateurs à sélectionner des rubriques spécifiques. Nous fournissons également le script ci-dessous pour l’équipe finance qui peut être utilisée pour étendre le modèle à des services ou des projets spécifiques en ajoutant, supprimant ou en modifiant à votre gré. Par exemple, si vous avez un service *marketing* , le script peut être adapté en renommant l’équipe de *finance* en *marketing* pour créer une nouvelle équipe marketing.

| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| Secteur <br>Finances  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canaux <ul><li>Général\*</li><li>Vulnérabilité\*</li></ul><br> Applications<ul><li>OneNote (épinglé au canal **privé** )</li> <li>Planificateur (épinglé au canal **privé** ) </li> </ul><br>Propriétés d’équipe <ul><li>Visibilité de l’équipe définie sur privée</li></ul> | 

* Canaux avec favoris automatique

Pour créer l’équipe finance en prédéfinissant les valeurs par défaut du modèle prédéfini, fournissez la représentation JSON de l’objet équipe dans le corps de la requête. Pour en savoir plus sur le déploiement de modèles d’équipes, voir l' [article Microsoft Graph sur la création d’une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Demande 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a>Exemple : script d’extension du modèle d’équipe finance

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a>Rubriques connexes

- [Prise en main des modèles Teams](get-started-with-teams-templates.md)
- [Créer une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en Preview)

