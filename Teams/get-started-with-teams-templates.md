---
title: Commencer avec les modèles d’équipe
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: Découvrez comment utiliser les modèles d’équipe pour créer une équipe avec des canaux prédéfinis.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801463"
---
# <a name="get-started-with-teams-templates"></a>Commencer avec les modèles d’équipe 

Définitions de structure d’une équipe conçu autour d’un projet ou les besoins de l’entreprise, les modèles d’équipe sont prédéfinies. Vous pouvez utiliser les modèles d’équipe pour créer rapidement des espaces de collaboration riche avec des canaux pour les différentes rubriques et préinstaller les applications pour extraire des services et contenu critique. Les modèles d’équipe fournissent une structure de l’équipe prédéfinies qui peut vous aider à créer facilement des équipes cohérentes au sein de votre organisation. 

Dans cet article, nous expliquerons les propriétés qui peuvent être définies dans des modèles, le modèle de base sont de types, et comment vous pouvez utiliser quelques exemples de demandes pour créer une équipe à partir d’un modèle.
 
Cet article est pour vous si vous êtes :

- Responsable de la planification, le déploiement et la gestion de plusieurs équipes au sein de votre organisation.<br>
- Un pour les développeurs souhaitant créer par programme une équipe avec les applications et les canaux prédéfinis 

## <a name="teams-template-capabilities"></a>Fonctionnalités de modèle d’équipes

La plupart des propriétés dans une équipe sont inclus et pris en charge par les modèles. Mais il existe quelques propriétés et les fonctionnalités qui ne sont pas actuellement pris en charge. Le tableau suivant fournit un résumé rapide de contenu, et ce qui n’est pas inclus dans les modèles d’équipe.

| **Propriétés de l’équipe pris en charge par les modèles d’équipe** | **Propriétés de l’équipe n’est pas encore pris en charge par les modèles d’équipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Type de modèle de base | Appartenance de l’équipe |
| Nom de l'équipe | Image de l’équipe |
| Description de l’équipe | Paramètres de canal |
| Visibilité de l’équipe (publique ou privée) | Connecteurs |
| Paramètres d’équipe (par exemple, membre, invité, @ mentions) | Fichiers et contenu |
| Canal automatique-favoris | |
| Application installée | |
| Onglets affichés | | 

> [!NOTE]
> Nous allons ajouter davantage de fonctionnalités de modèle dans les versions futures de Microsoft Teams, donc vérifier les informations les plus récentes sur les propriétés prises en charge.

## <a name="what-are-base-template-types"></a>Quels sont les types de modèle de base ?

Types de modèle de base des modèles spéciales créé par Microsoft pour industries spécifiques. Ces modèles de base contiennent souvent des applications qui ne sont pas disponibles dans les propriétés du magasin et l’équipe pas encore pris en charge individuellement dans les modèles d’équipe.

Une fois qu’un type de modèle de base est défini, vous pouvez étendre ou remplacer ces modèles spéciaux avec les propriétés supplémentaires que vous souhaitez spécifier. Mais certains types de modèle de base contiennent des propriétés qui ne peut pas être remplacées. 

Par défaut, le modèle de base est défini à **Standard** qui ne contient pas les applications propriétaires supplémentaires ou des propriétés spéciales. Voici la liste actuelle des types de modèles de base disponibles.

| Type de modèle de base | baseTemplateId | Applications propriétaires de modèle de base et des propriétés spéciales |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | Aucune propriétés et applications supplémentaires |
| Formation- <br>Classe de l’équipe<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | Applications :<ul><li>Bloc-notes OneNote de classe (épinglés sur l’onglet **Général** ) </li><li>Application des affectations (épinglée sur l’onglet **Général** )</li></ul> Propriétés de l’équipe :<ul><li>Visibilité de l’équipe définie sur **HiddenMembership** (ne peut pas être modifiée)</li></ul> |
| Formation-<br>Personnel de l’équipe<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | Applications :<ul><li>Bloc-notes OneNote de personnel (épinglés sur l’onglet **Général** )</li></ul> |
|Formation-<br>Équipe PLC |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | Applications :<ul><li>Bloc-notes OneNote de PLC (épinglés sur l’onglet **Général** )</ul></li>|
|||

Publication en retard de 2018, octobre <sup>1</sup>

> [!NOTE]
> Nous allons ajouter d’autres modèle de base de types dans les futures versions de Microsoft Teams, afin de rechercher dans les informations les plus récentes sur les propriétés prises en charge.

## <a name="examples"></a>Exemples 

Vous pouvez démarrer à l’aide d’un modèle pour créer une équipe à l’aide de l' [API de Microsoft Graph](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

### <a name="create-a-team-from-a-template"></a>Créer une équipe à partir d’un modèle

#### <a name="requests"></a>Demandes

**Demande de création d’une équipe avec le modèle de base standard**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

**Demande de créer une équipe avec un canal supplémentaire et ne pas autoriser les membres de supprimer des canaux**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

**Demande de création d’une équipe avec toutes les propriétés prises en charge**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a>Obtenir l’état

#### <a name="request"></a>Demande

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a>Réponse

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a>Rubriques connexes

- [Équipe de création](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en aperçu)
- [Nouvelle équipe](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Formation à Microsoft Teams pour les administrateurs](itadmin-readiness.md)