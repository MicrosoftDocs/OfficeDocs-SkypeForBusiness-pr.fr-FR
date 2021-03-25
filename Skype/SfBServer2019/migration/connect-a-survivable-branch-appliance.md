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
description: 'Chaque Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert de bureau d’enregistrement de sauvegarde pour le SBA. Lorsque le pool frontal est migré vers Skype Entreprise Server 2019, l’SBA doit être dissocié du pool frontal pendant la mise à niveau du pool. Une fois que le pool a été migré vers Skype Entreprise Server 2019, le SBA peut être réassocié au pool frontal mis à niveau. Cela implique la suppression du SBA de la topologie héritée dans le Générateur de topologie, puis l’ajout du SBA à la topologie Skype Entreprise Server 2019. Les utilisateurs d’un SBA hérité doivent d’abord être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie. Une fois que le SBA est ajouté à la topologie Skype Entreprise Server 2019, ces utilisateurs peuvent ensuite être déplacés vers le SBA. Voici un récapitulatif de ces étapes :'
ms.openlocfilehash: e56bae1631a315b6f42042fb6a7bedd4f144a1b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113340"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="38cde-108">Connexion d’une Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="38cde-108">Connect a Survivable Branch Appliance</span></span>

<span data-ttu-id="38cde-109">Chaque Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert de bureau d’enregistrement de sauvegarde pour le SBA.</span><span class="sxs-lookup"><span data-stu-id="38cde-109">Every Survivable Branch Appliance (SBA) is associated with a Front End pool that serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="38cde-110">Lorsque le pool frontal est migré vers Skype Entreprise Server 2019, le SBA doit être dissocié du pool frontal pendant la mise à niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="38cde-110">When the Front End pool is migrated to Skype for Business Server 2019, the SBA must be disassociated from the Front End pool while the pool is upgraded.</span></span> <span data-ttu-id="38cde-111">Une fois le pool migré vers Skype Entreprise Server 2019, le SBA peut être ré-associé au pool frontal mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="38cde-111">After the pool has been migrated to Skype for Business Server 2019, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="38cde-112">Cela implique la suppression du SBA de la topologie héritée dans le Générateur de topologie, puis l’ajout du SBA à la topologie Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="38cde-112">This involves deleting the SBA from the legacy topology in Topology Builder and then adding the SBA to the Skype for Business Server 2019 topology.</span></span> <span data-ttu-id="38cde-113">Les utilisateurs d’un SBA hérité doivent d’abord être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie.</span><span class="sxs-lookup"><span data-stu-id="38cde-113">Users homed on the legacy SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="38cde-114">Une fois que le SBA est ajouté à la topologie Skype Entreprise Server 2019, ces utilisateurs peuvent être déplacés vers le SBA.</span><span class="sxs-lookup"><span data-stu-id="38cde-114">After the SBA is added to the Skype for Business Server 2019 topology, those users can be moved back to the SBA.</span></span> <span data-ttu-id="38cde-115">Voici un récapitulatif de ces étapes :</span><span class="sxs-lookup"><span data-stu-id="38cde-115">These steps are summarized below:</span></span>
  
1. <span data-ttu-id="38cde-116">Déplacez les utilisateurs de succursales sur le SBA hérité vers un autre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="38cde-116">Move branch users homed on the legacy SBA to another Front End pool.</span></span>
    
2. <span data-ttu-id="38cde-117">Supprimez le SBA de la topologie héritée pour déconnecter le pool frontal existant en tant que bureau d’enregistrement de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="38cde-117">Remove SBA from the legacy topology to disconnect the existing Front End pool as a backup registrar.</span></span>
    
3. <span data-ttu-id="38cde-118">Ajoutez un SBA à la topologie Skype Entreprise Server 2019 et configurez ce nouveau pool frontal en tant que serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="38cde-118">Add SBA to the Skype for Business Server 2019 topology and configure this new Front End pool as the backup registrar.</span></span> 
    
4. <span data-ttu-id="38cde-119">Déplacez les utilisateurs de succursale vers le nouveau SBA Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="38cde-119">Move the branch users to the new Skype for Business Server 2019 SBA.</span></span>
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a><span data-ttu-id="38cde-120">Ajouter un site de succursale SBA hérité à votre topologie</span><span class="sxs-lookup"><span data-stu-id="38cde-120">Add legacy SBA branch site to your topology</span></span>

1. <span data-ttu-id="38cde-121">Ouvrez le **Générateur de topologie**.</span><span class="sxs-lookup"><span data-stu-id="38cde-121">Open **Topology Builder**.</span></span>
    
2. <span data-ttu-id="38cde-122">Dans le volet gauche, cliquez avec le bouton droit sur **Sites de succursale,** puis cliquez sur **Nouveau site de succursale.**</span><span class="sxs-lookup"><span data-stu-id="38cde-122">In the left pane, right-click **Branch sites**, and then click **New Branch Site**.</span></span>
    
3. <span data-ttu-id="38cde-123">Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis tapez le nom du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="38cde-123">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>
    
4. <span data-ttu-id="38cde-124">(Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="38cde-124">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>
    
5. <span data-ttu-id="38cde-125">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="38cde-125">Click **Next**.</span></span>
    
6. <span data-ttu-id="38cde-126">(Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** qui suit, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="38cde-126">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span> 
    
    1. <span data-ttu-id="38cde-127">Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="38cde-127">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2. <span data-ttu-id="38cde-128">Cliquez sur **Dép./Région**, puis tapez le nom du département ou de la région où se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="38cde-128">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3. <span data-ttu-id="38cde-129">Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="38cde-129">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>
    
7. <span data-ttu-id="38cde-130">Cliquez **sur** Suivant, puis, si vous utilisez un Survivable Branch Appliance ou un serveur Survivable Branch Server sur ce site, n’oubliez pas d’ouvrir l’Assistant Nouveau **Survivable Lorsque** cet Assistant ferme la case.</span><span class="sxs-lookup"><span data-stu-id="38cde-130">Click **Next**, and then, if you are using a Survivable Branch Appliance or Server at this site, be sure to clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span> <span data-ttu-id="38cde-131">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="38cde-131">Click **Finish**.</span></span>
    
8. <span data-ttu-id="38cde-132">Pour associer l’ancien SBA au pool frontal Skype Entreprise Server 2019 :</span><span class="sxs-lookup"><span data-stu-id="38cde-132">To associate the legacy SBA to the Skype for Business Server 2019 Front End pool:</span></span>
    
    1. <span data-ttu-id="38cde-133">Développez le site de succursale créé.</span><span class="sxs-lookup"><span data-stu-id="38cde-133">Expand the branch site that has been created.</span></span> 
    
    2. <span data-ttu-id="38cde-134">Cliquez avec le bouton droit sur la version héritée, puis cliquez sur **Nouveau.**</span><span class="sxs-lookup"><span data-stu-id="38cde-134">Right-click on legacy version, and then click **New**.</span></span>
    
    3. <span data-ttu-id="38cde-135">Cliquez **sur Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="38cde-135">Click **Survivable Branch Appliance**.</span></span>
    
9. <span data-ttu-id="38cde-136">Suivez les instructions de l’Assistant qui s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="38cde-136">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="38cde-137">Pour plus d’informations sur les éléments de l’Assistant, voir</span><span class="sxs-lookup"><span data-stu-id="38cde-137">For information about wizard items, see</span></span>    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > <span data-ttu-id="38cde-138">Un Survivable Branch Appliance ne peut être associé qu’à un magasin de surveillance.</span><span class="sxs-lookup"><span data-stu-id="38cde-138">A Survivable Branch Appliance can only be associated with a Monitoring Store.</span></span> 
  
10. <span data-ttu-id="38cde-139">Si vous n’utilisez pas de SBA ou de serveur sur ce site, désactivez la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="38cde-139">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>
    
11. <span data-ttu-id="38cde-140">Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.</span><span class="sxs-lookup"><span data-stu-id="38cde-140">Repeat the previous steps for each branch site you want to add to the topology.</span></span>
