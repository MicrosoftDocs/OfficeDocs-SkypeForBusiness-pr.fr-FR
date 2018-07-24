---
title: Surveiller l’utilisation du Service de mobilité et UCWA dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Résumé : Gérer le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.'
ms.openlocfilehash: 780d8fca068a78ec08312551d03dbdb5327df90e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975948"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="30960-103">Surveiller l’utilisation du Service de mobilité et UCWA dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="30960-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="30960-104">**Résumé :** Gérer le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="30960-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="30960-105">Prise en charge MCX pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="30960-105">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="30960-106">Vos utilisateurs devez mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="30960-106">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="30960-107">De manière continue, vous devez surveiller le processeur et la mémoire utilisée par le Skype pour Service de mobilité Business Server (Mcx) et l’API de Web Communications (UCWA) unifiée.</span><span class="sxs-lookup"><span data-stu-id="30960-107">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="30960-108">Pour cela, vous pouvez utiliser l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="30960-108">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="30960-109">**Pour l’API web de communications unifiées (UCWA) :**</span><span class="sxs-lookup"><span data-stu-id="30960-109">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="30960-110">Le processus de travail **LyncUcwa** dans le Gestionnaire des Services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="30960-110">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="30960-111">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="30960-111">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="30960-112">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="30960-112">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="30960-113">Pour la plupart des déploiements, l’utilisation du processeur par l’API UCWA doit en moyenne être inférieure à 15 %.</span><span class="sxs-lookup"><span data-stu-id="30960-113">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="30960-114">Utilisation de la mémoire doit être dans les limites décrites dans [surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="30960-114">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="30960-115">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="30960-115">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="30960-116">**LS:WEB - limitation et Authentication\WEB - nombre Total de demandes de traitement en**, qui indique le nombre de demandes web sur le serveur en attente.</span><span class="sxs-lookup"><span data-stu-id="30960-116">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="30960-117">Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="30960-117">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="30960-118">**ASP. net\requests Queued** (doit être toujours zéro).</span><span class="sxs-lookup"><span data-stu-id="30960-118">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="30960-119">Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web.</span><span class="sxs-lookup"><span data-stu-id="30960-119">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="30960-120">**Pour le service de mobilité (Mcx) :**</span><span class="sxs-lookup"><span data-stu-id="30960-120">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="30960-121">Processus de travail **CSIntMcxAppPool** et **CSExtMcxAppPool** dans le Gestionnaire des Services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="30960-121">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="30960-122">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="30960-122">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="30960-123">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="30960-123">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="30960-124">Pour la plupart des déploiements, l’utilisation du processeur par le service de mobilité doit en moyenne être inférieure à 15 %.</span><span class="sxs-lookup"><span data-stu-id="30960-124">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="30960-125">Utilisation de la mémoire doit être dans les limites décrites dans [surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="30960-125">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="30960-126">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="30960-126">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="30960-127">**ASP.NET v2.0.50727\Requests actuel**, qui indique le nombre de demandes web sur le serveur en attente.</span><span class="sxs-lookup"><span data-stu-id="30960-127">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="30960-128">Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="30960-128">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="30960-129">**ASP. net\requests Queued** (doit être toujours zéro).</span><span class="sxs-lookup"><span data-stu-id="30960-129">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="30960-130">Si vous atteignez ou dépassez ces valeurs, vous devez réévaluer et recalculer votre planification de la capacité afin de dimensionner correctement le processeur, le nombre de cœurs et la mémoire pour les ordinateurs qui hébergent les services web.</span><span class="sxs-lookup"><span data-stu-id="30960-130">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="30960-131">Prise en charge MCX pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="30960-131">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="30960-132">Vos utilisateurs devez mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="30960-132">Your users will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="30960-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="30960-133">See also</span></span>

[<span data-ttu-id="30960-134">Surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="30960-134">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)