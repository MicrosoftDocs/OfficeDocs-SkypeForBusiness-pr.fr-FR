---
title: Sélection des membres refusés
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
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Un administrateur de conversation permanente peut créer et gérer des catégories de salle de conversation. Dans le cadre de la création et de la gestion des catégories de salle de conversation, un administrateur de conversation permanente peut configurer les principaux (groupes/conteneurs/utilisateurs des services de domaine Active Directory) qui ont accès aux membres/créateurs des salles de conversation d’une catégorie particulière. Un administrateur de conversation permanente peut également ajouter des membres refusés à une catégorie et ceux-ci deviennent des exclusions explicites à la liste autorisée. DeniedMembers remplace ce qui se passe dans AllowedMembers.
ms.openlocfilehash: 5a31716c2fae15c6216ed050b543673479415a76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107960"
---
# <a name="select-denied-members"></a><span data-ttu-id="bec1d-106">Sélection des membres refusés</span><span class="sxs-lookup"><span data-stu-id="bec1d-106">Select Denied Members</span></span>

<span data-ttu-id="bec1d-107">Un administrateur de conversation permanente peut créer et gérer des catégories de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="bec1d-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="bec1d-108">Dans le cadre de la création et de la gestion des catégories de salle de conversation, un administrateur de conversation permanente peut configurer les principaux (groupes/conteneurs/utilisateurs des services de domaine Active Directory) qui ont accès aux membres/créateurs des salles de conversation d’une catégorie particulière.</span><span class="sxs-lookup"><span data-stu-id="bec1d-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="bec1d-109">Un administrateur de conversation permanente peut également ajouter des membres refusés à une catégorie et ceux-ci deviennent des exclusions explicites à la liste autorisée.</span><span class="sxs-lookup"><span data-stu-id="bec1d-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="bec1d-110">DeniedMembers remplace ce qui se passe dans AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="bec1d-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="bec1d-111">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="bec1d-111">Tasks that you can perform</span></span>

<span data-ttu-id="bec1d-112">Vous pouvez effectuer les tâches suivantes dans la page **Sélectionner les membres refusés** :</span><span class="sxs-lookup"><span data-stu-id="bec1d-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="bec1d-113">Configurer des catégories</span><span class="sxs-lookup"><span data-stu-id="bec1d-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="bec1d-114">Nouvelles fonctionnalités du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="bec1d-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="bec1d-115">Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du Panneau de contrôle Skype Entreprise Server, voir [Manage Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="bec1d-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="bec1d-116">Pour configurer les catégories des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="bec1d-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="bec1d-117">Dans **l’appartenance**, dans la **section** Membres refusés, ajoutez ou supprimez des utilisateurs et d’autres principaux Active Directory associés à des membres refusés de la salle.</span><span class="sxs-lookup"><span data-stu-id="bec1d-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="bec1d-118">Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de conversation permanente, voir Vue d’ensemble du serveur de [conversation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) permanente dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="bec1d-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="bec1d-119">Pour plus d’informations sur l’utilisation des configurations de serveur de conversation permanente, voir [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="bec1d-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="bec1d-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bec1d-120">See also</span></span>

[<span data-ttu-id="bec1d-121">Description de l’appartenance à la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="bec1d-121">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)