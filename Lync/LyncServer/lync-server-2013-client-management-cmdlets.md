---
title: 'Lync Server 2013 : applets de commande de gestion des clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client management cmdlets
ms:assetid: 0384f8ab-453d-49d6-aaa7-52439e27b7e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398087(v=OCS.15)
ms:contentKeyID: 48183261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa957a6c0c8e995a6e1cff8b0ec1df38ec732c6d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="6bae3-102">Applets de commande de gestion des clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bae3-102">Client management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bae3-103">_**Dernière modification de la rubrique :** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="6bae3-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="6bae3-104">La gestion des clients consiste principalement à déterminer les applications clientes (telles que Microsoft Lync 2013) qui seront autorisées à se connecter à Lync Server 2013 et à déterminer les fonctionnalités disponibles pour ces applications clientes une fois qu’elles ont ouvert une session.</span><span class="sxs-lookup"><span data-stu-id="6bae3-104">Client management consists primarily of determining which client applications (such as Microsoft Lync 2013) will be allowed to log on to Lync Server 2013 and determining the capabilities available to those client applications after they have logged on.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6bae3-105">Pour plus d’informations sur les applets de commande,&nbsp;Voir le blog Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>Server Windows PowerShell à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="6bae3-105">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="6bae3-106">Le contenu de chaque blog et les URL correspondantes peuvent faire l'objet de modifications sans préavis.</span><span class="sxs-lookup"><span data-stu-id="6bae3-106">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="client-management-cmdlets"></a><span data-ttu-id="6bae3-107">Applets de commande de gestion des clients</span><span class="sxs-lookup"><span data-stu-id="6bae3-107">Client Management Cmdlets</span></span>

<span data-ttu-id="6bae3-108">La plupart des tâches de gestion qui s’appliquent à la gestion des clients peuvent être effectuées à partir du panneau de configuration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6bae3-108">Most management tasks that apply to client management can be performed from the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="6bae3-109">Ces mêmes tâches peuvent être exécutées à l’aide d’applets de commande de Lync Server Management Shell ou à partir d’un script.</span><span class="sxs-lookup"><span data-stu-id="6bae3-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="6bae3-110">En utilisant un script, vous pouvez automatiser certaines tâches.</span><span class="sxs-lookup"><span data-stu-id="6bae3-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="6bae3-111">La liste suivante indique les applets de commande qui sont directement associées à la gestion des clients :</span><span class="sxs-lookup"><span data-stu-id="6bae3-111">The following is a list of cmdlets that relate directly to client management:</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-112">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-112">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-113">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-113">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-114">[New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-114">[New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-115">[Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-115">[Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-116">[Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-116">[Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6bae3-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6bae3-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6bae3-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="6bae3-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="6bae3-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6bae3-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

