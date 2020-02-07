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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec teams ou Skype entreprise.
ms.openlocfilehash: 7eeb319c9c352f4f04abef581b88c1eddf46951d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837304"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="47173-103">Serveurs proxy pour Skype Entreprise Online et Teams</span><span class="sxs-lookup"><span data-stu-id="47173-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="47173-104">Cet article fournit des instructions sur l’utilisation d’un serveur proxy avec teams ou Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="47173-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="47173-105">Il est déconseillé d'utiliser un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="47173-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="47173-p101">Lorsque le trafic est lié aux équipes ou à Skype entreprise via des proxys, Microsoft recommande de contournement des proxys. Les proxys ne permettent pas de sécuriser les équipes ou Skype entreprise, car le trafic est déjà crypté.</span><span class="sxs-lookup"><span data-stu-id="47173-p101">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="47173-p102">Un serveur proxy peut poser des problèmes. Les problèmes liés aux performances peuvent être introduits dans l’environnement par le biais d’une latence et d’une perte de paquets. Des problèmes tels que ceux-ci entraînent une utilisation négative de ces équipes ou des scénarios Skype entreprise tels que les flux audio et vidéo, où les flux en temps réel sont essentiels.</span><span class="sxs-lookup"><span data-stu-id="47173-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="47173-111">SI vous devez utiliser un serveur proxy</span><span class="sxs-lookup"><span data-stu-id="47173-111">If you need to use a proxy server</span></span>

<span data-ttu-id="47173-p103">Certaines organisations n’ont aucune option pour contourner un proxy pour le trafic d’équipes ou Skype entreprise. Si tel est le cas, vous devez garder à l’esprit les problèmes mentionnés ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="47173-p103">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="47173-114">Microsoft recommande également :</span><span class="sxs-lookup"><span data-stu-id="47173-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="47173-115">L'utilisation de la résolution DNS externe</span><span class="sxs-lookup"><span data-stu-id="47173-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="47173-116">L'utilisation du routage UDP direct</span><span class="sxs-lookup"><span data-stu-id="47173-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="47173-117">L'autorisation du trafic UDP</span><span class="sxs-lookup"><span data-stu-id="47173-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="47173-118">Suivi des autres recommandations de nos directives relatives à la mise en réseau :</span><span class="sxs-lookup"><span data-stu-id="47173-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="47173-119">Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="47173-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="47173-120">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="47173-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="47173-121">Ces conseils devraient limiter l'apparition de problèmes.</span><span class="sxs-lookup"><span data-stu-id="47173-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="47173-122">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="47173-122">Related topics</span></span>

[<span data-ttu-id="47173-123">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="47173-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 