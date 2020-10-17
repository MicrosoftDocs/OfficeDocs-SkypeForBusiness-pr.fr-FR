---
title: 'Lync Server 2013 : colocalisation des serveurs pris en charge pour les composants Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71c8e30cfd4257982781e446a61c18518b570e06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524001"
---
# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="6fdd5-102">Colocalisation de serveur prise en charge pour les composants Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fdd5-102">Supported server collocation for edge components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fdd5-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6fdd5-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6fdd5-104">Le service Edge d’accès, le service Edge de conférence Web, le service Edge A/V et le service proxy XMPP sont colocalisés sur les serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="6fdd5-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="6fdd5-105">Les serveurs suivants fournissent les fonctions nécessaires à l’accès des utilisateurs externes et doivent être déployés en tant que serveurs dédiés :</span><span class="sxs-lookup"><span data-stu-id="6fdd5-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="6fdd5-106">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="6fdd5-106">Edge Server</span></span>

  - <span data-ttu-id="6fdd5-107">Directeur (facultatif)</span><span class="sxs-lookup"><span data-stu-id="6fdd5-107">Director (Optional)</span></span>

  - <span data-ttu-id="6fdd5-108">Proxy inverse</span><span class="sxs-lookup"><span data-stu-id="6fdd5-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6fdd5-109">Le proxy inverse n’a pas besoin d’être dédié pour servir uniquement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fdd5-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="6fdd5-110">Par exemple, vous pouvez fournir des services pour publier les services Web Lync Server et fournir simultanément un site Web publié pour un autre site Web qui n’a aucune incidence sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fdd5-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="6fdd5-111">Si vous disposez déjà d’un serveur proxy inverse dans le réseau de périmètre pour prendre en charge d’autres services, vous pouvez l’utiliser pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fdd5-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

