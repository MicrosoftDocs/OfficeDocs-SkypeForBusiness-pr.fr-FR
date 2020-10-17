---
title: 'Lync Server 2013 : affichage des informations de lien de région réseau'
description: 'Lync Server 2013 : affichage des informations de lien de région réseau.'
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
ms.openlocfilehash: 0134ded9942ebda91050c1f7b0bbcfef018451a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565360"
---
# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="8551a-103">Affichage des informations de lien de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8551a-103">Viewing network region link information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8551a-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="8551a-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="8551a-105">Vous pouvez afficher les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="8551a-105">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="8551a-106">Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="8551a-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="8551a-107">Vous pouvez utiliser le panneau de configuration Lync Server pour afficher un lien existant entre deux régions réseau.</span><span class="sxs-lookup"><span data-stu-id="8551a-107">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="8551a-108">Pour plus d’informations sur la création ou la modification d’un lien de région réseau, voir [Configuring Network Region Links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="8551a-108">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="8551a-109">Pour afficher un lien de région réseau dans le panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="8551a-109">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8551a-110">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8551a-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8551a-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8551a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8551a-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8551a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8551a-113">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Lien de région**.</span><span class="sxs-lookup"><span data-stu-id="8551a-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="8551a-114">Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="8551a-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8551a-115">Vous ne pouvez afficher des informations que sur un lien de région à la fois.</span><span class="sxs-lookup"><span data-stu-id="8551a-115">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="8551a-116">Dans le menu **Edition**, sélectionnez **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="8551a-116">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8551a-117">Affichage des informations de lien de région réseau à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8551a-117">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8551a-118">Vous pouvez afficher les liens de région réseau à l’aide de Windows PowerShell et de la cmdlet **Get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="8551a-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="8551a-119">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8551a-119">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8551a-120">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="8551a-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="8551a-121">Pour afficher les informations d’un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="8551a-121">To view network region link information</span></span>

  - <span data-ttu-id="8551a-122">Pour afficher des informations sur tous les liens de région réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="8551a-122">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="8551a-123">Cette commande renvoie des informations comme celles-ci :</span><span class="sxs-lookup"><span data-stu-id="8551a-123">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="8551a-124">Pour plus d’informations, voir [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="8551a-124">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8551a-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8551a-125">See Also</span></span>


[<span data-ttu-id="8551a-126">Configuration des liens de sites réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8551a-126">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

