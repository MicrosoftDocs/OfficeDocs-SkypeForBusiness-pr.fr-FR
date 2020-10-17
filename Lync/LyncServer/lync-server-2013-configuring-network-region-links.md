---
title: 'Lync Server 2013 : configuration des liens de région réseau'
description: 'Lync Server 2013 : configuration des liens de région réseau.'
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
ms.openlocfilehash: b92593f3b8fcd5fe3307a9c193ed7cddcf6dfce0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547010"
---
# <a name="configuring-network-region-links-in-lync-server-2013"></a><span data-ttu-id="4d4dc-103">Configuration des liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d4dc-103">Configuring network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d4dc-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4d4dc-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4d4dc-105">Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="4d4dc-105">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4d4dc-106">Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="4d4dc-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4d4dc-107">Vous pouvez utiliser le panneau de configuration Lync Server pour définir un lien entre deux régions réseau et définir les limitations de bande passante sur les connexions audio et vidéo entre ces régions.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-107">You can use the Lync Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span> <span data-ttu-id="4d4dc-108">Pour plus d’informations sur la suppression d’un lien de région réseau existant, voir [Suppression de liens de région réseau dans Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="4d4dc-108">For details about deleting an existing network region link, see [Deleting network region links in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).</span></span>

<div>

## <a name="to-create-a-network-region-link"></a><span data-ttu-id="4d4dc-109">Pour créer un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="4d4dc-109">To create a network region link</span></span>

1.  <span data-ttu-id="4d4dc-110">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d4dc-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4d4dc-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d4dc-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4d4dc-113">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Lien de région**.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4d4dc-114">Dans la page **Lien de région**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-114">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="4d4dc-115">Dans **Nouveau lien de région**, tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-115">In **New Region Link**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4d4dc-116">Cette valeur doit être unique dans votre déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-116">This value must be unique within your Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="4d4dc-117">Dans la liste déroulante **région réseau \# 1** , sélectionnez l’une des deux régions à lier.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-117">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="4d4dc-118">Dans la liste déroulante **région réseau \# 2** , sélectionnez l’autre région à lier.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-118">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="4d4dc-119">Cette région doit être différente de la région sélectionnée pour la région réseau \# 1.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-119">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="4d4dc-120">(Facultatif) Si vous souhaitez ajouter des limites de bande passante sur les appels audio ou vidéo entre ces régions, sélectionnez un profil de stratégie de bande passante dans la liste déroulante **Stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-120">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="4d4dc-121">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-link"></a><span data-ttu-id="4d4dc-122">Pour modifier un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="4d4dc-122">To modify a network region link</span></span>

1.  <span data-ttu-id="4d4dc-123">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-123">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d4dc-124">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4d4dc-125">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d4dc-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4d4dc-126">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Lien de région**.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-126">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4d4dc-127">Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-127">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="4d4dc-128">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-128">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4d4dc-129">Dans **Modifier le lien de région**, vous pouvez modifier les régions liées ou le profil de stratégie de bande passante pour ce lien.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-129">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="4d4dc-130">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4d4dc-130">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d4dc-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4d4dc-131">See Also</span></span>


[<span data-ttu-id="4d4dc-132">Suppression de liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d4dc-132">Deleting network region links in Lync Server 2013</span></span>](lync-server-2013-deleting-network-region-links.md)  


[<span data-ttu-id="4d4dc-133">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4d4dc-133">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[<span data-ttu-id="4d4dc-134">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4d4dc-134">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[<span data-ttu-id="4d4dc-135">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4d4dc-135">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[<span data-ttu-id="4d4dc-136">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4d4dc-136">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
