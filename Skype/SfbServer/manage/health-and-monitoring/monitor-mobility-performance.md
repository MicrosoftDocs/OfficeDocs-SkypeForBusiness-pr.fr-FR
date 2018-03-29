---
title: Surveillance des performances de mobilité dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Résumé : En savoir plus sur le Service de mobilité (Mcx) et le site Web de Communications unifiées API (UCWA) dans Skype pour Business Server 2015.'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a><span data-ttu-id="73716-103">Surveillance des performances de mobilité dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="73716-103">Monitor mobility for performance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="73716-104">**Résumé :** En savoir plus sur le Service de mobilité (Mcx) et le site Web de Communications unifiées API (UCWA) dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="73716-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="73716-105">Le Skype pour Service de mobilité Business Server (Mcx) et l’API de Web Communications (UCWA) unifié augmente la charge sur les pools de serveurs frontaux et de Front-End.</span><span class="sxs-lookup"><span data-stu-id="73716-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="73716-106">Les périphériques mobiles qui maintiennent une connexion au serveur, même lorsque l’application mobile est réduite, par exemple les appareils Android et Nokia exécutant Lync 2010 Mobile, ainsi que des appareils Android et Apple exécutant Lync 2013 Mobile, imposent une charge plus importante que les périphériques qui mettre fin à leur connexion avec le serveur lorsque l’application mobile est réduite.</span><span class="sxs-lookup"><span data-stu-id="73716-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="73716-107">À mesure que votre utilisation mobile augmente, vous devez surveiller les performances de mobilité afin d’identifier toute nécessité d’augmentation de la capacité.</span><span class="sxs-lookup"><span data-stu-id="73716-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>
  
<span data-ttu-id="73716-108">Plusieurs limites influencent les performances de mobilité :</span><span class="sxs-lookup"><span data-stu-id="73716-108">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="73716-109">mémoire disponible ;</span><span class="sxs-lookup"><span data-stu-id="73716-109">Available memory</span></span>
    
- <span data-ttu-id="73716-110">limite de file d’attente des demandes ;</span><span class="sxs-lookup"><span data-stu-id="73716-110">Request queue limit</span></span>
    
- <span data-ttu-id="73716-111">connexions simultanées ;</span><span class="sxs-lookup"><span data-stu-id="73716-111">Concurrent connections</span></span>
    
- <span data-ttu-id="73716-112">longueur de la file d’attente des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="73716-112">IIS queue length</span></span>
    
<span data-ttu-id="73716-p102">Il existe d’autres limites sur les serveurs susceptibles d’avoir un impact sur les performances de mobilité : un maximum de douze connexions, authentifications, renouvellements et fins de sessions. Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.</span><span class="sxs-lookup"><span data-stu-id="73716-p102">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="73716-115">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="73716-115">In this section</span></span>

- [<span data-ttu-id="73716-116">Moniteur pour les limites de capacité de mémoire de serveur dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="73716-116">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="73716-117">Surveiller l’utilisation du Service de la mobilité et la UCWA dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="73716-117">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="73716-118">Configurer le Service de la mobilité pour des performances élevées dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="73716-118">Configure Mobility Service for high performance in Skype for Business Server 2015</span></span>](configure-service.md)
    
- [<span data-ttu-id="73716-119">IIS contrôle demande des fichiers journaux de suivi dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="73716-119">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="73716-120">Compteurs de performance de mobilité dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="73716-120">Mobility performance counters in Skype for Business Server 2015</span></span>](performance-counters.md)
    

