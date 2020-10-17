---
title: 'Lync Server 2013 : applets de commande de conférence Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing cmdlets
ms:assetid: dac4d934-1500-4799-be4d-82809d4e7eb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415675(v=OCS.15)
ms:contentKeyID: 48185556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a387760cbb7770a199b85c0e891c510fbdb2e72b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535391"
---
# <a name="web-conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="5e49a-102">Applets de commande de conférence Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e49a-102">Web conferencing cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e49a-103">_**Dernière modification de la rubrique :** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="5e49a-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="5e49a-104">Les réunions et les conférences en ligne sont des éléments importants dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e49a-104">Conferencing and online meetings are important elements in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="5e49a-105">Les applets de commande CsConferencingConfiguration et CsConferencingPolicy sont les principaux outils d’administration pour la gestion des conférences à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e49a-105">The CsConferencingConfiguration and CsConferencingPolicy cmdlets are the primary administrative tools for managing conferences by using Windows PowerShell.</span></span>

<div>

## <a name="web-conferencing-cmdlets"></a><span data-ttu-id="5e49a-106">Web Conferencing Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5e49a-106">Web Conferencing Cmdlets</span></span>

<span data-ttu-id="5e49a-107">Les cmdlets [New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15)) et [Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15)) fournissent des méthodes supplémentaires pour configurer et gérer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e49a-107">The [New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15)) and [Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15)) cmdlets provide additional ways to configure and manage Lync Server 2013.</span></span>

<span data-ttu-id="5e49a-108">**Conférence web**</span><span class="sxs-lookup"><span data-stu-id="5e49a-108">**Web Conferencing**</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-109">[Get-applet csconferencedisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-109">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-110">[Remove-applet csconferencedisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-110">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-111">[Set-applet csconferencedisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-111">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5e49a-112">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-112">[Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5e49a-113">[Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-113">[Get-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-114">[New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-114">[New-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-115">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-115">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-116">[Set-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-116">[Set-CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5e49a-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-118">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-118">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-119">[New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-119">[New-CsConferencingPolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-120">[Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-120">[Remove-CsConferencingPolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-121">[Set-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-121">[Set-CsConferencingPolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5e49a-122">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-122">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-123">[New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-123">[New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-124">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-124">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-125">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-125">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="5e49a-126">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-126">[Disable-CsMeetingRoom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))</span></span>

  - <span data-ttu-id="5e49a-127">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-127">[Enable-CsMeetingRoom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))</span></span>

  - <span data-ttu-id="5e49a-128">[Get-CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-128">[Get-CsMeetingRoom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))</span></span>

  - <span data-ttu-id="5e49a-129">[Move-CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-129">[Move-CsMeetingRoom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))</span></span>

  - <span data-ttu-id="5e49a-130">[Set-CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-130">[Set-CsMeetingRoom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="5e49a-131">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-131">[Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-132">[Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-132">[Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-133">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-133">[Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-134">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-134">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-135">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-135">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="5e49a-136">[Test-applet cswebscheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e49a-136">[Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e49a-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e49a-137">See Also</span></span>


[<span data-ttu-id="5e49a-138">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="5e49a-138">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

