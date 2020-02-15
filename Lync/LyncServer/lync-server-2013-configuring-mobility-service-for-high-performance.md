---
title: 'Lync Server 2013 : configuration du service de mobilité pour de hautes performances'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 460c56a9e51ab64491402eed22d40d60ad7d89c1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="c1f6b-102">Configuration du service de mobilité pour de hautes performances dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1f6b-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1f6b-103">_**Dernière modification de la rubrique :** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="c1f6b-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c1f6b-104">Cette rubrique s’applique uniquement au service de mobilité Lync Server 2013 (MCX) et ne s’applique pas à la UCWA (Unified Communications Web API), telle qu’elle est fournie dans les mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="c1f6b-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="c1f6b-105">Lorsque vous installez le service de mobilité (MCX) sur Internet Information Services (IIS) 7,5, le programme d’installation de Mobility service configure certains paramètres de performances sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c1f6b-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="c1f6b-106">Nous vous recommandons d’utiliser les services Internet (IIS) 7.5 pour la mobilité.</span><span class="sxs-lookup"><span data-stu-id="c1f6b-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="c1f6b-107">Ceux-ci affectent la quantité maximale de demandes utilisateur simultanées et la quantité maximale de threads autorisés pour le service de mobilité.</span><span class="sxs-lookup"><span data-stu-id="c1f6b-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="c1f6b-108">Voici les paramètres de performances :</span><span class="sxs-lookup"><span data-stu-id="c1f6b-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="c1f6b-109">Paramètres pour MCX sur IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="c1f6b-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="c1f6b-110">**maxConcurrentThreadsPerCPU** a la valeur zéro (0).</span><span class="sxs-lookup"><span data-stu-id="c1f6b-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="c1f6b-111">**maxConcurrentRequestsPerCPU** a la valeur zéro (0).</span><span class="sxs-lookup"><span data-stu-id="c1f6b-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="c1f6b-112">Le modèle de processus ASP.NET est AutoConfig (pour les services Internet (IIS) 7.5 uniquement).</span><span class="sxs-lookup"><span data-stu-id="c1f6b-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="c1f6b-113">La limite de file d’attente HTTP.sys a la valeur 1 000 (par défaut).</span><span class="sxs-lookup"><span data-stu-id="c1f6b-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

