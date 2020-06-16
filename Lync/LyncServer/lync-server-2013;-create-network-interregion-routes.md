---
title: Lync Server 2013 ; Créer des itinéraires inter-région réseau
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
ms.openlocfilehash: 156f2322d5b1b7cc1951f1cbd4df41eb231a8170
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a><span data-ttu-id="b3105-102">Créer des itinéraires inter-région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3105-102">Create network interregion routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3105-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b3105-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b3105-104">A *network interregion route* defines the route between a pair of network regions.</span><span class="sxs-lookup"><span data-stu-id="b3105-104">A *network interregion route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="b3105-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span><span class="sxs-lookup"><span data-stu-id="b3105-105">Each pair of network regions in your call admission control deployment requires a network interregion route.</span></span> <span data-ttu-id="b3105-106">This enables every network region within the deployment to access every other region.</span><span class="sxs-lookup"><span data-stu-id="b3105-106">This enables every network region within the deployment to access every other region.</span></span>

<span data-ttu-id="b3105-107">Alors que les liens de région définissent les limitations de bande passante sur les connexions entre les régions, un itinéraire inter-région détermine le chemin lié qu’empruntera la connexion pour aller d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="b3105-107">While region links set bandwidth limitations on the connections between regions, an interregion route determines which linked path the connection will traverse from one region to another.</span></span>

<span data-ttu-id="b3105-108">Pour plus d’informations sur l’utilisation des itinéraires inter-région réseau, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3105-108">For details about working with network interregion routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="b3105-109">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b3105-109">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="b3105-110">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b3105-110">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="b3105-111">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b3105-111">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [<span data-ttu-id="b3105-112">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="b3105-112">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

<span data-ttu-id="b3105-113">Dans l’exemple de topologie, les itinéraires inter-région réseau doivent être définis pour chacune des trois paires de régions : Amérique du Nord/EMEA, EMEA/APAC et Amérique du Nord/APAC.</span><span class="sxs-lookup"><span data-stu-id="b3105-113">In the example topology, network interregion routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a><span data-ttu-id="b3105-114">Pour créer des itinéraires inter-région réseau à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="b3105-114">To create network interregion routes by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="b3105-115">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b3105-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b3105-116">Exécutez l’applet de commande **New-CsNetworkInterRegionRoute** pour définir les itinéraires nécessaires.</span><span class="sxs-lookup"><span data-stu-id="b3105-116">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="b3105-117">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="b3105-117">For example, run:</span></span>
    
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
    > <span data-ttu-id="b3105-118">L’itinéraire inter-région réseau Amérique du Nord/APAC requiert deux liens de région réseau, car il n’existe aucun lien de région réseau direct entre elles.</span><span class="sxs-lookup"><span data-stu-id="b3105-118">The North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a><span data-ttu-id="b3105-119">Pour créer des itinéraires inter-région réseau à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="b3105-119">To create network interregion routes by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b3105-120">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3105-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b3105-121">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b3105-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b3105-122">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="b3105-122">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="b3105-123">Cliquez sur le bouton de navigation **Itinéraire de région**.</span><span class="sxs-lookup"><span data-stu-id="b3105-123">Click the **Region Route** navigation button.</span></span>

4.  <span data-ttu-id="b3105-124">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b3105-124">Click **New**.</span></span>

5.  <span data-ttu-id="b3105-125">Dans la page **Nouvel itinéraire de région**, cliquez sur **Nom**, puis tapez un nom pour l’itinéraire inter-région réseau.</span><span class="sxs-lookup"><span data-stu-id="b3105-125">On the **New Region Route** page, click **Name** and then type a name for the network interregion route.</span></span>

6.  <span data-ttu-id="b3105-126">Cliquez sur **région réseau \# 1**, puis sur une région réseau dans la liste que vous souhaitez acheminer vers la région réseau \# 2.</span><span class="sxs-lookup"><span data-stu-id="b3105-126">Click **Network Region \#1**, and then click a network region in the list that you want to route to Network Region \#2.</span></span>

7.  <span data-ttu-id="b3105-127">Cliquez sur **région réseau \# 2**, puis sur une région réseau dans la liste que vous souhaitez acheminer vers la région réseau \# 1.</span><span class="sxs-lookup"><span data-stu-id="b3105-127">Click **Network Region \#2**, and then click a network region in the list that you want to route to Network Region \#1.</span></span>

8.  <span data-ttu-id="b3105-128">Cliquez sur **Ajouter** en regard du champ **Liens de région réseau**, puis ajoutez un lien de région réseau qui sera utilisé dans l’itinéraire inter-région réseau.</span><span class="sxs-lookup"><span data-stu-id="b3105-128">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregion route.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="b3105-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span><span class="sxs-lookup"><span data-stu-id="b3105-129">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="b3105-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span><span class="sxs-lookup"><span data-stu-id="b3105-130">For example, the North America/APAC network interregion route requires two network region links because there is no direct network region link between them.</span></span>

    
    </div>

9.  <span data-ttu-id="b3105-131">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b3105-131">Click **Commit**.</span></span>

10. <span data-ttu-id="b3105-132">Pour terminer la création des itinéraires inter-région réseau pour votre topologie, répétez les étapes 4 à 9 en spécifiant les paramètres correspondant à d’autres itinéraires inter-région réseau.</span><span class="sxs-lookup"><span data-stu-id="b3105-132">To finish creating network interregion routes for your topology, repeat steps 4 through 9 with settings for other network interregion routes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

