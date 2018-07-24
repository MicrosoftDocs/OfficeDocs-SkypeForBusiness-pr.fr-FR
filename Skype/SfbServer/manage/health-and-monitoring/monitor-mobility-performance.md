---
title: Surveiller la mobilité pour les performances dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Résumé : En savoir plus sur le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.'
ms.openlocfilehash: 4affcb532697f24c87d62e18fc26552639dc00e1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990636"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="99f66-103">Surveiller la mobilité pour les performances dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="99f66-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="99f66-104">**Résumé :** Obtenir des informations sur le Service de mobilité (Mcx) et le Web de Communications unifiées API (UCWA) dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="99f66-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="99f66-105">Le Skype pour Service de mobilité Business Server (Mcx) et l’API de Web Communications (UCWA) unifiée augmente la charge sur les pools frontaux et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="99f66-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="99f66-106">Les appareils mobiles maintient une connexion au serveur même lorsque l’application mobile est réduite, tels que les appareils Android et Nokia exécutant Lync 2010 Mobile, ainsi que les appareils Android et Apple exécutant Lync 2013 Mobile, imposent une charge plus importante que les périphériques qui mettre fin à leur connexion au serveur lors de l’application mobile est réduite.</span><span class="sxs-lookup"><span data-stu-id="99f66-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="99f66-107">À mesure que votre utilisation mobile augmente, vous devez surveiller les performances de mobilité afin d’identifier toute nécessité d’augmentation de la capacité.</span><span class="sxs-lookup"><span data-stu-id="99f66-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="99f66-108">Prise en charge MCX pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="99f66-108">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="99f66-109">Vos utilisateurs devez mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="99f66-109">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="99f66-110">Plusieurs limites influencent les performances de mobilité :</span><span class="sxs-lookup"><span data-stu-id="99f66-110">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="99f66-111">mémoire disponible ;</span><span class="sxs-lookup"><span data-stu-id="99f66-111">Available memory</span></span>
    
- <span data-ttu-id="99f66-112">limite de file d’attente des demandes ;</span><span class="sxs-lookup"><span data-stu-id="99f66-112">Request queue limit</span></span>
    
- <span data-ttu-id="99f66-113">connexions simultanées ;</span><span class="sxs-lookup"><span data-stu-id="99f66-113">Concurrent connections</span></span>
    
- <span data-ttu-id="99f66-114">longueur de la file d’attente des services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="99f66-114">IIS queue length</span></span>
    
<span data-ttu-id="99f66-p103">Il existe d’autres limites sur les serveurs susceptibles d’avoir un impact sur les performances de mobilité : un maximum de douze connexions, authentifications, renouvellements et fins de sessions. Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.</span><span class="sxs-lookup"><span data-stu-id="99f66-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="99f66-117">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="99f66-117">In this section</span></span>

- [<span data-ttu-id="99f66-118">Surveiller les limites de capacité de mémoire de serveur dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="99f66-118">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="99f66-119">Surveiller l’utilisation du Service de mobilité et UCWA dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="99f66-119">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="99f66-120">Configurer le Service de mobilité pour de hautes performances dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="99f66-120">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="99f66-121">Surveillance des demandes IIS le suivi des fichiers journaux dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="99f66-121">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="99f66-122">Compteurs de performances de mobilité dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="99f66-122">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

