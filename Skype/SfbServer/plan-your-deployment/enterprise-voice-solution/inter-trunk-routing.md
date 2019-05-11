---
title: Routage entre les jonctions dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Découvrez comment Skype pour Business Server Enterprise Voice prend en charge le routage entre les jonctions.
ms.openlocfilehash: 60e91003e9b1b70393f99ef2ce6d8021fa2e5010
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924219"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="af9c3-103">Routage entre les jonctions dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="af9c3-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="af9c3-104">Découvrez comment Skype pour Business Server Enterprise Voice prend en charge le routage entre les jonctions.</span><span class="sxs-lookup"><span data-stu-id="af9c3-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="af9c3-105">Skype pour Business Server assure la gestion de session de base par le biais de la prise en charge de routage d’inter-jonctions.</span><span class="sxs-lookup"><span data-stu-id="af9c3-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="af9c3-106">Cela permet de Skype pour Business Server fournir des fonctionnalités de contrôle d’appel aux systèmes de téléphonie en aval.</span><span class="sxs-lookup"><span data-stu-id="af9c3-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="af9c3-107">Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (PSTN) pour que les appels d’un téléphone PBX (autocommutateur privé) puissent être acheminés vers la passerelle PSTN et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX.</span><span class="sxs-lookup"><span data-stu-id="af9c3-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="af9c3-108">De même, Skype pour Business Server peut interconnect deux ou plusieurs systèmes IP-PBX afin que les appels peuvent être placés et reçus entre les téléphones PBX à partir de différents systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="af9c3-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="af9c3-109">La figure suivante illustre Skype pour Business Server fournissant une interconnectivité entre une passerelle PSTN et un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="af9c3-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Diagramme IP-PBX/Passerelle RTC connectant Lync Server](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="af9c3-111">La figure suivante illustre Skype pour Business Server connectent deux systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="af9c3-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagramme IP-PBX/Passerelle RTC interconnectant Lync Server](../../media/inter_trunk02.jpg)
  

