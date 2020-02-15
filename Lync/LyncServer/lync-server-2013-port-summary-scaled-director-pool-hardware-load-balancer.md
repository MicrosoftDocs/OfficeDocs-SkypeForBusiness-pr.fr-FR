---
title: 'Lync Server 2013 : Résumé des ports-pool directeur mis à l’ampleur, équilibreur de charge matérielle'
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
ms.openlocfilehash: 18c0957d66d9b877a67819b8fd8d46d4e614cdad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="21212-102">Résumé des ports-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21212-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21212-103">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="21212-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="21212-104">Les exigences de port de pare-feu pour un pool directeur consistent en des ports utilisés pour établir la communication avec le directeur à partir de l’interface interne du serveur Edge ou de l’interface interne du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="21212-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="21212-105">Microsoft Lync Server 2013 attend par défaut que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts depuis le proxy inverse vers le directeur, ainsi que le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="21212-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="21212-106">En outre, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge vers le directeur et vers le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="21212-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="21212-107">Le protocole SIP utilise SIP/MTLS/TCP 5061 à partir du serveur Edge vers le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="21212-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="21212-108">Une règle qui autorise la communication SIP/MTLS/TCP 5061 depuis le directeur, le pool frontal et le serveur frontal vers l’interface interne du serveur Edge doit également être créée.</span><span class="sxs-lookup"><span data-stu-id="21212-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="21212-109">Ports et protocoles de directeur pour les définitions de pare-feu</span><span class="sxs-lookup"><span data-stu-id="21212-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21212-110">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="21212-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="21212-111">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="21212-111">Source IP address</span></span></th>
<th><span data-ttu-id="21212-112">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="21212-112">Destination IP address</span></span></th>
<th><span data-ttu-id="21212-113">Notes</span><span class="sxs-lookup"><span data-stu-id="21212-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21212-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="21212-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="21212-115">Interface interne de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="21212-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="21212-116">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="21212-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="21212-117">Initialement reçue par le côté externe du proxy inverse, la communication est envoyée aux services Web du directeur charge matérielle VIP et serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="21212-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21212-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="21212-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="21212-119">Interface interne de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="21212-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="21212-120">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="21212-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="21212-121">Initialement reçue par le côté externe du proxy inverse, la communication est envoyée aux services Web du directeur charge matérielle VIP et serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="21212-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21212-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="21212-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="21212-123">48000b</span><span class="sxs-lookup"><span data-stu-id="21212-123">Director</span></span></p></td>
<td><p><span data-ttu-id="21212-124">Serveur frontal ou pool frontal</span><span class="sxs-lookup"><span data-stu-id="21212-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="21212-125">Communication entre le directeur charge matérielle VIP et les serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="21212-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21212-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="21212-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="21212-127">Clients internes</span><span class="sxs-lookup"><span data-stu-id="21212-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="21212-128">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="21212-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="21212-129">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="21212-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21212-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="21212-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="21212-131">Clients internes</span><span class="sxs-lookup"><span data-stu-id="21212-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="21212-132">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="21212-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="21212-133">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="21212-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21212-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="21212-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="21212-135">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="21212-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="21212-136">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="21212-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="21212-137">Communication SIP du serveur Edge vers le directeur et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="21212-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21212-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="21212-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="21212-139">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="21212-139">Any</span></span></p></td>
<td><p><span data-ttu-id="21212-140">48000b</span><span class="sxs-lookup"><span data-stu-id="21212-140">Director</span></span></p></td>
<td><p><span data-ttu-id="21212-141">Commandes et collection de journaux du service de journalisation centralisée (ClsController. exe) ou de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="21212-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21212-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="21212-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="21212-143">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="21212-143">Any</span></span></p></td>
<td><p><span data-ttu-id="21212-144">48000b</span><span class="sxs-lookup"><span data-stu-id="21212-144">Director</span></span></p></td>
<td><p><span data-ttu-id="21212-145">Commandes et collection de journaux du service de journalisation centralisée (ClsController. exe) ou de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="21212-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21212-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="21212-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="21212-147">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="21212-147">Any</span></span></p></td>
<td><p><span data-ttu-id="21212-148">48000b</span><span class="sxs-lookup"><span data-stu-id="21212-148">Director</span></span></p></td>
<td><p><span data-ttu-id="21212-149">Commandes et collection de journaux du service de journalisation centralisée (ClsController. exe) ou de l’agent (ClsAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="21212-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

