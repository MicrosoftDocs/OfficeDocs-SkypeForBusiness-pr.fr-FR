---
title: Serveurs proxy pour Skype Entreprise Online et Teams
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
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec Skype entreprise.
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863748"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="8c571-103">Serveurs proxy pour Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8c571-103">Proxy servers for Skype for Business Online</span></span>

<span data-ttu-id="8c571-104">Cet article fournit des instructions sur l’utilisation d’un serveur proxy avec Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="8c571-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="8c571-105">Il est déconseillé d'utiliser un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="8c571-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="8c571-p101">Lorsqu’il s’agit du trafic de Skype entreprise sur proxy, Microsoft recommande de contournement des proxys. Les proxys ne permettent pas de sécuriser Skype entreprise, car le trafic est déjà crypté.</span><span class="sxs-lookup"><span data-stu-id="8c571-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="8c571-p102">Un serveur proxy peut poser des problèmes. Les problèmes liés aux performances peuvent être introduits dans l’environnement par le biais d’une latence et d’une perte de paquets. Des problèmes tels que ceux-ci entraînent une utilisation négative de ces équipes ou des scénarios Skype entreprise tels que les flux audio et vidéo, où les flux en temps réel sont essentiels.</span><span class="sxs-lookup"><span data-stu-id="8c571-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="8c571-111">SI vous devez utiliser un serveur proxy</span><span class="sxs-lookup"><span data-stu-id="8c571-111">If you need to use a proxy server</span></span>

<span data-ttu-id="8c571-p103">Certaines organisations n'ont pas d'autres choix que d'utiliser un serveur proxy pour le trafic Skype Entreprise. Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.</span><span class="sxs-lookup"><span data-stu-id="8c571-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="8c571-114">Microsoft recommande également :</span><span class="sxs-lookup"><span data-stu-id="8c571-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="8c571-115">L'utilisation de la résolution DNS externe</span><span class="sxs-lookup"><span data-stu-id="8c571-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="8c571-116">L'utilisation du routage UDP direct</span><span class="sxs-lookup"><span data-stu-id="8c571-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="8c571-117">L'autorisation du trafic UDP</span><span class="sxs-lookup"><span data-stu-id="8c571-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="8c571-118">Suivi des autres recommandations de nos directives relatives à la mise en réseau :</span><span class="sxs-lookup"><span data-stu-id="8c571-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="8c571-119">Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8c571-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="8c571-120">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8c571-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="8c571-121">Ces conseils devraient limiter l'apparition de problèmes.</span><span class="sxs-lookup"><span data-stu-id="8c571-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8c571-122">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="8c571-122">Related topics</span></span>

[<span data-ttu-id="8c571-123">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8c571-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 