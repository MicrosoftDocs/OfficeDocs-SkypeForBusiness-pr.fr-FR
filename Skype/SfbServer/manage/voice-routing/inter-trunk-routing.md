---
title: Routage entre les jonctions dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype pour Business Server assure la gestion de session de base par le biais de la prise en charge de routage d’inter-jonctions. '
ms.openlocfilehash: 66ee1f0cb9e37587d3c581b895528e27e7fad6c0
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222813"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="0dfd3-103">Routage entre les jonctions dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="0dfd3-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="0dfd3-104">Skype pour Business Server assure la gestion de session de base par le biais de la prise en charge de routage d’inter-jonctions.</span><span class="sxs-lookup"><span data-stu-id="0dfd3-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="0dfd3-105">Cette fonctionnalité permet de Skype pour Business Server fournir des fonctionnalités de contrôle d’appel aux systèmes de téléphonie en aval.</span><span class="sxs-lookup"><span data-stu-id="0dfd3-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="0dfd3-106">Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (PSTN) pour que les appels d’un téléphone PBX (autocommutateur privé) puissent être acheminés vers la passerelle PSTN et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX.</span><span class="sxs-lookup"><span data-stu-id="0dfd3-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="0dfd3-107">De même, Skype pour Business Server peut interconnect deux ou plusieurs systèmes IP-PBX afin que les appels peuvent être placés et reçus entre les téléphones PBX à partir de différents systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="0dfd3-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="0dfd3-108">La figure suivante illustre Skype pour Business Server fournissant une interconnectivité entre une passerelle PSTN et un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="0dfd3-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Interconnectivité entre une passerelle PSTN et un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="0dfd3-110">La figure suivante illustre Skype pour Business Server connectent deux systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="0dfd3-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype pour Business Server connectent deux systèmes IP-PGX](../../media/two-ip-pbx-systems.jpg)

