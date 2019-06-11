---
title: 'Lync Server 2013 : Résumé des ports - Équilibrage de charge DNS et matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd2a276f9495d314d2a8d4588f027df08978b94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="8bc93-102">Résumé des ports - Équilibrage de charge DNS et matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bc93-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bc93-103">_**Dernière modification de la rubrique:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8bc93-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8bc93-104">La configuration requise pour les ports de pare-feu pour un seul directeur consiste à utiliser les ports utilisés pour établir une communication avec le directeur à partir de l’interface interne ou du réseau interne du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="8bc93-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="8bc93-105">Microsoft Lync Server 2013 par défaut s’attend à ce que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts du proxy inverse au directeur, ainsi qu’au pool frontal et au serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="8bc93-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="8bc93-106">Par ailleurs, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge au directeur et au serveur principal et au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="8bc93-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="8bc93-107">Le protocole SIP utilise SIP/MTLS/TCP 5061 du serveur Edge au pool frontal et au serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="8bc93-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="8bc93-108">Une règle qui autorise la communication SIP/MTLS/TCP 5061 à partir du réalisateur, du pool frontal et du serveur frontal vers l’interface interne du serveur Edge doit également être créée.</span><span class="sxs-lookup"><span data-stu-id="8bc93-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="8bc93-109">Ports et protocoles de Director uniques pour les définitions de pare-feu</span><span class="sxs-lookup"><span data-stu-id="8bc93-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bc93-110">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="8bc93-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8bc93-111">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="8bc93-111">Source IP address</span></span></th>
<th><span data-ttu-id="8bc93-112">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="8bc93-112">Destination IP address</span></span></th>
<th><span data-ttu-id="8bc93-113">Remarques</span><span class="sxs-lookup"><span data-stu-id="8bc93-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bc93-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="8bc93-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="8bc93-115">Interface interne du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="8bc93-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="8bc93-116">Adresse VIP de l’équilibrage de charge matérielle Director</span><span class="sxs-lookup"><span data-stu-id="8bc93-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="8bc93-117">Initialement reçues par le côté extérieur du proxy inverse, la communication est envoyée aux services d’adresse IP du directeur HLB et aux services Web du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="8bc93-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc93-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="8bc93-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="8bc93-119">Interface interne du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="8bc93-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="8bc93-120">Adresse VIP de l’équilibrage de charge matérielle Director</span><span class="sxs-lookup"><span data-stu-id="8bc93-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="8bc93-121">Initialement reçues par le côté extérieur du proxy inverse, la communication est envoyée aux services d’adresse IP du directeur HLB et aux services Web du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="8bc93-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc93-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="8bc93-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="8bc93-123">directeur</span><span class="sxs-lookup"><span data-stu-id="8bc93-123">Director</span></span></p></td>
<td><p><span data-ttu-id="8bc93-124">Pool frontal ou serveur frontal</span><span class="sxs-lookup"><span data-stu-id="8bc93-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="8bc93-125">Communications entre les serveurs entre le directeur HLB VIP et le serveur frontal ou les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="8bc93-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc93-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="8bc93-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="8bc93-127">Clients internes</span><span class="sxs-lookup"><span data-stu-id="8bc93-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="8bc93-128">Adresse VIP de l’équilibrage de charge matérielle Director</span><span class="sxs-lookup"><span data-stu-id="8bc93-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="8bc93-129">Le directeur fournit des services Web aux clients externes et internes.</span><span class="sxs-lookup"><span data-stu-id="8bc93-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc93-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="8bc93-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="8bc93-131">Clients internes</span><span class="sxs-lookup"><span data-stu-id="8bc93-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="8bc93-132">Adresse VIP de l’équilibrage de charge matérielle Director</span><span class="sxs-lookup"><span data-stu-id="8bc93-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="8bc93-133">Le directeur fournit des services Web aux clients externes et internes.</span><span class="sxs-lookup"><span data-stu-id="8bc93-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc93-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="8bc93-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="8bc93-135">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="8bc93-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8bc93-136">directeur</span><span class="sxs-lookup"><span data-stu-id="8bc93-136">Director</span></span></p></td>
<td><p><span data-ttu-id="8bc93-137">Communication SIP du serveur Edge au directeur ainsi qu’aux serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="8bc93-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc93-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="8bc93-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="8bc93-139">Indifférente</span><span class="sxs-lookup"><span data-stu-id="8bc93-139">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc93-140">directeur</span><span class="sxs-lookup"><span data-stu-id="8bc93-140">Director</span></span></p></td>
<td><p><span data-ttu-id="8bc93-141">Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClsAgent. exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="8bc93-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bc93-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="8bc93-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="8bc93-143">Indifférente</span><span class="sxs-lookup"><span data-stu-id="8bc93-143">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc93-144">directeur</span><span class="sxs-lookup"><span data-stu-id="8bc93-144">Director</span></span></p></td>
<td><p><span data-ttu-id="8bc93-145">Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClsAgent. exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="8bc93-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bc93-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="8bc93-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="8bc93-147">Indifférente</span><span class="sxs-lookup"><span data-stu-id="8bc93-147">Any</span></span></p></td>
<td><p><span data-ttu-id="8bc93-148">directeur</span><span class="sxs-lookup"><span data-stu-id="8bc93-148">Director</span></span></p></td>
<td><p><span data-ttu-id="8bc93-149">Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClsAgent. exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="8bc93-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

