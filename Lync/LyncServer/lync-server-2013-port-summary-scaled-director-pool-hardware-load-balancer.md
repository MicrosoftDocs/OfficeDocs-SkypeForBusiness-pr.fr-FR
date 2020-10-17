---
title: 'Lync Server 2013 : Résumé des ports-pool directeur mis à l’ampleur, équilibreur de charge matérielle'
description: 'Lync Server 2013 : Résumé des ports-pool directeur mis à l’ampleur, équilibreur de charge matérielle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10bfb3a3ad3a38b6cb0e46414bf22deecc71d7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564550"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="1d82e-103">Résumé des ports-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d82e-103">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d82e-104">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="1d82e-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="1d82e-105">Les exigences de port de pare-feu pour un pool directeur consistent en des ports utilisés pour établir la communication avec le directeur à partir de l’interface interne du serveur Edge ou de l’interface interne du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="1d82e-105">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="1d82e-106">Microsoft Lync Server 2013 attend par défaut que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts depuis le proxy inverse vers le directeur, ainsi que le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1d82e-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="1d82e-107">En outre, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge vers le directeur et vers le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1d82e-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1d82e-108">Le protocole SIP utilise SIP/MTLS/TCP 5061 à partir du serveur Edge vers le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1d82e-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1d82e-109">Une règle qui autorise la communication SIP/MTLS/TCP 5061 depuis le directeur, le pool frontal et le serveur frontal vers l’interface interne du serveur Edge doit également être créée.</span><span class="sxs-lookup"><span data-stu-id="1d82e-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="1d82e-110">Ports et protocoles de directeur pour les définitions de pare-feu</span><span class="sxs-lookup"><span data-stu-id="1d82e-110">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d82e-111">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="1d82e-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1d82e-112">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="1d82e-112">Source IP address</span></span></th>
<th><span data-ttu-id="1d82e-113">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="1d82e-113">Destination IP address</span></span></th>
<th><span data-ttu-id="1d82e-114">Notes</span><span class="sxs-lookup"><span data-stu-id="1d82e-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d82e-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="1d82e-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="1d82e-116">Interface interne de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="1d82e-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1d82e-117">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="1d82e-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1d82e-118">Initialement reçue par le côté externe du proxy inverse, la communication est envoyée aux services Web du directeur charge matérielle VIP et serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="1d82e-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d82e-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="1d82e-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="1d82e-120">Interface interne de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="1d82e-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1d82e-121">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="1d82e-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1d82e-122">Initialement reçue par le côté externe du proxy inverse, la communication est envoyée aux services Web du directeur charge matérielle VIP et serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="1d82e-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d82e-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="1d82e-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="1d82e-124">Directeur</span><span class="sxs-lookup"><span data-stu-id="1d82e-124">Director</span></span></p></td>
<td><p><span data-ttu-id="1d82e-125">Serveur frontal ou pool frontal</span><span class="sxs-lookup"><span data-stu-id="1d82e-125">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="1d82e-126">Communication entre le directeur charge matérielle VIP et les serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="1d82e-126">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d82e-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="1d82e-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="1d82e-128">Clients internes</span><span class="sxs-lookup"><span data-stu-id="1d82e-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1d82e-129">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="1d82e-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1d82e-130">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="1d82e-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d82e-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="1d82e-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="1d82e-132">Clients internes</span><span class="sxs-lookup"><span data-stu-id="1d82e-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1d82e-133">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="1d82e-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1d82e-134">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="1d82e-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d82e-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="1d82e-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="1d82e-136">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="1d82e-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1d82e-137">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="1d82e-137">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="1d82e-138">Communication SIP du serveur Edge vers le directeur et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="1d82e-138">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d82e-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="1d82e-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="1d82e-140">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="1d82e-140">Any</span></span></p></td>
<td><p><span data-ttu-id="1d82e-141">Directeur</span><span class="sxs-lookup"><span data-stu-id="1d82e-141">Director</span></span></p></td>
<td><p><span data-ttu-id="1d82e-142">Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClsAgent.exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="1d82e-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d82e-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="1d82e-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="1d82e-144">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="1d82e-144">Any</span></span></p></td>
<td><p><span data-ttu-id="1d82e-145">Directeur</span><span class="sxs-lookup"><span data-stu-id="1d82e-145">Director</span></span></p></td>
<td><p><span data-ttu-id="1d82e-146">Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClsAgent.exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="1d82e-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d82e-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="1d82e-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="1d82e-148">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="1d82e-148">Any</span></span></p></td>
<td><p><span data-ttu-id="1d82e-149">Directeur</span><span class="sxs-lookup"><span data-stu-id="1d82e-149">Director</span></span></p></td>
<td><p><span data-ttu-id="1d82e-150">Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClsAgent.exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="1d82e-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

