---
title: Modèles d’équipe pour les petites et moyennes entreprises créés avec Microsoft Graph
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Utilisez Microsoft Teams modèles prédéfinis créés dans Microsoft Graph pour créer rapidement et facilement des équipes pour les petites et moyennes entreprises.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5317b989bd7fe77f34743b6554cd356c226c2fa8
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646303"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Modèles d’équipe intégrés à Microsoft Graph pour les petites et moyennes entreprises

Les modèles d’équipe dans Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant une structure d’équipe prédéfinie de paramètres, de canaux et d'applications préinstallées.

Pour les petites et moyennes entreprises, les modèles peuvent être particulièrement puissants, car ils vous aident à déployer rapidement Teams au sein de votre organisation. Les modèles aident également les utilisateurs à s’orienter sur la façon d’utiliser efficacement Teams. Cet article vous est destiné si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation.

Nous proposons actuellement trois modèles prédéfinits pour les petites et moyennes entreprises que vous pouvez utiliser dans différentes situations. Tous les modèles créent des équipes *privées* . Une fois les équipes créées et prêtes à être déployées dans votre organisation, vous pouvez définir la confidentialité sur *Org-Wide* ou *Public*, le cas échéant.

Pour en savoir plus sur les modèles d’équipe en général, consultez [Démarrage avec des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>modèle Company-Wide

Le modèle Company-Wide est destiné à la communication et à la collaboration pour l’ensemble de l’entreprise. Vous pouvez utiliser le canal Général pour les annonces à l’échelle de l’entreprise, les actualités du secteur ou les postes de direction. Le canal ressources humaines est un excellent endroit pour consolider toutes les activités liées aux RH telles que les postes, l’intégration des nouveaux employés, la formation et le développement. Le canal Fun Stuff fournit une plateforme sociale pour tous les billets aléatoires et amusants.

| Type de modèle  | TemplateId | Propriétés fournies avec ce modèle de base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>À l’échelle de l’entreprise | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canaux <ul><li>Général\*</li><li>Ressources humaines\*</li><li>Trucs amusants\*</li></ul><br> Applications<ul><li>Portail d'entreprise (site web épinglé au canal **Ressources humaines**) </li> </UL><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Privé</li></ul> |

*Canaux favoris automatiques 

Pour créer l’équipe Company-Wide en prenant les paramètres par défaut à partir du modèle prédéfini, fournissez la représentation JSON de l’objet d’équipe dans le corps de la requête. Pour en savoir plus sur le déploiement de modèles d’équipe, consultez l’article Microsoft Graph [sur la création d’une équipe](/graph/api/team-post?view=graph-rest-beta).

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

## <a name="executive-team-template"></a>Modèle d’équipe de direction

Le modèle d’équipe de direction est idéal pour créer une équipe permettant aux cadres de l’entreprise de communiquer et de collaborer sur des initiatives d’entreprise telles que les priorités annuelles, les budgets budgétaires, les initiatives stratégiques et les principaux clients. Ce modèle est fourni avec un canal *privé* pour inviter des utilisateurs sélectionnés pour des rubriques spécifiques.

| Type de modèle  | TemplateId | Propriétés fournies avec ce modèle de base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Équipe des cadres | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canaux <ul><li>Général\*</li><li>Privé \*</li></ul> Applications<ul><li>OneNote (épinglé au canal **privé**)</li> <li>Planificateur (épinglé au canal **privé** ) </li></ul><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Privé</li></ul> | 

*Canaux favoris automatiques<br>

Pour créer l’équipe Executives en prenant les paramètres par défaut à partir du modèle prédéfini, fournissez la représentation JSON de l’objet d’équipe dans le corps de la requête. Pour en savoir plus sur le déploiement de modèles d’équipe, consultez l’article Microsoft Graph [sur la création d’une équipe](/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Demande 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>Modèle d’équipe départementale

Le modèle d’équipe départemental peut être utilisé pour créer une équipe pour des ministères individuels ou pour des projets. Le modèle d’équipe Finance est idéal pour tous les billets, annonces et collaboration et communication quotidiennes au sein des membres de l’équipe Finance et des membres de l’équipe de direction, le cas échéant. Le modèle est fourni avec un canal *privé* pour inviter des utilisateurs sélectionnés pour des rubriques spécifiques.

Nous fournissons également le script ci-dessous pour l’équipe finance qui peut être utilisé pour étendre le modèle à des services supplémentaires ou des projets spécifiques en ajoutant, en supprimant ou en modifiant à votre goût. Par exemple, si vous avez un service *Marketing*, le script peut être adapté en renommant l’équipe *finance-marketing* pour créer une équipe marketing.

| Type de modèle | TemplateId | Propriétés fournies avec ce modèle de base |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>Finances  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canaux <ul><li>Général\*</li><li>Privé \*</li></ul><br> Applications<ul><li>OneNote (épinglé au canal **privé**)</li> <li>Planificateur (épinglé au canal **privé** ) </li> </ul><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Privé</li></ul> | 

*Canaux favoris automatiques

Pour créer l’équipe finance en prenant les paramètres par défaut à partir du modèle prédéfini, fournissez la représentation JSON de l’objet d’équipe dans le corps de la requête. Pour en savoir plus sur le déploiement de modèles d’équipe, consultez l’article Microsoft Graph [sur la création d’une équipe](/graph/api/team-post?view=graph-rest-beta).

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

### <a name="example-finance-team-template-extension-script"></a>Exemple : Script d’extension de modèle Finance Team

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

## <a name="related-topics"></a>Voir aussi

- [Utiliser des modèles d’équipe dans le Centre d’administration Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Prise en main des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md)
- [Créer une équipe](/graph/api/team-post?view=graph-rest-beta) (en préversion)
