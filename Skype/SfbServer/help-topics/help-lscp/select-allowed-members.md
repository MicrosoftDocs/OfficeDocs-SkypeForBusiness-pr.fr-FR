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
# <a name="select-allowed-members"></a><span data-ttu-id="6c2fc-105">Sélection des membres autorisés</span><span class="sxs-lookup"><span data-stu-id="6c2fc-105">Select Allowed Members</span></span>

<span data-ttu-id="6c2fc-106">La création et la gestion de salles de conversation permanente sont beaucoup plus faciles avec l’utilisation correcte des catégories.</span><span class="sxs-lookup"><span data-stu-id="6c2fc-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="6c2fc-107">Un administrateur de conversation permanente peut définir **AllowedMembers** et **Creators** pour chaque catégorie, et peut également définir les paramètres et comportements de salle de conversation par défaut qui seront appliqués à toutes les salles de conversation créées dans la catégorie.</span><span class="sxs-lookup"><span data-stu-id="6c2fc-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="6c2fc-108">Les administrateurs de conversation permanente créent et gèrent des catégories à l’aide du panneau de Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6c2fc-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="6c2fc-109">Les utilisateurs, les unités d’organisation et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie.</span><span class="sxs-lookup"><span data-stu-id="6c2fc-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="6c2fc-110">Une fois la catégorie créée, ils peuvent choisir des utilisateurs, des utilisateurs et des groupes d’utilisateurs dans la liste **AllowedMembers** de la catégorie en tant que responsables et membres de salle de conversation pour gérer et participer à la salle.</span><span class="sxs-lookup"><span data-stu-id="6c2fc-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="6c2fc-111">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="6c2fc-111">Tasks that you can perform</span></span>

<span data-ttu-id="6c2fc-112">Vous pouvez effectuer les tâches suivantes dans la page **Sélectionner les membres autorisés** :</span><span class="sxs-lookup"><span data-stu-id="6c2fc-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="6c2fc-113">Configurer des catégories</span><span class="sxs-lookup"><span data-stu-id="6c2fc-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="6c2fc-114">Nouvelles fonctionnalités du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6c2fc-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="6c2fc-115">Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du Panneau de contrôle Skype Entreprise Server, voir [Manage Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="6c2fc-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="6c2fc-116">Pour configurer les catégories des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="6c2fc-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="6c2fc-117">Dans l’appartenance, dans la **section** Membres autorisés, ajoutez ou supprimez des utilisateurs et d’autres principaux des services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation, etc.) qui sont autorisés à être ajoutés en tant que membres des salles de conversation appartenant à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="6c2fc-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="6c2fc-118">Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (à moins que la salle ne soit masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).</span><span class="sxs-lookup"><span data-stu-id="6c2fc-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="6c2fc-119">Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de conversation permanente, voir Vue d’ensemble du serveur de [conversation](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) permanente dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="6c2fc-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="6c2fc-120">Pour plus d’informations sur l’utilisation des configurations de serveur de conversation permanente, voir [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="6c2fc-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c2fc-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6c2fc-121">See also</span></span>

[<span data-ttu-id="6c2fc-122">Description de l’appartenance à la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="6c2fc-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
