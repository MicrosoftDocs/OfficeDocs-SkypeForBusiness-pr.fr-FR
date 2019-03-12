---
title: Serveurs proxy pour Skype Entreprise Online et Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: M365-collaboration
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec des équipes ou Skype pour les entreprises.
ms.openlocfilehash: e2d14c8307de2ee64a766394805498505719189a
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542806"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="9d4bf-103">Serveurs proxy pour Skype Entreprise Online et Teams</span><span class="sxs-lookup"><span data-stu-id="9d4bf-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="9d4bf-104">Cet article fournit des instructions sur l’utilisation d’un serveur proxy avec des équipes ou Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="9d4bf-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="9d4bf-105">Il est déconseillé d'utiliser un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="9d4bf-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="9d4bf-106">Lorsqu’il s’agit des équipes ou Skype pour le trafic d’entreprise sur des serveurs proxy, Microsoft vous recommande de contourner les serveurs proxy.</span><span class="sxs-lookup"><span data-stu-id="9d4bf-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="9d4bf-107">Proxys n’apporte des équipes ou Skype pour les entreprises plus sécurisé, car le trafic est déjà chiffré.</span><span class="sxs-lookup"><span data-stu-id="9d4bf-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="9d4bf-108">De plus, un serveur proxy peut entraîner des complications.</span><span class="sxs-lookup"><span data-stu-id="9d4bf-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="9d4bf-109">Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="9d4bf-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="9d4bf-110">Problèmes tels que ceux-ci entraînera une expérience négative dans ces équipes ou des Skype pour les scénarios d’entreprise en tant qu’audio et vidéo, où les flux de données en temps réel est essentielles.</span><span class="sxs-lookup"><span data-stu-id="9d4bf-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="9d4bf-111">SI vous devez utiliser un serveur proxy</span><span class="sxs-lookup"><span data-stu-id="9d4bf-111">If you need to use a proxy server</span></span>

<span data-ttu-id="9d4bf-112">Certaines organisations n’ont aucune option pour ignorer un proxy pour les équipes ou Skype pour le trafic d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="9d4bf-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="9d4bf-113">Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.</span><span class="sxs-lookup"><span data-stu-id="9d4bf-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="9d4bf-114">Microsoft recommande également :</span><span class="sxs-lookup"><span data-stu-id="9d4bf-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="9d4bf-115">L'utilisation de la résolution DNS externe</span><span class="sxs-lookup"><span data-stu-id="9d4bf-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="9d4bf-116">L'utilisation du routage UDP direct</span><span class="sxs-lookup"><span data-stu-id="9d4bf-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="9d4bf-117">L'autorisation du trafic UDP</span><span class="sxs-lookup"><span data-stu-id="9d4bf-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="9d4bf-118">Suivant les autres recommandations de nos instructions de mise en réseau :</span><span class="sxs-lookup"><span data-stu-id="9d4bf-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="9d4bf-119">Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9d4bf-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="9d4bf-120">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9d4bf-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="9d4bf-121">Ces conseils devraient limiter l'apparition de problèmes.</span><span class="sxs-lookup"><span data-stu-id="9d4bf-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9d4bf-122">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="9d4bf-122">Related topics</span></span>

[<span data-ttu-id="9d4bf-123">Optimisation de votre réseau pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="9d4bf-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 