---
title: Routage inter-acheminements dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype Entreprise Server offre une gestion de session de base par le biais de la prise en charge du routage entre les éléments. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814124"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="52d64-103">Routage inter-acheminements dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="52d64-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="52d64-104">Skype Entreprise Server offre une gestion de session de base par le biais de la prise en charge du routage entre les éléments.</span><span class="sxs-lookup"><span data-stu-id="52d64-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="52d64-105">Cette fonctionnalité permet à Skype Entreprise Server de fournir des fonctionnalités de contrôle des appels aux systèmes téléphoniques en aval.</span><span class="sxs-lookup"><span data-stu-id="52d64-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="52d64-106">Le routage entre les connexions peut interconnecter un SYSTÈME IP-PBX à une passerelle de réseau téléphonique commuté (PSTN) afin que les appels provenant d’un téléphone PBX (autoconnexion privé) soient acheminés vers le réseau téléphonique commuté et que les appels PSTN entrants soient acheminés vers un téléphone PBX.</span><span class="sxs-lookup"><span data-stu-id="52d64-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="52d64-107">De même, Skype Entreprise Server peut interconnecter au moins deux systèmes IP-PBX afin que les appels soient passé et reçus entre des téléphones PBX à partir des différents systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="52d64-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="52d64-108">La figure suivante illustre Skype Entreprise Server fournissant une interconnectivité entre une passerelle PSTN et un système IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="52d64-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Interconnectivité entre une passerelle PSTN et un SYSTÈME IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="52d64-110">La figure suivante illustre la connexion de deux systèmes IP-PBX à Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="52d64-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype Entreprise Server connectant deux systèmes IP-PGX](../../media/two-ip-pbx-systems.jpg)

