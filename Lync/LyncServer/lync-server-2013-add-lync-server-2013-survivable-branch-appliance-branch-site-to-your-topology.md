---
title: Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83ae19b3683b725db64b2f598eb6fc3d182bac17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="831a5-102">Ajout d’un site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie</span><span class="sxs-lookup"><span data-stu-id="831a5-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="831a5-103">_**Dernière modification de la rubrique:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="831a5-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="831a5-104">Microsoft Lync Server 2013 les appareils de branchement Survivables (SBA) ne peuvent pas être associés à un pool Microsoft Lync Server 2010 frontal en tant qu’Bureau d’enregistrement de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="831a5-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="831a5-105">Le SBA doit être associé à un pool Microsoft Lync Server 2013 front end.</span><span class="sxs-lookup"><span data-stu-id="831a5-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="831a5-106">Ces étapes supposent un serveur Microsoft Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="831a5-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="831a5-107">Suivez cette procédure sur le site central.</span><span class="sxs-lookup"><span data-stu-id="831a5-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="831a5-108">Pour ajouter des sites de succursale avec Microsoft Lync Server 2013 SBA à votre topologie</span><span class="sxs-lookup"><span data-stu-id="831a5-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="831a5-109">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="831a5-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="831a5-110">Dans l’arborescence de la console, développez le site central, développez **sites**de succursales, puis cliquez sur **nouveau site de succursale**.</span><span class="sxs-lookup"><span data-stu-id="831a5-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="831a5-111">Dans la boîte de dialogue **définir un nouveau site de succursale** , cliquez sur **nom**, puis tapez un nom pour le nouveau site de succursale.</span><span class="sxs-lookup"><span data-stu-id="831a5-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="831a5-112">Facultatif Cliquez sur **Description**, puis tapez une description significative pour le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="831a5-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="831a5-113">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="831a5-113">Click **Next**.</span></span>

6.  <span data-ttu-id="831a5-114">Facultatif Dans la boîte de dialogue **définir un nouveau site de succursale** suivante, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="831a5-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="831a5-115">Cliquez sur **City**, puis tapez le nom de la ville dans laquelle se trouve le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="831a5-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="831a5-116">Cliquez sur **état/région**, puis tapez le nom de l’État ou de la région où se trouve le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="831a5-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="831a5-117">Cliquez sur **indicatif du pays**, puis tapez le code d’appel à deux chiffres correspondant au pays/la région où se trouve le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="831a5-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="831a5-118">Cliquez sur **suivant**, puis effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="831a5-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="831a5-119">Si vous utilisez un appareil de branchement ou un serveur de succursales survivant sur ce site, vérifiez que la case à cocher **ouvrir le nouvel Assistant survie à la fermeture de cet Assistant** est activée.</span><span class="sxs-lookup"><span data-stu-id="831a5-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="831a5-120">Si vous n’utilisez pas une application de succursale Survivable ou un serveur de succursales survivant sur ce site, désactivez la case à cocher **ouvrir le nouvel Assistant survie à la fermeture de cet Assistant** .</span><span class="sxs-lookup"><span data-stu-id="831a5-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="831a5-121">Cliquez sur **Terminer**, puis suivez les instructions de l’Assistant qui s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="831a5-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="831a5-122">Pour plus d’informations sur les éléments de l’Assistant, voir [définir une unité ou un serveur de succursales survivant dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="831a5-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="831a5-123">Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.</span><span class="sxs-lookup"><span data-stu-id="831a5-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="831a5-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="831a5-124">See Also</span></span>


[<span data-ttu-id="831a5-125">Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831a5-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="831a5-126">Définition d’une passerelle RTC pour un site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831a5-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="831a5-127">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831a5-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="831a5-128">Configurer un Trunk sans dérivation multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831a5-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

