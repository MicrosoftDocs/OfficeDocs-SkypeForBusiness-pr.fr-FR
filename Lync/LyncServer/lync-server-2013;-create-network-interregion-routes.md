---
title: Lync Server 2013; Créer des itinéraires de réseau interrégion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: be1c28450708660e2322144802c81d5458ded6da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "34821816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="a168f-102">Créer des itinéraires réseau interrégion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a168f-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a168f-103">_**Dernière modification de la rubrique:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a168f-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a168f-104">Un *itinéraire réseau interrégional* définit l’itinéraire entre deux régions du réseau.</span><span class="sxs-lookup"><span data-stu-id="a168f-104">A *network interregion route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="a168f-105">Chaque paire de zones réseau dans le déploiement de votre contrôle d’admission des appels nécessite un itinéraire réseau interrégional.</span><span class="sxs-lookup"><span data-stu-id="a168f-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span></span> <span data-ttu-id="a168f-106">Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région.</span><span class="sxs-lookup"><span data-stu-id="a168f-106">This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="a168f-107">Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions, un itinéraire interrégional détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="a168f-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="a168f-108">Pour plus d’informations sur l’utilisation des itinéraires réseau interrégional, voir la documentation Lync Server Management Shell pour les applets de commande suivantes:</span><span class="sxs-lookup"><span data-stu-id="a168f-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="a168f-109">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a168f-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="a168f-110">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a168f-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="a168f-111">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a168f-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="a168f-112">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="a168f-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="a168f-113">Dans l’exemple de topologie, des itinéraires réseau interrégion doivent être définis pour chacune des paires de trois régions: Amérique du Nord/EMEA, EMEA/APAC et Amérique du Nord/APAC.</span><span class="sxs-lookup"><span data-stu-id="a168f-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="a168f-114">Pour créer des itinéraires réseau interrégion à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a168f-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="a168f-115">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a168f-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a168f-116">Exécutez l’applet de commande **New-CsNetworkInterRegionRoute** pour définir les itinéraires nécessaires.</span><span class="sxs-lookup"><span data-stu-id="a168f-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="a168f-117">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="a168f-117">For example, run:</span></span>
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="a168f-118">L’itinéraire interrégional du réseau Amérique du Nord et l’Asie du Nord nécessite deux liaisons de région réseau dans la mesure où il n’existe aucun lien de région réseau directe entre eux.</span><span class="sxs-lookup"><span data-stu-id="a168f-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="a168f-119">Pour créer des itinéraires réseau en utilisant le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="a168f-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a168f-120">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a168f-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a168f-121">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a168f-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a168f-122">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="a168f-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="a168f-123">Cliquez sur le bouton de navigation **Itinéraire de région**.</span><span class="sxs-lookup"><span data-stu-id="a168f-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="a168f-124">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a168f-124">Click **New**.</span></span>

5.  <span data-ttu-id="a168f-125">Sur la page **nouveau routage de zone** , cliquez sur **nom** , puis tapez un nom pour l’itinéraire réseau interrégion.</span><span class="sxs-lookup"><span data-stu-id="a168f-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="a168f-126">Cliquez sur **région \#réseau 1**, puis cliquez sur une région réseau dans la liste que vous voulez diriger vers la région \#2 du réseau.</span><span class="sxs-lookup"><span data-stu-id="a168f-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="a168f-127">Cliquez sur **région \#2**du réseau, puis cliquez sur une région réseau dans la liste que vous voulez diriger vers la \#région 1 du réseau.</span><span class="sxs-lookup"><span data-stu-id="a168f-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="a168f-128">Cliquez sur **Ajouter** à côté du champ liens entre les **zones du réseau** , puis ajoutez un lien de région réseau qui sera utilisé dans l’itinéraire réseau interrégion.</span><span class="sxs-lookup"><span data-stu-id="a168f-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="a168f-129">Si vous créez un itinéraire pour deux régions réseau qui n’ont pas de lien de région réseau direct entre elles, vous devez ajouter tous les liens nécessaires pour terminer l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="a168f-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="a168f-130">Par exemple, l’itinéraire d’interrégion du réseau Amérique du Nord ou Pacifique nécessite deux liaisons de région réseau, car il n’y a pas de lien de région réseau directe entre eux.</span><span class="sxs-lookup"><span data-stu-id="a168f-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="a168f-131">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a168f-131">Click **Commit**.</span></span>

10. <span data-ttu-id="a168f-132">Pour finaliser la création de itinéraires d’interrégion pour votre topologie, répétez les étapes 4 à 9 avec les paramètres des autres itinéraires réseau interrégion.</span><span class="sxs-lookup"><span data-stu-id="a168f-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

