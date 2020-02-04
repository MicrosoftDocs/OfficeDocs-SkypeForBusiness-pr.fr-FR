---
title: 'Lync Server 2013 : configuration de liens de région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d069bb5215fc977a35481a916f49e86fa644284
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="e7066-102">Configuration de liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7066-102">Configuring network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7066-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e7066-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e7066-104">Vous pouvez configurer des liens entre deux régions réseau dans le cadre de la commande d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="e7066-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="e7066-105">Les régions d’un réseau sont liées par le biais de la connectivité du réseau étendu (WAN) physique.</span><span class="sxs-lookup"><span data-stu-id="e7066-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="e7066-106">Le panneau de configuration de Lync Server vous permet de définir un lien entre deux zones du réseau et de définir les limites de bande passante pour les connexions audio et vidéo entre ces régions.</span><span class="sxs-lookup"><span data-stu-id="e7066-106">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="e7066-107">Pour plus d’informations sur la suppression d’un lien de région réseau existant, reportez-vous à [la rubrique Suppression de liens de région réseau dans Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="e7066-107">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="e7066-108">Pour créer un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="e7066-108">To create a network region link</span></span>

1.  <span data-ttu-id="e7066-109">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e7066-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e7066-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7066-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e7066-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e7066-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e7066-112">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **liaison de région**.</span><span class="sxs-lookup"><span data-stu-id="e7066-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="e7066-113">Dans la page de **liaison région** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e7066-113">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="e7066-114">Dans le **lien nouvelle zone**, tapez une valeur dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="e7066-114">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7066-115">Cette valeur doit être unique dans le cadre de votre déploiement 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7066-115">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="e7066-116">Dans la liste déroulante \*\* \#région réseau 1\*\* , sélectionnez l’une des deux régions à lier.</span><span class="sxs-lookup"><span data-stu-id="e7066-116">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="e7066-117">Dans la liste déroulante \*\* \#région de réseau 2\*\* , sélectionnez la autre zone à lier.</span><span class="sxs-lookup"><span data-stu-id="e7066-117">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="e7066-118">Cette région doit être différente de la région sélectionnée pour la région \#réseau 1.</span><span class="sxs-lookup"><span data-stu-id="e7066-118">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="e7066-119">Facultatif Si vous voulez appliquer des limitations de bande passante aux appels audio et vidéo entre ces régions, sélectionnez un profil de stratégie de bande passante dans la liste déroulante **stratégie de bande passante** .</span><span class="sxs-lookup"><span data-stu-id="e7066-119">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="e7066-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="e7066-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="e7066-121">Pour modifier un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="e7066-121">To modify a network region link</span></span>

1.  <span data-ttu-id="e7066-122">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e7066-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e7066-123">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7066-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e7066-124">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e7066-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e7066-125">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **liaison de région**.</span><span class="sxs-lookup"><span data-stu-id="e7066-125">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="e7066-126">Dans la page de liaison de la **zone** , cliquez sur le lien dans la région que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="e7066-126">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="e7066-127">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e7066-127">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e7066-128">Dans le **lien modifier la région**, vous pouvez modifier les régions liées ou le profil de la stratégie de bande passante pour ce lien.</span><span class="sxs-lookup"><span data-stu-id="e7066-128">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="e7066-129">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="e7066-129">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7066-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7066-130">See Also</span></span>


[<span data-ttu-id="e7066-131">Supprimer des liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7066-131">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="e7066-132">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e7066-132">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="e7066-133">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e7066-133">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="e7066-134">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e7066-134">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="e7066-135">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e7066-135">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
