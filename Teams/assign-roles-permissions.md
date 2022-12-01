---
title: Affecter des propriétaires et des membres d’équipe dans Microsoft Centre d’administration Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b25a5d654e4bd7a807918aa86e0bfd52aff2ca04
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198756"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams-admin-center"></a>Affecter des propriétaires et des membres d’équipe dans Microsoft Centre d’administration Teams

**Propriétaire** et **membre** sont les deux rôles d’utilisateur dans Microsoft Teams. L’utilisateur qui crée une équipe se voit accorder le statut de propriétaire par défaut. Les propriétaires et les membres ont différents types d’autorisations et de fonctionnalités lors de l’interaction avec une équipe et ses canaux. Consultez [Vue d’ensemble des équipes et des canaux dans Microsoft Teams](teams-channels-overview.md) pour en savoir plus sur les rôles dans Teams.

> [!NOTE]
> Si une équipe est créée à partir d’un groupe Microsoft 365 existant, les autorisations sont héritées.

## <a name="assign-a-user-role-in-teams-admin-center"></a>Attribuer un rôle d’utilisateur dans le Centre d’administration Teams

1. Dans le Centre d’administration Teams, développez **Teams** et sélectionnez **Gérer les équipes**.
2. Sélectionnez le nom de l’équipe sous la colonne nom d’affichage.
3. Sous l’onglet Membres, vous pouvez ajouter ou supprimer des membres et attribuer des rôles de propriétaire et de modérateur aux membres.

## <a name="restrict-permission-to-create-teams"></a>Restreindre l’autorisation de créer des équipes

Tous les utilisateurs disposant d’une boîte aux lettres dans Exchange Online disposent des autorisations nécessaires pour créer Microsoft 365 groupes et une équipe dans Microsoft Teams. Empêchez les utilisateurs de créer des équipes et de Microsoft 365 groupes en déléguant des droits de création et de gestion de groupe à un ensemble d’utilisateurs. Si cette restriction est active, ni les propriétaires d’équipe ni les membres ne peuvent créer de nouvelles équipes. Si vous souhaitez en savoir plus, consultez l’article [Gérer qui peut créer des groupes Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="user-permissions-based-on-assigned-roles"></a>Autorisations utilisateur en fonction des rôles attribués

Le tableau ci-dessous présente les différences d’autorisations entre un propriétaire et un membre.

### <a name="teams"></a>Équipes

|Tâches Teams| Propriétaire d'équipe | Membre de l’équipe |
|---------|---------|---------|
|Créer/supprimer une équipe  |    Oui     |     Non    |
|Modifier le nom/la description d'une équipe   |     Oui    |     Non     |
|Ajouter des membres à une équipe privée    |     Oui    |  Non |
|Ajouter des membres à l’équipe publique    |     Oui    |     Oui   |
|Demande d’ajout d’un nouveau membre   |     N/A    |    Oui   |
|Promouvoir/rétrograder l’état de l’utilisateur | Oui | Non |
|Quitter une équipe  |    Oui     |     Oui    |
|Ajouter/supprimer des applications   |     Oui    |     Oui, si activé par le propriétaire de l’équipe     |

### <a name="channels"></a>Canaux

|***Tâches de canal standard** _ | _ *Propriétaire de l’équipe** | **Membre de l’équipe**|
|----|----|----|
|Créer/supprimer un canal  |     Oui    |    Oui, si activé par le propriétaire de l’équipe      |
|Modifier le nom/la description d'un canal    |    Oui     |     Oui, si activé par le propriétaire de l’équipe    |
|***Tâches de canal privé***|
|Créer un canal    |    Oui     |    Oui, si activé par le propriétaire de l’équipe      |
|Supprimer un canal    |    Oui     |    Non     |
|Modifier le nom/la description d'un canal |     Non    |    N/A     |
|***Tâches de canal partagé***
|Créer un canal    |    Oui     |     Non    |
|Supprimer un canal | Oui | Non |
|Modifier le nom/la description d'un canal    |    Non     |     Non    |
