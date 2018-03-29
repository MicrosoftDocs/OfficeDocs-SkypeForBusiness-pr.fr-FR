---
title: Routage interjonctions dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Découvrez comment Skype pour Business Server Voix Entreprise prend en charge le routage inter-trunk.
ms.openlocfilehash: 58872fccca335792ccbdf03c2c8475c328197426
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="inter-trunk-routing-in-skype-for-business-server-2015"></a><span data-ttu-id="99d85-103">Routage interjonctions dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="99d85-103">Inter-trunk routing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="99d85-104">Découvrez comment Skype pour Business Server Voix Entreprise prend en charge le routage inter-trunk.</span><span class="sxs-lookup"><span data-stu-id="99d85-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="99d85-105">Skype pour Business Server fournit la gestion de session de base par le biais de la prise en charge de la gamme intertrunk.</span><span class="sxs-lookup"><span data-stu-id="99d85-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="99d85-106">Ainsi, Skype pour Business Server fournir des fonctionnalités de contrôle d’appel à des systèmes de téléphonie en aval.</span><span class="sxs-lookup"><span data-stu-id="99d85-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="99d85-107">Le routage entre les jonctions peut interconnecter un IP-PBX à une passerelle de réseau de téléphonique commuté (PSTN) pour que les appels d’un téléphone PBX (autocommutateur privé) puissent être acheminés vers la passerelle PSTN et que les appels PSTN entrants puissent être acheminés vers un téléphone PBX.</span><span class="sxs-lookup"><span data-stu-id="99d85-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="99d85-108">De même, Skype pour Business Server pouvez interconnecter deux ou plusieurs systèmes IP-PBX afin que les appels peuvent être placés et reçus entre téléphones PBX de différents systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="99d85-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="99d85-109">La figure suivante illustre la Skype pour Business Server fournissant l’interconnectivité entre une passerelle PSTN et un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="99d85-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Diagramme IP-PBX/Passerelle RTC connectant Lync Server](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="99d85-111">La figure suivante illustre la Skype pour Business Server connexion de deux systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="99d85-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagramme IP-PBX/Passerelle RTC interconnectant Lync Server](../../media/inter_trunk02.jpg)
  

