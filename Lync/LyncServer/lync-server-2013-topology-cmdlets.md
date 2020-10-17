---
title: 'Lync Server 2013 : applets de commande de topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology cmdlets
ms:assetid: 3ed739a7-d58d-475d-8240-fa8d2c6dc7e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415648(v=OCS.15)
ms:contentKeyID: 48183942
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 559bcaca41abb9b28be89baac2adee32ad10ddb0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530371"
---
# <a name="topology-cmdlets-jn-lync-server-2013"></a><span data-ttu-id="188fe-102">Applets de commande de topologie Jn Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="188fe-102">Topology cmdlets jn Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="188fe-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="188fe-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="188fe-104">La plupart des applets de commande de topologie incluses dans Microsoft Lync Server 2013 sont conçues pour être utilisées avec le générateur de configuration et de topologie ; pour cette raison, il existe un certain nombre d’applets de commande de topologie que les administrateurs appellent rarement directement.</span><span class="sxs-lookup"><span data-stu-id="188fe-104">Many of the topology cmdlets included in Microsoft Lync Server 2013 are designed for use with Setup and Topology Builder; because of that, there are a number of topology cmdlets that administrators will rarely call directly.</span></span> <span data-ttu-id="188fe-105">Toutefois, il est possible que les administrateurs soient tenus d’utiliser ces applets de commande ; par exemple, après la création de nouveaux comptes Kerberos, vous devez exécuter l’applet de commande [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) pour que les modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="188fe-105">However, there will be times when administrators will be required to use these cmdlets; for example, after creating new Kerberos accounts you must run the [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) cmdlet to cause the changes to take effect.</span></span> <span data-ttu-id="188fe-106">En outre, les administrateurs exécuteront probablement des applets de commande telles que [test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) et [test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) pour garantir que Lync Server 2013 a été correctement installé et fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="188fe-106">In addition, administrators will likely run cmdlets such as [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) and [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) to help ensure that Lync Server 2013 has been correctly installed and is working as expected.</span></span>

<div>

## <a name="topology-cmdlets"></a><span data-ttu-id="188fe-107">Applets de commande de topologie</span><span class="sxs-lookup"><span data-stu-id="188fe-107">Topology Cmdlets</span></span>

<span data-ttu-id="188fe-108">La liste suivante répertorie les applets de commande qui sont directement liées à la gestion de votre topologie Lync Server :</span><span class="sxs-lookup"><span data-stu-id="188fe-108">The following is a list of cmdlets that relate directly managing your Lync Server topology:</span></span>

<span data-ttu-id="188fe-109">**Topologie**</span><span class="sxs-lookup"><span data-stu-id="188fe-109">**Topology**</span></span>

  - <span></span>  
    <span data-ttu-id="188fe-110">[Get-applet cspool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-110">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="188fe-111">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-111">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="188fe-112">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-112">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="188fe-113">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-113">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="188fe-114">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-114">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="188fe-115">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-115">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="188fe-116">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-116">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="188fe-117">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-117">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="188fe-118">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-118">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="188fe-119">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-119">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="188fe-120">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-120">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="188fe-121">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-121">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="188fe-122">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-122">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="188fe-123">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-123">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="188fe-124">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="188fe-124">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="188fe-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="188fe-125">See Also</span></span>


[<span data-ttu-id="188fe-126">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="188fe-126">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

