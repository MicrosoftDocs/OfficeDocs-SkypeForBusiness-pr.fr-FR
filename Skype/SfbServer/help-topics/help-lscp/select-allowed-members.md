---
title: Sélection des membres autorisés
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Création et gestion de salles de Chat persistant sont beaucoup plus facile avec la bonne utilisation des catégories. Un administrateur de Chat persistants peuvent définir des créateurs et AllowedMembers pour chaque catégorie et peuvent également définir les paramètres par défaut de salle de conversation et les comportements qui s’appliqueront à toutes les salles de conversation créées dans la catégorie. Administrateurs de Chat persistant créer et gérer des catégories en utilisant le panneau de configuration ou les applets de commande Windows PowerShell.
ms.openlocfilehash: 3ced3c26147038cfaba23a8e532982fcf8810592
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="select-allowed-members"></a>Sélection des membres autorisés
 
Création et gestion de salles de Chat persistant sont beaucoup plus facile avec la bonne utilisation des catégories. Un administrateur de Chat persistants peuvent définir des **créateurs** et **AllowedMembers** pour chaque catégorie et peuvent également définir les paramètres par défaut de salle de conversation et les comportements qui s’appliqueront à toutes les salles de conversation créées dans la catégorie. Administrateurs de Chat persistant créer et gérer des catégories en utilisant le panneau de configuration ou les applets de commande Windows PowerShell.
  
Les utilisateurs, les unités d’organisation et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie créée, ils peuvent choisir les utilisateurs, les unités d’organisation et les groupes d’utilisateurs à partir de la liste de **AllowedMembers** de la catégorie en tant que responsables de la salle de conversation et les membres à gérer et à participer à la salle.
  
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Sélectionner les membres autorisés**, vous pouvez effectuer les tâches suivantes :
  
- [Configurer les catégories](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [Nouvelles fonctionnalités de serveur de conversation permanent](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide de la Skype pour Business Server du Panneau de configuration, voir [Gérer les Skype pour Business Server 2015](../../manage/manage.md).
  
## <a name="to-configure-categories-for-chat-rooms"></a>Pour configurer les catégories des salles de conversation

Dans **l’appartenance**, dans la section **membres d’autorisés** , ajouter ou supprimer des utilisateurs et des autres entités de Services de domaine Active Directory (utilisateurs, groupes de distribution, les unités d’organisation, etc.) qui sont autorisées à être ajoutés comme membres de salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (sauf si la salle est masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).
  
### 

Pour plus d’informations sur les fonctionnalités du serveur de conversation persistant de, consultez [Vue d’ensemble de persistant Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de serveur de conversation persistant, consultez [Configuration d’un serveur de Chat persistant](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) dans la documentation sur le déploiement et la [gestion de Lync Server 2013, serveur de Chat persistant](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) dans la documentation sur les opérations.
  
## <a name="see-also"></a>Voir aussi

#### 

[Présentation de l’appartenance de conversation permanent](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

