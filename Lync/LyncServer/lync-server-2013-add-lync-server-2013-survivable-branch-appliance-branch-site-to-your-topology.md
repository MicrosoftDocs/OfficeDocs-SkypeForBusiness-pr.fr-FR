---
title: Ajouter le site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie
description: Ajoutez le site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b50c03dd53c7637fcf0914db290b3e452b64b83
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572030"
---
# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="9c8be-103">Ajouter le site de succursale Survivable Branch Appliance Lync Server 2013 à votre topologie</span><span class="sxs-lookup"><span data-stu-id="9c8be-103">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c8be-104">_**Dernière modification de la rubrique :** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="9c8be-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="9c8be-105">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) ne peut pas être associé à un pool frontal Microsoft Lync Server 2010 comme serveur d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9c8be-105">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="9c8be-106">Le SBA doit être associé à un pool frontal Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c8be-106">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="9c8be-107">Ces étapes supposent une Microsoft Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="9c8be-107">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="9c8be-108">Cette procédure doit être effectuée sur le site central.</span><span class="sxs-lookup"><span data-stu-id="9c8be-108">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="9c8be-109">Pour ajouter des sites de succursale avec Microsoft Lync Server 2013 SBA à votre topologie</span><span class="sxs-lookup"><span data-stu-id="9c8be-109">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="9c8be-110">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9c8be-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="9c8be-111">Dans l’arborescence de la console, développez successivement le site central, **Sites de succursale**, puis cliquez sur **Nouveau site de succursale**.</span><span class="sxs-lookup"><span data-stu-id="9c8be-111">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="9c8be-112">Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis tapez un nom pour le nouveau site de succursale.</span><span class="sxs-lookup"><span data-stu-id="9c8be-112">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="9c8be-113">(Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="9c8be-113">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="9c8be-114">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9c8be-114">Click **Next**.</span></span>

6.  <span data-ttu-id="9c8be-115">(Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** qui suit, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c8be-115">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="9c8be-116">Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="9c8be-116">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="9c8be-117">Cliquez sur **Dép./Région**, puis tapez le nom du département ou de la région où se trouve le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="9c8be-117">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="9c8be-118">Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.</span><span class="sxs-lookup"><span data-stu-id="9c8be-118">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="9c8be-119">Cliquez sur **Suivant** et effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c8be-119">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="9c8be-120">Si vous utilisez un Survivable Branch Appliance ou un serveur Survivable Branch Server sur ce site, vérifiez que la case à cocher **ouvrir l’Assistant Nouveau Survivable Branch Wizard à la fermeture de cet Assistant** est activée.</span><span class="sxs-lookup"><span data-stu-id="9c8be-120">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="9c8be-121">Si vous n’utilisez pas un Survivable Branch Appliance ou un serveur Survivable Branch Server sur ce site, désactivez la case à cocher **ouvrir l’Assistant Nouveau Survivable Branch Server lors de la fermeture de cet Assistant** .</span><span class="sxs-lookup"><span data-stu-id="9c8be-121">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="9c8be-122">Cliquez sur **Terminer**, puis suivez les instructions de l’Assistant qui s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="9c8be-122">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="9c8be-123">Pour plus d’informations sur les éléments de l’Assistant, voir [define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="9c8be-123">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="9c8be-124">Répétez les étapes précédentes pour chaque site de succursale que vous souhaitez ajouter à la topologie.</span><span class="sxs-lookup"><span data-stu-id="9c8be-124">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c8be-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c8be-125">See Also</span></span>


[<span data-ttu-id="9c8be-126">Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c8be-126">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="9c8be-127">Définition d’une passerelle PSTN pour un site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c8be-127">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="9c8be-128">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c8be-128">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="9c8be-129">Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c8be-129">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

