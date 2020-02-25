---
title: Canaux privés dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer des canaux privés dans Microsoft Teams.
ms.openlocfilehash: 761d6a06da6bb02991e706f6e18ac8ce7d4106f4
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265629"
---
# <a name="private-channels-in-microsoft-teams"></a>Canaux privés dans Microsoft teams

Dans Microsoft Teams, les canaux privés créent des espaces dédiés à la collaboration au sein de vos équipes. Seuls les utilisateurs de l’équipe qui sont propriétaires ou membres du canal privé peuvent accéder au canal. Tout le monde, y compris les invités, peut être ajouté en tant que membre d’un canal privé tant qu’il est déjà membre de l’équipe.

Vous souhaiterez peut-être utiliser un canal privé si vous souhaitez limiter la collaboration aux personnes qui ont besoin de savoir si vous voulez faciliter la communication entre un groupe de personnes affectées à un projet spécifique, sans avoir à créer une équipe supplémentaire à gérer.

Par exemple, un canal privé est utile dans les cas suivants :

- Un groupe de personnes d’une équipe souhaite disposer d’un espace ciblé pour collaborer sans avoir à créer une équipe séparée.
- Un sous-ensemble de personnes d’une équipe a besoin d’un canal privé pour discuter des informations sensibles, telles que les budgets, la réapprovisionnement, le positionnement stratégique, etc.

Une icône de verrou indique un canal privé. Seuls les membres de canaux privés peuvent afficher les canaux privés qu’ils ont ajoutés et y participer.

![Capture d’écran de canaux privés dans une équipe](media/private-channels-in-teams.png)

## <a name="what-you-need-to-know-about-private-channels"></a>Ce que vous devez savoir sur les canaux privés

Pour l’instant, les canaux privés prennent en charge les connecteurs et les onglets (à l’exception du flux, du planificateur et des formulaires). Nous travaillons à la prise en charge des applications complètes pour les canaux privés, y compris les extensions de messagerie et les robots.

Chaque équipe peut avoir au maximum 30 canaux privés et chaque canal privé peut avoir au maximum 250 membres. La limite de 30 canaux privés est en plus de la 200 canal de canal privé par équipe.

> [!NOTE]
> Dans la plupart des cas, nous ajoutons des capacités aux canaux privés, vous pouvez consulter les informations les plus récentes relatives aux applications, aux réunions de canal et à la mise à l’échelle des canaux privés pour les équipes de grande envergure.

## <a name="when-to-create-a-private-channel"></a>Quand créer un canal privé

Pour déterminer si un canal privé est approprié, prenez en considération les questions suivantes sur les personnes qui doivent collaborer et la collaboration.

|Existe-t-il déjà une équipe ayant ces personnes en tant que membres d’équipe ?  |Est-ce que cette tâche doit rester privée d’autres personnes ?  |Existe-t-il plusieurs rubriques distinctes à aborder ?  |Recommandation  |
|---------|---------|---------|---------|
|Oui       |Oui          |Oui          |Créez un canal privé dans l’équipe existante ou envisagez de créer des canaux privés dédiés pour chaque sujet.         |
|Oui      |Oui         |Non         |Créer un canal privé dans l’équipe existante.         |
|Oui     |Non         |Non         |Créer un canal dans l’équipe existante.         |
|Non     |Non         |Non         |Envisagez de créer une équipe.         |
|Non     |Non         |Oui         |Envisagez de créer une équipe puis, en fonction de la confidentialité de chaque sujet, envisagez de créer des canaux standard ou privés distincts pour chaque sujet.         |
|Non     |Oui         |Non         |Créez une nouvelle équipe et envisagez de créer un canal privé.         |

Lorsqu’un canal privé est créé, il est lié à l’équipe parente et ne peut pas être déplacé vers une autre équipe. Par ailleurs, les canaux privés ne peuvent pas être convertis en canaux standard, et inversement.

## <a name="private-channel-creation-and-membership"></a>Création et appartenance de canal privé

### <a name="who-can-create-private-channels"></a>Qui peut créer des canaux privés ?

Par défaut, tous les propriétaires d’équipe ou membre d’équipe peuvent créer un canal privé. Les invités ne peuvent pas les créer. La possibilité de créer des canaux privés peut être gérée au niveau de l’équipe et au niveau de l’Organisation :

- Dans l’onglet **paramètres** d’une équipe, les propriétaires d’équipe peuvent désactiver ou activer la possibilité pour les membres de créer des canaux privés.
- En tant qu’administrateur, vous pouvez utiliser des [stratégies](teams-policies.md) pour contrôler les utilisateurs de votre organisation qui sont autorisés à créer des canaux privés.

La personne qui crée un canal privé est le propriétaire du canal privé et seul le propriétaire du canal privé peut directement ajouter ou supprimer des personnes. Un propriétaire de canal privé peut ajouter n’importe quel membre d’équipe à un canal privé qu’il a créé, y compris aux invités. Les membres d’un canal privé disposent d’un espace de conversation sécurisé et lors de l’ajout de nouveaux membres, ils peuvent voir toutes les conversations (même les anciennes conversations) dans ce canal privé.

### <a name="what-happens-when-a-team-member-leaves-or-is-removed-from-a-team"></a>Que se passe-t-il lorsqu’un membre d’équipe quitte une équipe ou est supprimé de celle-ci ?

Si un membre d’équipe quitte une équipe ou est supprimé de celle-ci, il sera également supprimé de tous les canaux privés de l’équipe. Si l’utilisateur est rajouté à l’équipe, il doit être rajouté aux canaux privés de l’équipe.

### <a name="what-happens-when-a-private-channel-owner-is-removed-from-a-private-channel"></a>Que se passe-t-il si un propriétaire de canal privé est supprimé d’un canal privé ?

Le propriétaire d’un canal privé ne peut pas être supprimé via le client teams s’il s’agit du dernier propriétaire d’un ou de plusieurs canaux privés.

Si un propriétaire de canal privé quitte votre organisation ou s’il est supprimé du groupe Office 365 associé à l’équipe, un membre du canal privé est promu automatiquement en tant que propriétaire de canal privé.

### <a name="what-can-team-owners-and-team-members-see-in-a-private-channel"></a>Que peuvent voir les propriétaires d’équipe et les membres d’une équipe dans un canal privé ?

Les propriétaires d’équipe peuvent afficher les noms de tous les canaux privés dans leur équipe et peuvent également supprimer un canal privé de l’équipe. (Un canal privé supprimé peut être restauré dans les 30 jours suivant sa suppression). Les propriétaires d’équipe ne peuvent pas voir les fichiers dans un canal privé ou les conversations et la liste de membres d’un canal privé, sauf s’ils sont membres de ce canal privé.

Le tableau suivant indique qui peut voir ce qui se trouve dans un canal privé.

|Option  |Le propriétaire de l’équipe peut voir |Les membres d’une équipe peuvent voir |
|---------|---------|---------|
|Nom et description    |Tous les canaux privés de l’équipe         |Uniquement les canaux privés auxquels ils sont ajoutés         |
|Conversations et onglets     |Uniquement lorsqu’elle est ajoutée au canal privé         |Uniquement lorsqu’elle est ajoutée au canal privé         |
|Fichiers et contenu    |Uniquement lorsqu’elle est ajoutée au canal privé        |Uniquement lorsqu’elle est ajoutée au canal privé         |
|Propriétaire du canal privé    |Tous les canaux privés de l’équipe        |Uniquement lorsqu’elle est ajoutée au canal privé         |
|Date de la dernière activité  |Tous les canaux privés de l’équipe       |Uniquement lorsqu’elle est ajoutée au canal privé         |

## <a name="manage-private-channels"></a>Gérer les canaux privés

Le tableau ci-après décrit les actions que les propriétaires, membres et invités peuvent faire dans les canaux privés.

|Action  |Propriétaire de l’équipe|Membre de l’équipe|Invité d’équipe|Propriétaire du canal privé|Membre du canal privé|Invité du canal privé|
|---------|---------|---------|---------|---------|---------|---------|
|Créer un canal privé|Oui <sup>1</sup>|Oui<sup>, 1, 2</sup>|Non|N/A|N/D|N/D|
|Supprimer un canal privé|Oui|Non|Non|Oui|Non|Non|
|Quitter un canal privé|N/D|N/D|N/D|Oui<sup>3</sup>|Oui |Oui |
|Modifier un canal privé|Non|N/A|N/D|Oui|Non|Non|
|Restaurer un canal privé supprimé|Oui|Non|Non|Oui|Non|Non|
|Ajouter des membres|Non|N/A|N/D|Oui|Non|Non|
|Modifier les paramètres|Non|N/A|N/D|Oui|Non|Non|
|Gérer les onglets et les applications|Non|N/A|N/A|Yes<sup>4</sup>|Oui<sup>5</sup>|Non|

<sup>1</sup> en supposant que vous, l’administrateur, configuré, autorise l’utilisateur à créer des canaux privés.<br>
<sup>2</sup> chaque équipe dispose d’un paramètre que les propriétaires d’équipe peuvent activer ou désactiver pour autoriser les membres de l’équipe à créer des canaux privés. Les propriétaires d’équipe peuvent toujours créer des canaux privés.<br>
<sup>3</sup> en supposant que le propriétaire du canal privé n’est pas le dernier propriétaire du canal. <br>
<sup>4</sup> nécessite que l’équipe dispose d’une application installée pour pouvoir l’utiliser sur un canal privé.<br>
<sup>5</sup> les propriétaires de canal privé peuvent configurer cet affichage.

### <a name="manage-private-channel-membership-and-settings"></a>Gérer l’appartenance aux canaux privés et les paramètres

Chaque canal privé possède ses propres paramètres, y compris la possibilité d’ajouter et de supprimer des membres, d’ajouter des onglets et de @mentioning pour l’ensemble du canal. Ces paramètres sont indépendants des paramètres d’équipe parents. Lorsqu’un canal privé est créé, il hérite des paramètres de l’équipe parent, après quoi ses paramètres peuvent être modifiés indépendamment des paramètres de l’équipe parent.

Le propriétaire du canal privé peut cliquer sur **gérer le canal**, puis utiliser les onglets **membres** et **paramètres** pour ajouter ou supprimer des membres et modifier les paramètres.  

![Capture d’écran de paramètres de canal privé](media/private-channels-in-teams-channel-settings.png)

## <a name="manage-the-life-cycle-of-private-channels"></a>Gérer le cycle de vie des canaux privés

Pour obtenir des instructions sur la gestion du cycle de vie des canaux privés au sein de votre organisation, voir [gérer le cycle de vie des canaux privés dans teams](private-channels-life-cycle-management.md) . Cela comprend comment contrôler si les utilisateurs de votre organisation peuvent créer des canaux privés, créer un canal privé pour le compte d’un propriétaire d’équipe, et obtenir la liste de tous les messages de canal privé à des fins d’archivage et d’audit, ainsi que d’autres tâches de gestion.  

## <a name="private-channel-sharepoint-sites"></a>Sites SharePoint de canal privé

Chaque canal privé dispose de sa propre collection de sites SharePoint optimisée pour le partage de fichiers et la mise en service rapide. La collection de sites séparée est de garantir que l’accès aux fichiers de canal privé est limité uniquement aux membres du canal privé par rapport au site d’équipe où les propriétaires d’équipe ont accès à toutes les ressources au sein de la collection de sites. Ces collections de sites sont créées à l’aide d’une bibliothèque de documents par défaut, et peuvent être facilement améliorées dans une collection de sites complète via l' [interface de gestion de site](https://support.office.com/article/Enable-or-disable-site-collection-features-A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Chaque collection de sites est créée dans la même zone géographique que la collection de sites de l’équipe parente. Ces sites légers possèdent un ID de modèle personnalisé, « TEAMCHANNEL # 0 », pour faciliter la gestion via PowerShell et l’API Graph.  Le mode de création n’est pas visible dans le centre d’administration SharePoint.

Pour prendre en charge un plus grand nombre de collections de sites par client, la limite est passée de 500 000 à 2 millions. Une collection de sites de canal privé synchronise la classification des données et hérite des autorisations d’accès invité de la collection de sites de l’équipe parente.  L’appartenance au propriétaire de la collection de sites et aux groupes de membres reste synchronisée avec l’appartenance du canal privé au sein d’Teams. Toute modification apportée à l’appartenance des groupes de propriétaires ou de membres dans SharePoint Online sera automatiquement enregistrée en tant qu’appartenance au canal privé dans les quatre heures. Dans les scénarios où certains utilisateurs ont besoin d’accéder à des documents sans avoir besoin d’accéder à des messages de canal privé, ajoutez-les au groupe visiteurs sur le site ou à un nouveau groupe qui est différent des propriétaires et des membres.

Teams gère le cycle de vie de la collection de sites SharePoint du canal privé. Si la collection de sites est supprimée en dehors de teams, un travail en arrière-plan restaure le site dans un délai de quatre heures tant que le canal privé est toujours actif. Si le site est supprimé et supprimé définitivement, une nouvelle collection de sites est mise en service pour le canal privé.

Si un canal privé ou une équipe contenant un canal privé est restauré, les collections de sites y sont restaurées. Si une collection de sites de canal privé est restaurée et qu’elle se trouve au-delà de la fenêtre de suppression du canal privé de 30 jours, la collection de sites opère en tant que collection de sites autonome.

## <a name="private-channel-message-compliance-records"></a>Enregistrements de conformité des messages de canal privé

Les enregistrements de messages envoyés dans un canal privé sont remis à la boîte aux lettres de tous les membres du canal privé plutôt qu’à une boîte aux lettres de groupe. Les titres des enregistrements sont mis en forme pour indiquer le canal privé depuis lequel ils ont été envoyés.

Pour plus d’informations sur l’exécution d’une recherche eDiscovery sur des messages de canal privé, voir [découverte électronique des canaux privés](ediscovery-investigation.md#ediscovery-of-private-channels).

## <a name="considerations-around-access-in-private-channels"></a>Considérations relatives à l’accès dans les canaux privés

Lors de la création d’un bloc-notes OneNote dans un canal privé, les utilisateurs supplémentaires peuvent toujours accéder au bloc-notes, car le comportement est identique à celui de partage d’accès à tout autre élément d’un site SharePoint de canal privé avec un utilisateur.

Si un utilisateur dispose d’un accès à un bloc-notes dans un canal privé par le biais de SharePoint, la suppression de l’utilisateur de l’équipe ou du canal privé ne supprime pas l’accès de l’utilisateur au bloc-notes.

Si un bloc-notes existant est ajouté en tant qu’onglet à un canal privé, l’accès au canal privé n’est pas modifié. Ce qui signifie que :

- Par défaut, tout le monde n’a pas accès au bloc-notes. En effet, ils ne peuvent pas avoir accès à l’emplacement de l’hébergement du bloc-notes, par exemple le site SharePoint d’un autre équipe.
- Les utilisateurs qui ne sont pas membres du canal privé peuvent afficher le bloc-notes.  

## <a name="related-topics"></a>Rubriques connexes

- [Présentation des équipes et des canaux dans Microsoft Teams](teams-channels-overview.md)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
- [Utiliser l’API Microsoft Graph pour travailler avec des équipes](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
