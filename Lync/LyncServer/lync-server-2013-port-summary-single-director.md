---
title: 'Lync Server 2013 : Résumé des ports - Directeur unique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5568a37093f161caef6717df5d3a3f09be6f18c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="c6487-102">Résumé des ports - Directeur unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6487-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6487-103">_**Dernière modification de la rubrique:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c6487-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c6487-104">La configuration requise pour les ports de pare-feu pour un seul directeur consiste à utiliser les ports utilisés pour établir une communication avec le directeur à partir de l’interface interne ou du réseau interne du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="c6487-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="c6487-105">Microsoft Lync Server 2013 par défaut s’attend à ce que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts du proxy inverse au directeur, ainsi qu’au pool frontal et au serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c6487-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="c6487-106">Par ailleurs, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge au directeur et au serveur principal et au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="c6487-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="c6487-107">Le protocole SIP utilise SIP/MTLS/TCP 5061 du serveur Edge au pool frontal et au serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c6487-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="c6487-108">Une règle qui autorise la communication SIP/MTLS/TCP 5061 à partir du réalisateur, du pool frontal et du serveur frontal vers l’interface interne du serveur Edge doit également être créée.</span><span class="sxs-lookup"><span data-stu-id="c6487-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="c6487-109">Ports et protocoles de Director uniques pour les définitions de pare-feu</span><span class="sxs-lookup"><span data-stu-id="c6487-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6487-110">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="c6487-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c6487-111">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="c6487-111">Source IP address</span></span></th>
<th><span data-ttu-id="c6487-112">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="c6487-112">Destination IP address</span></span></th>
<th><span data-ttu-id="c6487-113">Remarques</span><span class="sxs-lookup"><span data-stu-id="c6487-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6487-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="c6487-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="c6487-115">Interface interne du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="c6487-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="c6487-116">directeur</span><span class="sxs-lookup"><span data-stu-id="c6487-116">Director</span></span></p></td>
<td><p><span data-ttu-id="c6487-117">Initialement reçues par le côté extérieur du proxy inverse, la communication est envoyée au directeur et aux services Web du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="c6487-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6487-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="c6487-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="c6487-119">Interface interne du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="c6487-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="c6487-120">directeur</span><span class="sxs-lookup"><span data-stu-id="c6487-120">Director</span></span></p></td>
<td><p><span data-ttu-id="c6487-121">Initialement reçues par le côté extérieur du proxy inverse, la communication est envoyée au directeur et aux services Web du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="c6487-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6487-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="c6487-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="c6487-123">directeur</span><span class="sxs-lookup"><span data-stu-id="c6487-123">Director</span></span></p></td>
<td><p><span data-ttu-id="c6487-124">Serveur frontal ou liste de front-end</span><span class="sxs-lookup"><span data-stu-id="c6487-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="c6487-125">Communication entre serveur entre le directeur et le serveur frontal</span><span class="sxs-lookup"><span data-stu-id="c6487-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6487-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="c6487-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="c6487-127">Clients internes</span><span class="sxs-lookup"><span data-stu-id="c6487-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="c6487-128">Services Web de Director</span><span class="sxs-lookup"><span data-stu-id="c6487-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="c6487-129">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="c6487-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6487-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="c6487-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="c6487-131">Clients internes</span><span class="sxs-lookup"><span data-stu-id="c6487-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="c6487-132">Services Web de Director</span><span class="sxs-lookup"><span data-stu-id="c6487-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="c6487-133">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="c6487-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6487-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="c6487-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="c6487-135">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="c6487-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c6487-136">directeur</span><span class="sxs-lookup"><span data-stu-id="c6487-136">Director</span></span></p></td>
<td><p><span data-ttu-id="c6487-137">Communication SIP du serveur Edge au directeur et au serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c6487-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6487-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="c6487-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="c6487-139">Indifférente</span><span class="sxs-lookup"><span data-stu-id="c6487-139">Any</span></span></p></td>
<td><p><span data-ttu-id="c6487-140">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="c6487-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c6487-141">Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClasAgent. exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="c6487-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6487-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="c6487-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="c6487-143">Indifférente</span><span class="sxs-lookup"><span data-stu-id="c6487-143">Any</span></span></p></td>
<td><p><span data-ttu-id="c6487-144">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="c6487-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c6487-145">Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClasAgent. exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="c6487-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6487-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="c6487-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="c6487-147">Indifférente</span><span class="sxs-lookup"><span data-stu-id="c6487-147">Any</span></span></p></td>
<td><p><span data-ttu-id="c6487-148">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="c6487-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c6487-149">Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClasAgent. exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="c6487-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

