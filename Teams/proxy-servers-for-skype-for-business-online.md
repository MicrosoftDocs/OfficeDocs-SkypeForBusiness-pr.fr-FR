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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec Microsoft Teams ou Skype Entreprise.
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117722"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="84901-103">Serveurs proxy pour Teams ou Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="84901-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="84901-104">Cet article fournit des conseils sur l’utilisation d’un serveur proxy avec Teams ou Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="84901-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="84901-105">Il est déconseillé d'utiliser un serveur proxy.</span><span class="sxs-lookup"><span data-stu-id="84901-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="84901-106">En ce qui concerne le trafic Teams ou Skype Entreprise, Microsoft recommande d’ignorer les serveurs.</span><span class="sxs-lookup"><span data-stu-id="84901-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="84901-107">En raison du chiffrement déjà chiffré, le trafic n’assure pas la sécurité de Teams ou de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="84901-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="84901-108">De plus, un serveur proxy peut entraîner des complications.</span><span class="sxs-lookup"><span data-stu-id="84901-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="84901-109">Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="84901-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="84901-110">De tels problèmes entraînent une expérience négative dans les scénarios Teams ou Skype Entreprise tels que l’audio et la vidéo, pour lequel les flux en temps réel sont essentiels.</span><span class="sxs-lookup"><span data-stu-id="84901-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="84901-111">SI vous devez utiliser un serveur proxy</span><span class="sxs-lookup"><span data-stu-id="84901-111">If you need to use a proxy server</span></span>

<span data-ttu-id="84901-112">Certaines organisations n’ont pas d’autres choix que d’utiliser un proxy pour le trafic d’Équipes ou de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="84901-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="84901-113">Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.</span><span class="sxs-lookup"><span data-stu-id="84901-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="84901-114">Microsoft recommande également :</span><span class="sxs-lookup"><span data-stu-id="84901-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="84901-115">L'utilisation de la résolution DNS externe</span><span class="sxs-lookup"><span data-stu-id="84901-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="84901-116">L'utilisation du routage UDP direct</span><span class="sxs-lookup"><span data-stu-id="84901-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="84901-117">L'autorisation du trafic UDP</span><span class="sxs-lookup"><span data-stu-id="84901-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="84901-118">Suivant les autres recommandations de nos directives en matière de mise en réseau : Préparer le réseau de votre [organisation pour Teams](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="84901-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="84901-119">Ces conseils devraient limiter l'apparition de problèmes.</span><span class="sxs-lookup"><span data-stu-id="84901-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="84901-120">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="84901-120">Related topics</span></span>

[<span data-ttu-id="84901-121">Principes de connectivité réseau de Microsoft 365 et Office 365</span><span class="sxs-lookup"><span data-stu-id="84901-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="84901-122">Préparer le réseau de votre organisation pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84901-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)