---
title: Surveiller l’utilisation du service de mobilité et de l’UCWA dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Résumé : Gérez le service de mobilité (Mcx) et l’API web de communications unifiées (UCWA) dans Skype Entreprise Server.'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814244"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="74264-103">Surveiller l’utilisation du service de mobilité et de l’UCWA dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="74264-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="74264-104">**Résumé :** Gérez le service de mobilité (Mcx) et l’API web de communications unifiées (UCWA) dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="74264-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="74264-105">La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="74264-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="74264-106">Tous les clients mobiles Skype Entreprise actuels utilisent déjà l’API web de communications unifiées (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="74264-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="74264-107">Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="74264-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="74264-108">Régulièrement, vous devez surveiller le processeur et la mémoire utilisés par le service de mobilité de Skype Entreprise Server (Mcx) et l’API web de communications unifiées (UCWA).</span><span class="sxs-lookup"><span data-stu-id="74264-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="74264-109">Pour surveiller l’utilisation, vous pouvez utiliser les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="74264-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="74264-110">**Pour l’API web de communications unifiées (UCWA) :**</span><span class="sxs-lookup"><span data-stu-id="74264-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="74264-111">Processus **de travail LyncUcwa** dans le Gestionnaire des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="74264-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="74264-112">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="74264-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="74264-113">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="74264-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="74264-114">Pour la plupart des déploiements, l’utilisation du processeur UCWA doit être inférieure à 15 % en moyenne.</span><span class="sxs-lookup"><span data-stu-id="74264-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="74264-115">L’utilisation de la mémoire doit être dans les limites décrites dans [monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="74264-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="74264-116">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performance suivants pour déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="74264-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="74264-117">**LS:WEB - Limitation** et authentification\WEB - Nombre total de demandes en cours de traitement, ce qui indique le nombre de demandes web en attente sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="74264-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="74264-118">Lorsque ce compteur atteint 10 000, les demandes suivantes échouent, avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="74264-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="74264-119">**ASP.NET\Requests Queued** (doit toujours être égal à zéro).</span><span class="sxs-lookup"><span data-stu-id="74264-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="74264-120">Si vous respectez ou dépassez ces valeurs, vous devez revoir et re calculer votre planification de capacité pour le resserrage correct du processeur, du nombre de cœurs et de la mémoire pour les ordinateurs hébergeant les services web.</span><span class="sxs-lookup"><span data-stu-id="74264-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="74264-121">**Pour le service de mobilité (Mcx) :**</span><span class="sxs-lookup"><span data-stu-id="74264-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="74264-122">Processus **de travail CSIntMcxAppPool** et **CSExtMcxAppPool** dans le Gestionnaire des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="74264-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="74264-123">Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;</span><span class="sxs-lookup"><span data-stu-id="74264-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="74264-124">les compteurs de performances **UC** et **Processeur**.</span><span class="sxs-lookup"><span data-stu-id="74264-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="74264-125">Pour la plupart des déploiements, l’utilisation du processeur du service de mobilité doit être inférieure à 15 % en moyenne.</span><span class="sxs-lookup"><span data-stu-id="74264-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="74264-126">L’utilisation de la mémoire doit être dans les limites décrites dans [monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="74264-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="74264-127">Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :</span><span class="sxs-lookup"><span data-stu-id="74264-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="74264-128">**ASP.NET v2.0.50727\Requests Current**, qui indique le nombre de demandes web en attente sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="74264-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="74264-129">Lorsque ce compteur atteint 5 000, les demandes suivantes échouent avec le message d’erreur « 503 - Service indisponible ».</span><span class="sxs-lookup"><span data-stu-id="74264-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="74264-130">**ASP.NET\Requests Queued** (doit toujours être égal à zéro).</span><span class="sxs-lookup"><span data-stu-id="74264-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="74264-131">Si vous respectez ou dépassez ces valeurs, vous devez revoir et recompiler votre planification de capacité pour le recalcul correct du processeur, du nombre de cœurs et de la mémoire pour les ordinateurs hébergeant les services web.</span><span class="sxs-lookup"><span data-stu-id="74264-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="74264-132">La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="74264-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="74264-133">Tous les clients mobiles Skype Entreprise actuels utilisent déjà l’API web de communications unifiées (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="74264-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="74264-134">Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="74264-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="74264-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="74264-135">See also</span></span>

[<span data-ttu-id="74264-136">Surveiller les limites de capacité de mémoire des serveurs dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="74264-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
