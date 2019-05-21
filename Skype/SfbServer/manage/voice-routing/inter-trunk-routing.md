---
title: Routage inter-Trunk dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype entreprise Server fournit une gestion de session de base grâce à la prise en charge du routage intertrunk. '
ms.openlocfilehash: 2c5438f78da78870a5dae8c697d4d30d19a316ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274967"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="98942-103">Routage inter-Trunk dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="98942-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="98942-104">Skype entreprise Server fournit une gestion de session de base grâce à la prise en charge du routage intertrunk.</span><span class="sxs-lookup"><span data-stu-id="98942-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="98942-105">Cette fonctionnalité permet à Skype entreprise Server de fournir des fonctionnalités de contrôle d’appel aux systèmes de téléphonie en aval.</span><span class="sxs-lookup"><span data-stu-id="98942-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="98942-106">Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (PSTN) pour que les appels d’un téléphone PBX (autocommutateur privé) puissent être acheminés vers la passerelle PSTN et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX.</span><span class="sxs-lookup"><span data-stu-id="98942-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="98942-107">De la même façon, Skype entreprise Server peut interconnecter au moins deux systèmes IP-PBX pour que les appels puissent être placés et reçus entre les téléphones PBX des différents systèmes IP PBX.</span><span class="sxs-lookup"><span data-stu-id="98942-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="98942-108">La figure suivante illustre Skype entreprise Server permettant une interconnexion entre une passerelle RTC et un PBX IP.</span><span class="sxs-lookup"><span data-stu-id="98942-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Interconnexion entre une passerelle RTC et un PBX IP](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="98942-110">La figure suivante illustre Skype entreprise Server connectant deux systèmes PBX IP.</span><span class="sxs-lookup"><span data-stu-id="98942-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype entreprise Server connectant deux systèmes IP-PGX](../../media/two-ip-pbx-systems.jpg)

