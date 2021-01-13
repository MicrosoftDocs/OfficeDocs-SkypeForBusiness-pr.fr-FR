---
title: Surveiller les performances de la mobilité dans Skype Entreprise Server
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Résumé : Découvrez le service de mobilité (Mcx) et l’API web de communications unifiées (UCWA) dans Skype Entreprise Server.'
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816834"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="b3835-103">Surveiller les performances de la mobilité dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b3835-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="b3835-104">**Résumé :** Découvrez le service de mobilité (Mcx) et l’API web de communications unifiées (UCWA) dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b3835-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="b3835-105">Le service de mobilité de Skype Entreprise Server (Mcx) et l’API web de communications unifiées (UCWA) augmentent la charge sur les serveurs frontux et les pools frontux.</span><span class="sxs-lookup"><span data-stu-id="b3835-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="b3835-106">Les appareils mobiles qui maintiennent une connexion au serveur même lorsque l’application mobile est réduite, comme les appareils Android et Nokia exécutant Lync 2010 Mobile, ainsi que les appareils Android et Apple exécutant Lync 2013 Mobile, imposent une charge plus élevée que les appareils qui terminent leur connexion au serveur lorsque l’application mobile est réduite.</span><span class="sxs-lookup"><span data-stu-id="b3835-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="b3835-107">À mesure que votre utilisation de la mobilité augmente, vous devez surveiller les performances de mobilité pour déterminer quand vous devez augmenter votre capacité.</span><span class="sxs-lookup"><span data-stu-id="b3835-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="b3835-108">La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b3835-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b3835-109">Tous les clients mobiles Skype Entreprise actuels utilisent déjà l’API web de communications unifiées (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts.</span><span class="sxs-lookup"><span data-stu-id="b3835-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b3835-110">Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.</span><span class="sxs-lookup"><span data-stu-id="b3835-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="b3835-111">Plusieurs limites influencent les performances de mobilité :</span><span class="sxs-lookup"><span data-stu-id="b3835-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="b3835-112">Mémoire disponible</span><span class="sxs-lookup"><span data-stu-id="b3835-112">Available memory</span></span>
    
- <span data-ttu-id="b3835-113">Limite de file d’attente des demandes</span><span class="sxs-lookup"><span data-stu-id="b3835-113">Request queue limit</span></span>
    
- <span data-ttu-id="b3835-114">Connexions simultanées</span><span class="sxs-lookup"><span data-stu-id="b3835-114">Concurrent connections</span></span>
    
- <span data-ttu-id="b3835-115">Longueur de file d’attente IIS</span><span class="sxs-lookup"><span data-stu-id="b3835-115">IIS queue length</span></span>
    
<span data-ttu-id="b3835-116">Les autres limites sur les serveurs qui peuvent influencer les performances de mobilité sont un maximum de 12 ouvertures de session, authentifications, renouvellements de session et résiliations simultanées.</span><span class="sxs-lookup"><span data-stu-id="b3835-116">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="b3835-117">Ces valeurs maximales n’ont pas besoin d’être modifiées pour la plupart des déploiements.</span><span class="sxs-lookup"><span data-stu-id="b3835-117">These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b3835-118">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="b3835-118">In this section</span></span>

- [<span data-ttu-id="b3835-119">Surveiller les limites de capacité de mémoire des serveurs dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b3835-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="b3835-120">Surveiller l’utilisation du service de mobilité et de l’UCWA dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b3835-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="b3835-121">Configurer le service de mobilité pour des performances élevées dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b3835-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="b3835-122">Surveillance des fichiers journaux de suivi des demandes IIS dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b3835-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="b3835-123">Compteurs de performances de mobilité dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b3835-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

