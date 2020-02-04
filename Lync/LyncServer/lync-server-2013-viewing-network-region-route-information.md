---
title: 'Lync Server 2013 : affichage des informations de routage de la région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8299bd598edf18b7ed7f06088e4bfbbcebab354
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a><span data-ttu-id="c2e0e-102">Affichage des informations sur les itinéraires de la région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2e0e-102">Viewing network region route information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2e0e-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c2e0e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c2e0e-104">Chaque région au sein d’une configuration de contrôle d’admission des appels (CAC) doit disposer d’un moyen d’accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="c2e0e-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="c2e0e-105">Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions et représentent également les liens physiques, un itinéraire détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="c2e0e-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="c2e0e-106">Utilisez les procédures suivantes pour afficher les itinéraires des régions de réseau existants dans Lync Server 2013 Server Control Control ou Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c2e0e-106">Use the following procedures to view existing network region routes in Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="c2e0e-107">Pour plus d’informations sur la création et la modification des itinéraires de région réseau, voir [création ou modification des itinéraires de région réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="c2e0e-107">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a><span data-ttu-id="c2e0e-108">Pour afficher les informations sur les itinéraires de la région réseau dans Lync Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="c2e0e-108">To view network region route information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c2e0e-109">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="c2e0e-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c2e0e-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2e0e-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c2e0e-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c2e0e-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c2e0e-112">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **itinéraire des régions**.</span><span class="sxs-lookup"><span data-stu-id="c2e0e-112">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="c2e0e-113">Sur la page itinéraire de la **région** , cliquez sur le secteur que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="c2e0e-113">On the **Region Route** page, click the region route that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c2e0e-114">Vous pouvez uniquement afficher un itinéraire par région à la fois.</span><span class="sxs-lookup"><span data-stu-id="c2e0e-114">You can only view one region route at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="c2e0e-115">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="c2e0e-115">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c2e0e-116">Affichage des informations sur les itinéraires de région réseau à l’aide d’applets de requête Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2e0e-116">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c2e0e-117">Les informations sur les itinéraires de région réseau peuvent être affichées à l’aide de Windows PowerShell et de l’applet de requête get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="c2e0e-117">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="c2e0e-118">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2e0e-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c2e0e-119">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="c2e0e-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-route-information"></a><span data-ttu-id="c2e0e-120">Pour afficher les informations relatives aux itinéraires de la région réseau</span><span class="sxs-lookup"><span data-stu-id="c2e0e-120">To view network region route information</span></span>

  - <span data-ttu-id="c2e0e-121">Pour afficher des informations sur tous les itinéraires de vos régions réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="c2e0e-121">To view information about all your network region routes, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="c2e0e-122">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="c2e0e-122">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

<span data-ttu-id="c2e0e-123">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="c2e0e-123">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2e0e-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c2e0e-124">See Also</span></span>


[<span data-ttu-id="c2e0e-125">Création ou modification des itinéraires de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2e0e-125">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[<span data-ttu-id="c2e0e-126">Supprimer des itinéraires de région réseau existants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2e0e-126">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

