---
title: Surveiller la mobilité pour les performances dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Résumé : En savoir plus sur le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.'
ms.openlocfilehash: 476d03fa17cad163fa9426ca35853cfe29f87bb1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886281"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="6597f-103">Surveiller la mobilité pour les performances dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="6597f-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="6597f-104">**Résumé :** Obtenir des informations sur le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="6597f-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="6597f-105">Le Skype pour Service de mobilité Business Server (Mcx) et l’API de Web Communications (UCWA) unifiée augmente la charge sur les pools frontaux et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="6597f-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="6597f-106">Les appareils mobiles maintient une connexion au serveur même lorsque l’application mobile est réduite, tels que les appareils Android et Nokia exécutant Lync 2010 Mobile, ainsi que les appareils Android et Apple exécutant Lync 2013 Mobile, imposent une charge plus importante que les périphériques qui mettre fin à leur connexion au serveur lors de l’application mobile est réduite.</span><span class="sxs-lookup"><span data-stu-id="6597f-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="6597f-107">À mesure que votre utilisation mobile augmente, vous devez surveiller les performances de mobilité afin d’identifier toute nécessité d’augmentation de la capacité.</span><span class="sxs-lookup"><span data-stu-id="6597f-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="6597f-108">Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6597f-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="6597f-109">Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="6597f-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="6597f-110">Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="6597f-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="6597f-111">Plusieurs limites influencent les performances de mobilité :</span><span class="sxs-lookup"><span data-stu-id="6597f-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="6597f-112">mémoire disponible ;</span><span class="sxs-lookup"><span data-stu-id="6597f-112">Available memory</span></span>
    
- <span data-ttu-id="6597f-113">limite de file d’attente des demandes ;</span><span class="sxs-lookup"><span data-stu-id="6597f-113">Request queue limit</span></span>
    
- <span data-ttu-id="6597f-114">connexions simultanées ;</span><span class="sxs-lookup"><span data-stu-id="6597f-114">Concurrent connections</span></span>
    
- <span data-ttu-id="6597f-115">longueur de la file d’attente des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="6597f-115">IIS queue length</span></span>
    
<span data-ttu-id="6597f-p103">Il existe d’autres limites sur les serveurs susceptibles d’avoir un impact sur les performances de mobilité : un maximum de douze connexions, authentifications, renouvellements et fins de sessions. Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.</span><span class="sxs-lookup"><span data-stu-id="6597f-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="6597f-118">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="6597f-118">In this section</span></span>

- [<span data-ttu-id="6597f-119">Surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="6597f-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="6597f-120">Surveiller l’utilisation du Service de mobilité et UCWA dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="6597f-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="6597f-121">Configurer le Service de mobilité pour de hautes performances dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="6597f-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="6597f-122">Surveillance des demandes IIS le suivi des fichiers journaux dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="6597f-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="6597f-123">Compteurs de performances de mobilité dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="6597f-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

