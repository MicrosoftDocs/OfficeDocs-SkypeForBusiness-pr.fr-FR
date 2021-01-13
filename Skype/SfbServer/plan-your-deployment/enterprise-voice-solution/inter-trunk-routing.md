---
title: Routage inter-acheminements dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Découvrez comment Skype Entreprise Server Voix Entreprise prend en charge le routage inter-acheminements.
ms.openlocfilehash: fc03f0df530be12ad1d08148850c11d8f92a2791
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825595"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="8477c-103">Routage inter-acheminements dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8477c-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="8477c-104">Découvrez comment Skype Entreprise Server Voix Entreprise prend en charge le routage inter-acheminements.</span><span class="sxs-lookup"><span data-stu-id="8477c-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="8477c-105">Skype Entreprise Server offre une gestion de session de base par le biais de la prise en charge du routage entre les éléments.</span><span class="sxs-lookup"><span data-stu-id="8477c-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="8477c-106">Cela permet à Skype Entreprise Server de fournir des fonctionnalités de contrôle des appels aux systèmes téléphoniques en aval.</span><span class="sxs-lookup"><span data-stu-id="8477c-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="8477c-107">Le routage entre les connexions peut interconnecter un SYSTÈME IP-PBX à une passerelle de réseau téléphonique commuté (PSTN) afin que les appels provenant d’un téléphone PBX (autoconnexion privé) soient acheminés vers le réseau téléphonique commuté et que les appels PSTN entrants soient acheminés vers un téléphone PBX.</span><span class="sxs-lookup"><span data-stu-id="8477c-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="8477c-108">De même, Skype Entreprise Server peut interconnecter au moins deux systèmes IP-PBX afin que les appels soient passé et reçus entre des téléphones PBX à partir des différents systèmes IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="8477c-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="8477c-109">La figure suivante illustre Skype Entreprise Server fournissant une interconnectivité entre une passerelle PSTN et un système IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="8477c-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Diagramme Lync Server connectant la passerelle PSTN/IP-PBX](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="8477c-111">La figure suivante illustre la connexion de deux systèmes IP-PBX à Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8477c-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagramme Lync Server interconnectant les systèmes IP-PAX](../../media/inter_trunk02.jpg)
  

