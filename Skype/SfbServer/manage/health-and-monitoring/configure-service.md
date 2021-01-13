---
title: Configurer le service de mobilité pour des performances élevées dans Skype Entreprise Server
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Résumé : Découvrez le service de mobilité dans Skype Entreprise Server.'
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817034"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="8f9a4-103">Configurer le service de mobilité pour des performances élevées dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8f9a4-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="8f9a4-104">**Résumé :** Découvrez le service de mobilité dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8f9a4-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8f9a4-105">Cette rubrique s’applique uniquement au service de mobilité De Skype Entreprise Server (Mcx) et ne s’applique pas à l’API web de communications unifiées (UCWA), comme remis dans les mises à jour cumulatives pour Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="8f9a4-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="8f9a4-106">Lorsque vous installez le service de mobilité (Mcx) sur Internet Information Services (IIS) 7.5, le programme d’installation du service de mobilité configure certains paramètres de performances sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="8f9a4-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="8f9a4-107">Nous vous recommandons d’utiliser les services Internet (IIS) 7.5 pour la mobilité.</span><span class="sxs-lookup"><span data-stu-id="8f9a4-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="8f9a4-108">Ceux-ci affectent la quantité maximale de demandes utilisateur simultanées et la quantité maximale de threads autorisés pour le service de mobilité.</span><span class="sxs-lookup"><span data-stu-id="8f9a4-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="8f9a4-109">Voici les paramètres de performances :</span><span class="sxs-lookup"><span data-stu-id="8f9a4-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="8f9a4-110">Paramètres de Mcx sur IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="8f9a4-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="8f9a4-111">**maxConcurrentThreadsPerCPU** a la valeur zéro (0).</span><span class="sxs-lookup"><span data-stu-id="8f9a4-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="8f9a4-112">**maxConcurrentRequestsPerCPU** a la valeur zéro (0).</span><span class="sxs-lookup"><span data-stu-id="8f9a4-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="8f9a4-113">Le modèle de processus ASP.NET est AutoConfig (pour les services Internet (IIS) 7.5 uniquement).</span><span class="sxs-lookup"><span data-stu-id="8f9a4-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="8f9a4-114">La limite de file d’attente HTTP.sys a la valeur 1 000 (par défaut).</span><span class="sxs-lookup"><span data-stu-id="8f9a4-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

