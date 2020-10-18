---
title: 'Lync Server 2013 : modes de déviation du trafic multimédia'
description: 'Lync Server 2013 : modes de déviation du trafic multimédia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a7f1a71930df7ef92a29087f42bdb9382b3904c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577900"
---
# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="5f375-103">Modes de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f375-103">Media bypass modes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f375-104">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="5f375-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="5f375-p101">Vous devez configurer le contournement de média à la fois au niveau global et au niveau de chaque jonction PSTN. Lorsque vous activez le contournement de média au niveau global, vous avez le choix entre deux options : **Toujours ignorer** et **Utiliser la configuration des sites et des régions**.</span><span class="sxs-lookup"><span data-stu-id="5f375-p101">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="5f375-p102">L’option **Toujours ignorer** engendre une tentative de contournement pour tous les appels PSTN. \*\*\*\* Cette option s’applique aux déploiements au sein desquels il n’est pas nécessaire d’activer le contrôle d’admission des appels ou pour lesquels il n’est pas nécessaire de spécifier des informations de configuration détaillées sur les tentatives de contournement de média. De plus, **Toujours ignorer** est utilisée lorsque la connectivité entre les clients et les passerelles PSTN est satisfaisante. Dans cette configuration, les sous-réseaux sont mappés à un seul ID de contournement, qui est calculé par le système.</span><span class="sxs-lookup"><span data-stu-id="5f375-p102">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="5f375-p103">L’option **Utiliser la configuration des sites et des régions** associe l’ID de contournement à la configuration de site ou de région chargée de prendre la décision relative au contournement. Cette configuration présente l’avantage d’apporter la souplesse de configurer le contournement pour la plupart des topologies courantes. Elle permet de contrôler de manière précise quand le contournement doit se produire et prend en charge les interactions avec le contrôle d’admission des appels (CAC). Le système tente de vous faciliter la tâche en affectant automatiquement des ID de contournement comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="5f375-p103">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision. This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC). The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="5f375-114">Le système affecte automatiquement un ID de contournement unique à chaque région.</span><span class="sxs-lookup"><span data-stu-id="5f375-114">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="5f375-115">Tout site connecté à une région via une liaison de réseau étendu (WAN) non soumise à des contraintes de bande passante hérite du même ID de contournement que la région.</span><span class="sxs-lookup"><span data-stu-id="5f375-115">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="5f375-116">Un site connecté à une région via une liaison de réseau étendu à bande passante restreinte se voit affecter un ID de contournement différent de celui de la région.</span><span class="sxs-lookup"><span data-stu-id="5f375-116">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="5f375-117">Les sous-réseaux associés à chaque site héritent de l’ID de contournement de ce site.</span><span class="sxs-lookup"><span data-stu-id="5f375-117">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5f375-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f375-118">See Also</span></span>


[<span data-ttu-id="5f375-119">Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f375-119">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="5f375-120">Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f375-120">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="5f375-121">Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f375-121">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

