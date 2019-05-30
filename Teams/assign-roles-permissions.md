---
title: Affecter des propriétaires d’équipe et des membres dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Découvrez comment assigner des rôles et des autorisations de propriétaire et de membre d'équipe dans Microsoft Teams, notamment des autorisations de création d'équipes.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 423a12e8fce0c9d7508e97c1f57e17a0ba8a0ff0
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493801"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Affecter des propriétaires d’équipe et des membres dans Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Microsoft Teams inclut deux rôles : **Propriétaire** et **Membre**. Par défaut, un utilisateur qui crée une équipe a le statut de Propriétaire. Si une équipe est créée à partir d'un groupe existant Office 365, les autorisations sont héritées.

Le tableau ci-après présente les différences d'autorisations entre un propriétaire et un membre.


|                                   | Propriétaire d'équipe | Membre de l’équipe |
|-----------------------------------|------------|-------------|
|          **Créer une équipe**          |    Oui<sup>1</sup>     |     Non      |
|          **Quitter une équipe**           |    Oui     |     Oui     |
|  **Modifier le nom/la description d'une équipe**   |    Oui     |     Non      |
|          **Supprimer l’équipe**          |    Oui     |     Non      |
|          **Ajouter un canal**          |    Oui     |    Oui<sup>2</sup>|
| **Modifier le nom/la description d'un canal** |    Oui     |    Oui<sup>2</sup>|
|        **Supprimer un canal**         |    Oui     |    Oui<sup>2</sup>|
|          **Ajouter des membres**          |  Oui<sup>3</sup>   |     Non<sup>4</sup>    |
|          **Demande d’ajouter des membres**          |  S/O   |     Oui<sup>5</sup>     |
|           **Ajouter des onglets**            |    Oui     |    Oui<sup>2</sup>|
|        **Ajouter des connecteurs**         |    Oui     |    Oui<sup>2</sup>|
|           **Ajouter des bots**            |    Oui     |    Oui<sup>2</sup>|

<sup>1</sup> les propriétaires des équipes peuvent créer des équipes, sauf s’ils sont restreints. Voir « Autorisations nécessaires pour créer des équipes » ci-dessous.
>
<sup>2</sup> Ces éléments peuvent être désactivés par un propriétaire au niveau d'une équipe, auquel cas les membres n'y auront pas accès.

<sup>3</sup> après avoir ajouté un membre à une équipe, un propriétaire peut également promouvoir un membre au statut de propriétaire. Il est également possible pour un propriétaire d’abaisser leur propre état pour un membre.

<sup>4</sup> les membres de Teams peuvent ajouter d’autres membres à une équipe publique.

<sup>5</sup> un membre d’équipe ne peut pas ajouter directement des membres à une équipe privée, ils peuvent demander qu’une personne soit ajoutée à une équipe dont ils sont déjà membres. Lorsqu’un membre demande l’ajout d»une personne à une équipe, les propriétaires des équipes reçoivent une alerte de demande en attente qu’ils peuvent accepter ou refuser.



> [!NOTE]
> Les propriétaires peuvent nommer d'autres membres en tant que propriétaires à l'aide de l'option Afficher les équipes. Une équipe peut compter 100 propriétaires maximum. Pour gérer au mieux l'équipe, il est recommandé de définir plusieurs propriétaires ; cela évitera également qu'une équipe comptant un seul propriétaire de se retrouver orpheline si celui-ci quitte l'organisation. Pour plus d'informations sur les groupes orphelins, reportez-vous à l'article [Attribuer un nouveau propriétaire à un groupe orphelin](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).


<a name="permissions-to-create-teams"></a>Autorisations de créations d'équipes
---------------------------

Par défaut, tous les utilisateurs avec une boîte aux lettres dans Exchange Online disposent des autorisations pour créer des groupes Office 365 et par conséquent une équipe dans Microsoft Teams. Vous pouvez avoir un contrôle plus étroit et limiter la création d’équipes et par conséquent la création de nouveaux groupes Office 365 en déléguant la gestion des droits et la création de groupes à un ensemble d’utilisateurs. Pour plus d'informations, reportez-vous à l’article[Gérer qui peut créer des Groupes Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Icône représentant un point de décision](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Point de décision         |Les utilisateurs Microsoft Teams pourront-ils créer des équipes (recommandé) ?         |
| ![Icône représentant les étapes suivantes](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Étapes suivantes         |Modifiez les autorisations par défaut des utilisateurs autorisés à créer des groupes Office 365 si vous devez limiter les autorisations de création d'équipes.         |
