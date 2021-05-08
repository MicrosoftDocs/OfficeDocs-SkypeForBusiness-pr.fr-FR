---
title: Serveurs proxy pour Teams ou Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec Skype Entreprise.
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240413"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="f5ee0-103">Serveurs proxy pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f5ee0-103">Proxy servers for Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="f5ee0-104">Cet article fournit des conseils sur l’utilisation d’un serveur proxy avec Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f5ee0-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="f5ee0-105">Il est déconseillé d'utiliser un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="f5ee0-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="f5ee0-106">En ce qui concerne le trafic Skype Entreprise, Microsoft recommande d'éviter d'utiliser un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="f5ee0-106">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="f5ee0-107">En raison de la sécurité du trafic, Skype Entreprise pas sécurisés, car le trafic est déjà chiffré.</span><span class="sxs-lookup"><span data-stu-id="f5ee0-107">Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="f5ee0-108">De plus, un serveur proxy peut entraîner des complications.</span><span class="sxs-lookup"><span data-stu-id="f5ee0-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="f5ee0-109">Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="f5ee0-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="f5ee0-110">De tels problèmes entraînent une expérience négative dans les scénarios Teams ou Skype Entreprise tels que l’audio et la vidéo, pour lequel les flux en temps réel sont essentiels.</span><span class="sxs-lookup"><span data-stu-id="f5ee0-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="f5ee0-111">SI vous devez utiliser un serveur proxy</span><span class="sxs-lookup"><span data-stu-id="f5ee0-111">If you need to use a proxy server</span></span>

<span data-ttu-id="f5ee0-p103">Certaines organisations n'ont pas d'autres choix que d'utiliser un serveur proxy pour le trafic Skype Entreprise. Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.</span><span class="sxs-lookup"><span data-stu-id="f5ee0-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="f5ee0-114">Microsoft recommande également :</span><span class="sxs-lookup"><span data-stu-id="f5ee0-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="f5ee0-115">L'utilisation de la résolution DNS externe</span><span class="sxs-lookup"><span data-stu-id="f5ee0-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="f5ee0-116">L'utilisation du routage UDP direct</span><span class="sxs-lookup"><span data-stu-id="f5ee0-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="f5ee0-117">L'autorisation du trafic UDP</span><span class="sxs-lookup"><span data-stu-id="f5ee0-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="f5ee0-118">En suivant les autres recommandations de nos directives en matière de mise en réseau :</span><span class="sxs-lookup"><span data-stu-id="f5ee0-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="f5ee0-119">Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f5ee0-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="f5ee0-120">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f5ee0-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="f5ee0-121">Ces conseils devraient limiter l'apparition de problèmes.</span><span class="sxs-lookup"><span data-stu-id="f5ee0-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f5ee0-122">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="f5ee0-122">Related topics</span></span>

[<span data-ttu-id="f5ee0-123">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f5ee0-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 
