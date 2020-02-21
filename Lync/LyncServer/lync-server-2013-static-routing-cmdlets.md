---
title: 'Lync Server 2013 : cmdlets de routage statique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Static routing cmdlets
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416492(v=OCS.15)
ms:contentKeyID: 48184496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 630d9e6651836c44f961a35d2849558306416d69
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181657"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="static-routing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="03842-102">Cmdlets de routage statique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03842-102">Static routing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03842-103">_**Dernière modification de la rubrique :** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="03842-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="03842-p101">Grâce aux itinéraires statiques, les administrateurs peuvent déterminer à l’avance les itinéraires réseau empruntés par les messages SIP. Quand un message est reçu par un serveur, le serveur contrôle l’adresse du message puis transfère le message au serveur du tronçon suivant préconfiguré par un administrateur. S’ils sont configurés correctement, les itinéraires statiques contribuent à assurer une remise précise et en temps voulu des messages, tout en garantissant une charge minime sur les serveurs.</span><span class="sxs-lookup"><span data-stu-id="03842-p101">With static routes, administrators can predetermine the network routes taken by SIP messages. When a message is received by a server, the server checks the message address and then forwards the message to the next hop server preconfigured by an administrator. If configured correctly, static routes help ensure timely, and accurate, delivery of messages, and with minimal overheard placed on servers.</span></span>

<div>

## <a name="static-routing-cmdlets"></a><span data-ttu-id="03842-107">Applets de commande de routage statique</span><span class="sxs-lookup"><span data-stu-id="03842-107">Static Routing Cmdlets</span></span>

<span data-ttu-id="03842-108">Sauf indication contraire du personnel du support technique Microsoft, les itinéraires statiques configurés pour Microsoft Lync Server 2013 doivent être créés à l’aide de la cmdlet [New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="03842-108">Unless otherwise instructed by Microsoft support personnel, static routes configured for Microsoft Lync Server 2013 should be created using the [New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="03842-109">Une fois qu’un itinéraire a été créé, vous pouvez alors utiliser les applets de commande CsStaticRoutingConfiguration pour l’ajouter à la collection de routage statique.</span><span class="sxs-lookup"><span data-stu-id="03842-109">After a route has been created, you can then use the CsStaticRoutingConfiguration cmdlets to add that route to a static routing collection.</span></span>

<span data-ttu-id="03842-110">**Routage statique**</span><span class="sxs-lookup"><span data-stu-id="03842-110">**Static Routing**</span></span>

  - <span></span>  
    <span data-ttu-id="03842-111">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-111">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="03842-112">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-112">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="03842-113">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-113">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="03842-114">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-114">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="03842-115">[New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-115">[New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="03842-116">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-116">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="03842-117">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-117">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="03842-118">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-118">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="03842-119">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-119">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="03842-120">[New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-120">[New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="03842-121">[New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-121">[New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="03842-122">[New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-122">[New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="03842-123">[New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-123">[New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="03842-124">[New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-124">[New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="03842-125">[New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-125">[New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="03842-126">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-126">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="03842-127">[New-CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="03842-127">[New-CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03842-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03842-128">See Also</span></span>


[<span data-ttu-id="03842-129">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="03842-129">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

