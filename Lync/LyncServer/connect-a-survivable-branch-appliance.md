---
title: Connexion d’une Survivable Branch Appliance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0fcba962129353ddeb5e5f4c77520cf6d127733
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="4e001-102">Connexion d’une Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="4e001-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e001-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4e001-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4e001-104">Chaque Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert de serveur d’inscriptions de sauvegarde pour le SBA.</span><span class="sxs-lookup"><span data-stu-id="4e001-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="4e001-105">Lorsque le pool frontal est migré vers Lync Server 2013, le SBA doit être désassocié à partir du pool frontal Lync Server 2010, tandis que le pool est mis à niveau, une fois le pool migré vers Lync Server 2013, le SBA peut être réassocié au pool frontal mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="4e001-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="4e001-106">Cela implique de supprimer le SBA de la topologie Lync Server 2010 héritée dans le générateur de topologie, puis d’ajouter le SBA à la topologie Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e001-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="4e001-107">Les utilisateurs hébergés sur l’ancien Lync Server 2010 SBA doivent d’abord être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie.</span><span class="sxs-lookup"><span data-stu-id="4e001-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="4e001-108">Une fois que le SBA est ajouté à la topologie Lync Server 2013, ces utilisateurs peuvent ensuite être déplacés vers le SBA.</span><span class="sxs-lookup"><span data-stu-id="4e001-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="4e001-109">Voici un récapitulatif de ces étapes :</span><span class="sxs-lookup"><span data-stu-id="4e001-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="4e001-110">Déplacez les utilisateurs de succursale hébergés sur l’ancien SBA Lync Server 2010 vers un autre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="4e001-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="4e001-111">Supprimez SBA de la topologie Lync Server 2010 héritée pour déconnecter le pool frontal existant en tant que serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="4e001-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="4e001-112">Ajoutez SBA à la topologie Lync Server 2013 et configurez ce nouveau pool frontal comme serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="4e001-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="4e001-113">Déplacez les utilisateurs de succursale vers le nouveau Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="4e001-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="4e001-114">**Ajouter le site de succursale SBA Lync Server 2010 à votre topologie**</span><span class="sxs-lookup"><span data-stu-id="4e001-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="4e001-115">Ouvrez le **Générateur de topologie**.</span><span class="sxs-lookup"><span data-stu-id="4e001-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="4e001-116">Dans le volet gauche, cliquez avec le bouton droit sur **Sites de succursale**, puis cliquez sur **Nouveau site de succursale**.</span><span class="sxs-lookup"><span data-stu-id="4e001-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="4e001-117">Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis entrez le nom du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="4e001-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="4e001-118">(Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="4e001-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="4e001-119">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4e001-119">Click **Next**.</span></span>

6.  <span data-ttu-id="4e001-120">(Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** qui suit, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4e001-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="4e001-121">Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="4e001-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="4e001-122">Cliquez sur **Dép./Région**, puis tapez le nom du département ou de la région où se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="4e001-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="4e001-123">Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="4e001-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="4e001-124">Cliquez sur **Suivant** et effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4e001-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="4e001-125">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span><span class="sxs-lookup"><span data-stu-id="4e001-125">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span></span> <span data-ttu-id="4e001-126">Click **Finish**.</span><span class="sxs-lookup"><span data-stu-id="4e001-126">Click **Finish**.</span></span>

8.  <span data-ttu-id="4e001-127">Pour associer l’ancien serveur Lync Server 2010 SBA au pool frontal Lync Server 2013, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4e001-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="4e001-128">Développez le site de succursale créé.</span><span class="sxs-lookup"><span data-stu-id="4e001-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="4e001-129">Cliquez avec le bouton droit sur **Lync Server 2010** puis cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="4e001-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="4e001-130">Cliquez sur **Survivable Branch Appliance…**</span><span class="sxs-lookup"><span data-stu-id="4e001-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="4e001-131">Suivez les instructions de l’Assistant qui s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="4e001-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="4e001-132">Pour plus d’informations sur les éléments de l’Assistant, voir [define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="4e001-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4e001-133">Une appliance Survivable Branch Lync Server 2010 ne peut être associée qu’à un magasin de surveillance Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4e001-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="4e001-134">Si vous n’utilisez pas de SBA ou de serveur sur ce site, désactivez la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="4e001-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="4e001-135">Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.</span><span class="sxs-lookup"><span data-stu-id="4e001-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

