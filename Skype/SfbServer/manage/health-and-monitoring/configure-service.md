---
title: Configurer le Service de mobilité pour de hautes performances dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Résumé : En savoir plus sur le Service de mobilité dans Skype pour Business Server.'
ms.openlocfilehash: 3e3f0df7550a64236335108453f0c35d902a1713
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197491"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="49d7a-103">Configurer le Service de mobilité pour de hautes performances dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="49d7a-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="49d7a-104">**Résumé :** Obtenir des informations sur le Service de mobilité dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="49d7a-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="49d7a-105">Cette rubrique s’applique uniquement à la Skype pour le Service de mobilité Business Server (Mcx) et ne s’applique pas à Unified Communications Web API (UCWA), fourni dans les mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="49d7a-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="49d7a-106">Lorsque vous installez le Service de mobilité (Mcx) sur les Services Internet (IIS) 7.5, le programme d’installation du Service de mobilité configure certains paramètres de performances sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="49d7a-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="49d7a-107">Nous vous recommandons d’utiliser les services Internet (IIS) 7.5 pour la mobilité.</span><span class="sxs-lookup"><span data-stu-id="49d7a-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="49d7a-108">Ceux-ci affectent la quantité maximale de demandes utilisateur simultanées et la quantité maximale de threads autorisés pour le service de mobilité.</span><span class="sxs-lookup"><span data-stu-id="49d7a-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="49d7a-109">Voici les paramètres de performances :</span><span class="sxs-lookup"><span data-stu-id="49d7a-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="49d7a-110">Paramètres pour Mcx sur IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="49d7a-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="49d7a-111">**maxConcurrentThreadsPerCPU** est fixé sur zéro (0).</span><span class="sxs-lookup"><span data-stu-id="49d7a-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="49d7a-112">**maxConcurrentRequestsPerCPU** est fixé sur zéro (0).</span><span class="sxs-lookup"><span data-stu-id="49d7a-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="49d7a-113">Le modèle de processus ASP.NET est AutoConfig (pour les services Internet (IIS) 7.5 uniquement).</span><span class="sxs-lookup"><span data-stu-id="49d7a-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="49d7a-114">La limite de file d’attente HTTP.sys a la valeur 1 000 (par défaut).</span><span class="sxs-lookup"><span data-stu-id="49d7a-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

