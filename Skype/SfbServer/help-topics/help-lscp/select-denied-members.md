---
title: Sélection des membres refusés
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Un administrateur de Chat persistants peuvent créer et gérer des catégories de la salle de conversation. Dans le cadre de la création et la gestion des catégories de la salle de conversation, un administrateur de Chat persistante peut configurer des entités de sécurité (groupes/conteneurs/utilisateurs Active Directory Domain Services) qui ont accès à être membres/créateurs de salles de discussion d’une catégorie particulière. Un administrateur de Chat persistante peut également ajouter des DeniedMembers à une catégorie, et ceux-ci deviennent des exclusions explicites à la liste autorisée. DeniedMembers remplacer ce qui est de AllowedMembers.
ms.openlocfilehash: f8fc7179df8facb98408e4506cf681cbefb97c62
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="select-denied-members"></a><span data-ttu-id="0385a-106">Sélection des membres refusés</span><span class="sxs-lookup"><span data-stu-id="0385a-106">Select Denied Members</span></span>
 
<span data-ttu-id="0385a-107">Un administrateur de Chat persistants peuvent créer et gérer des catégories de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="0385a-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="0385a-108">Dans le cadre de la création et la gestion des catégories de la salle de conversation, un administrateur de Chat persistante peut configurer des entités de sécurité (groupes/conteneurs/utilisateurs Active Directory Domain Services) qui ont accès à être membres/créateurs de salles de discussion d’une catégorie particulière.</span><span class="sxs-lookup"><span data-stu-id="0385a-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="0385a-109">Un administrateur de Chat persistante peut également ajouter des DeniedMembers à une catégorie, et ceux-ci deviennent des exclusions explicites à la liste autorisée.</span><span class="sxs-lookup"><span data-stu-id="0385a-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="0385a-110">DeniedMembers remplacer ce qui est de AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="0385a-110">DeniedMembers override what's in AllowedMembers.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="0385a-111">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="0385a-111">Tasks that you can perform</span></span>

<span data-ttu-id="0385a-112">Dans la page **Sélectionner les membres refusés**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="0385a-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>
  
- [<span data-ttu-id="0385a-113">Configurer les catégories</span><span class="sxs-lookup"><span data-stu-id="0385a-113">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="0385a-114">Nouvelles fonctionnalités de serveur de conversation permanent</span><span class="sxs-lookup"><span data-stu-id="0385a-114">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
<span data-ttu-id="0385a-115">Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide de la Skype pour Business Server du Panneau de configuration, voir [Gérer les Skype pour Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="0385a-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="0385a-116">Pour configurer les catégories des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="0385a-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="0385a-117">**Appartenance**, dans la section **membres de refusé** , ajouter ou supprimer des utilisateurs et des autres entités de sécurité Active Directory associées aux membres refusées à partir de la salle de.</span><span class="sxs-lookup"><span data-stu-id="0385a-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
  
### 

<span data-ttu-id="0385a-118">Pour plus d’informations sur les fonctionnalités du serveur de conversation persistant de, consultez [Vue d’ensemble de persistant Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="0385a-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="0385a-119">Pour plus d’informations sur l’utilisation des configurations de serveur de conversation persistant, consultez [Configuration d’un serveur de Chat persistant](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) dans la documentation sur le déploiement et la [gestion de Lync Server 2013, serveur de Chat persistant](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="0385a-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0385a-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0385a-120">See also</span></span>

#### 

[<span data-ttu-id="0385a-121">Présentation de l’appartenance de conversation permanent</span><span class="sxs-lookup"><span data-stu-id="0385a-121">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

