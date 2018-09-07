---
title: Serveurs proxy pour Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Cet article vous orientera dans l'utilisation d'un serveur proxy avec Skype ºEntreprise.
ms.openlocfilehash: 3d83e2f6d4eb2b88a52eb949217ac2f00c72acff
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850012"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="72ee9-103">Serveurs proxy pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="72ee9-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="72ee9-104">Cet article vous orientera dans l'utilisation d'un serveur proxy avec Skype ºEntreprise.</span><span class="sxs-lookup"><span data-stu-id="72ee9-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="72ee9-105">Il est déconseillé d'utiliser un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="72ee9-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="72ee9-p101">En ce qui concerne le trafic Skype Entreprise, Microsoft recommande d'éviter d'utiliser un serveur proxy. En effet, cela ne permettra pas de sécuriser davantage Skype Entreprise, car son trafic est déjà chiffré.</span><span class="sxs-lookup"><span data-stu-id="72ee9-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="72ee9-p102">De plus, un serveur proxy peut entraîner des complications. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. De tels difficultés altèreront l'expérience tant dans les scénarios Skype Entreprise audio que vidéo, pour lesquels les transmissions en continu en temps réel sont essentielles..</span><span class="sxs-lookup"><span data-stu-id="72ee9-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="72ee9-111">SI vous devez utiliser un serveur proxy</span><span class="sxs-lookup"><span data-stu-id="72ee9-111">If you need to use a proxy server</span></span>

<span data-ttu-id="72ee9-p103">Certaines organisations n'ont pas d'autres choix que d'utiliser un serveur proxy pour le trafic Skype Entreprise. Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.</span><span class="sxs-lookup"><span data-stu-id="72ee9-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="72ee9-114">Microsoft recommande également :</span><span class="sxs-lookup"><span data-stu-id="72ee9-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="72ee9-115">L'utilisation de la résolution DNS externe</span><span class="sxs-lookup"><span data-stu-id="72ee9-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="72ee9-116">L'utilisation du routage UDP direct</span><span class="sxs-lookup"><span data-stu-id="72ee9-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="72ee9-117">L'autorisation du trafic UDP</span><span class="sxs-lookup"><span data-stu-id="72ee9-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="72ee9-118">L'application des autres recommandations de nos directives relatives à la mise en réseau :</span><span class="sxs-lookup"><span data-stu-id="72ee9-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="72ee9-119">Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="72ee9-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="72ee9-120">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="72ee9-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="72ee9-121">Ces conseils devraient limiter l'apparition de problèmes.</span><span class="sxs-lookup"><span data-stu-id="72ee9-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="72ee9-122">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="72ee9-122">Related topics</span></span>

[<span data-ttu-id="72ee9-123">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="72ee9-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 