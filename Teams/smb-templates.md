---
title: Modèles d’équipe pour petites et moyennes entreprises créés avec Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
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
description: Utilisez Microsoft Teams modèles prédéfinés créés dans Microsoft Graph pour créer rapidement et facilement des équipes pour les petites et moyennes entreprises.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 324470ffc3366750777c75776e4ae4e783dbb17f
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045680"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>Modèles d’équipe créés dans Microsoft Graph pour les petites et moyennes entreprises

Les modèles d’équipe Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d'applications préinstallées.

Pour les petites et moyennes entreprises, les modèles peuvent être particulièrement puissants, car ils vous aident à déployer rapidement des Teams au sein de votre organisation. Les modèles aident également les utilisateurs à s’orienter dans l’utilisation efficace d’Teams. Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation.

Nous proposons actuellement trois modèles pré-conçus pour les PETITES et moyennes entreprises que vous pouvez utiliser dans différentes situations. Tous les modèles créent *des équipes* privées. Une fois que vous avez créé les équipes et que  vous êtes prêt à déployer dans votre organisation, vous pouvez définir la confidentialité sur Échelle de l’organisation ou *Publique,* le cas échéant.

Pour en savoir plus sur les modèles d’équipe en général, voir Commencer à utiliser les [modèles d’équipe à](get-started-with-teams-templates.md)l’aide de Microsoft Graph.

## <a name="company-wide-template"></a>Company-Wide modèle

Le Company-Wide modèle est conçu pour la communication et la collaboration pour l’ensemble de l’entreprise. Vous pouvez utiliser le canal Général pour les annonces à l’échelle de l’entreprise, les actualités du secteur ou les publications de la direction. Le canal Ressources humaines est l’endroit idéal pour consolider toutes les activités RH, telles que les publications de poste, l’intégration des nouveaux employés, la formation et le développement. Le canal Outils amusants fournit une plateforme sociale pour toutes les publications aléatoires et amusantes.

| Type de modèle  | TemplateId | Propriétés fournies avec ce modèle de base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| PME - <br>À l’échelle de l’entreprise | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Canaux <ul><li>Général\*</li><li>Ressources humaines\*</li><li>Amusant\*</li></ul><br> Applications<ul><li>Portail d'entreprise (site web épinglé au **canal des ressources** humaines) </li> </UL><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Privé</li></ul> |

*Canaux favoris automatiquement 

Pour créer l’équipe Company-Wide en prenant les paramètres par défaut à partir du modèle prédéfiny, fournissez la représentation JSON de l’objet d’équipe dans le corps de la demande. Pour en savoir plus sur le déploiement des modèles d’équipe, consultez l’article Graph Microsoft [sur la création d’une équipe.](/graph/api/team-post?view=graph-rest-beta)

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

Le modèle d’équipe de direction est idéal pour créer une équipe pour que les cadres d’une entreprise communiquent et collaborent sur des initiatives d’entreprise telles que les priorités annuelles, les budgets budgétaires, les initiatives stratégiques et les principaux clients. Ce modèle est livré avec un *canal privé* pour inviter des utilisateurs spécifiques à des sujets spécifiques.

| Type de modèle  | TemplateId | Propriétés fournies avec ce modèle de base |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| PME - <br>Équipe cadres | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Canaux <ul><li>Général\*</li><li>Privé \*</li></ul> Applications<ul><li>OneNote (épinglé au **canal** privé)</li> <li>Planificateur (épinglé au **canal** privé) </li></ul><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Privé</li></ul> | 

*Canaux favoris automatiquement<br>

Pour créer l’équipe Cadres en prenant les paramètres par défaut à partir du modèle prédéfiny, fournissez la représentation JSON de l’objet d’équipe dans le corps de la demande. Pour en savoir plus sur le déploiement des modèles d’équipe, consultez l’article Graph Microsoft [sur la création d’une équipe.](/graph/api/team-post?view=graph-rest-beta)

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

## <a name="departmental-team-template"></a>Modèle d’équipe par département

Le modèle d’équipe par département peut être utilisé pour créer une équipe pour des services individuels ou pour des projets. Le modèle d’équipe Finances est idéal pour tous les billets, les annonces et la collaboration et la communication quotidiennes au sein des membres de l’équipe Finances et des membres de l’équipe de direction, le cas échéant. Le modèle est livré avec un *canal privé* pour inviter des utilisateurs spécifiques à des sujets spécifiques.

Nous fournissons également le script ci-dessous à l’équipe Finances, qui peut être utilisé pour étendre le modèle à d’autres départements ou projets spécifiques en l’ajoutant, en le supprimant ou en le modifiez comme bon vous semble. Par exemple, si vous avez un service marketing, le script peut  être  adapté en renommant l’équipe du service financier au service marketing pour créer une équipe marketing. 

| Type de modèle | TemplateId | Propriétés fournies avec ce modèle de base |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| PME - <br>Finances  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Canaux <ul><li>Général\*</li><li>Privé \*</li></ul><br> Applications<ul><li>OneNote (épinglé au **canal** privé)</li> <li>Planificateur (épinglé au **canal** privé) </li> </ul><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Privé</li></ul> | 

*Canaux favoris automatiquement

Pour créer l’équipe Finances en prenant les paramètres par défaut du modèle prédéfiny, fournissez la représentation JSON de l’objet d’équipe dans le corps de la demande. Pour en savoir plus sur le déploiement des modèles d’équipe, consultez l’article Graph Microsoft [sur la création d’une équipe.](/graph/api/team-post?view=graph-rest-beta)

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

### <a name="example-finance-team-template-extension-script"></a>Exemple : Script d’extension de modèle Équipe Finance

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
- [Créer une équipe](/graph/api/team-post?view=graph-rest-beta) (en prévisualisation)
