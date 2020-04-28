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
- seo-marvel-apr2020
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec Microsoft teams ou Skype entreprise.
ms.openlocfilehash: 5a0d35ee2b8c95c4dea30886497e184f57077264
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905676"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="8beff-103">Serveurs proxy pour Skype Entreprise Online et Teams</span><span class="sxs-lookup"><span data-stu-id="8beff-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="8beff-104">Cet article fournit des instructions sur l’utilisation d’un serveur proxy avec teams ou Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="8beff-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="8beff-105">Il est déconseillé d'utiliser un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="8beff-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="8beff-p101">Lorsque le trafic est lié aux équipes ou à Skype entreprise via des proxys, Microsoft recommande de contournement des proxys. Les proxys ne permettent pas de sécuriser les équipes ou Skype entreprise, car le trafic est déjà crypté.</span><span class="sxs-lookup"><span data-stu-id="8beff-p101">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="8beff-p102">Un serveur proxy peut poser des problèmes. Les problèmes liés aux performances peuvent être introduits dans l’environnement par le biais d’une latence et d’une perte de paquets. Des problèmes tels que ceux-ci entraînent une utilisation négative de ces équipes ou des scénarios Skype entreprise tels que les flux audio et vidéo, où les flux en temps réel sont essentiels.</span><span class="sxs-lookup"><span data-stu-id="8beff-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="8beff-111">SI vous devez utiliser un serveur proxy</span><span class="sxs-lookup"><span data-stu-id="8beff-111">If you need to use a proxy server</span></span>

<span data-ttu-id="8beff-p103">Certaines organisations n’ont aucune option pour contourner un proxy pour le trafic d’équipes ou Skype entreprise. Si tel est le cas, vous devez garder à l’esprit les problèmes mentionnés ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="8beff-p103">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="8beff-114">Microsoft recommande également :</span><span class="sxs-lookup"><span data-stu-id="8beff-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="8beff-115">L'utilisation de la résolution DNS externe</span><span class="sxs-lookup"><span data-stu-id="8beff-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="8beff-116">L'utilisation du routage UDP direct</span><span class="sxs-lookup"><span data-stu-id="8beff-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="8beff-117">L'autorisation du trafic UDP</span><span class="sxs-lookup"><span data-stu-id="8beff-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="8beff-118">Suivi des autres recommandations de nos recommandations en matière de réseau : [préparer le réseau de votre organisation aux équipes](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="8beff-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="8beff-119">Ces conseils devraient limiter l'apparition de problèmes.</span><span class="sxs-lookup"><span data-stu-id="8beff-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8beff-120">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="8beff-120">Related topics</span></span>

[<span data-ttu-id="8beff-121">Principes de connectivité réseau d’Office 365</span><span class="sxs-lookup"><span data-stu-id="8beff-121">Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="8beff-122">Préparer le réseau de votre organisation pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8beff-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)
