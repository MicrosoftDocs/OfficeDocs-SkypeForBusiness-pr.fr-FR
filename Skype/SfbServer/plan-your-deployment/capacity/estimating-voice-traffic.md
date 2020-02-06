---
title: Estimation de l’utilisation et du trafic vocaux pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Vous pouvez utiliser la métrique suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports requis pour prendre en charge ce trafic.
ms.openlocfilehash: f324a3030a8265288a30062fdfc1040a1aea8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816063"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="6882c-103">Estimation de l’utilisation et du trafic vocaux pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6882c-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="6882c-104">Vous pouvez utiliser la métrique suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports requis pour prendre en charge ce trafic.</span><span class="sxs-lookup"><span data-stu-id="6882c-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="6882c-105">Pour **Faible trafic** (1 appel PSTN par utilisateur et par heure), 15 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="6882c-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="6882c-106">Pour **Trafic moyen** (2 appels PSTN par utilisateur et par heure), 10 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="6882c-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="6882c-107">Pour **Trafic important** (au moins 3 appels PSTN par utilisateur et par heure), 5 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="6882c-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="6882c-108">Le nombre de ports à son tour détermine le nombre de serveurs de médiation et de passerelles qui seront nécessaires.</span><span class="sxs-lookup"><span data-stu-id="6882c-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="6882c-109">La taille des passerelles de réseau téléphonique commuté (PSTN) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports.</span><span class="sxs-lookup"><span data-stu-id="6882c-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="6882c-110">(Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)</span><span class="sxs-lookup"><span data-stu-id="6882c-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="6882c-p102">Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.</span><span class="sxs-lookup"><span data-stu-id="6882c-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

