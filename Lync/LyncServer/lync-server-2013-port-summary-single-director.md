---
title: 'Lync Server 2013 : Résumé des ports-directeur unique'
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
ms.openlocfilehash: 27095f154d4a79af949d3568bb444adfc83699c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="997ef-102">Résumé des ports-directeur unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="997ef-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="997ef-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="997ef-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="997ef-104">Les exigences de port de pare-feu pour un seul directeur consistent en des ports utilisés pour établir la communication avec le directeur depuis l’interface interne ou le réseau interne du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="997ef-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="997ef-105">Microsoft Lync Server 2013 attend par défaut que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts depuis le proxy inverse vers le directeur, ainsi que le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="997ef-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="997ef-106">En outre, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge vers le directeur et vers le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="997ef-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="997ef-107">Le protocole SIP utilise SIP/MTLS/TCP 5061 à partir du serveur Edge vers le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="997ef-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="997ef-108">Une règle qui autorise la communication SIP/MTLS/TCP 5061 depuis le directeur, le pool frontal et le serveur frontal vers l’interface interne du serveur Edge doit également être créée.</span><span class="sxs-lookup"><span data-stu-id="997ef-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="997ef-109">Ports et protocoles de directeur unique pour les définitions de pare-feu</span><span class="sxs-lookup"><span data-stu-id="997ef-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="997ef-110">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="997ef-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="997ef-111">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="997ef-111">Source IP address</span></span></th>
<th><span data-ttu-id="997ef-112">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="997ef-112">Destination IP address</span></span></th>
<th><span data-ttu-id="997ef-113">Notes</span><span class="sxs-lookup"><span data-stu-id="997ef-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="997ef-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="997ef-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="997ef-115">Interface interne de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="997ef-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="997ef-116">48000b</span><span class="sxs-lookup"><span data-stu-id="997ef-116">Director</span></span></p></td>
<td><p><span data-ttu-id="997ef-117">Initialement reçus par le côté externe du proxy inverse, la communication est envoyée aux services Web du directeur et du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="997ef-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ef-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="997ef-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="997ef-119">Interface interne de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="997ef-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="997ef-120">48000b</span><span class="sxs-lookup"><span data-stu-id="997ef-120">Director</span></span></p></td>
<td><p><span data-ttu-id="997ef-121">Initialement reçus par le côté externe du proxy inverse, la communication est envoyée aux services Web du directeur et du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="997ef-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="997ef-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="997ef-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="997ef-123">48000b</span><span class="sxs-lookup"><span data-stu-id="997ef-123">Director</span></span></p></td>
<td><p><span data-ttu-id="997ef-124">Serveur frontal ou pool frontal</span><span class="sxs-lookup"><span data-stu-id="997ef-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="997ef-125">Communication entre le directeur et le serveur frontal</span><span class="sxs-lookup"><span data-stu-id="997ef-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ef-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="997ef-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="997ef-127">Clients internes</span><span class="sxs-lookup"><span data-stu-id="997ef-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="997ef-128">Services Web Director</span><span class="sxs-lookup"><span data-stu-id="997ef-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="997ef-129">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="997ef-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="997ef-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="997ef-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="997ef-131">Clients internes</span><span class="sxs-lookup"><span data-stu-id="997ef-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="997ef-132">Services Web Director</span><span class="sxs-lookup"><span data-stu-id="997ef-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="997ef-133">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="997ef-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ef-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="997ef-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="997ef-135">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="997ef-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="997ef-136">48000b</span><span class="sxs-lookup"><span data-stu-id="997ef-136">Director</span></span></p></td>
<td><p><span data-ttu-id="997ef-137">Communication SIP entre le serveur Edge et le directeur, ainsi que le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="997ef-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="997ef-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="997ef-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="997ef-139">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="997ef-139">Any</span></span></p></td>
<td><p><span data-ttu-id="997ef-140">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="997ef-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="997ef-141">Commandes et collection de journaux du service de journalisation centralisée (ClsController. exe) ou de l’agent (ClasAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="997ef-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997ef-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="997ef-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="997ef-143">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="997ef-143">Any</span></span></p></td>
<td><p><span data-ttu-id="997ef-144">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="997ef-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="997ef-145">Commandes et collection de journaux du service de journalisation centralisée (ClsController. exe) ou de l’agent (ClasAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="997ef-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="997ef-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="997ef-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="997ef-147">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="997ef-147">Any</span></span></p></td>
<td><p><span data-ttu-id="997ef-148">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="997ef-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="997ef-149">Commandes et collection de journaux du service de journalisation centralisée (ClsController. exe) ou de l’agent (ClasAgent. exe)</span><span class="sxs-lookup"><span data-stu-id="997ef-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

