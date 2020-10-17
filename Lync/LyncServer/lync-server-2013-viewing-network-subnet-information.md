---
title: 'Lync Server 2013 : affichage des informations de sous-réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453d66d35d02d6b0e91f0c6b82b1ccfe71f149b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535601"
---
# <a name="viewing-network-subnet-information-in-lync-server-2013"></a><span data-ttu-id="c1660-102">Affichage des informations de sous-réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1660-102">Viewing network subnet information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1660-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c1660-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c1660-104">Vous pouvez utiliser la procédure suivante pour afficher un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="c1660-104">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="c1660-105">Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="c1660-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="c1660-106">Pour plus d’informations sur la création ou la modification de sous-réseaux réseau, voir [créer ou modifier des sous-réseaux dans Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="c1660-106">For details about creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<div>

## <a name="to-view-a-network-subnet"></a><span data-ttu-id="c1660-107">Pour afficher un sous-réseau</span><span class="sxs-lookup"><span data-stu-id="c1660-107">To view a network subnet</span></span>

1.  <span data-ttu-id="c1660-108">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="c1660-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c1660-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1660-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c1660-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c1660-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c1660-111">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="c1660-111">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c1660-112">Dans la page **Sous-réseau**, cliquez sur le sous-réseau que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="c1660-112">On the **Subnet** page, click the subnet that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1660-113">Vous ne pouvez afficher qu’un seul sous-réseau à la fois.</span><span class="sxs-lookup"><span data-stu-id="c1660-113">You can only view one subnet at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="c1660-114">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="c1660-114">On the **Edit** menu, click **Show details…**.</span></span>

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c1660-115">Affichage des informations de configuration de sous-réseau à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1660-115">Viewing Network Subnet Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c1660-116">Les informations de sous-réseau peuvent être visualisées à l’aide de Windows PowerShell et de l’applet de commande Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="c1660-116">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="c1660-117">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1660-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c1660-118">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="c1660-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-subnet-information"></a><span data-ttu-id="c1660-119">Pour afficher les informations de sous-réseau</span><span class="sxs-lookup"><span data-stu-id="c1660-119">To view network subnet information</span></span>

  - <span data-ttu-id="c1660-120">Pour afficher des informations sur tous les sous-réseaux de votre réseau, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="c1660-120">To view information about all your network subnets, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="c1660-121">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c1660-121">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

<span data-ttu-id="c1660-122">Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="c1660-122">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1660-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1660-123">See Also</span></span>


[<span data-ttu-id="c1660-124">Création ou modification de sous-réseaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1660-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
[<span data-ttu-id="c1660-125">Suppression de sous-réseaux réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1660-125">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

