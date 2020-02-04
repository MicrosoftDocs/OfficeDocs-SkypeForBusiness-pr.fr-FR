---
title: 'Lync Server 2013 : Résumé des ports - Directeur unique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0179d6fd27207d28caa10ffa01bea155f9b00c03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="1dc73-102">Résumé des ports - Directeur unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dc73-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dc73-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1dc73-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1dc73-104">La configuration requise pour les ports de pare-feu pour un seul directeur consiste à utiliser les ports utilisés pour établir une communication avec le directeur à partir de l’interface interne ou du réseau interne du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="1dc73-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="1dc73-105">Microsoft Lync Server 2013 par défaut s’attend à ce que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts du proxy inverse au directeur, ainsi qu’au pool frontal et au serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1dc73-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="1dc73-106">Par ailleurs, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge au directeur et au serveur principal et au pool frontal.</span><span class="sxs-lookup"><span data-stu-id="1dc73-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1dc73-107">Le protocole SIP utilise SIP/MTLS/TCP 5061 du serveur Edge au pool frontal et au serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1dc73-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="1dc73-108">Une règle qui autorise la communication SIP/MTLS/TCP 5061 à partir du réalisateur, du pool frontal et du serveur frontal vers l’interface interne du serveur Edge doit également être créée.</span><span class="sxs-lookup"><span data-stu-id="1dc73-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="1dc73-109">Ports et protocoles de Director uniques pour les définitions de pare-feu</span><span class="sxs-lookup"><span data-stu-id="1dc73-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dc73-110">Rôles/protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="1dc73-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1dc73-111">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="1dc73-111">Source IP address</span></span></th>
<th><span data-ttu-id="1dc73-112">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="1dc73-112">Destination IP address</span></span></th>
<th><span data-ttu-id="1dc73-113">Remarques</span><span class="sxs-lookup"><span data-stu-id="1dc73-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dc73-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="1dc73-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="1dc73-115">Interface interne du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="1dc73-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1dc73-116">directeur</span><span class="sxs-lookup"><span data-stu-id="1dc73-116">Director</span></span></p></td>
<td><p><span data-ttu-id="1dc73-117">Initialement reçues par le côté extérieur du proxy inverse, la communication est envoyée au directeur et aux services Web du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="1dc73-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc73-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="1dc73-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="1dc73-119">Interface interne du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="1dc73-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="1dc73-120">directeur</span><span class="sxs-lookup"><span data-stu-id="1dc73-120">Director</span></span></p></td>
<td><p><span data-ttu-id="1dc73-121">Initialement reçues par le côté extérieur du proxy inverse, la communication est envoyée au directeur et aux services Web du serveur principal.</span><span class="sxs-lookup"><span data-stu-id="1dc73-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc73-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="1dc73-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="1dc73-123">directeur</span><span class="sxs-lookup"><span data-stu-id="1dc73-123">Director</span></span></p></td>
<td><p><span data-ttu-id="1dc73-124">Serveur frontal ou liste de front-end</span><span class="sxs-lookup"><span data-stu-id="1dc73-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="1dc73-125">Communication entre serveur entre le directeur et le serveur frontal</span><span class="sxs-lookup"><span data-stu-id="1dc73-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc73-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="1dc73-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="1dc73-127">Clients internes</span><span class="sxs-lookup"><span data-stu-id="1dc73-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1dc73-128">Services Web de Director</span><span class="sxs-lookup"><span data-stu-id="1dc73-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="1dc73-129">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="1dc73-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc73-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="1dc73-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="1dc73-131">Clients internes</span><span class="sxs-lookup"><span data-stu-id="1dc73-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="1dc73-132">Services Web de Director</span><span class="sxs-lookup"><span data-stu-id="1dc73-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="1dc73-133">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="1dc73-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc73-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="1dc73-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="1dc73-135">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="1dc73-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1dc73-136">directeur</span><span class="sxs-lookup"><span data-stu-id="1dc73-136">Director</span></span></p></td>
<td><p><span data-ttu-id="1dc73-137">Communication SIP du serveur Edge au directeur et au serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1dc73-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc73-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="1dc73-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="1dc73-139">Indifférente</span><span class="sxs-lookup"><span data-stu-id="1dc73-139">Any</span></span></p></td>
<td><p><span data-ttu-id="1dc73-140">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="1dc73-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1dc73-141">Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClasAgent. exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="1dc73-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dc73-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="1dc73-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="1dc73-143">Indifférente</span><span class="sxs-lookup"><span data-stu-id="1dc73-143">Any</span></span></p></td>
<td><p><span data-ttu-id="1dc73-144">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="1dc73-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1dc73-145">Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClasAgent. exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="1dc73-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dc73-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="1dc73-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="1dc73-147">Indifférente</span><span class="sxs-lookup"><span data-stu-id="1dc73-147">Any</span></span></p></td>
<td><p><span data-ttu-id="1dc73-148">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="1dc73-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1dc73-149">Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClasAgent. exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="1dc73-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

