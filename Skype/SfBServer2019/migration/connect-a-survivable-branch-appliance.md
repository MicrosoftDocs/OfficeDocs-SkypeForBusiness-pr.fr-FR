---
title: Connexion d’une Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Chaque serveur Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert à un serveur d’inscriptions de sauvegarde pour le SBA. Lorsque le pool est migré vers Skype pour Business Server 2019, le SBA serveur frontal doit être dissocié du pool frontal alors que le pool est mis à niveau, une fois que le pool a été migré vers Skype pour Business Server 2019, le SBA peut être nouveau associé à la mise à niveau E avant pool ND. Cela consiste à supprimer le SBA à partir de la topologie héritée dans le Générateur de topologie et en ajoutant le SBA à la Skype pour Business Server 2019 topologie. Les utilisateurs hébergés sur hérité que SBA doit tout d’abord être déplacé vers un autre pool frontal avant de supprimer le SBA de la topologie. Une fois le SBA est ajouté à la Skype pour topologie Business Server 2019, ces utilisateurs peuvent ensuite revenir au SBA. Ces étapes sont résumées ci-dessous :'
ms.openlocfilehash: e4917b20e9e680627e92935dcb10ebf06c2e3d2d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887483"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="025b2-108">Connexion d’une Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="025b2-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="025b2-109">Chaque serveur Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert à un serveur d’inscriptions de sauvegarde pour le SBA.</span><span class="sxs-lookup"><span data-stu-id="025b2-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="025b2-110">Lorsque le pool frontal est migré vers Skype pour Business Server 2019, SBA doit être dissocié le pool frontal alors que le pool est mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="025b2-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="025b2-111">Une fois que le pool a été migré vers Skype pour Business Server 2019, le SBA peut être nouveau associé au pool frontal mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="025b2-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="025b2-112">Cela consiste à supprimer le SBA à partir de la topologie héritée dans le Générateur de topologie et en ajoutant le SBA à la Skype pour Business Server 2019 topologie.</span><span class="sxs-lookup"><span data-stu-id="025b2-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="025b2-113">Les utilisateurs hébergés sur hérité que SBA doit tout d’abord être déplacé vers un autre pool frontal avant de supprimer le SBA de la topologie.</span><span class="sxs-lookup"><span data-stu-id="025b2-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="025b2-114">Après que le SBA est ajouté à la Skype pour topologie Business Server 2019, ces utilisateurs peuvent être déplacés vers le SBA.</span><span class="sxs-lookup"><span data-stu-id="025b2-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="025b2-115">Ces étapes sont résumées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="025b2-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="025b2-116">Déplacez les utilisateurs de succursale hébergement sur le SBA hérité vers un autre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="025b2-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="025b2-117">Supprimez le SBA de la topologie héritée pour déconnecter le pool frontal existant en tant qu’un serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="025b2-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="025b2-118">Ajouter le SBA à la Skype pour topologie Business Server 2019 et configurez ce nouveau pool frontal en tant que le serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="025b2-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="025b2-119">Déplacer les utilisateurs de succursale vers le nouveau Skype pour Business Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="025b2-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="025b2-120">Ajouter un site de succursale SBA hérité à votre topologie</span><span class="sxs-lookup"><span data-stu-id="025b2-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="025b2-121">Ouvrez **le Générateur de topologie**.</span><span class="sxs-lookup"><span data-stu-id="025b2-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="025b2-122">Dans le volet gauche, cliquez sur **sites de succursale**, puis cliquez sur **Nouveau Site de succursale**.</span><span class="sxs-lookup"><span data-stu-id="025b2-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="025b2-123">Dans la boîte de dialogue **Définir un nouveau Site de succursale** , cliquez sur **nom**, puis tapez le nom du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="025b2-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="025b2-124">(Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="025b2-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="025b2-125">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="025b2-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="025b2-126">(Facultatif) Dans la boîte de dialogue **Définir un nouveau Site de succursale** suivante, effectuez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="025b2-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="025b2-127">Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="025b2-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="025b2-128">Cliquez sur Dép./région \*\*\*\*, puis tapez le nom de l’état ou la région dans lequel se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="025b2-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="025b2-129">Cliquez sur **Code du pays**, puis tapez le code appelant à deux chiffres pour le pays/la région dans laquelle se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="025b2-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="025b2-130">Cliquez sur **suivant**, puis, si vous utilisez un serveur Survivable Branch Appliance ou un serveur de ce site, veillez à désactiver la case à cocher **Ouvrir l’Assistant Survivable nouvelle fermeture de cet Assistant** .</span><span class="sxs-lookup"><span data-stu-id="025b2-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="025b2-131">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="025b2-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="025b2-132">Pour associer le SBA hérité pour la Skype pour Business Server 2019 un pool frontal :</span><span class="sxs-lookup"><span data-stu-id="025b2-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="025b2-133">Développez le site de succursale qui a été créé.</span><span class="sxs-lookup"><span data-stu-id="025b2-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="025b2-134">Avec le bouton droit sur la version héritée, puis cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="025b2-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="025b2-135">Cliquez sur **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="025b2-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="025b2-136">Suivez les instructions de l’Assistant qui s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="025b2-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="025b2-137">Pour plus d’informations sur les éléments de l’Assistant, consultez</span><span class="sxs-lookup"><span data-stu-id="025b2-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="025b2-138">Un Survivable Branch Appliance peut uniquement être associé à un magasin de surveillance.</span><span class="sxs-lookup"><span data-stu-id="025b2-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="025b2-139">Si vous n’utilisez pas un Survivable Branch Appliance ou un serveur de ce site, désactivez la case à cocher **Ouvrir l’Assistant Survivable nouvelle fermeture de cet Assistant** , puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="025b2-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="025b2-140">Répétez les étapes précédentes pour chaque site de succursale que vous souhaitez ajouter à la topologie.</span><span class="sxs-lookup"><span data-stu-id="025b2-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

