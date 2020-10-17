---
title: 'Lync Server 2013 : applets de commande de topologie'
description: 'Lync Server 2013 : applets de commande de topologie.'
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
ms.openlocfilehash: 7f77febaa3beb4acc25bc5bc54dd0d5585fe18fc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549110"
---
# <a name="topology-cmdlets-jn-lync-server-2013"></a><span data-ttu-id="c11be-103">Applets de commande de topologie Jn Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c11be-103">Topology cmdlets jn Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c11be-104">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="c11be-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="c11be-105">La plupart des applets de commande de topologie incluses dans Microsoft Lync Server 2013 sont conçues pour être utilisées avec le générateur de configuration et de topologie ; pour cette raison, il existe un certain nombre d’applets de commande de topologie que les administrateurs appellent rarement directement.</span><span class="sxs-lookup"><span data-stu-id="c11be-105">Many of the topology cmdlets included in Microsoft Lync Server 2013 are designed for use with Setup and Topology Builder; because of that, there are a number of topology cmdlets that administrators will rarely call directly.</span></span> <span data-ttu-id="c11be-106">Toutefois, il est possible que les administrateurs soient tenus d’utiliser ces applets de commande ; par exemple, après la création de nouveaux comptes Kerberos, vous devez exécuter l’applet de commande [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) pour que les modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="c11be-106">However, there will be times when administrators will be required to use these cmdlets; for example, after creating new Kerberos accounts you must run the [Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15)) cmdlet to cause the changes to take effect.</span></span> <span data-ttu-id="c11be-107">En outre, les administrateurs exécuteront probablement des applets de commande telles que [test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) et [test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) pour garantir que Lync Server 2013 a été correctement installé et fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="c11be-107">In addition, administrators will likely run cmdlets such as [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15)) and [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15)) to help ensure that Lync Server 2013 has been correctly installed and is working as expected.</span></span>

<div>

## <a name="topology-cmdlets"></a><span data-ttu-id="c11be-108">Applets de commande de topologie</span><span class="sxs-lookup"><span data-stu-id="c11be-108">Topology Cmdlets</span></span>

<span data-ttu-id="c11be-109">La liste suivante répertorie les applets de commande qui sont directement liées à la gestion de votre topologie Lync Server :</span><span class="sxs-lookup"><span data-stu-id="c11be-109">The following is a list of cmdlets that relate directly managing your Lync Server topology:</span></span>

<span data-ttu-id="c11be-110">**Topologie**</span><span class="sxs-lookup"><span data-stu-id="c11be-110">**Topology**</span></span>

  - <span></span>  
    <span data-ttu-id="c11be-111">[Get-applet cspool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-111">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c11be-112">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-112">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c11be-113">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-113">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c11be-114">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-114">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c11be-115">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-115">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c11be-116">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-116">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c11be-117">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-117">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c11be-118">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-118">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c11be-119">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-119">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c11be-120">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-120">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c11be-121">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-121">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c11be-122">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-122">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c11be-123">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-123">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c11be-124">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-124">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c11be-125">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c11be-125">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c11be-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c11be-126">See Also</span></span>


[<span data-ttu-id="c11be-127">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="c11be-127">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

