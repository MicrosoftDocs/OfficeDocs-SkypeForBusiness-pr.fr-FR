---
title: Lync Server 2013 ; Créer des itinéraires inter-région réseau
description: Lync Server 2013 ; Créez des itinéraires inter-région réseau.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 44c8c62a86f7cfb6ca5b1148dc097c1d7786ad29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546050"
---
# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="5d61a-103">Créer des itinéraires inter-région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d61a-103">Create network interregion routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d61a-104">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="5d61a-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="5d61a-p101">Un *itinéraire inter-région réseau* définit l’itinéraire entre deux régions réseau. Chaque paire de régions réseau dans votre déploiement de contrôle d’admission des appels requiert un itinéraire inter-région réseau. Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région.</span><span class="sxs-lookup"><span data-stu-id="5d61a-p101">A *network interregion route* defines the route between a pair of network regions. Each pair of network regions in your call admission control deployment requires a network interregion route. This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="5d61a-108">Alors que les liens de région définissent les limitations de bande passante sur les connexions entre les régions, un itinéraire inter-région détermine le chemin lié qu’empruntera la connexion pour aller d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="5d61a-108">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="5d61a-109">Pour plus d’informations sur l’utilisation des itinéraires inter-région réseau, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="5d61a-109">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="5d61a-110">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="5d61a-110">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="5d61a-111">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="5d61a-111">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="5d61a-112">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="5d61a-112">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="5d61a-113">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="5d61a-113">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="5d61a-114">Dans l’exemple de topologie, les itinéraires inter-région réseau doivent être définis pour chacune des trois paires de régions : Amérique du Nord/EMEA, EMEA/APAC et Amérique du Nord/APAC.</span><span class="sxs-lookup"><span data-stu-id="5d61a-114">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="5d61a-115">Pour créer des itinéraires inter-région réseau à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="5d61a-115">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="5d61a-116">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5d61a-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5d61a-117">Exécutez l’applet de commande **New-CsNetworkInterRegionRoute** pour définir les itinéraires nécessaires.</span><span class="sxs-lookup"><span data-stu-id="5d61a-117">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="5d61a-118">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="5d61a-118">For example, run:</span></span>
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="5d61a-119">L’itinéraire inter-région réseau Amérique du Nord/APAC requiert deux liens de région réseau, car il n’existe aucun lien de région réseau direct entre elles.</span><span class="sxs-lookup"><span data-stu-id="5d61a-119">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="5d61a-120">Pour créer des itinéraires inter-région réseau à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="5d61a-120">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5d61a-121">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d61a-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5d61a-122">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5d61a-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="5d61a-123">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="5d61a-123">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="5d61a-124">Cliquez sur le bouton de navigation **Itinéraire de région**.</span><span class="sxs-lookup"><span data-stu-id="5d61a-124">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="5d61a-125">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5d61a-125">Click **New**.</span></span>

5.  <span data-ttu-id="5d61a-126">Dans la page **Nouvel itinéraire de région**, cliquez sur **Nom**, puis tapez un nom pour l’itinéraire inter-région réseau.</span><span class="sxs-lookup"><span data-stu-id="5d61a-126">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="5d61a-127">Cliquez sur **région réseau \# 1**, puis sur une région réseau dans la liste que vous souhaitez acheminer vers la région réseau \# 2.</span><span class="sxs-lookup"><span data-stu-id="5d61a-127">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="5d61a-128">Cliquez sur **région réseau \# 2**, puis sur une région réseau dans la liste que vous souhaitez acheminer vers la région réseau \# 1.</span><span class="sxs-lookup"><span data-stu-id="5d61a-128">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="5d61a-129">Cliquez sur **Ajouter** en regard du champ **Liens de région réseau**, puis ajoutez un lien de région réseau qui sera utilisé dans l’itinéraire inter-région réseau.</span><span class="sxs-lookup"><span data-stu-id="5d61a-129">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="5d61a-p104">Si vous créez un itinéraire pour deux régions réseau qui n’ont pas de lien de région réseau direct entre elles, vous devez ajouter tous les liens nécessaires pour terminer l’itinéraire. Par exemple, l’itinéraire inter-région réseau Amérique du Nord/APAC requiert deux liens de région réseau, car il n’existe aucun lien de région réseau direct entre elles.</span><span class="sxs-lookup"><span data-stu-id="5d61a-p104">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route. For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="5d61a-132">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5d61a-132">Click **Commit**.</span></span>

10. <span data-ttu-id="5d61a-133">Pour terminer la création des itinéraires inter-région réseau pour votre topologie, répétez les étapes 4 à 9 en spécifiant les paramètres correspondant à d’autres itinéraires inter-région réseau.</span><span class="sxs-lookup"><span data-stu-id="5d61a-133">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

