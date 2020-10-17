---
title: 'Lync Server 2013 : affichage des informations de région réseau'
description: 'Lync Server 2013 : affichage des informations de région réseau.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 225cafc392b9b9d0c23f3882d530ad6d2b59f165
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565370"
---
# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="126e6-103">Affichage des informations de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="126e6-103">Viewing network region information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="126e6-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="126e6-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="126e6-105">Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="126e6-105">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="126e6-106">Chaque région réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="126e6-106">Every network region must be associated with a central site.</span></span> <span data-ttu-id="126e6-107">Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute.</span><span class="sxs-lookup"><span data-stu-id="126e6-107">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="126e6-108">Vous pouvez utiliser le panneau de configuration Lync Server pour afficher les régions réseau.</span><span class="sxs-lookup"><span data-stu-id="126e6-108">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="126e6-109">Les régions réseau incluent des paramètres qui déterminent si d’autres chemins via Internet peuvent être empruntés pour les connexions audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="126e6-109">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="126e6-110">Utilisez cette rubrique pour afficher des régions réseau existantes.</span><span class="sxs-lookup"><span data-stu-id="126e6-110">Use this topic to view existing network regions.</span></span> <span data-ttu-id="126e6-111">Pour plus d’informations sur la création ou la modification de régions réseau existantes, voir [Creating or Modifying Network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="126e6-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="126e6-112">Pour afficher des informations sur une région réseau à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="126e6-112">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="126e6-113">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="126e6-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="126e6-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="126e6-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="126e6-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="126e6-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="126e6-116">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Région**.</span><span class="sxs-lookup"><span data-stu-id="126e6-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="126e6-117">Dans la page **Région**, cliquez sur la région que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="126e6-117">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="126e6-118">Vous ne pouvez afficher qu’une région à la fois.</span><span class="sxs-lookup"><span data-stu-id="126e6-118">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="126e6-119">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="126e6-119">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="126e6-120">Affichage des informations de région réseau à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="126e6-120">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="126e6-121">Vous pouvez afficher les informations de région réseau à l’aide de Windows PowerShell et de la cmdlet **Get-applet csnetworkregion** .</span><span class="sxs-lookup"><span data-stu-id="126e6-121">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="126e6-122">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="126e6-122">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="126e6-123">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="126e6-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="126e6-124">Pour afficher les informations de région réseau</span><span class="sxs-lookup"><span data-stu-id="126e6-124">To view network region information</span></span>

  - <span data-ttu-id="126e6-125">Pour afficher des informations sur toutes vos régions réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="126e6-125">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="126e6-126">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="126e6-126">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="126e6-127">Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="126e6-127">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="126e6-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="126e6-128">See Also</span></span>


[<span data-ttu-id="126e6-129">Création ou modification de régions réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="126e6-129">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="126e6-130">Suppression des régions réseau existantes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="126e6-130">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

