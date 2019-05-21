---
title: Surveiller la mobilité des performances dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Résumé: en savoir plus sur le service de mobilité (MCX) et l’API Web de communications unifiées (UCWA) dans Skype entreprise Server.'
ms.openlocfilehash: 7b8340d90b5e1fa18c4dfaa7d61f986344ccbb33
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279920"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="7f0c5-103">Surveiller la mobilité des performances dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7f0c5-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="7f0c5-104">**Résumé:** En savoir plus sur le service de mobilité (MCX) et l’API Unified Communications Web API (UCWA) dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7f0c5-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="7f0c5-105">Le service de mobilité de Skype entreprise Server (MCX) et l’API Web de communications unifiées (UCWA) augmentent la charge sur les serveurs frontaux et les listes frontales.</span><span class="sxs-lookup"><span data-stu-id="7f0c5-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="7f0c5-106">Les appareils mobiles qui maintiennent une connexion au serveur, même lorsque l’application mobile est réduite (par exemple, les appareils Android et Nokia exécutant Lync 2010 mobile, ainsi que les appareils Android et Apple exécutant Lync 2013 mobile, imposent un chargement supérieur aux appareils mettre fin à sa connexion au serveur lorsque l’application mobile est réduite;</span><span class="sxs-lookup"><span data-stu-id="7f0c5-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="7f0c5-107">À mesure que votre utilisation mobile augmente, vous devez surveiller les performances de mobilité afin d’identifier toute nécessité d’augmentation de la capacité.</span><span class="sxs-lookup"><span data-stu-id="7f0c5-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="7f0c5-108">La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7f0c5-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="7f0c5-109">Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts.</span><span class="sxs-lookup"><span data-stu-id="7f0c5-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="7f0c5-110">Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="7f0c5-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="7f0c5-111">Plusieurs limites influencent les performances de mobilité :</span><span class="sxs-lookup"><span data-stu-id="7f0c5-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="7f0c5-112">mémoire disponible ;</span><span class="sxs-lookup"><span data-stu-id="7f0c5-112">Available memory</span></span>
    
- <span data-ttu-id="7f0c5-113">limite de file d’attente des demandes ;</span><span class="sxs-lookup"><span data-stu-id="7f0c5-113">Request queue limit</span></span>
    
- <span data-ttu-id="7f0c5-114">connexions simultanées ;</span><span class="sxs-lookup"><span data-stu-id="7f0c5-114">Concurrent connections</span></span>
    
- <span data-ttu-id="7f0c5-115">longueur de la file d’attente des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="7f0c5-115">IIS queue length</span></span>
    
<span data-ttu-id="7f0c5-p103">Il existe d’autres limites sur les serveurs susceptibles d’avoir un impact sur les performances de mobilité : un maximum de douze connexions, authentifications, renouvellements et fins de sessions. Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.</span><span class="sxs-lookup"><span data-stu-id="7f0c5-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7f0c5-118">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="7f0c5-118">In this section</span></span>

- [<span data-ttu-id="7f0c5-119">Surveiller les limites de capacité de mémoire serveur dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7f0c5-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="7f0c5-120">Surveiller l’utilisation du service de mobilité et de UCWA dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7f0c5-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="7f0c5-121">Configurer le service de mobilité pour des performances élevées dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7f0c5-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="7f0c5-122">Surveiller les fichiers journaux de suivi de requête IIS dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7f0c5-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="7f0c5-123">Compteurs de performance de mobilité dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7f0c5-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

