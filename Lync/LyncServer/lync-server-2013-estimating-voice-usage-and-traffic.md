---
title: 'Lync Server 2013 : Estimation du trafic et de l’utilisation de la voix'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06093893c5de9a08322e1577fbbbe6779d4209cc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="ed067-102">Estimation du trafic et de l’utilisation de la voix pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed067-102">Estimating voice usage and traffic for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed067-103">_**Dernière modification de la rubrique :** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="ed067-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="ed067-104">L’outil de planification de Microsoft Lync Server 2013 utilise la métrique suivante pour estimer le trafic utilisateur sur chaque site, ainsi que le nombre de ports requis pour prendre en charge ce trafic.</span><span class="sxs-lookup"><span data-stu-id="ed067-104">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="ed067-105">Pour **Faible trafic** (1 appel PSTN par utilisateur et par heure), 15 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="ed067-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="ed067-106">Pour **Trafic moyen** (2 appels PSTN par utilisateur et par heure), 10 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="ed067-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="ed067-107">Pour **Trafic important** (au moins 3 appels PSTN par utilisateur et par heure), 5 utilisateurs par port.</span><span class="sxs-lookup"><span data-stu-id="ed067-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="ed067-108">Le nombre de ports à son tour détermine le nombre de serveurs de médiation et de passerelles qui seront nécessaires.</span><span class="sxs-lookup"><span data-stu-id="ed067-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="ed067-109">La taille des passerelles de réseau téléphonique commuté (PSTN) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports.</span><span class="sxs-lookup"><span data-stu-id="ed067-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="ed067-110">(Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)</span><span class="sxs-lookup"><span data-stu-id="ed067-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="ed067-p102">Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.</span><span class="sxs-lookup"><span data-stu-id="ed067-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

