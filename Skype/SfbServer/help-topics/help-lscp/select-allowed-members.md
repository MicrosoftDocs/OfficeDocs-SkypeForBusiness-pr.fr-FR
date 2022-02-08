---
title: Sélection des membres autorisés
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: La création et la gestion des salles de conversation permanente sont beaucoup plus faciles avec l’utilisation correcte des catégories. Un administrateur de conversation permanente peut définir AllowedMembers et Creators pour chaque catégorie, et peut également définir les paramètres et comportements de salle de conversation par défaut qui seront appliqués à toutes les salles de conversation créées dans la catégorie. Les administrateurs de conversation permanente créent et gèrent des catégories à l’aide du panneau de Windows PowerShell cmdlets.
ms.openlocfilehash: 69e75459e7b94981a2a32885e6db0ea5ebea9804
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386012"
---
# <a name="select-allowed-members"></a>Sélection des membres autorisés

La création et la gestion des salles de conversation permanente sont beaucoup plus faciles avec l’utilisation correcte des catégories. Un administrateur de conversation permanente peut définir **AllowedMembers** et **Creators** pour chaque catégorie, et peut également définir les paramètres et comportements de salle de conversation par défaut qui seront appliqués à toutes les salles de conversation créées dans la catégorie. Les administrateurs de conversation permanente créent et gèrent des catégories à l’aide du panneau de Windows PowerShell cmdlets.

Les utilisateurs, les unités d’organisation et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie créée, ils peuvent choisir des utilisateurs, des utilisateurs et des groupes d’utilisateurs dans la liste **AllowedMembers** de la catégorie en tant que responsables et membres de salle de conversation pour gérer et participer à la salle.

## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Sélectionner les membres autorisés** :

- [Configurer des catégories](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [Nouvelles fonctionnalités du serveur de conversation permanente](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du Panneau de Skype Entreprise Server, voir [Manage Skype Entreprise Server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>Pour configurer les catégories des salles de conversation

Dans l’appartenance **, dans** **la section Membres** autorisés, ajoutez ou supprimez des utilisateurs et d’autres principaux des services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation, etc.) qui sont autorisés à être ajoutés en tant que membres des salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (à moins que la salle ne soit masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).


Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de conversation permanente, voir Vue d’ensemble du serveur de [conversation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) permanente dans la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de serveur de conversation permanente, voir [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.

## <a name="see-also"></a>Voir aussi

[Description de l’appartenance à la conversation permanente](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)