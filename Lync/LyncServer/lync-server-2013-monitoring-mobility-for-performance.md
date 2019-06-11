---
title: 'Lync Server 2013: surveillance de la mobilité pour les performances'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3b6cbdefcb7c78f68fe8838109dea3be5b8203d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="a8354-102">Surveiller la mobilité des performances dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8354-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8354-103">_**Dernière modification de la rubrique:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="a8354-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="a8354-104">Le service de mobilité de Lync Server (MCX) et l’API Web de communications unifiées (UCWA) augmentent la charge de serveurs frontaux et de listes frontales.</span><span class="sxs-lookup"><span data-stu-id="a8354-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="a8354-105">Les appareils mobiles qui maintiennent une connexion au serveur, même lorsque l’application mobile est réduite (par exemple, les appareils Android et Nokia exécutant Lync 2010 mobile, ainsi que les appareils Android et Apple exécutant Lync 2013 mobile, imposent un chargement supérieur aux appareils mettre fin à sa connexion au serveur lorsque l’application mobile est réduite;</span><span class="sxs-lookup"><span data-stu-id="a8354-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="a8354-106">À mesure que votre utilisation mobile augmente, vous devez surveiller les performances de mobilité afin d’identifier toute nécessité d’augmentation de la capacité.</span><span class="sxs-lookup"><span data-stu-id="a8354-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="a8354-107">Plusieurs limites influencent les performances de mobilité :</span><span class="sxs-lookup"><span data-stu-id="a8354-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="a8354-108">mémoire disponible ;</span><span class="sxs-lookup"><span data-stu-id="a8354-108">Available memory</span></span>

  - <span data-ttu-id="a8354-109">limite de file d’attente des demandes ;</span><span class="sxs-lookup"><span data-stu-id="a8354-109">Request queue limit</span></span>

  - <span data-ttu-id="a8354-110">connexions simultanées ;</span><span class="sxs-lookup"><span data-stu-id="a8354-110">Concurrent connections</span></span>

  - <span data-ttu-id="a8354-111">longueur de la file d’attente des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="a8354-111">IIS queue length</span></span>

<span data-ttu-id="a8354-112">Il existe d’autres limitations sur les serveurs qui peuvent influer sur les performances de mobilité, à 12 connexions simultanées, authentifications, renouvellement de session et interruptions.</span><span class="sxs-lookup"><span data-stu-id="a8354-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="a8354-113">Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.</span><span class="sxs-lookup"><span data-stu-id="a8354-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a8354-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a8354-114">In This Section</span></span>

  - [<span data-ttu-id="a8354-115">Surveiller les limites de capacité de mémoire serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8354-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="a8354-116">Surveiller l’utilisation du service de mobilité et de UCWA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8354-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="a8354-117">Configuration d’un service de mobilité pour des performances élevées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8354-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="a8354-118">Surveiller les fichiers journaux de suivi de requête IIS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8354-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="a8354-119">Compteurs de performance de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8354-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

