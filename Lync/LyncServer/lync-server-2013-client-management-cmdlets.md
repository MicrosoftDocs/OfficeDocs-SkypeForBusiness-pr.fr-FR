---
title: 'Lync Server 2013 : cmdlets de gestion du client'
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
ms.openlocfilehash: 023b7c165d1366d42303f4b609401fcc7bbe6a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="ec773-102">Cmdlets de gestion des clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec773-102">Client management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec773-103">_**Dernière modification de la rubrique :** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="ec773-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="ec773-104">La gestion des clients consiste essentiellement à identifier les applications clientes (par exemple, Microsoft Lync 2013) qui seront autorisées à se connecter à Lync Server 2013 et à déterminer les fonctionnalités disponibles pour ces applications clientes après leur connexion.</span><span class="sxs-lookup"><span data-stu-id="ec773-104">Client management consists primarily of determining which client applications (such as Microsoft Lync 2013) will be allowed to log on to Lync Server 2013 and determining the capabilities available to those client applications after they have logged on.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ec773-105">Pour plus d’informations sur les applets de applet,&nbsp;consultez le blog Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>Server Windows PowerShell à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="ec773-105">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="ec773-106">Le contenu des blogs et leurs URL peuvent être modifiés sans préavis.</span><span class="sxs-lookup"><span data-stu-id="ec773-106">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="client-management-cmdlets"></a><span data-ttu-id="ec773-107">Cmdlets de gestion du client</span><span class="sxs-lookup"><span data-stu-id="ec773-107">Client Management Cmdlets</span></span>

<span data-ttu-id="ec773-108">La plupart des tâches de gestion qui s’appliquent à la gestion des clients peuvent être effectuées à partir du panneau de configuration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec773-108">Most management tasks that apply to client management can be performed from the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="ec773-109">Ces mêmes tâches peuvent être effectuées à l’aide d’applets de interface de Lync Server Management Shell ou à partir d’un script.</span><span class="sxs-lookup"><span data-stu-id="ec773-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="ec773-110">À l’aide d’un script, vous pouvez automatiser certaines tâches.</span><span class="sxs-lookup"><span data-stu-id="ec773-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="ec773-111">La liste suivante répertorie les applets de commande qui concernent directement la gestion du client :</span><span class="sxs-lookup"><span data-stu-id="ec773-111">The following is a list of cmdlets that relate directly to client management:</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-112">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-112">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-113">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-113">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-114">[Nouveau-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-114">[New-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-115">[Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-115">[Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-116">[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-116">[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ec773-117">[Nouveau-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ec773-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-119">[Nouveau-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ec773-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ec773-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-128">[Nouveau-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ec773-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ec773-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

