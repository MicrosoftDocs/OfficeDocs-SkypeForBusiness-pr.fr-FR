---
title: Connexion d’une Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Chaque appareil de branchement survivant (SBA) est associé à une réserve frontale qui sert de bureau d’enregistrement de sauvegarde pour le SBA. Lorsque le pool frontal est migré vers Skype entreprise Server 2019, l’SBA doit être désassocié du pool frontal lors de la mise à niveau du pool, une fois que le regroupement a été déplacé vers Skype entreprise Server 2019, l’adresse SBA peut être réassociée au premier plan. Pool ND. Cela implique la suppression de l’SBA de la topologie héritée dans le générateur de topologie, puis l’ajout de l’SBA à la topologie 2019 de Skype entreprise Server. Les utilisateurs hébergés sur l’ancien SBA doivent d’abord être déplacés vers un autre pool frontal avant de supprimer l’SBA de la topologie. Une fois que le SBA a été ajouté à la topologie 2019 de Skype entreprise Server, il peut ensuite être ramené à l’adresse SBA. Ces étapes sont décrites ci-dessous:'
ms.openlocfilehash: 7cb933018d24dafb978464338f01f97b25e15539
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275544"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="00630-108">Connexion d’une Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="00630-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="00630-109">Chaque appareil branche survivant (SBA) est associé à un pool frontal qui sert de bureau d’enregistrement de sauvegarde pour le SBA.</span><span class="sxs-lookup"><span data-stu-id="00630-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="00630-110">Lorsque le pool frontal est migré vers Skype entreprise Server 2019, l’interface SBA doit être désassociée du pool frontal lors de la mise à niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="00630-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="00630-111">Une fois que le regroupement a été déplacé vers Skype entreprise Server 2019, il est possible d’associer de nouveau l’SBA au pool frontal mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="00630-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="00630-112">Cela implique la suppression de l’SBA de la topologie héritée dans le générateur de topologie, puis l’ajout de l’SBA à la topologie 2019 de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="00630-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="00630-113">Les utilisateurs hébergés sur l’ancien SBA doivent d’abord être déplacés vers un autre pool frontal avant de supprimer l’SBA de la topologie.</span><span class="sxs-lookup"><span data-stu-id="00630-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="00630-114">Une fois que le SBA a été ajouté à la topologie 2019 de Skype entreprise Server, il peut être ramené à l’SBA.</span><span class="sxs-lookup"><span data-stu-id="00630-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="00630-115">Ces étapes sont décrites ci-dessous:</span><span class="sxs-lookup"><span data-stu-id="00630-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="00630-116">Déplacez les utilisateurs de succursales hébergés de l’ancien SBA vers un autre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="00630-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="00630-117">Supprimez SBA de la topologie héritée pour déconnecter le pool frontal existant en tant qu’Bureau d’enregistrement de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="00630-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="00630-118">Ajoutez SBA à la topologie 2019 de Skype entreprise Server et configurez cette nouvelle réserve frontale en tant qu’Bureau d’enregistrement de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="00630-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="00630-119">Déplacez les utilisateurs de la succursale vers le nouveau Skype entreprise Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="00630-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="00630-120">Ajouter un site de filiale hérité de SBA à votre topologie</span><span class="sxs-lookup"><span data-stu-id="00630-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="00630-121">Ouvrez le **Générateur de topologie**.</span><span class="sxs-lookup"><span data-stu-id="00630-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="00630-122">Dans le volet gauche, cliquez avec le bouton droit sur **sites**de succursales, puis cliquez sur **nouveau site de succursale**.</span><span class="sxs-lookup"><span data-stu-id="00630-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="00630-123">Dans la boîte de dialogue **définir un nouveau site de succursale** , cliquez sur **nom**, puis tapez le nom du site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="00630-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="00630-124">Facultatif Cliquez sur **Description**, puis tapez une description significative pour le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="00630-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="00630-125">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="00630-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="00630-126">Facultatif Dans la boîte de dialogue **définir un nouveau site de succursale** suivante, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="00630-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="00630-127">Cliquez sur **City**, puis tapez le nom de la ville dans laquelle se trouve le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="00630-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="00630-128">Cliquez sur **état/région**, puis tapez le nom de l’État ou de la région où se trouve le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="00630-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="00630-129">Cliquez sur **indicatif du pays**, puis tapez le code d’appel à deux chiffres correspondant au pays/la région où se trouve le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="00630-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="00630-130">Cliquez sur **suivant**, puis, si vous utilisez une application ou un serveur Survivable sur ce site, désactivez la case à cocher **ouvrir le nouvel Assistant survie lorsque cet Assistant se ferme** .</span><span class="sxs-lookup"><span data-stu-id="00630-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="00630-131">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="00630-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="00630-132">Pour associer l’ancien SBA au pool frontal 2019 de Skype entreprise Server, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="00630-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="00630-133">Développez le site de succursale qui a été créé.</span><span class="sxs-lookup"><span data-stu-id="00630-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="00630-134">Cliquez avec le bouton droit sur version héritée, puis cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="00630-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="00630-135">Cliquez sur l' **application branchement Survivable**.</span><span class="sxs-lookup"><span data-stu-id="00630-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="00630-136">Suivez les instructions de l’Assistant qui s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="00630-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="00630-137">Pour plus d’informations sur les éléments de l’Assistant, voir</span><span class="sxs-lookup"><span data-stu-id="00630-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="00630-138">Une unité de branchement Survivable ne peut être associée qu’à un magasin d’analyse.</span><span class="sxs-lookup"><span data-stu-id="00630-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="00630-139">Si vous n’utilisez pas d’appareil ou serveur de succursales survivant sur ce site, désactivez la case à cocher **ouvrir le nouvel Assistant survie lorsque cet Assistant se ferme** , puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="00630-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="00630-140">Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.</span><span class="sxs-lookup"><span data-stu-id="00630-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

