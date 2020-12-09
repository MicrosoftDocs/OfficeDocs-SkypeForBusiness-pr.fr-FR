---
title: Canaux privés dans Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
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
ms.openlocfilehash: 9cec7abc4af736a72b83bc978709dacf4e7c18e8
ms.sourcegitcommit: 68dffc3aca46992448bc2be0689bfd352e016316
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49601679"
---
# <a name="private-channels-in-microsoft-teams"></a>Canaux privés dans Microsoft Teams

Les canaux privés dans Microsoft Teams créent des espaces ciblés pour la collaboration au sein de vos équipes. Seuls les utilisateurs de l’équipe qui sont propriétaires ou membres du canal privé peuvent accéder au canal. Tous les utilisateurs, notamment les invités, peuvent être ajoutés en tant que membre d’un canal privé, dès lors qu’ils sont déjà membres de l’équipe.

Vous souhaiterez peut-être utiliser un canal privé si vous voulez limiter la collaboration à ceux qui en ont besoin ou si vous souhaitez faciliter la communication entre un groupe de personnes affectées à un projet spécifique, sans avoir à créer une équipe supplémentaire à gérer.

Par exemple, un canal privé est utile dans les cas suivants :

- Certains membres d’une équipe souhaite utiliser un espace ciblé pour collaborer sans avoir à créer une équipe distincte.
- Un sous-groupe de personnes dans une équipe souhaite disposer d'un canal privé pour discuter d'informations sensibles, telles que les budgets, les ressources, le positionnement stratégique, etc.

Une icône de verrouillage indique un canal privé. Seuls les membres des canaux privés peuvent voir et participer aux canaux privés auxquels ils sont ajoutés.

Lors de la création d’un canal privé, celui-ci est lié à l’équipe parente et ne peut pas être déplacé vers une autre équipe. De plus, les canaux privés ne peuvent pas être convertis en canaux standard et vice-versa.

![Capture d’écran des canaux privés dans une équipe](media/private-channels-in-teams.png)

## <a name="private-channel-creation"></a>Création d’un canal privé

Par défaut, tout membre ou propriétaire d’une équipe peut créer un canal privé. Les invités ne peuvent pas les créer. La possibilité de créer des canaux privés peut être gérée au niveau de l’équipe et au niveau de l’organisation. Utiliser des [stratégies](teams-policies.md) pour contrôler les utilisateurs de votre organisation qui sont autorisés à créer des canaux privés. Une fois que vous avez défini les stratégies, les propriétaires d’équipe peuvent désactiver ou activer la possibilité pour les membres de créer des canaux privés dans l’onglet **paramètres** d’une équipe.

La personne qui crée un canal privé est le propriétaire de ce canal et elle est la seule a pouvoir directement y ajouter ou en supprimer des utilisateurs. Un propriétaire de canal privé peut ajouter un membre d’équipe à un canal privé qu’il a créé, même des invités. Les membres d’un canal privé disposent d’un espace de conversation sécurisé, et lorsque de nouveaux membres sont ajoutés, ils peuvent voir toutes les conversations (y compris les anciennes) de ce canal privé.

Les propriétaires d’équipe peuvent voir le nom de tous les canaux privés dans leur équipe et peuvent également supprimer n’importe quel canal privé au sein de l’équipe. (Un canal privé supprimé peut être restauré dans un délai de 30 jours après sa suppression). Les propriétaires d’équipe ne peuvent pas voir les fichiers ou la liste des conversations et des membres d’un canal privé, sauf s’ils sont membres de ce canal privé.

Les membres d’une équipe peuvent uniquement voir les canaux privés qu’ils ont ajoutés.

## <a name="adding-and-removing-owners-and-members"></a>Ajout et suppression de propriétaires et de membres

Un propriétaire de canal privé ne peut pas être supprimé via le client Teams s’il est le dernier propriétaire d’un ou plusieurs canaux privés.

Si un propriétaire de canal privé quitte votre organisation ou s’il est supprimé du groupe Microsoft 365 associé à l’équipe, un membre du canal privé est promu automatiquement en tant que propriétaire du canal privé.

Si un membre d’une équipe quitte ou est supprimé d’une équipe, cet utilisateur quitte ou est supprimé également de tous les canaux privés au sein de l’équipe. Si l'utilisateur est réintégré dans l'équipe, il doit être réintégré dans les canaux privés de l'équipe.

## <a name="channel-owner-settings"></a>Paramètres de propriétaire de canal

Chaque canal privé possède ses propres paramètres que le propriétaire du canal peut gérer, y compris la possibilité d’ajouter et de supprimer des membres, d’ajouter des onglets et de @mentioning pour l’ensemble du canal. Ces paramètres sont indépendants de ceux de l’équipe parente. Lors de la création d’un canal privé, celui-ci hérite des paramètres de l’équipe parente. Ensuite, ses paramètres peuvent être modifiés indépendamment de ceux de l’équipe parente.

Le propriétaire du canal privé peut cliquer sur **Gérer les canaux**, puis utiliser les **Membres** et l’onglet **Paramètres** pour ajouter ou supprimer des membres et modifier les paramètres.

![Capture d’écran des paramètres de canaux privés](media/private-channels-in-teams-channel-settings.png)

## <a name="private-channel-owner-and-member-actions"></a>Action du propriétaire du canal privé et des membres

Le tableau suivant décrit les actions que les propriétaires, les membres et les invités peuvent effectuer dans les canaux privés.

|Action  |Propriétaire d’une équipe|Membre de l’équipe|Invité de l’équipe|Propriétaire du canal privé|Membre du canal privé|Invité du canal privé|
|---------|---------|---------|---------|---------|---------|---------|
|Créer un canal privé|Administrateur contrôlé|Administrateur et propriétaire de l’équipe contrôlés|Non|N/A|N/A|S/O|
|Supprimer un canal privé|Oui|Non|Non|Oui|Non|Non|
|Quitter un canal privé|S/O|N/A|N/A|Oui, sauf s’il s’agit du dernier propriétaire|Oui|Oui|
|Modifier un canal privé|Non|N/A|N/A|Oui|Non|Non|
|Restaurer un canal privé supprimé|Oui|Non|Non|Oui|Non|Non|
|Ajouter des membres|Non|N/A|N/A|Oui|Non|Non|
|Modifier les paramètres|Non|N/A|N/A|Oui|Non|Non|
|Gérer les onglets et les applications|Non|N/A|N/A|Oui, les applications doivent être installées pour l’équipe|Propriétaire de canal contrôlé|Non|

## <a name="manage-the-lifecycle-of-private-channels"></a>Gérer le cycle de vie des canaux privés

Pour obtenir des instructions sur la gestion du cycle de vie des canaux privés au sein de votre organisation, voir [gérer le cycle de vie des canaux privés dans teams](private-channels-life-cycle-management.md) . Et notamment, comment contrôler si les utilisateurs de votre organisation peuvent créer des canaux privés, comment créer un canal privé au nom d'un propriétaire d'équipe, comment obtenir une liste de tous les messages de canaux privés à des fins d'archivage et d'audit ainsi que d'autres tâches de gestion.  

## <a name="private-channel-sharepoint-sites"></a>Canal privé des sites SharePoint

Chaque canal privé possède son propre site SharePoint. Pour garantir que l’accès aux fichiers de canal privé est limité uniquement aux membres du canal privé. Ces sites sont créés à l’aide d’une bibliothèque de documents par défaut, et peuvent être facilement améliorés vers un site complet via l' [interface de gestion de site](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Chaque site est créé dans la même zone géographique que le site de l’équipe parente. Ces sites légers ont un ID de modèle personnalisé, « TEAMCHANNEL#0 », pour simplifier la gestion via PowerShell et l’API Graph.

Un site de canal privé synchronise la classification des données et hérite des autorisations d’accès invité du site de l’équipe parente. L’appartenance au propriétaire du site et aux groupes de membres reste synchronisée avec l’appartenance du canal privé au sein d’Teams. Les modifications apportées à l’appartenance des groupes de propriétaires ou de membres dans SharePoint seront automatiquement reversées en appartenance au canal privé dans les quatre heures. Si certains utilisateurs ont besoin d’accéder à des documents sans avoir besoin d’accéder aux messages de canal privé, ajoutez-les au groupe visiteurs sur le site ou à un nouveau groupe séparé des propriétaires et des membres.

Teams gère le cycle de vie du site du canal privé. Si le site est supprimé en dehors de teams, un travail en arrière-plan restaure le site dans un délai de quatre heures tant que le canal privé est toujours actif. Si le site est supprimé de manière définitive, un nouveau site est approvisionné pour le canal privé.

Si un canal privé ou une équipe contenant un canal privé est restauré, les sites y sont restaurés. Si un site de canal privé est restauré et qu’il se trouve au-delà de la fenêtre de suppression du canal privé de 30 jours, le site fonctionne en tant que site autonome.

## <a name="private-channel-message-compliance-records"></a>Enregistrements de conformité des messages de canal privé

Les enregistrements pour les messages envoyés dans un canal privé sont distribués dans la boîte aux lettres de tous les membres du canal privé, plutôt que dans une boîte aux lettres de groupe. Les titres des enregistrements sont mis en forme de façon à indiquer le canal privé à partir duquel ils ont été envoyés.

Si vous souhaitez en savoir plus sur l'exécution d'une recherche eDiscovery pour les messages de canaux privés, consultez l’article [eDiscovery des canaux privés](ediscovery-investigation.md#ediscovery-of-private-channels).

## <a name="considerations-around-file-access-in-private-channels"></a>Considérations relatives à l’accès aux fichiers dans les canaux privés

Lorsqu'un nouveau bloc-notes OneNote est créé dans un canal privé, des utilisateurs supplémentaires peuvent toujours avoir accès au bloc-notes car le comportement est le même que le partage de l'accès à tout autre élément d'un site SharePoint de canal privé avec un utilisateur.

Si un utilisateur se voit accorder l'accès à un bloc-notes dans un canal privé via SharePoint, la suppression de l'utilisateur de l'équipe ou du canal privé ne supprimera pas l'accès de l'utilisateur au bloc-notes.

Si un bloc-notes existant est ajouté en tant qu’onglet à un canal privé, l’accès au canal privé n’est pas modifié et le bloc-notes conserve ses autorisations existantes.

## <a name="private-channel-limitations"></a>Limitations relatives aux canaux privés

Actuellement, les canaux privés prennent en charge les connecteurs et les onglets (à l’exception de Stream, Planner et Forms). Nous travaillons à la prise en charge complète des applications pour les canaux privés, y compris les extensions et les robots.

Chaque équipe peut avoir un maximum de 30 canaux privés et chaque canal privé peut avoir au maximum 250 membres. La limite des 30 canaux privés vient s’ajouter à la limite des 200 canaux standard par équipe. 

Lorsque vous créez une équipe à partir d’une équipe existante, tous les canaux privés de l’équipe existante ne seront pas copiés.

## <a name="related-topics"></a>Sujets associés

[Présentation des équipes et des canaux dans Teams](teams-channels-overview.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)

[Utiliser l’API Microsoft Graph pour travailler avec Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview)
