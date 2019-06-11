---
title: 'Lync Server 2013: cmdlets de routage statique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Static routing cmdlets
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416492(v=OCS.15)
ms:contentKeyID: 48184496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca2171e66c9441dc2f2f0ff2a8475e03becefd1a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="static-routing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="20240-102">Cmdlets de routage statique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20240-102">Static routing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20240-103">_**Dernière modification de la rubrique:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="20240-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="20240-104">Les itinéraires statiques permettent aux administrateurs de prédéterminer les itinéraires réseau pris par les messages SIP.</span><span class="sxs-lookup"><span data-stu-id="20240-104">With static routes, administrators can predetermine the network routes taken by SIP messages.</span></span> <span data-ttu-id="20240-105">Lorsqu’un message est reçu par un serveur, le serveur vérifie l’adresse du message, puis transfère le message au serveur du tronçon suivant préconfiguré par un administrateur.</span><span class="sxs-lookup"><span data-stu-id="20240-105">When a message is received by a server, the server checks the message address and then forwards the message to the next hop server preconfigured by an administrator.</span></span> <span data-ttu-id="20240-106">S’il est configuré correctement, les itinéraires statiques permettent de garantir l’exactitude et la précision de la remise des messages, et le préentendement minimal placé sur les serveurs.</span><span class="sxs-lookup"><span data-stu-id="20240-106">If configured correctly, static routes help ensure timely, and accurate, delivery of messages, and with minimal overheard placed on servers.</span></span>

<div>

## <a name="static-routing-cmdlets"></a><span data-ttu-id="20240-107">Cmdlets de routage statique</span><span class="sxs-lookup"><span data-stu-id="20240-107">Static Routing Cmdlets</span></span>

<span data-ttu-id="20240-108">Sauf disposition contraire du support technique de Microsoft, les itinéraires statiques configurés pour Microsoft Lync Server 2013 doivent être créés à l’aide de l’applet [de commande New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="20240-108">Unless otherwise instructed by Microsoft support personnel, static routes configured for Microsoft Lync Server 2013 should be created using the [New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="20240-109">Après la création d’un itinéraire, vous pouvez utiliser les applets de CsStaticRoutingConfiguration pour ajouter cet itinéraire à une collection de routage statique.</span><span class="sxs-lookup"><span data-stu-id="20240-109">After a route has been created, you can then use the CsStaticRoutingConfiguration cmdlets to add that route to a static routing collection.</span></span>

<span data-ttu-id="20240-110">**Routage statique**</span><span class="sxs-lookup"><span data-stu-id="20240-110">**Static Routing**</span></span>

  - <span></span>  
    <span data-ttu-id="20240-111">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-111">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="20240-112">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-112">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="20240-113">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-113">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="20240-114">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-114">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="20240-115">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-115">[New-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="20240-116">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-116">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="20240-117">[Nouveau-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-117">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="20240-118">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-118">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="20240-119">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-119">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="20240-120">[Nouveau-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-120">[New-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="20240-121">[Nouveau-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-121">[New-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="20240-122">[Nouveau-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-122">[New-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="20240-123">[Nouveau-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-123">[New-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="20240-124">[Nouveau-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-124">[New-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="20240-125">[Nouveau-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-125">[New-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="20240-126">[Nouveau-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-126">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="20240-127">[Nouveau-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="20240-127">[New-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="20240-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="20240-128">See Also</span></span>


[<span data-ttu-id="20240-129">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="20240-129">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

