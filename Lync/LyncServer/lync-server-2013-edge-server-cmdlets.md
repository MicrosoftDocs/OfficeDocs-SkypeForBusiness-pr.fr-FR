---
title: 'Lync Server 2013 : cmdlets serveur Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server cmdlets
ms:assetid: 1a5427f4-a0d1-4652-8135-91333158ffc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415635(v=OCS.15)
ms:contentKeyID: 48183534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d142bc2a98fbbb1d8147943e379ae1e1a243b18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="b635d-102">Cmdlets du serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b635d-102">Edge Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b635d-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="b635d-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="b635d-104">Les serveurs Edge vous permettent d’étendre les fonctionnalités de Microsoft Lync Server 2013 aux personnes qui ne sont pas connectées à votre réseau interne.</span><span class="sxs-lookup"><span data-stu-id="b635d-104">Edge Servers provide a way for you to extend the capabilities of Microsoft Lync Server 2013 to people who are not logged on to your internal network.</span></span> <span data-ttu-id="b635d-105">Par exemple, si vous avez des utilisateurs distants : les utilisateurs authentifiés qui se connectent à Lync Server 2013 via Internet plutôt que via le réseau interne, vous devez configurer un serveur Edge qui exécute le service Lync Server Access Edge.</span><span class="sxs-lookup"><span data-stu-id="b635d-105">For example, if you have remote users -- authenticated users who log on to Lync Server 2013 over the Internet rather than through the internal network -- you will need to set up an Edge Server that runs the Lync Server Access Edge service.</span></span> <span data-ttu-id="b635d-106">Par ailleurs, il est nécessaire d’utiliser les serveurs de périphérie pour établir une Fédération avec une autre organisation ou pour permettre aux utilisateurs de communiquer avec des personnes disposant de comptes disposant d’un service de messagerie instantanée\!public tel que Yahoo, AOL ou MSN.</span><span class="sxs-lookup"><span data-stu-id="b635d-106">Additionally, Edge Servers are required if you want to establish federation with another organization or if you want to give your users the right to communicate with people who have accounts with a public instant messaging service such as Yahoo\!, AOL, or MSN.</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="b635d-107">À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="b635d-107">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="b635d-108">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="b635d-108">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="b635d-109">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="b635d-109">Messenger until the service shut down date.</span></span> <span data-ttu-id="b635d-110">Date de fin de vie du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="b635d-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="b635d-111">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="b635d-111">has been announced.</span></span> <span data-ttu-id="b635d-112">Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b635d-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="b635d-113">La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="b635d-113">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="b635d-114">Messenger.</span><span class="sxs-lookup"><span data-stu-id="b635d-114">Messenger.</span></span> <span data-ttu-id="b635d-115">La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo !, le contrat sous-jacent pour lequel le son est arrêté.</span><span class="sxs-lookup"><span data-stu-id="b635d-115">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="b635d-116">Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="b635d-116">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="b635d-117">La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync.</span><span class="sxs-lookup"><span data-stu-id="b635d-117">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="b635d-118">Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</span><span class="sxs-lookup"><span data-stu-id="b635d-118">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<div>

## <a name="edge-server-cmdlets"></a><span data-ttu-id="b635d-119">Cmdlets Edge Server</span><span class="sxs-lookup"><span data-stu-id="b635d-119">Edge Server Cmdlets</span></span>

<span data-ttu-id="b635d-120">Vous trouverez ci-dessous une liste des applets de commande liés directement à la gestion des serveurs Edge :</span><span class="sxs-lookup"><span data-stu-id="b635d-120">The following is a list of cmdlets that relate directly to managing Edge Servers:</span></span>

<span data-ttu-id="b635d-121">**serveur Edge**</span><span class="sxs-lookup"><span data-stu-id="b635d-121">**Edge Server**</span></span>

  - <span></span>  
    <span data-ttu-id="b635d-122">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b635d-122">[Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b635d-123">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b635d-123">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b635d-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b635d-124">[Get-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b635d-125">[Nouveau-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b635d-125">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b635d-126">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b635d-126">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="b635d-127">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b635d-127">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b635d-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b635d-128">[Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="b635d-129">[Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="b635d-129">[Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b635d-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b635d-130">See Also</span></span>


[<span data-ttu-id="b635d-131">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b635d-131">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

