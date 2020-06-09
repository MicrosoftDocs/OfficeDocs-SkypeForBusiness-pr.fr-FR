---
title: Canaux privés dans Microsoft Teams
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
description: Découvrez comment utiliser et gérer les canaux privés dans Microsoft Teams.
ms.openlocfilehash: 769fd2b489d65b276823abd7c3ff8f579100617a
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637933"
---
# <a name="private-channels-in-microsoft-teams"></a>Canaux privés dans Microsoft Teams

Les canaux privés dans Microsoft Teams créent des espaces ciblés pour la collaboration au sein de vos équipes. Seuls les utilisateurs de l’équipe qui sont propriétaires ou membres du canal privé peuvent accéder au canal. Tous les utilisateurs, notamment les invités, peuvent être ajoutés en tant que membre d’un canal privé, dès lors qu’ils sont déjà membres de l’équipe.

Vous souhaiterez peut-être utiliser un canal privé si vous voulez limiter la collaboration à ceux qui en ont besoin ou si vous souhaitez faciliter la communication entre un groupe de personnes affectées à un projet spécifique, sans avoir à créer une équipe supplémentaire à gérer.

Par exemple, un canal privé est utile dans les cas suivants :

- Certains membres d’une équipe souhaite utiliser un espace ciblé pour collaborer sans avoir à créer une équipe distincte.
- Un sous-groupe de personnes dans une équipe souhaite disposer d'un canal privé pour discuter d'informations sensibles, telles que les budgets, les ressources, le positionnement stratégique, etc.

Une icône de verrouillage indique un canal privé. Seuls les membres des canaux privés peuvent voir et participer aux canaux privés auxquels ils sont ajoutés.

![Capture d’écran des canaux privés dans une équipe](media/private-channels-in-teams.png)

## <a name="what-you-need-to-know-about-private-channels"></a>Ce que vous devez savoir sur les canaux privés

Actuellement, les canaux privés prennent en charge les connecteurs et les onglets (à l’exception de Stream, Planner et Forms). Nous travaillons à la prise en charge complète des applications pour les canaux privés, y compris les extensions et les robots.

Chaque équipe peut avoir un maximum de 30 canaux privés et chaque canal privé peut avoir au maximum 250 membres. La limite des 30 canaux privés vient s’ajouter à la limite des 200 canaux standard par équipe.

> [!NOTE]
> Nous ajoutons continuellement des capacités aux canaux privés, vous pouvez ainsi consulter les informations les plus récentes sur les applications, les réunions de canal et la mise à l'échelle des canaux privés pour les grandes équipes.

## <a name="when-to-create-a-private-channel"></a>Quand créer un canal privé

Pour déterminer si un canal privé est adapté, demandez-vous quelles sont les personnes qui doivent travailler ensemble et quel est le sujet de cette collaboration.

|Ces personnes font-elles déjà parties d’une équipe ?  |Ce travail doit-il rester privé ?  |Y a-t-il différents sujets à aborder ?  |Recommandation  |
|---------|---------|---------|---------|
|Oui      |Oui         |Oui         |Créer un canal privé au sein de l’équipe existante ou envisager de créer des canaux privés dédiés pour chaque sujet.         |
|Oui     |Oui         |Non         |Créer un canal privé dans l’équipe existante.         |
|Oui     |Non         |Non         |Créer un canal dans l’équipe existante.         |
|Non     |Non         |Non         |Envisager la création d’une nouvelle équipe.         |
|Non     |Non         |Oui         |Envisager de créer une équipe, puis, en fonction du niveau de confidentialité, créer des canaux standard ou privés distincts pour chaque sujet.         |
|Non     |Oui         |Non         |Créer une équipe et envisager de créer un canal privé.         |

Lors de la création d’un canal privé, celui-ci est lié à l’équipe parente et ne peut pas être déplacé vers une autre équipe. De plus, les canaux privés ne peuvent pas être convertis en canaux standard et vice-versa.

## <a name="private-channel-creation-and-membership"></a>Création et adhésion à un canal privé 

### <a name="who-can-create-private-channels"></a>Qui peut créer des canaux privés ?

Par défaut, tout membre ou propriétaire d’une équipe peut créer un canal privé. Les invités ne peuvent pas les créer. La possibilité de créer des canaux privés peut être gérée au niveau de l’équipe et au niveau de l’organisation.

> 1. Accédez au centre d’administration à l’adresse <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

> 2. Utiliser des [stratégies](teams-policies.md) pour contrôler les utilisateurs de votre organisation qui sont autorisés à créer des canaux privés.
    Une fois que vous avez défini les stratégies, les propriétaires d’équipe peuvent désactiver ou activer la possibilité pour les membres de créer des canaux privés dans l’onglet **paramètres** d’une équipe.

La personne qui crée un canal privé est le propriétaire de ce canal et elle est la seule a pouvoir directement y ajouter ou en supprimer des utilisateurs. Un propriétaire de canal privé peut ajouter un membre d’équipe à un canal privé qu’il a créé, même des invités. Les membres d’un canal privé disposent d’un espace de conversation sécurisé, et lorsque de nouveaux membres sont ajoutés, ils peuvent voir toutes les conversations (y compris les anciennes) de ce canal privé.

### <a name="what-happens-when-a-team-member-leaves-or-is-removed-from-a-team"></a>Que se passe-t-il lorsqu’un membre d’une équipe quitte ou est supprimé d’une équipe ?

Si un membre d’une équipe quitte ou est supprimé d’une équipe, cet utilisateur quitte ou est supprimé également de tous les canaux privés au sein de l’équipe. Si l'utilisateur est réintégré dans l'équipe, il doit être réintégré dans les canaux privés de l'équipe.

### <a name="what-happens-when-a-private-channel-owner-is-removed-from-a-private-channel"></a>Que se passe-t-il lorsqu’un propriétaire de canal privé est supprimé d’un canal privé ?

Un propriétaire de canal privé ne peut pas être supprimé via le client Teams s’il est le dernier propriétaire d’un ou plusieurs canaux privés.

Si un propriétaire de canal privé quitte votre organisation ou s’il est supprimé du groupe Microsoft 365 associé à l’équipe, un membre du canal privé est promu automatiquement en tant que propriétaire du canal privé.

### <a name="what-can-team-owners-and-team-members-see-in-a-private-channel"></a>Que peuvent voir les propriétaires d’équipe et les membres d’équipe dans un canal privé ?

Les propriétaires d’équipe peuvent voir le nom de tous les canaux privés dans leur équipe et peuvent également supprimer n’importe quel canal privé au sein de l’équipe. (Un canal privé supprimé peut être restauré dans un délai de 30 jours après sa suppression). Les propriétaires d’équipe ne peuvent pas voir les fichiers ou la liste des conversations et des membres d’un canal privé, sauf s’ils sont membres de ce canal privé.

Le tableau suivant montre qui peut voir quoi sur un canal privé.

|Élément  |Le propriétaire de l’équipe peut voir |Les membres d’une équipe peuvent voir |
|---------|---------|---------|
|Nom et description    |Tous les canaux privés de l’équipe         |Uniquement les canaux privés auxquels ils sont ajoutés         |
|Conversations et onglets     |Uniquement lorsqu'il est ajouté au canal privé         |Uniquement lorsqu'il est ajouté au canal privé         |
|Fichiers et contenu    |Uniquement lorsqu'il est ajouté au canal privé        |Uniquement lorsqu'il est ajouté au canal privé         |
|Propriétaire du canal privé    |Tous les canaux privés de l’équipe        |Uniquement lorsqu'il est ajouté au canal privé         |
|Horodatage de la dernière activité  |Tous les canaux privés de l’équipe       |Uniquement lorsqu'il est ajouté au canal privé         |

## <a name="manage-private-channels"></a>Gérer les canaux privés

Le tableau suivant décrit les actions que les propriétaires, les membres et les invités peuvent effectuer dans les canaux privés.

|Action  |Propriétaire d’une équipe|Membre de l’équipe|Invité de l’équipe|Propriétaire du canal privé|Membre du canal privé|Invité du canal privé|
|---------|---------|---------|---------|---------|---------|---------|
|Créer un canal privé|Oui <sup>1</sup>|Oui<sup>1,2</sup>|Non|N/A|N/A |N/A |
|Supprimer un canal privé|Oui|Non|Non|Oui|Non|Non|
|Quitter un canal privé|S/O|N/A |N/A |Oui<sup>3</sup>|Oui |Oui|
|Modifier un canal privé|Non|N/A|N/A|Oui|Non|Non|
|Restaurer un canal privé supprimé|Oui|Non|Non|Oui|Non|Non|
|Ajouter des membres|Non|N/A|N/A|Oui|Non|Non|
|Modifier les paramètres|Non|N/A|N/A|Oui|Non|Non|
|Gérer les onglets et les applications|Non|N/A|N/A|Oui <sup>4</sup>|Oui<sup>5</sup>|Non|

<sup>1</sup> En supposant que la stratégie que vous, l'administrateur, avez configurée, permette à l'utilisateur de créer des canaux privés.<br>
<sup>2</sup> Chaque équipe a un paramètre que les propriétaires d'équipe peuvent activer ou désactiver pour permettre aux membres de l'équipe de créer des canaux privés. Les propriétaires d’équipe peuvent toujours créer des canaux privés.<br>
<sup>3</sup> En supposant que le propriétaire du canal privé ne soit pas le dernier propriétaire du canal. <br>
<sup>4</sup> Nécessite que l'équipe ait installé une application pour qu'une chaîne privée l'utilise.<br>
<sup>5</sup> Les propriétaires de canal privé peuvent configurer cela.

### <a name="manage-private-channel-membership-and-settings"></a>Gérer les paramètres et l’adhésion au canal privé

Chaque canal privé possède ses propres paramètres, notamment la possibilité d’ajouter et de supprimer des membres, d’ajouter des onglets et de @mentionner pour l’ensemble du canal. Ces paramètres sont indépendants de ceux de l’équipe parente. Lors de la création d’un canal privé, celui-ci hérite des paramètres de l’équipe parente. Ensuite, ses paramètres peuvent être modifiés indépendamment de ceux de l’équipe parente.

Le propriétaire du canal privé peut cliquer sur **Gérer les canaux**, puis utiliser les **Membres** et l’onglet **Paramètres** pour ajouter ou supprimer des membres et modifier les paramètres.  

![Capture d’écran des paramètres de canaux privés](media/private-channels-in-teams-channel-settings.png)

## <a name="manage-the-life-cycle-of-private-channels"></a>Gérer le cycle de vie des canaux privés

Vous pouvez consultez l’article [Gérer le cycle de vie des canaux privés dans Teams](private-channels-life-cycle-management.md) pour obtenir plus d’informations sur la gestion du cycle de vie des canaux privés au sein de votre organisation. Et notamment, comment contrôler si les utilisateurs de votre organisation peuvent créer des canaux privés, comment créer un canal privé au nom d'un propriétaire d'équipe, comment obtenir une liste de tous les messages de canaux privés à des fins d'archivage et d'audit ainsi que d'autres tâches de gestion.  

## <a name="private-channel-sharepoint-sites"></a>Canal privé des sites SharePoint

Chaque canal privé possède sa propre collection de sites SharePoint optimisée pour le partage de fichiers et la mise en service rapide. La collection de sites différents garantit que l'accès aux fichiers des canaux privés est limité uniquement aux membres du canal privé contrairement au site d'équipe, où les propriétaires d'équipe ont accès à tous les actifs de la collection de sites. Ces collections de sites sont créées avec une bibliothèque de documents par défaut, et peuvent être facilement améliorées dans une collection de sites complète via l’[interface de gestion de site](https://support.office.com/article/Enable-or-disable-site-collection-features-A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Chaque collection de sites est créée dans la même zone géographique que la collection de sites de l’équipe parente. Ces sites légers ont un ID de modèle personnalisé, « TEAMCHANNEL#0 », pour simplifier la gestion via PowerShell et l’API Graph.  Par défaut, ils ne sont pas visibles dans le centre d’administration SharePoint.

Pour accepter un plus grand nombre de collections de sites par client, la limite est passée de 500 000 à 2 000 000. Une collection de sites de canaux privés synchronise la classification des données et hérite des autorisations d'accès invité de la collection de sites de l'équipe parente.  L’adhésion au propriétaire de la collection de sites et aux groupes de membres est synchronisée avec l’adhésion au canal privé au sein de Teams. Toutes les modifications apportées à l'appartenance aux groupes Propriétaire ou Membre dans SharePoint Online seront automatiquement converties en appartenance à un canal privé dans les quatre heures. Si certains utilisateurs ont besoin d’accéder à des documents sans avoir besoin d’accéder aux messages de canal privé, ajoutez-les au groupe visiteurs sur le site ou à un nouveau groupe séparé des propriétaires et des membres.

Teams gère le cycle de vie de la collection de sites SharePoint du canal privé. Si la collection de sites est supprimée en dehors de Teams, un travail d'arrière-plan restaure le site dans les quatre heures tant que le canal privé est toujours actif. Si le site est supprimé définitivement, une nouvelle collection de sites est fournie pour le canal privé.

Si un canal privé ou une équipe contenant un canal privé est restauré, les collections de sites sont restaurées également. Si une collection de sites de canal privé est restaurée et dépasse la fenêtre de suppression logicielle de 30 jours, la collection de sites fonctionne comme une collection de sites autonome.

## <a name="private-channel-message-compliance-records"></a>Enregistrements de conformité des messages de canal privé

Les enregistrements pour les messages envoyés dans un canal privé sont distribués dans la boîte aux lettres de tous les membres du canal privé, plutôt que dans une boîte aux lettres de groupe. Les titres des enregistrements sont mis en forme de façon à indiquer le canal privé à partir duquel ils ont été envoyés.

Si vous souhaitez en savoir plus sur l'exécution d'une recherche eDiscovery pour les messages de canaux privés, consultez l’article [eDiscovery des canaux privés](ediscovery-investigation.md#ediscovery-of-private-channels).

## <a name="considerations-around-access-in-private-channels"></a>Considérations sur l’accès dans les canaux privés

Lorsqu'un nouveau bloc-notes OneNote est créé dans un canal privé, des utilisateurs supplémentaires peuvent toujours avoir accès au bloc-notes car le comportement est le même que le partage de l'accès à tout autre élément d'un site SharePoint de canal privé avec un utilisateur.

Si un utilisateur se voit accorder l'accès à un bloc-notes dans un canal privé via SharePoint, la suppression de l'utilisateur de l'équipe ou du canal privé ne supprimera pas l'accès de l'utilisateur au bloc-notes.

Si un bloc-notes existant est ajouté en tant qu'onglet à un canal privé, l'accès au canal privé n'est pas modifié. Cela signifie que :

- Par défaut, tous les membres du canal privé ne pourront pas accéder au bloc-notes. En effet, il est possible qu’ils n’aient pas accès à l’emplacement où le bloc-notes est hébergé, par exemple, le site SharePoint d’une autre équipe.
- Les utilisateurs qui ne sont pas membres du canal privé peuvent afficher le bloc-notes.  

## <a name="related-topics"></a>Sujets associés

- [Présentation des équipes et des canaux dans Teams](teams-channels-overview.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Utiliser l’API Microsoft Graph pour travailler avec Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
