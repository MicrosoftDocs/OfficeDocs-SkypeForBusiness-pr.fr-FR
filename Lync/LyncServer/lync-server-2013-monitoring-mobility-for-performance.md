---
title: 'Lync Server 2013 : surveillance de la mobilité pour les performances'
description: 'Lync Server 2013 : surveillance de la mobilité pour des performances optimales.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6c366542e88406df043ba1a782ee12cd64bd804
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562900"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="2cd73-103">Surveillance de la mobilité pour les performances dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cd73-103">Monitoring mobility for performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cd73-104">_**Dernière modification de la rubrique :** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="2cd73-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="2cd73-105">Le service Lync Server Mobility (MCX) et l’API Web Unified Communications (UCWA) augmentent la charge sur les serveurs frontaux et les pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="2cd73-105">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="2cd73-106">Les appareils mobiles qui maintiennent une connexion au serveur même lorsque l’application mobile est réduite, comme les appareils Android et Nokia exécutant Lync 2010 mobile, ainsi que les appareils Android et Apple exécutant Lync 2013 mobile, imposent une charge supérieure aux appareils qui mettent fin à leur connexion au serveur lorsque l’application mobile est réduite.</span><span class="sxs-lookup"><span data-stu-id="2cd73-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="2cd73-107">À mesure que votre utilisation de la mobilité augmente, vous devez surveiller les performances de mobilité afin de déterminer si vous devez augmenter votre capacité.</span><span class="sxs-lookup"><span data-stu-id="2cd73-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="2cd73-108">Plusieurs limites influent sur les performances de mobilité :</span><span class="sxs-lookup"><span data-stu-id="2cd73-108">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="2cd73-109">Mémoire disponible</span><span class="sxs-lookup"><span data-stu-id="2cd73-109">Available memory</span></span>

  - <span data-ttu-id="2cd73-110">Limite de file d’attente de requêtes</span><span class="sxs-lookup"><span data-stu-id="2cd73-110">Request queue limit</span></span>

  - <span data-ttu-id="2cd73-111">Connexions simultanées</span><span class="sxs-lookup"><span data-stu-id="2cd73-111">Concurrent connections</span></span>

  - <span data-ttu-id="2cd73-112">Longueur de file d’attente IIS</span><span class="sxs-lookup"><span data-stu-id="2cd73-112">IIS queue length</span></span>

<span data-ttu-id="2cd73-113">Les autres limites sur les serveurs pouvant influer sur les performances de mobilité sont un maximum de douze abonnements simultanés, des authentifications, des renouvellements de session et des arrêts.</span><span class="sxs-lookup"><span data-stu-id="2cd73-113">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="2cd73-114">Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.</span><span class="sxs-lookup"><span data-stu-id="2cd73-114">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2cd73-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2cd73-115">In This Section</span></span>

  - [<span data-ttu-id="2cd73-116">Surveillance des limites de capacité de mémoire des serveurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cd73-116">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="2cd73-117">Surveillance du service de mobilité et de l’utilisation d’UCWA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cd73-117">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="2cd73-118">Configuration du service de mobilité pour de hautes performances dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cd73-118">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="2cd73-119">Surveillance des fichiers journaux de suivi des demandes IIS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cd73-119">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="2cd73-120">Compteurs de performances de mobilité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cd73-120">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

