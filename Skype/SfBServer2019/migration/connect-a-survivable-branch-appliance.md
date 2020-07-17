---
title: Connexion d’une Survivable Branch Appliance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Chaque Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert de serveur d’inscriptions de sauvegarde pour le SBA. Lorsque le pool frontal est migré vers Skype entreprise Server 2019, le SBA doit être désactivée du pool frontal pendant la mise à niveau du pool, une fois que le pool a été migré vers Skype entreprise Server 2019, le SBA peut être réassocié au pool frontal mis à niveau. Cela implique de supprimer le SBA de la topologie héritée dans le générateur de topologie, puis d’ajouter le SBA à la topologie Skype entreprise Server 2019. Les utilisateurs hébergés sur le SBA hérité doivent d’abord être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie. Une fois que le SBA est ajouté à la topologie Skype entreprise Server 2019, ces utilisateurs peuvent ensuite être déplacés vers le SBA. Voici un récapitulatif de ces étapes :'
ms.openlocfilehash: 23fea7694a754b82ecad684d2ea02b603a6c7299
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751546"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="37187-108">Connexion d’une Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="37187-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="37187-109">Chaque Survivable Branch Appliance (SBA) est associé à un pool de serveurs frontaux qui sert de serveur d’inscriptions de sauvegarde pour le SBA.</span><span class="sxs-lookup"><span data-stu-id="37187-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="37187-110">Lorsque le pool frontal est migré vers Skype entreprise Server 2019, le SBA doit être désassocié du pool frontal pendant la mise à niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="37187-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="37187-111">Une fois le pool migré vers Skype entreprise Server 2019, le SBA peut être réassocié au pool frontal mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="37187-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="37187-112">Cela implique de supprimer le SBA de la topologie héritée dans le générateur de topologie, puis d’ajouter le SBA à la topologie Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="37187-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="37187-113">Les utilisateurs hébergés sur le SBA hérité doivent d’abord être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie.</span><span class="sxs-lookup"><span data-stu-id="37187-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="37187-114">Une fois que le SBA est ajouté à la topologie Skype entreprise Server 2019, ces utilisateurs peuvent être déplacés vers le SBA.</span><span class="sxs-lookup"><span data-stu-id="37187-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="37187-115">Voici un récapitulatif de ces étapes :</span><span class="sxs-lookup"><span data-stu-id="37187-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="37187-116">Déplacez les utilisateurs de succursale hébergés sur l’SBA hérité dans un autre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="37187-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="37187-117">Supprimez SBA de la topologie héritée pour déconnecter le pool frontal existant en tant que serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="37187-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="37187-118">Ajoutez SBA à la topologie Skype entreprise Server 2019 et configurez ce nouveau pool frontal comme serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="37187-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="37187-119">Déplacez les utilisateurs de succursale vers le nouveau Skype entreprise Server 2019 SBA.</span><span class="sxs-lookup"><span data-stu-id="37187-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="37187-120">Ajouter un site de succursale hérité SBA à votre topologie</span><span class="sxs-lookup"><span data-stu-id="37187-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="37187-121">Ouvrez le **Générateur de topologie**.</span><span class="sxs-lookup"><span data-stu-id="37187-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="37187-122">Dans le volet de gauche, cliquez avec le bouton droit sur **sites de succursale**, puis cliquez sur **nouveau site de succursale**.</span><span class="sxs-lookup"><span data-stu-id="37187-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="37187-123">Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis tapez le nom du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="37187-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="37187-124">(Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="37187-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="37187-125">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="37187-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="37187-126">(Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** qui suit, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="37187-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="37187-127">Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="37187-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="37187-128">Cliquez sur **Dép./Région**, puis tapez le nom du département ou de la région où se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="37187-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="37187-129">Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="37187-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="37187-130">Cliquez sur **suivant**, puis, si vous utilisez un Survivable Branch Appliance ou serveur sur ce site, veillez à désactiver la case à cocher **ouvrir l’Assistant Nouveau Survivable** Branch Server à la fermeture de cet Assistant.</span><span class="sxs-lookup"><span data-stu-id="37187-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="37187-131">Cliquez sur**Terminer**.</span><span class="sxs-lookup"><span data-stu-id="37187-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="37187-132">Pour associer le SBA hérité au pool frontal Skype entreprise Server 2019, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="37187-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="37187-133">Développez le site de succursale créé.</span><span class="sxs-lookup"><span data-stu-id="37187-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="37187-134">Cliquez avec le bouton droit sur version héritée, puis cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="37187-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="37187-135">Cliquez sur **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="37187-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="37187-136">Suivez les instructions de l’Assistant qui s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="37187-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="37187-137">Pour plus d’informations sur les éléments de l’Assistant, voir</span><span class="sxs-lookup"><span data-stu-id="37187-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="37187-138">Un Survivable Branch Appliance ne peut être associé qu’à un magasin de surveillance.</span><span class="sxs-lookup"><span data-stu-id="37187-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="37187-139">Si vous n’utilisez pas de SBA ou de serveur sur ce site, désactivez la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="37187-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="37187-140">Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.</span><span class="sxs-lookup"><span data-stu-id="37187-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
    

