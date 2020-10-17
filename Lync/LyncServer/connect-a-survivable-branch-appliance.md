---
title: Connexion d’une Survivable Branch Appliance
description: Connectez un Survivable Branch appliance.
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
ms.openlocfilehash: f5bbf9e1a4189d3c80d6dec449adf68b82cd3691
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550280"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="67395-103">Connexion d’une Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="67395-103">Connect a Survivable Branch Appliance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67395-104">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="67395-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="67395-105">Chaque Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert de serveur d’inscriptions de sauvegarde pour le SBA.</span><span class="sxs-lookup"><span data-stu-id="67395-105">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="67395-106">Lorsque le pool frontal est migré vers Lync Server 2013, le SBA doit être désassocié à partir du pool frontal Lync Server 2010, tandis que le pool est mis à niveau, une fois le pool migré vers Lync Server 2013, le SBA peut être réassocié au pool frontal mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="67395-106">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="67395-107">Cela implique de supprimer le SBA de la topologie Lync Server 2010 héritée dans le générateur de topologie, puis d’ajouter le SBA à la topologie Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67395-107">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="67395-108">Les utilisateurs hébergés sur l’ancien Lync Server 2010 SBA doivent d’abord être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie.</span><span class="sxs-lookup"><span data-stu-id="67395-108">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="67395-109">Une fois que le SBA est ajouté à la topologie Lync Server 2013, ces utilisateurs peuvent ensuite être déplacés vers le SBA.</span><span class="sxs-lookup"><span data-stu-id="67395-109">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="67395-110">Voici un récapitulatif de ces étapes :</span><span class="sxs-lookup"><span data-stu-id="67395-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="67395-111">Déplacez les utilisateurs de succursale hébergés sur l’ancien SBA Lync Server 2010 vers un autre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="67395-111">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="67395-112">Supprimez SBA de la topologie Lync Server 2010 héritée pour déconnecter le pool frontal existant en tant que serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="67395-112">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="67395-113">Ajoutez SBA à la topologie Lync Server 2013 et configurez ce nouveau pool frontal comme serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="67395-113">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="67395-114">Déplacez les utilisateurs de succursale vers le nouveau Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="67395-114">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="67395-115">**Ajouter le site de succursale SBA Lync Server 2010 à votre topologie**</span><span class="sxs-lookup"><span data-stu-id="67395-115">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="67395-116">Ouvrez le **Générateur de topologie**.</span><span class="sxs-lookup"><span data-stu-id="67395-116">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="67395-117">Dans le volet gauche, cliquez avec le bouton droit sur **Sites de succursale**, puis cliquez sur **Nouveau site de succursale**.</span><span class="sxs-lookup"><span data-stu-id="67395-117">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="67395-118">Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis entrez le nom du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="67395-118">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="67395-119">(Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="67395-119">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="67395-120">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="67395-120">Click **Next**.</span></span>

6.  <span data-ttu-id="67395-121">(Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** qui suit, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="67395-121">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="67395-122">Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="67395-122">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="67395-123">Cliquez sur **Dép./Région**, puis tapez le nom du département ou de la région où se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="67395-123">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="67395-124">Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="67395-124">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="67395-125">Cliquez sur **Suivant** et effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="67395-125">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="67395-p102">Si vous utilisez un SBA ou un serveur Lync 2010 sur ce site, assurez-vous d’avoir désactivé la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**. Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="67395-p102">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option. Click **Finish**.</span></span>

8.  <span data-ttu-id="67395-128">Pour associer l’ancien serveur Lync Server 2010 SBA au pool frontal Lync Server 2013, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="67395-128">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="67395-129">Développez le site de succursale créé.</span><span class="sxs-lookup"><span data-stu-id="67395-129">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="67395-130">Cliquez avec le bouton droit sur **Lync Server 2010** puis cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="67395-130">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="67395-131">Cliquez sur **Survivable Branch Appliance…**</span><span class="sxs-lookup"><span data-stu-id="67395-131">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="67395-132">Suivez les instructions de l’Assistant qui s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="67395-132">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="67395-133">Pour plus d’informations sur les éléments de l’Assistant, voir [define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="67395-133">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="67395-134">Une appliance Survivable Branch Lync Server 2010 ne peut être associée qu’à un magasin de surveillance Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="67395-134">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="67395-135">Si vous n’utilisez pas de SBA ou de serveur sur ce site, désactivez la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="67395-135">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="67395-136">Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.</span><span class="sxs-lookup"><span data-stu-id="67395-136">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

