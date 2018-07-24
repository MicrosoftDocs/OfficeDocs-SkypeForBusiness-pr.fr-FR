---
title: Sélection des créateurs
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: Création et gestion des salles de conversation permanente sont beaucoup plus facile avec l’utilisation correcte des catégories. Un administrateur de conversation permanente peut définir AllowedMembers et créateurs pour chaque catégorie et permettre également définir les paramètres de salle de conversation par défaut et les comportements qui seront appliquées à toutes les salles de conversation créées dans la catégorie. Persistent Chat créer et gérer les catégories à l’aide de Skype pour le panneau de configuration serveur Business ou Windows PowerShell cmdlets.
ms.openlocfilehash: 9a814a5a6408e80fc1b51679fad80ef8c44f6b49
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21005583"
---
# <a name="select-creators"></a><span data-ttu-id="999fe-105">Sélection des créateurs</span><span class="sxs-lookup"><span data-stu-id="999fe-105">Select Creators</span></span>
 
<span data-ttu-id="999fe-106">Création et gestion des salles de conversation permanente sont beaucoup plus facile avec l’utilisation correcte des catégories.</span><span class="sxs-lookup"><span data-stu-id="999fe-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="999fe-107">Un administrateur de conversation permanente peut définir **AllowedMembers** et **créateurs** pour chaque catégorie et permettre également définir les paramètres de salle de conversation par défaut et les comportements qui seront appliquées à toutes les salles de conversation créées dans la catégorie.</span><span class="sxs-lookup"><span data-stu-id="999fe-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="999fe-108">Persistent Chat créer et gérer les catégories à l’aide de Skype pour le panneau de configuration serveur Business ou Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="999fe-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="999fe-109">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="999fe-109">Tasks that you can perform</span></span>

<span data-ttu-id="999fe-110">Dans la page **Sélectionner les créateurs**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="999fe-110">You can perform the following tasks on the **Select Creators** page:</span></span>
  
- [<span data-ttu-id="999fe-111">Configurer les catégories</span><span class="sxs-lookup"><span data-stu-id="999fe-111">Configure Categories</span></span>](http://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)
    
- [<span data-ttu-id="999fe-112">Nouvelles fonctionnalités de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="999fe-112">New Persistent Chat Server Features</span></span>](http://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)
    
<span data-ttu-id="999fe-113">Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide de la Skype pour le panneau de configuration serveur Business, voir [Gérer les Skype pour Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="999fe-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="999fe-114">Pour configurer les catégories des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="999fe-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="999fe-115">Dans **l’appartenance**, dans la section **créateurs** , ajouter ou supprimer des utilisateurs et autres principaux Active Directory associé aux créateurs de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="999fe-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="999fe-116">Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.</span><span class="sxs-lookup"><span data-stu-id="999fe-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
  


<span data-ttu-id="999fe-117">Pour plus d’informations sur les serveurs de conversation permanente des fonctionnalités, voir [Vue d’ensemble de Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="999fe-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](http://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="999fe-118">Pour plus d’informations sur l’utilisation des configurations de serveur de conversation permanente, voir [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) dans la documentation de déploiement et la [gestion de Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="999fe-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](http://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](http://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="999fe-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="999fe-119">See also</span></span>

[<span data-ttu-id="999fe-120">Présentation de l’appartenance de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="999fe-120">Understanding Persistent Chat Membership</span></span>](http://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
  
[<span data-ttu-id="999fe-121">Utilisation des catégories pour administrer le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="999fe-121">Using Categories to Administer Persistent Chat Server</span></span>](http://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)
  
[<span data-ttu-id="999fe-122">Déplacement d’une salle de conversation à partir d’une catégorie vers une autre</span><span class="sxs-lookup"><span data-stu-id="999fe-122">Moving a Chat Room from One Category to Another</span></span>](http://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)
  
[<span data-ttu-id="999fe-123">Création ou modification d’une salle</span><span class="sxs-lookup"><span data-stu-id="999fe-123">Creating or Editing a New Room</span></span>](http://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)