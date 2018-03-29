---
title: Configuration du service de mobilité pour de hautes performances dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Résumé : En savoir plus sur le Service de la mobilité dans Skype pour Business Server 2015.'
ms.openlocfilehash: 12f64ed75195bb94365686d76cdfca841e6c9c8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server-2015"></a><span data-ttu-id="dd22c-103">Configuration du service de mobilité pour de hautes performances dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="dd22c-103">Configure Mobility Service for high performance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dd22c-104">**Résumé :** Obtenir des informations sur le Service de la mobilité dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dd22c-104">**Summary:** Learn about the Mobility Service in Skype for Business Server 2015.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dd22c-105">Cette rubrique s’applique uniquement à la Skype pour Service de mobilité 2015 Business Server (Mcx) et ne s’applique pas aux Unified Communications Web API (UCWA), fourni dans les mises à jour cumulatives de Lync Server 2013 : février 2013.</span><span class="sxs-lookup"><span data-stu-id="dd22c-105">This topic applies only to the Skype for Business Server 2015 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="dd22c-106">Lorsque vous installez le Service de mobilité (Mcx) sur les Services Internet (IIS) 7.5, le programme d’installation du Service de la mobilité configure certains paramètres de performances sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="dd22c-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="dd22c-107">Nous vous recommandons d’utiliser les services Internet (IIS) 7.5 pour la mobilité.</span><span class="sxs-lookup"><span data-stu-id="dd22c-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="dd22c-108">Ceux-ci affectent la quantité maximale de demandes utilisateur simultanées et la quantité maximale de threads autorisés pour le service de mobilité.</span><span class="sxs-lookup"><span data-stu-id="dd22c-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="dd22c-109">Voici les paramètres de performances :</span><span class="sxs-lookup"><span data-stu-id="dd22c-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="dd22c-110">Paramètres pour Mcx sur IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="dd22c-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="dd22c-111">**maxConcurrentThreadsPerCPU** a la valeur zéro (0).</span><span class="sxs-lookup"><span data-stu-id="dd22c-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="dd22c-112">**maxConcurrentRequestsPerCPU** a la valeur zéro (0).</span><span class="sxs-lookup"><span data-stu-id="dd22c-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="dd22c-113">Le modèle de processus ASP.NET est AutoConfig (pour les services Internet (IIS) 7.5 uniquement).</span><span class="sxs-lookup"><span data-stu-id="dd22c-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="dd22c-114">La limite de file d’attente HTTP.sys a la valeur 1 000 (par défaut).</span><span class="sxs-lookup"><span data-stu-id="dd22c-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

