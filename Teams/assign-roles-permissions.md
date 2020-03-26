---
title: Affecter des propriétaires d’équipe et des membres dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Découvrez comment assigner des rôles et des autorisations de propriétaire et de membre d'équipe dans Microsoft Teams, notamment des autorisations de création d'équipes.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f411de7f0c373e82b450cd41b828fd591777311b
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978456"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Affecter des propriétaires d’équipe et des membres dans Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Dans Microsoft Teams, il existe deux rôles d’utilisateur : **propriétaire** et **membre**. Par défaut, un utilisateur qui crée une équipe dispose du statut de propriétaire. De plus, les propriétaires et les membres peuvent disposer de capacités de modérateur pour un canal (à condition que la modération ait été configurée). Si une équipe est créée à partir d’un groupe Office 365 existant, les autorisations sont héritées.

Le tableau ci-après présente les différences d'autorisations entre un propriétaire et un membre.


|                                   | Propriétaire d'équipe | Membre de l’équipe |
|-----------------------------------|------------|-------------|
|          **Créer une équipe**          |    Oui<sup>1</sup>     |     Non      |
|          **Quitter une équipe**           |    Oui     |     Oui     |
|  **Modifier le nom/la description d'une équipe**   |    Oui     |     Non      |
|          **Supprimer l’équipe**          |    Oui     |     Non      |
|          **Ajouter un canal standard**          |    Oui     |    Oui<sup>2</sup>|
| **Modifier le nom ou la description du canal standard** |    Oui     |    Oui<sup>2</sup>|
|        **Supprimer un canal standard**         |    Oui     |    Oui<sup>2</sup>|
|          ***Ajouter un canal privé**          |    Oui     |    Oui<sup>2</sup>|
| ***Modifier le nom ou la description du canal privé** |    Non     |    N/D|
|        ***Supprimer un canal privé**         |    Oui     |    Non|
|          **Ajouter des membres**          |  Oui<sup>3</sup>   |     Non<sup>4</sup>    |
|          **Demande d’ajouter des membres**          |  S/O   |     Oui<sup>5</sup>     |
|           **Ajouter des applications**            |    Oui     |    Oui<sup>2</sup>|

<sup>1</sup> les propriétaires des équipes peuvent créer des équipes, sauf s’ils sont restreints. [Autorisations pour créer des équipes](#permissions-to-create-teams) ci-dessous.<br>
<sup>2</sup> un propriétaire peut désactiver ces éléments au niveau de l’équipe, auquel cas les membres ne peuvent pas y accéder.<br>
<sup>3</sup> après avoir ajouté un membre à une équipe, un propriétaire peut également promouvoir un membre au statut de propriétaire. Il est également possible pour un propriétaire d’abaisser leur propre état pour un membre.<br>
<sup>4</sup> les membres de Teams peuvent ajouter d’autres membres à une équipe publique.<br>
<sup>5</sup> un membre d’équipe ne peut pas ajouter directement des membres à une équipe privée, ils peuvent demander qu’une personne soit ajoutée à une équipe dont ils sont déjà membres. Lorsqu’un membre demande l’ajout d»une personne à une équipe, les propriétaires des équipes reçoivent une alerte de demande en attente qu’ils peuvent accepter ou refuser.

* Pour en savoir plus sur les autorisations de canaux privés, voir [canaux privés dans teams](private-channels.md).

> [!NOTE]
> Les propriétaires peuvent faire des propriétaires d’autres membres dans l’option **afficher les équipes** . Une équipe peut compter 100 propriétaires maximum. Nous vous recommandons d’avoir au moins quelques propriétaires pour vous aider à gérer l’équipe. Cela permet également d’éviter les groupes orphelins si un propriétaire unique quitte votre organisation. Pour plus d'informations sur les groupes orphelins, reportez-vous à l'article [Attribuer un nouveau propriétaire à un groupe orphelin](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

## <a name="moderator-capabilities"></a>Fonctionnalités de modérateur

Outre d’autres fonctionnalités, les propriétaires d’équipe et les membres peuvent disposer de capacités de modérateur pour un canal (à condition que cette modération soit activée pour une équipe). Les modérateurs peuvent commencer de nouvelles publications dans un canal et contrôler si les membres d’une équipe peuvent répondre à des messages de canal existants. Ils peuvent également contrôler si les robots et connecteurs peuvent renvoyer des messages de canal.

Les fonctionnalités de modérateur sont affectées au niveau du canal. Les propriétaires d’équipe disposent de fonctionnalités de modérateur par défaut. Les membres d’une équipe ont désactivé les fonctionnalités de modérateur par défaut, mais les propriétaires d’une équipe peuvent fournir des fonctionnalités de modérateur pour un canal à un membre d’équipe. Les modérateurs au sein d’un canal peuvent ajouter ou supprimer d’autres modérateurs dans ce canal.

Pour plus d’informations sur les fonctionnalités de modérateur, voir [configurer et gérer la modération de canal dans Microsoft teams](manage-channel-moderation-in-teams.md).

## <a name="assign-a-user-role"></a>Attribuer un rôle d’utilisateur

Pour attribuer un rôle d’utilisateur, dans équipes, sélectionnez le nom de l’équipe, puis cliquez sur **autres options** > **gérer l’équipe**. Dans l’onglet **membres** , vous pouvez ajouter des membres et sélectionner propriétaires et modérateurs (si vous disposez des autorisations nécessaires). Pour plus d’informations, voir [modifier les paramètres d’équipe dans](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)Teams.

## <a name="permissions-to-create-teams"></a>Autorisations de créations d'équipes

Par défaut, tous les utilisateurs avec une boîte aux lettres dans Exchange Online disposent des autorisations pour créer des groupes Office 365 et par conséquent une équipe dans Microsoft Teams. Vous pouvez avoir un contrôle plus étroit et limiter la création d’équipes et par conséquent la création de nouveaux groupes Office 365 en déléguant la gestion des droits et la création de groupes à un ensemble d’utilisateurs. Pour plus d'informations, reportez-vous à l’article[Gérer qui peut créer des Groupes Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Icône représentant un point de décision](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Point de décision         |Les utilisateurs Microsoft Teams pourront-ils créer des équipes (recommandé) ?         |
| ![Icône représentant les étapes suivantes](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Étapes suivantes         |Modifiez les autorisations par défaut des utilisateurs autorisés à créer des groupes Office 365 si vous devez limiter les autorisations de création d'équipes.         |
