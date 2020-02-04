---
title: 'Lync Server 2013 : affichage des informations de liaison de la zone réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 935d1a98bd4f446ec8861ae8382eb724611a945f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="fe97d-102">Affichage des informations sur les liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe97d-102">Viewing network region link information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe97d-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fe97d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fe97d-104">Vous pouvez afficher les liens entre deux régions réseau dans le cadre du contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="fe97d-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="fe97d-105">Les régions d’un réseau sont liées par le biais de la connectivité du réseau étendu (WAN) physique.</span><span class="sxs-lookup"><span data-stu-id="fe97d-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="fe97d-106">Vous pouvez utiliser le panneau de configuration de Lync Server pour afficher un lien existant entre deux zones du réseau.</span><span class="sxs-lookup"><span data-stu-id="fe97d-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="fe97d-107">Pour plus d’informations sur la création ou la modification d’un lien de région réseau, voir [configurer les liens de région réseau dans Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="fe97d-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="fe97d-108">Pour afficher un lien de région réseau dans le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="fe97d-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fe97d-109">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="fe97d-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fe97d-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe97d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fe97d-111">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fe97d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fe97d-112">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **liaison de région**.</span><span class="sxs-lookup"><span data-stu-id="fe97d-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="fe97d-113">Dans la page de liaison de la **zone** , cliquez sur le lien de la région que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="fe97d-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe97d-114">Vous pouvez uniquement afficher des informations sur un lien de région à la fois.</span><span class="sxs-lookup"><span data-stu-id="fe97d-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="fe97d-115">Dans le menu **édition** , cliquez sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="fe97d-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fe97d-116">Affichage d’informations sur les liaisons de région réseau à l’aide d’applets de requête Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe97d-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fe97d-117">Vous pouvez afficher les liens de région réseau à l’aide de Windows PowerShell et de l’applet **de requête get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="fe97d-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="fe97d-118">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fe97d-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fe97d-119">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="fe97d-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="fe97d-120">Pour afficher les informations sur le lien dans la région réseau</span><span class="sxs-lookup"><span data-stu-id="fe97d-120">To view network region link information</span></span>

  - <span data-ttu-id="fe97d-121">Pour afficher des informations sur tous les liens de votre région réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="fe97d-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="fe97d-122">Cette commande renvoie le type d’informations suivant :</span><span class="sxs-lookup"><span data-stu-id="fe97d-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="fe97d-123">Pour plus d’informations, consultez la rubrique [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="fe97d-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe97d-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe97d-124">See Also</span></span>


[<span data-ttu-id="fe97d-125">Configuration de liens de site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe97d-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

