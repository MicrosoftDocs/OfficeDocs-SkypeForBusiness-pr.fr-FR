---
title: 'Lync Server 2013: cmdlets Mobility'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility cmdlets
ms:assetid: 42a30a34-d66b-4c91-b596-a6fc7666e600
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690019(v=OCS.15)
ms:contentKeyID: 48183973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34b62a35da2d289bee1a08abe354ed990c75e6fb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2cc61-102">Cmdlets de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cc61-102">Mobility cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cc61-103">_**Dernière modification de la rubrique:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="2cc61-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="2cc61-104">Des cmdlets de mobilité ont été introduites pour gérer la fonctionnalité de mobilité ajoutée dans la mise à jour cumulative pour Lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="2cc61-104">Mobility cmdlets were introduced to manage the mobility feature added in cumulative update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="2cc61-105">Utilisez ces applets de applet pour gérer les paramètres des fonctionnalités de mobilité, tels que la configuration de service de mobilité et les stratégies utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2cc61-105">Use these cmdlets to manage settings for mobility features, such as Mobility Service configuration and user policies.</span></span>

<div>

## <a name="mobility-cmdlets"></a><span data-ttu-id="2cc61-106">Cmdlets de mobilité</span><span class="sxs-lookup"><span data-stu-id="2cc61-106">Mobility Cmdlets</span></span>

<span data-ttu-id="2cc61-107">Les applets de commande qui configurent les fonctionnalités de mobilité vous permettent d’exécuter des commandes à partir de Lync Server Management Shell ou d’écrire des scripts pour configurer et tester divers paramètres de mobilité.</span><span class="sxs-lookup"><span data-stu-id="2cc61-107">The cmdlets that configure mobility features allow you to run commands from the Lync Server Management Shell or to write scripts to configure and test various mobility settings.</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-108">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690014(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-108">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690014(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-109">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-109">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690022(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-110">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690054(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-110">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690054(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-111">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh689980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-111">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh689980(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-112">[New-CsWebLink](https://technet.microsoft.com/en-us/library/Hh690053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-112">[New-CsWebLink](https://technet.microsoft.com/en-us/library/Hh690053(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cc61-113">[Get-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690031(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-113">[Get-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690031(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-114">[New-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-114">[New-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690035(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-115">[Remove-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-115">[Remove-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690026(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-116">[Set-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-116">[Set-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690050(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cc61-117">[Get-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-117">[Get-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690017(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-118">[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-118">[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690038(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-119">[New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh689987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-119">[New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh689987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-120">[Remove-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-120">[Remove-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-121">[Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-121">[Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690021(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cc61-122">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-122">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-123">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690027(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-123">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690027(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-124">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690028(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-124">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690028(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-125">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-125">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690013(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2cc61-126">[Test-CsMcxConference](https://technet.microsoft.com/en-us/library/Hh690045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-126">[Test-CsMcxConference](https://technet.microsoft.com/en-us/library/Hh690045(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-127">[Test-CsMcxP2PIM](https://technet.microsoft.com/en-us/library/Hh690020(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-127">[Test-CsMcxP2PIM](https://technet.microsoft.com/en-us/library/Hh690020(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2cc61-128">[Test-CsMcxPushNotification](https://technet.microsoft.com/en-us/library/Hh690043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2cc61-128">[Test-CsMcxPushNotification](https://technet.microsoft.com/en-us/library/Hh690043(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2cc61-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2cc61-129">See Also</span></span>


[<span data-ttu-id="2cc61-130">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cc61-130">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

