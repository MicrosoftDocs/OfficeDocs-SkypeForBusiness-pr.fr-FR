---
title: 'Lync Server 2013 : suppression des itinéraires de région réseau existants'
description: 'Lync Server 2013 : suppression des itinéraires de région réseau existants.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2501dc3f4ed88a56e9f591e3af11a673046280a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557900"
---
# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="33a4c-103">Suppression des itinéraires de région réseau existants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33a4c-103">Deleting existing network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33a4c-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="33a4c-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="33a4c-105">Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="33a4c-105">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="33a4c-106">Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre.</span><span class="sxs-lookup"><span data-stu-id="33a4c-106">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="33a4c-107">Vous pouvez utiliser le panneau de configuration Lync Server pour configurer les itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="33a4c-107">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="33a4c-108">Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau.</span><span class="sxs-lookup"><span data-stu-id="33a4c-108">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="33a4c-109">Utilisez cette rubrique pour supprimer des itinéraires de région réseau existants.</span><span class="sxs-lookup"><span data-stu-id="33a4c-109">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="33a4c-110">Pour plus d’informations sur la création ou la modification des itinéraires de région réseau, voir [création ou modification des itinéraires de région réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="33a4c-110">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="33a4c-111">Pour supprimer un itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="33a4c-111">To delete a network region route</span></span>

1.  <span data-ttu-id="33a4c-112">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="33a4c-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33a4c-113">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33a4c-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="33a4c-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="33a4c-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="33a4c-115">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Itinéraire de région**.</span><span class="sxs-lookup"><span data-stu-id="33a4c-115">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="33a4c-116">Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région à supprimer.</span><span class="sxs-lookup"><span data-stu-id="33a4c-116">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33a4c-p103">Vous pouvez supprimer plusieurs itinéraires de région à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs itinéraires de région. Ou, pour sélectionner tous les itinéraires de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="33a4c-p103">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="33a4c-120">Dans le menu **Edition**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="33a4c-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="33a4c-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="33a4c-121">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33a4c-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33a4c-122">See Also</span></span>


[<span data-ttu-id="33a4c-123">Création ou modification des itinéraires de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33a4c-123">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="33a4c-124">[Configurer un itinéraire de région réseau](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="33a4c-124">[Configure a Network Region Route](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="33a4c-125">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="33a4c-125">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="33a4c-126">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="33a4c-126">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="33a4c-127">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="33a4c-127">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="33a4c-128">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="33a4c-128">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

