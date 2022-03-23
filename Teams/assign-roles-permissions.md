---
title: Affecter des propriétaires d’équipe et des membres dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Découvrez comment assigner des rôles et des autorisations de propriétaire et de membre d'équipe dans Microsoft Teams, notamment des autorisations de création d'équipes.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9ca46e3fa967019e674651ea27299b6552144a7
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711958"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams"></a>Affecter des propriétaires d’équipe et des membres dans Microsoft Teams

Dans Microsoft Teams, il existe deux rôles d’utilisateur : **propriétaire** et **membre**. Par défaut, l’utilisateur qui crée une équipe se voit attribuer le statut de propriétaire. De plus, les propriétaires et les membres peuvent disposer des capacités de modérateur pour un canal (à condition que la modération ait été configurée). Si une équipe est créée à partir d’un groupe de Microsoft 365 existant, les autorisations sont héritées.

Le tableau ci-dessous présente les différences d’autorisations entre un propriétaire et un membre.


|    Tâche                               | Propriétaire d'équipe | Membre de l’équipe |
|-----------------------------------|------------|-------------|
|          **Créer une équipe**          |    Oui <sup>1</sup>     |     Non      |
|          **Quitter une équipe**           |    Oui     |     Oui     |
|  **Modifier le nom/la description d'une équipe**   |    Oui     |     Non      |
|          **Supprimer l’équipe**          |    Oui     |     Non      |
|          **Ajouter un canal standard**          |    Oui     |    Oui<sup>2</sup>|
| **Modifier le nom/la description d’un canal standard** |    Oui     |    Oui<sup>2</sup>|
|        **Supprimer un canal standard**         |    Oui     |    Oui<sup>2</sup>|
|          ***Ajouter un canal privé**          |    Oui     |    Oui<sup>2</sup>|
| ***Modifier le nom/la description d’un canal privé** |    Non     |    N/A|
|        ***Supprimer un canal privé**         |    Oui     |    Non|
|          **Ajouter un canal partagé**          |    Oui     |    Non|
| **Modifier le nom/la description d’un canal partagé** |    Non     |    <sup>Non6</sup>|
|        **Supprimer un canal partagé**         |    Oui     |    <sup>Non6</sup>|
|          **Ajouter des membres**          |  Oui<sup>3</sup>   |     Non<sup>4</sup>    |
|          **Demande d’ajouter des membres**          |  S/O   |     Oui<sup>5</sup>     |
|           **Ajouter des applications**            |    Oui     |    Oui<sup>2</sup>|

<sup>1</sup> les propriétaires des équipes peuvent créer des équipes, sauf s’ils sont restreints. [Autorisations pour créer des équipes](#permissions-to-create-teams) ci-dessous.<br>
<sup>2</sup> Un propriétaire peut désactiver ces éléments au niveau de l’équipe, auquel cas, les membres n’y auront pas accès.<br>
<sup>3</sup> après avoir ajouté un membre à une équipe, un propriétaire peut également promouvoir un membre au statut de propriétaire. Il est également possible pour un propriétaire d’abaisser leur propre état pour un membre.<br>
<sup>4</sup> les membres de Teams peuvent ajouter d’autres membres à une équipe publique.<br>
<sup>5</sup> un membre d’équipe ne peut pas ajouter directement des membres à une équipe privée, ils peuvent demander qu’une personne soit ajoutée à une équipe dont ils sont déjà membres. Lorsqu’un membre demande l’ajout d»une personne à une équipe, les propriétaires des équipes reçoivent une alerte de demande en attente qu’ils peuvent accepter ou refuser.<br>
<sup>6</sup> Si le membre de l’équipe est propriétaire d’un canal partagé, il peut effectuer cette action.

*Si vous souhaitez en savoir plus sur les autorisations des canaux privés, consultez l’article [Canaux privés dans Teams](private-channels.md).

> [!NOTE]
> Les propriétaires peuvent nommer d’autres membres en tant que propriétaires à l’aide de l’option **Afficher les équipes**. Une équipe peut avoir 100 propriétaires maximum. Pour gérer au mieux l’équipe, il est recommandé de définir plusieurs propriétaires. Cela évitera également qu’une équipe ne comptant un seul propriétaire se retrouve orpheline si celui-ci quitte l’organisation. Si vous souhaitez en savoir plus sur les groupes orphelins, consultez l’article [Attribuer un nouveau propriétaire à un groupe orphelin](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

## <a name="moderator-capabilities"></a>Capacités du modérateur

En plus des autres fonctionnalités, les propriétaires et les membres d’une équipe peuvent avoir des capacités de modérateur pour un canal (à condition que la modération soit activée pour une équipe). Les modérateurs peuvent commencer de nouvelles publications dans un canal et contrôler si les membres d’une équipe peuvent répondre aux messages existants du canal. Ils peuvent également contrôler si les bots et les connecteurs peuvent envoyer des messages de canal.

Les fonctionnalités du modérateur sont attribuées au niveau du canal. Par défaut, les propriétaires d’équipe disposent de fonctionnalités de modération. Les membres de l’équipe disposent de fonctionnalités de modérateur désactivées par défaut, mais le propriétaire d’une équipe peut accorder des fonctionnalités de modération pour un canal à un membre d’une équipe. Les modérateurs d’un canal peuvent ajouter et supprimer d’autres modérateurs au sein de ce canal.

Si vous souhaitez en savoir plus, consultez l’article [Configurer et gérer la modération des canaux dans Microsoft Teams](manage-channel-moderation-in-teams.md).

## <a name="assign-a-user-role"></a>Attribuer un rôle utilisateur

Pour attribuer un rôle d’utilisateur, dans Teams, sélectionnez le nom de l’équipe et cliquez sur **Autres options** > **Gérer l’équipe**. Dans l’onglet **Membres**, vous pouvez ajouter des membres et choisir des propriétaires et des modérateurs (si vous disposez des autorisations suffisantes). Pour plus d’informations, [voir Modifier les paramètres d’une équipe dans Teams](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc).

## <a name="permissions-to-create-teams"></a>Autorisations pour créer une équipe

Par défaut, tous les utilisateurs avec une boîte aux lettres dans Exchange Online disposent des autorisations nécessaires pour créer des groupes Microsoft 365 et par conséquent une équipe dans Microsoft Teams. Vous pouvez avoir un contrôle plus étroit et limiter la création d’équipes et par conséquent la création de nouveaux groupes Microsoft 365 en déléguant la gestion des droits et la création de groupes à un ensemble d’utilisateurs. Si vous souhaitez en savoir plus, consultez l’article[Gérer qui peut créer des Groupes Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).
