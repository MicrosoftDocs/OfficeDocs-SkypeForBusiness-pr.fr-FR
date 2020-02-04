---
title: 'Lync Server 2013 : suppression des itinéraires de région réseau existants'
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
ms.openlocfilehash: e9f9ba7c20aff0bba3101edc9b04f3704314cfc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="5a640-102">Supprimer des itinéraires de région réseau existants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a640-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a640-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5a640-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5a640-104">Chaque région au sein d’une configuration de contrôle d’admission des appels (CAC) doit disposer d’un moyen d’accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="5a640-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="5a640-105">Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions et représentent également les liens physiques, un itinéraire détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="5a640-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="5a640-106">Vous pouvez utiliser le panneau de configuration de Lync Server pour configurer les itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="5a640-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="5a640-107">Dans le panneau de configuration de Lync Server, vous pouvez créer, modifier ou supprimer un itinéraire de la région du réseau.</span><span class="sxs-lookup"><span data-stu-id="5a640-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="5a640-108">Utilisez cette rubrique pour supprimer des itinéraires de la région de réseau existants.</span><span class="sxs-lookup"><span data-stu-id="5a640-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="5a640-109">Pour plus d’informations sur la création et la modification des itinéraires de région réseau, voir [création ou modification des itinéraires de région réseau dans Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="5a640-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="5a640-110">Pour supprimer un itinéraire de la région du réseau</span><span class="sxs-lookup"><span data-stu-id="5a640-110">To delete a network region route</span></span>

1.  <span data-ttu-id="5a640-111">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5a640-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5a640-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a640-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5a640-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5a640-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5a640-114">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **itinéraire des régions**.</span><span class="sxs-lookup"><span data-stu-id="5a640-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="5a640-115">Sur la page itinéraire de la **région** , cliquez sur le secteur que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="5a640-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a640-116">Vous pouvez supprimer plusieurs itinéraires par région à la fois.</span><span class="sxs-lookup"><span data-stu-id="5a640-116">You can delete more than one region route at a time.</span></span> <span data-ttu-id="5a640-117">Pour cela, appuyez sur CTRL et sélectionnez plusieurs itinéraires de région tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="5a640-117">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="5a640-118">Pour sélectionner tous les itinéraires de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>édition</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="5a640-118">Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="5a640-119">Dans le menu **modifier** , cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5a640-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="5a640-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a640-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5a640-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a640-121">See Also</span></span>


[<span data-ttu-id="5a640-122">Création ou modification des itinéraires de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a640-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="5a640-123">[Configurer un itinéraire de région réseau](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5a640-123">[Configure a Network Region Route](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="5a640-124">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="5a640-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="5a640-125">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="5a640-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="5a640-126">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="5a640-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="5a640-127">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="5a640-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

