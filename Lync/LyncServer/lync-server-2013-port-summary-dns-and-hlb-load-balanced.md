---
title: 'Lync Server 2013 : Résumé des ports-équilibrage de charge DNS et charge matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6ba03a73538426b9c820388f65e728c36881148
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527941"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="c0d63-102">Résumé des ports-équilibrage de charge DNS et charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0d63-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0d63-103">_**Dernière modification de la rubrique :** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c0d63-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c0d63-104">Les exigences de port de pare-feu pour un seul directeur consistent en des ports utilisés pour établir la communication avec le directeur depuis l’interface interne ou le réseau interne du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="c0d63-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="c0d63-105">Microsoft Lync Server 2013 attend par défaut que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts depuis le proxy inverse vers le directeur, ainsi que le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c0d63-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="c0d63-106">En outre, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge vers le directeur et vers le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c0d63-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="c0d63-107">Le protocole SIP utilise SIP/MTLS/TCP 5061 à partir du serveur Edge vers le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c0d63-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="c0d63-108">Une règle qui autorise la communication SIP/MTLS/TCP 5061 depuis le directeur, le pool frontal et le serveur frontal vers l’interface interne du serveur Edge doit également être créée.</span><span class="sxs-lookup"><span data-stu-id="c0d63-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="c0d63-109">Ports et protocoles de directeur unique pour les définitions de pare-feu</span><span class="sxs-lookup"><span data-stu-id="c0d63-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0d63-110">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c0d63-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c0d63-111">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="c0d63-111">Source IP address</span></span></th>
<th><span data-ttu-id="c0d63-112">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="c0d63-112">Destination IP address</span></span></th>
<th><span data-ttu-id="c0d63-113">Notes</span><span class="sxs-lookup"><span data-stu-id="c0d63-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0d63-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="c0d63-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="c0d63-115">Interface interne de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="c0d63-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="c0d63-116">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="c0d63-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="c0d63-117">Initialement reçue par le côté externe du proxy inverse, la communication est envoyée aux services Web de l’adresse IP virtuelle et du serveur frontal charge matérielle directeur.</span><span class="sxs-lookup"><span data-stu-id="c0d63-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0d63-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="c0d63-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="c0d63-119">Interface interne de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="c0d63-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="c0d63-120">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="c0d63-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="c0d63-121">Initialement reçue par le côté externe du proxy inverse, la communication est envoyée aux services Web de l’adresse IP virtuelle et du serveur frontal charge matérielle directeur.</span><span class="sxs-lookup"><span data-stu-id="c0d63-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0d63-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="c0d63-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="c0d63-123">Directeur</span><span class="sxs-lookup"><span data-stu-id="c0d63-123">Director</span></span></p></td>
<td><p><span data-ttu-id="c0d63-124">Pool frontal ou serveur frontal</span><span class="sxs-lookup"><span data-stu-id="c0d63-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="c0d63-125">Communication entre le directeur charge matérielle VIP et le serveur frontal ou les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="c0d63-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0d63-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="c0d63-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="c0d63-127">Clients internes</span><span class="sxs-lookup"><span data-stu-id="c0d63-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="c0d63-128">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="c0d63-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="c0d63-129">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="c0d63-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0d63-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="c0d63-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="c0d63-131">Clients internes</span><span class="sxs-lookup"><span data-stu-id="c0d63-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="c0d63-132">Adresse IP du programme d’équilibrage de la charge matérielle directeur</span><span class="sxs-lookup"><span data-stu-id="c0d63-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="c0d63-133">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="c0d63-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0d63-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="c0d63-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="c0d63-135">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="c0d63-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c0d63-136">Directeur</span><span class="sxs-lookup"><span data-stu-id="c0d63-136">Director</span></span></p></td>
<td><p><span data-ttu-id="c0d63-137">Communication SIP entre le serveur Edge et le directeur, ainsi que les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="c0d63-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0d63-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="c0d63-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="c0d63-139">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="c0d63-139">Any</span></span></p></td>
<td><p><span data-ttu-id="c0d63-140">Directeur</span><span class="sxs-lookup"><span data-stu-id="c0d63-140">Director</span></span></p></td>
<td><p><span data-ttu-id="c0d63-141">Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClsAgent.exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="c0d63-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0d63-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="c0d63-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="c0d63-143">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="c0d63-143">Any</span></span></p></td>
<td><p><span data-ttu-id="c0d63-144">Directeur</span><span class="sxs-lookup"><span data-stu-id="c0d63-144">Director</span></span></p></td>
<td><p><span data-ttu-id="c0d63-145">Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClsAgent.exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="c0d63-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0d63-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="c0d63-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="c0d63-147">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="c0d63-147">Any</span></span></p></td>
<td><p><span data-ttu-id="c0d63-148">Directeur</span><span class="sxs-lookup"><span data-stu-id="c0d63-148">Director</span></span></p></td>
<td><p><span data-ttu-id="c0d63-149">Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClsAgent.exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="c0d63-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

