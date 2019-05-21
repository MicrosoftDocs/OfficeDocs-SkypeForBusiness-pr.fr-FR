---
title: Configurer le service de mobilité pour des performances élevées dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Résumé: en savoir plus sur le service de mobilité dans Skype entreprise Server.'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305842"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="b60c7-103">Configurer le service de mobilité pour des performances élevées dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b60c7-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="b60c7-104">**Résumé:** En savoir plus sur le service de mobilité dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b60c7-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b60c7-105">Cette rubrique s’applique uniquement au service de mobilité Skype entreprise Server (MCX) et ne s’applique pas à l’API Unified Communications Web API (UCWA), telle que publiée dans les mises à jour cumulatives pour Lync Server 2013: février 2013.</span><span class="sxs-lookup"><span data-stu-id="b60c7-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="b60c7-106">Lorsque vous installez le service de mobilité (MCX) sur Internet Information Services (IIS) 7,5, le programme d’installation de service de mobilité configure certains paramètres de performance sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b60c7-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="b60c7-107">Nous vous recommandons d’utiliser les services Internet (IIS) 7.5 pour la mobilité.</span><span class="sxs-lookup"><span data-stu-id="b60c7-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="b60c7-108">Ceux-ci affectent la quantité maximale de demandes utilisateur simultanées et la quantité maximale de threads autorisés pour le service de mobilité.</span><span class="sxs-lookup"><span data-stu-id="b60c7-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="b60c7-109">Voici les paramètres de performances :</span><span class="sxs-lookup"><span data-stu-id="b60c7-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="b60c7-110">Paramètres pour Mcx sur IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="b60c7-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="b60c7-111">**maxConcurrentThreadsPerCPU** est fixé sur zéro (0).</span><span class="sxs-lookup"><span data-stu-id="b60c7-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="b60c7-112">**maxConcurrentRequestsPerCPU** est fixé sur zéro (0).</span><span class="sxs-lookup"><span data-stu-id="b60c7-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="b60c7-113">Le modèle de processus ASP.NET est AutoConfig (pour les services Internet (IIS) 7.5 uniquement).</span><span class="sxs-lookup"><span data-stu-id="b60c7-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="b60c7-114">La limite de file d’attente HTTP.sys a la valeur 1 000 (par défaut).</span><span class="sxs-lookup"><span data-stu-id="b60c7-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

