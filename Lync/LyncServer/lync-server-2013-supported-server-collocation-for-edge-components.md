---
title: 'Lync Server 2013 : Colocalisation de serveur prise en charge pour les composants Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ad78cc1060c64181a75acefa21e64809e0d7b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="a72ff-102">Colocalisation de serveur prise en charge pour les composants Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a72ff-102">Supported server collocation for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a72ff-103">_**Dernière modification de la rubrique:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a72ff-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a72ff-104">Service Edge d’accès, service Edge de conférence Web, service Edge A/V et service proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="a72ff-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="a72ff-105">Les serveurs suivants fournissent les fonctions requises pour l’accès des utilisateurs externes et doivent être déployées en tant que serveurs dédiés:</span><span class="sxs-lookup"><span data-stu-id="a72ff-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="a72ff-106">serveur Edge</span><span class="sxs-lookup"><span data-stu-id="a72ff-106">Edge Server</span></span>

  - <span data-ttu-id="a72ff-107">Director (facultatif)</span><span class="sxs-lookup"><span data-stu-id="a72ff-107">Director (Optional)</span></span>

  - <span data-ttu-id="a72ff-108">Proxy inverse</span><span class="sxs-lookup"><span data-stu-id="a72ff-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a72ff-109">Il n’est pas nécessaire de dédier le proxy inverse au service Lync Server 2013 uniquement.</span><span class="sxs-lookup"><span data-stu-id="a72ff-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="a72ff-110">Par exemple, vous pouvez fournir des services pour publier les services Web de Lync Server et fournir simultanément un site Web publié pour un autre site Web qui n’est pas du tout porteur sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a72ff-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="a72ff-111">Si vous disposez déjà d’un serveur proxy inverse dans le réseau de périmètre pour prendre en charge d’autres services, vous pouvez l’utiliser pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a72ff-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

