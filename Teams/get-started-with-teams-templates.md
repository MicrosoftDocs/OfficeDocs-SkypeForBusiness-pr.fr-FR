---
title: Commencer avec les modèles d’équipe
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 7850ad245eebee96b6852e7f0cc57a35adcca9f7
ms.sourcegitcommit: 8a56ed2107dfa378864576d1e137ab0086f5da08
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2018
ms.locfileid: "23996247"
---
# <a name="get-started-with-teams-templates"></a>Commencer avec les modèles d’équipe 

Définitions de structure d’une équipe conçu autour d’un projet ou les besoins de l’entreprise, les modèles d’équipe sont prédéfinies. Vous pouvez utiliser les modèles d’équipe pour créer rapidement des espaces de collaboration riche avec des canaux pour les différentes rubriques et préinstaller les applications pour extraire des services et contenu critique. Les modèles d’équipe fournissent une structure de l’équipe prédéfinies qui peut vous aider à créer facilement des équipes cohérentes au sein de votre organisation. 

Dans cet article, nous expliquerons les propriétés qui peuvent être définies dans des modèles, le modèle de base sont de types, et comment vous pouvez utiliser quelques exemples de demandes pour créer une équipe à partir d’un modèle.
 
Cet article est pour vous si vous êtes :

• Responsable de la planification, le déploiement et la gestion de plusieurs équipes sur le développeur de votre organisation • une recherche pour créer une équipe avec prédéfinies canaux et applications par programme

## <a name="team-template-capabilities"></a>Fonctionnalités de modèle d’équipe

La plupart des propriétés dans une équipe sont inclus et pris en charge par les modèles. Toutefois, il existe quelques propriétés et les fonctionnalités qui ne sont actuellement pas pris en charge. Le tableau suivant fournit un résumé rapide de contenu, et ce qui n’est pas inclus dans les modèles d’équipe.

| **Propriétés de l’équipe pris en charge par les modèles d’équipe** | **Propriétés de l’équipe n’est pas encore pris en charge par les modèles d’équipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Type de modèle de base | Appartenance de l’équipe |
| Nom de l'équipe | Image de l’équipe |
| Description de l’équipe | Paramètres de canal (par exemple, auto-favori et confidentialité) |
| Visibilité de l’équipe (publique ou privée) | Connecteurs |
| Paramètres d’équipe (par exemple, membre, invité, @ mentions) | Fichiers et contenu |
| Canal automatique-favoris | |
| Application installée | |
| Onglets affichés | | 

> [!NOTE]
> Nous allons ajouter davantage de fonctionnalités de modèle dans les versions futures de Microsoft Teams, donc vérifier les informations les plus récentes sur les propriétés prises en charge.

## <a name="what-are-base-template-types"></a>Quels sont les types de modèle de base ?

Types de modèle de base des modèles spéciales créé par Microsoft pour industries spécifiques. Ces modèles de base contiennent souvent des applications qui ne sont pas disponibles dans les propriétés du magasin et l’équipe n’est pas encore individuellement pris en charge dans les modèles d’équipe.

Une fois qu’un type de modèle de base est défini, vous pouvez étendre ou remplacer ces modèles spéciaux avec les propriétés supplémentaires que vous souhaitez spécifier. Toutefois, certains types de modèle de base contiennent des propriétés qui ne peut pas être remplacées. 

Par défaut, le modèle de base est défini à **Standard** qui ne contient pas les applications propriétaires supplémentaires ou des propriétés spéciales. Voici la liste actuelle des types de modèles de base disponibles.

| Type de modèle de base | baseTemplateId | Applications propriétaires de modèle de base et des propriétés spéciales |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | Aucune propriétés et applications supplémentaires |
| Prestataires - coordination de soins | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | Applications :<br/> -Application patients (épinglée sur l’onglet **Général** )<br/> <br/>Canaux : <br/> -Annonces<br/> -DIABETE<br/> -Des<br/> -Registered personnel |
| Prestataires - processus clin de œil | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | Canaux :<br/> -Évitables décès<br/> -Passer en revue les mortalité <br/> -Prévention des appartient à <br/> -Plans SEPSIE |
| Formation - classe équipe<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | Applications :<br/> -OneNote classe bloc-notes (épinglés sur l’onglet **Général** ) <br/> -Application affectations (épinglée sur l’onglet **Général** ) <br/><br/> Propriétés de l’équipe <br/> -Visibilité de l’équipe valeur **HiddenMembership** (ne peut pas être modifiée) |
| Formation - personnel de l’équipe<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | Applications<br/> -Bloc-notes personnel (épinglés sur l’onglet **Général** ) |

Publication en retard de 2018, octobre <sup>1</sup>

> [!NOTE]
> Nous allons ajouter d’autres modèle de base de types dans les futures versions de Microsoft Teams, afin de rechercher dans les informations les plus récentes sur les propriétés prises en charge.

## <a name="examples"></a>Exemples 

Vous pouvez commencer à créer une équipe via le modèle à l’installation de [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).

### <a name="create-a-team-from-a-template"></a>Créer une équipe à partir d’un modèle

#### <a name="requests"></a>Demandes

**Demande de création d’une équipe avec le modèle de base standard**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

**Demande de créer une équipe avec un canal supplémentaire et ne pas autoriser les membres de supprimer des canaux**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

**Demande de création d’une équipe avec toutes les propriétés prises en charge**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a>Réponse

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
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

- [Équipe de création](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (en aperçu)
- [Nouvelle équipe](https://docs.microsoft.com/en-us/powershell/module/teams/New-Team?view=teams-ps)
- [Formation à Microsoft Teams pour les administrateurs](itadmin-readiness.md)