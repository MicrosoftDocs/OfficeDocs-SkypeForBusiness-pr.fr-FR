---
title: Sélection des membres autorisés
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: La création et la gestion de salles de conversation permanente sont beaucoup plus faciles avec l’utilisation correcte des catégories. Un administrateur de conversation permanente peut définir AllowedMembers et Creators pour chaque catégorie, et peut également définir les paramètres et comportements de salle de conversation par défaut qui seront appliqués à toutes les salles de conversation créées dans la catégorie. Les administrateurs de conversation permanente créent et gèrent des catégories à l’aide du panneau de Windows PowerShell cmdlets.
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829134"
---
# <a name="select-allowed-members"></a>Sélection des membres autorisés

La création et la gestion de salles de conversation permanente sont beaucoup plus faciles avec l’utilisation correcte des catégories. Un administrateur de conversation permanente peut définir **AllowedMembers** et **Creators** pour chaque catégorie, et peut également définir les paramètres et comportements de salle de conversation par défaut qui seront appliqués à toutes les salles de conversation créées dans la catégorie. Les administrateurs de conversation permanente créent et gèrent des catégories à l’aide du panneau de Windows PowerShell cmdlets.

Les utilisateurs, les unités d’organisation et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie créée, ils peuvent choisir des utilisateurs, des utilisateurs et des groupes d’utilisateurs dans la liste **AllowedMembers** de la catégorie en tant que responsables et membres de salle de conversation pour gérer et participer à la salle.

## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Sélectionner les membres autorisés** :

- [Configurer des catégories](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [Nouvelles fonctionnalités du serveur de conversation permanente](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du Panneau de contrôle Skype Entreprise Server, voir [Manage Skype for Business Server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>Pour configurer les catégories des salles de conversation

Dans l’appartenance, dans la **section** Membres autorisés, ajoutez ou supprimez des utilisateurs et d’autres principaux des services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation, etc.) qui sont autorisés à être ajoutés en tant que membres des salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (à moins que la salle ne soit masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).


Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de conversation permanente, voir Vue d’ensemble du serveur de [conversation](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) permanente dans la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de serveur de conversation permanente, voir [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.

## <a name="see-also"></a>Voir aussi

[Description de l’appartenance à la conversation permanente](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
