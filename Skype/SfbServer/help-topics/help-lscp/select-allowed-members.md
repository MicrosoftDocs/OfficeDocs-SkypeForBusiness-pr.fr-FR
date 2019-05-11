---
title: Sélection des membres autorisés
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Création et gestion des salles de conversation permanente sont beaucoup plus facile avec l’utilisation correcte des catégories. Un administrateur de conversation permanente peut définir AllowedMembers et créateurs pour chaque catégorie et peuvent également définir les paramètres de salle de conversation par défaut et les comportements qui seront appliquées à toutes les salles de conversation créées dans la catégorie. Les administrateurs de conversation permanente créer et gérer des catégories à l’aide du Panneau de configuration ou les applets de commande Windows PowerShell.
ms.openlocfilehash: d7dcb2b6b3fb8712acfb6c35b134a4b15441454d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924625"
---
# <a name="select-allowed-members"></a><span data-ttu-id="0c842-105">Sélection des membres autorisés</span><span class="sxs-lookup"><span data-stu-id="0c842-105">Select Allowed Members</span></span>

<span data-ttu-id="0c842-106">Création et gestion des salles de conversation permanente sont beaucoup plus facile avec l’utilisation correcte des catégories.</span><span class="sxs-lookup"><span data-stu-id="0c842-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="0c842-107">Un administrateur de conversation permanente peut définir **AllowedMembers** et **créateurs** pour chaque catégorie et peuvent également définir les paramètres de salle de conversation par défaut et les comportements qui seront appliquées à toutes les salles de conversation créées dans la catégorie.</span><span class="sxs-lookup"><span data-stu-id="0c842-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="0c842-108">Les administrateurs de conversation permanente créer et gérer des catégories à l’aide du Panneau de configuration ou les applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c842-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="0c842-109">Les utilisateurs, les unités d’organisation et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie.</span><span class="sxs-lookup"><span data-stu-id="0c842-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="0c842-110">Une fois la catégorie est créée, ils peuvent choisir les utilisateurs, les unités d’organisation et les groupes d’utilisateurs à partir de la liste de **AllowedMembers** de la catégorie en tant que gestionnaires de salles de conversation et des membres pour gérer et participer à la salle.</span><span class="sxs-lookup"><span data-stu-id="0c842-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="0c842-111">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="0c842-111">Tasks that you can perform</span></span>

<span data-ttu-id="0c842-112">Dans la page **Sélectionner les membres autorisés**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="0c842-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="0c842-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="0c842-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="0c842-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="0c842-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="0c842-115">Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide de la Skype pour le panneau de configuration serveur Business, voir [Gérer les Skype pour Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="0c842-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="0c842-116">Pour configurer les catégories des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="0c842-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="0c842-117">Dans **l’appartenance**, dans la section **membres autorisés** , ajouter ou supprimer des utilisateurs et autres entités de Services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation et ainsi de suite) sont autorisées à ajouter en tant que membres des salles de conversation appartenant à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="0c842-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="0c842-118">Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (sauf si la salle est masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).</span><span class="sxs-lookup"><span data-stu-id="0c842-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="0c842-119">Pour plus d’informations sur les serveurs de conversation permanente des fonctionnalités, voir [Vue d’ensemble de Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="0c842-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="0c842-120">Pour plus d’informations sur l’utilisation des configurations de serveur de conversation permanente, voir [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) dans la documentation de déploiement et la [gestion de Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="0c842-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c842-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c842-121">See also</span></span>

[<span data-ttu-id="0c842-122">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="0c842-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
