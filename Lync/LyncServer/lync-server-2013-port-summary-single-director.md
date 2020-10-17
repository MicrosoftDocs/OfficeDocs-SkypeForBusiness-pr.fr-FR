---
title: 'Lync Server 2013 : Résumé des ports-directeur unique'
description: 'Lync Server 2013 : Résumé des ports-directeur unique.'
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
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566370"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="677ce-103">Résumé des ports-directeur unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="677ce-103">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="677ce-104">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="677ce-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="677ce-105">Les exigences de port de pare-feu pour un seul directeur consistent en des ports utilisés pour établir la communication avec le directeur depuis l’interface interne ou le réseau interne du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="677ce-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="677ce-106">Microsoft Lync Server 2013 attend par défaut que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts depuis le proxy inverse vers le directeur, ainsi que le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="677ce-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="677ce-107">En outre, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge vers le directeur et vers le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="677ce-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="677ce-108">Le protocole SIP utilise SIP/MTLS/TCP 5061 à partir du serveur Edge vers le pool frontal et le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="677ce-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="677ce-109">Une règle qui autorise la communication SIP/MTLS/TCP 5061 depuis le directeur, le pool frontal et le serveur frontal vers l’interface interne du serveur Edge doit également être créée.</span><span class="sxs-lookup"><span data-stu-id="677ce-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="677ce-110">Ports et protocoles de directeur unique pour les définitions de pare-feu</span><span class="sxs-lookup"><span data-stu-id="677ce-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="677ce-111">Rôle/Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="677ce-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="677ce-112">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="677ce-112">Source IP address</span></span></th>
<th><span data-ttu-id="677ce-113">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="677ce-113">Destination IP address</span></span></th>
<th><span data-ttu-id="677ce-114">Notes</span><span class="sxs-lookup"><span data-stu-id="677ce-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="677ce-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="677ce-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="677ce-116">Interface interne de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="677ce-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="677ce-117">Directeur</span><span class="sxs-lookup"><span data-stu-id="677ce-117">Director</span></span></p></td>
<td><p><span data-ttu-id="677ce-118">Initialement reçus par le côté externe du proxy inverse, la communication est envoyée aux services Web du directeur et du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="677ce-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="677ce-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="677ce-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="677ce-120">Interface interne de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="677ce-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="677ce-121">Directeur</span><span class="sxs-lookup"><span data-stu-id="677ce-121">Director</span></span></p></td>
<td><p><span data-ttu-id="677ce-122">Initialement reçus par le côté externe du proxy inverse, la communication est envoyée aux services Web du directeur et du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="677ce-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="677ce-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="677ce-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="677ce-124">Directeur</span><span class="sxs-lookup"><span data-stu-id="677ce-124">Director</span></span></p></td>
<td><p><span data-ttu-id="677ce-125">Serveur frontal ou pool frontal</span><span class="sxs-lookup"><span data-stu-id="677ce-125">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="677ce-126">Communication entre le directeur et le serveur frontal</span><span class="sxs-lookup"><span data-stu-id="677ce-126">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="677ce-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="677ce-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="677ce-128">Clients internes</span><span class="sxs-lookup"><span data-stu-id="677ce-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="677ce-129">Services Web Director</span><span class="sxs-lookup"><span data-stu-id="677ce-129">Director web services</span></span></p></td>
<td><p><span data-ttu-id="677ce-130">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="677ce-130">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="677ce-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="677ce-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="677ce-132">Clients internes</span><span class="sxs-lookup"><span data-stu-id="677ce-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="677ce-133">Services Web Director</span><span class="sxs-lookup"><span data-stu-id="677ce-133">Director web services</span></span></p></td>
<td><p><span data-ttu-id="677ce-134">Le directeur fournit des services Web aux clients internes et externes.</span><span class="sxs-lookup"><span data-stu-id="677ce-134">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="677ce-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="677ce-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="677ce-136">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="677ce-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="677ce-137">Directeur</span><span class="sxs-lookup"><span data-stu-id="677ce-137">Director</span></span></p></td>
<td><p><span data-ttu-id="677ce-138">Communication SIP entre le serveur Edge et le directeur, ainsi que le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="677ce-138">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="677ce-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="677ce-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="677ce-140">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="677ce-140">Any</span></span></p></td>
<td><p><span data-ttu-id="677ce-141">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="677ce-141">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="677ce-142">Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClasAgent.exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="677ce-142">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="677ce-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="677ce-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="677ce-144">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="677ce-144">Any</span></span></p></td>
<td><p><span data-ttu-id="677ce-145">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="677ce-145">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="677ce-146">Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClasAgent.exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="677ce-146">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="677ce-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="677ce-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="677ce-148">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="677ce-148">Any</span></span></p></td>
<td><p><span data-ttu-id="677ce-149">Interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="677ce-149">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="677ce-150">Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClasAgent.exe) et collection de journaux</span><span class="sxs-lookup"><span data-stu-id="677ce-150">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

