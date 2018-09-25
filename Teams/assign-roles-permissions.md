---
title: Affecter des propriétaires de l’équipe et des membres dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Découvrez comment assigner des rôles et des autorisations de propriétaire et de membre d'équipe dans Microsoft Teams, notamment des autorisations de création d'équipes.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1d5b3f52caf7de455d2b579a3360d17e18602450
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014290"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Affecter des propriétaires de l’équipe et des membres dans Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Dans Microsoft Teams, il existe deux rôles d’utilisateur : **propriétaire** et des **membres**. Par défaut, un utilisateur qui crée une nouvelle équipe est accordé à l’état de propriétaire. Si une équipe est créée à partir d’un groupe de 365 Office existant, les autorisations sont héritées.

Le tableau ci-après présente les différences d'autorisations entre un propriétaire et un membre :

|  |Propriétaire d'équipe  |Membre d'équipe  |
|---------|---------|---------|
|**Créer une équipe**     |Oui        |Non         |
|**Quitter une équipe**     |Oui         |Oui         |
|**Modifier le nom/la description d'une équipe**      |Oui         |Non         |
|**Supprimer une équipe**      |Oui         |Non         |
|**Ajouter un canal**      |Oui         |Oui*         |
|**Modifier le nom/la description d'un canal**      |Oui         |Oui*         |
|**Supprimer un canal**      |Oui         |Oui*         |
|**Ajouter des membres**      |Oui**         |Non         |
|**Ajouter des onglets**      |Oui         |Oui*         |
|**Ajouter des connecteurs**      |Oui         |Oui*         |
|**Ajouter des bots**      |Oui         |Oui*         |
\*Ces éléments peuvent être désactivées par un propriétaire à un niveau équipe, dans ce cas membres auront pas accès à ces derniers.

\*\*Après avoir ajouté un membre à une équipe, un propriétaire peut également promouvoir un membre au statut de Propriétaire. Il est également possible pour un propriétaire de rétrograder son propre statut à celui de membre.



> [!NOTE]
> Les propriétaires peuvent nommer d'autres membres en tant que propriétaires à l'aide de l'option Afficher les équipes. Une équipe peut compter 100 propriétaires maximum. Pour gérer au mieux l'équipe, il est recommandé de définir plusieurs propriétaires ; cela évitera également qu'une équipe comptant un seul propriétaire de se retrouver orpheline si celui-ci quitte l'organisation. Pour plus d'informations sur les groupes orphelins, reportez-vous à l'article [Attribuer un nouveau propriétaire à un groupe orphelin](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).


<a name="permissions-to-create-teams"></a>Autorisations de créations d'équipes
---------------------------

Par défaut, tous les utilisateurs avec une boîte aux lettres dans Exchange Online disposent des autorisations pour créer des groupes d’Office 365 et, par conséquent, une équipe au sein de Microsoft Teams. Vous pouvez contrôler plus étroitement et restreindre la création de nouvelles équipes ainsi que la création de nouveaux groupes d’Office 365 en déléguant la création d’un groupe et les droits de gestion pour un ensemble d’utilisateurs. Pour plus d’informations, voir [Manage qui peut créer des groupes d’Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Icône Point de décision.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Point de décision         |Les utilisateurs Microsoft Teams pourront-ils créer des équipes (recommandé) ?         |
| ![Icône Étapes suivantes.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Étapes suivantes         |Modifiez les autorisations par défaut des utilisateurs autorisés à créer des groupes Office 365 si vous devez limiter les autorisations de création d'équipes.         |
