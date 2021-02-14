---
title: Sélectionner les créateurs
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
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: La création et la gestion de salles de conversation permanente sont beaucoup plus faciles avec l’utilisation correcte des catégories. Un administrateur de conversation permanente peut définir AllowedMembers et Creators pour chaque catégorie, et peut également définir les paramètres et comportements de salle de conversation par défaut qui seront appliqués à toutes les salles de conversation créées dans la catégorie. Les administrateurs de conversation permanente créent et gèrent des catégories à l’aide du Panneau de Windows PowerShell Skype Entreprise Server.
ms.openlocfilehash: 9fc8bf615de02a4c9eefcd204c832c5c8691eb7e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821954"
---
# <a name="select-creators"></a><span data-ttu-id="ddf85-105">Sélectionner les créateurs</span><span class="sxs-lookup"><span data-stu-id="ddf85-105">Select Creators</span></span>

<span data-ttu-id="ddf85-106">La création et la gestion de salles de conversation permanente sont beaucoup plus faciles avec l’utilisation correcte des catégories.</span><span class="sxs-lookup"><span data-stu-id="ddf85-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="ddf85-107">Un administrateur de conversation permanente peut définir **AllowedMembers** et **Creators** pour chaque catégorie, et peut également définir les paramètres et comportements de salle de conversation par défaut qui seront appliqués à toutes les salles de conversation créées dans la catégorie.</span><span class="sxs-lookup"><span data-stu-id="ddf85-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="ddf85-108">Les administrateurs de conversation permanente créent et gèrent des catégories à l’aide du Panneau de Windows PowerShell Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ddf85-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="ddf85-109">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="ddf85-109">Tasks that you can perform</span></span>

<span data-ttu-id="ddf85-110">Vous pouvez effectuer les tâches suivantes dans la page **Sélectionner les créateurs** :</span><span class="sxs-lookup"><span data-stu-id="ddf85-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="ddf85-111">Configurer des catégories</span><span class="sxs-lookup"><span data-stu-id="ddf85-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="ddf85-112">Nouvelles fonctionnalités du serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ddf85-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="ddf85-113">Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du Panneau de contrôle Skype Entreprise Server, voir [Manage Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="ddf85-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="ddf85-114">Pour configurer les catégories des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="ddf85-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="ddf85-115">Dans **l’appartenance,** dans la section **Créateurs,** ajoutez ou supprimez des utilisateurs et d’autres principaux Active Directory associés aux créateurs de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="ddf85-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="ddf85-116">Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.</span><span class="sxs-lookup"><span data-stu-id="ddf85-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="ddf85-117">Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de conversation permanente, voir Vue d’ensemble du serveur de [conversation](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) permanente dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="ddf85-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="ddf85-118">Pour plus d’informations sur l’utilisation des configurations de serveur de conversation permanente, voir [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="ddf85-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddf85-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ddf85-119">See also</span></span>

[<span data-ttu-id="ddf85-120">Description de l’appartenance à la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ddf85-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="ddf85-121">Utilisation de catégories pour administrer le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="ddf85-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="ddf85-122">Déplacement d’une salle de conversation d’une catégorie vers une autre</span><span class="sxs-lookup"><span data-stu-id="ddf85-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="ddf85-123">Création ou modification d’une salle</span><span class="sxs-lookup"><span data-stu-id="ddf85-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
