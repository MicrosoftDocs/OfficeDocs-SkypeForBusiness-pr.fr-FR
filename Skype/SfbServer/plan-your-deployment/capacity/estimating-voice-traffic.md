---
title: Estimation de l’utilisation de la voix et du trafic pour Skype Entreprise Server
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
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: Vous pouvez utiliser la mesure suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports requis pour prendre en charge ce trafic.
ms.openlocfilehash: c631361a7ef6d4706632f59366adac3384a6d255
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827684"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="0c035-103">Estimation de l’utilisation de la voix et du trafic pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0c035-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="0c035-104">Vous pouvez utiliser la mesure suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports requis pour prendre en charge ce trafic.</span><span class="sxs-lookup"><span data-stu-id="0c035-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="0c035-105">Pour **Faible trafic** (1 appel PSTN par utilisateur et par heure), 15 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="0c035-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="0c035-106">Pour **Trafic moyen** (2 appels PSTN par utilisateur et par heure), 10 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="0c035-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="0c035-107">Pour **Trafic important** (au moins 3 appels PSTN par utilisateur et par heure), 5 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="0c035-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="0c035-108">Le nombre de ports détermine à son tour le nombre de serveurs de médiation et de passerelles qui seront requis.</span><span class="sxs-lookup"><span data-stu-id="0c035-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="0c035-109">La taille des passerelles de réseau téléphonique commuté (PSTN) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports.</span><span class="sxs-lookup"><span data-stu-id="0c035-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="0c035-110">(Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)</span><span class="sxs-lookup"><span data-stu-id="0c035-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="0c035-p102">Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.</span><span class="sxs-lookup"><span data-stu-id="0c035-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

