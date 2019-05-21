---
title: Routage inter-Trunk dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Découvrez comment Skype entreprise Server Voice prend en charge le routage inter-Trunk.
ms.openlocfilehash: f590463eced61cf2e8b19a27f7cfc2dd648c63c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276830"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="a139c-103">Routage inter-Trunk dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a139c-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="a139c-104">Découvrez comment Skype entreprise Server Voice prend en charge le routage inter-Trunk.</span><span class="sxs-lookup"><span data-stu-id="a139c-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="a139c-105">Skype entreprise Server fournit une gestion de session de base grâce à la prise en charge du routage intertrunk.</span><span class="sxs-lookup"><span data-stu-id="a139c-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="a139c-106">Cela permet à Skype entreprise Server de fournir des fonctionnalités de contrôle d’appel aux systèmes de téléphonie en aval.</span><span class="sxs-lookup"><span data-stu-id="a139c-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="a139c-107">Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (PSTN) pour que les appels d’un téléphone PBX (autocommutateur privé) puissent être acheminés vers la passerelle PSTN et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX.</span><span class="sxs-lookup"><span data-stu-id="a139c-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="a139c-108">De la même façon, Skype entreprise Server peut interconnecter au moins deux systèmes IP-PBX pour que les appels puissent être placés et reçus entre les téléphones PBX des différents systèmes IP PBX.</span><span class="sxs-lookup"><span data-stu-id="a139c-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="a139c-109">La figure suivante illustre Skype entreprise Server permettant une interconnexion entre une passerelle RTC et un PBX IP.</span><span class="sxs-lookup"><span data-stu-id="a139c-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Diagramme IP-PBX/Passerelle RTC connectant Lync Server](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="a139c-111">La figure suivante illustre Skype entreprise Server connectant deux systèmes PBX IP.</span><span class="sxs-lookup"><span data-stu-id="a139c-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagramme IP-PBX/Passerelle RTC interconnectant Lync Server](../../media/inter_trunk02.jpg)
  

