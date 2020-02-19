---
title: 'Lync Server 2013 : Résumé DNS-pool directeur mis à l’ampleur, équilibreur de charge matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 790b740e9f22c52a166759799fcb085dce453a25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="1fec8-102">Résumé DNS-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fec8-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fec8-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1fec8-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1fec8-104">Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge le directeur avec équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="1fec8-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="1fec8-105">Le rôle du directeur requiert des enregistrements DNS similaires comme serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="1fec8-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="1fec8-106">Le nombre d’enregistrements nécessaires est reflété dans les autres noms du sujet requis sur le certificat directeur.</span><span class="sxs-lookup"><span data-stu-id="1fec8-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="1fec8-107">Différent du serveur frontal, le pool directeur n’héberge pas les comptes d’utilisateur ou n’héberge pas les services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="1fec8-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="1fec8-108">Enregistrements DNS requis pour le pool directeur à l’aide d’un programme d’équilibrage de la charge matérielle et de l’équilibrage de la charge DNS</span><span class="sxs-lookup"><span data-stu-id="1fec8-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fec8-109">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="1fec8-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1fec8-110">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="1fec8-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="1fec8-111">Adresse IP/Nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="1fec8-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="1fec8-112">Mappe vers/Commentaires</span><span class="sxs-lookup"><span data-stu-id="1fec8-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fec8-113">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="1fec8-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1fec8-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1fec8-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1fec8-115">48000b</span><span class="sxs-lookup"><span data-stu-id="1fec8-115">Director</span></span></p></td>
<td><p><span data-ttu-id="1fec8-116">Enregistrement d’hôte directeur utilisé pour la communication de réplication et de serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="1fec8-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fec8-117">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="1fec8-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1fec8-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="1fec8-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="1fec8-119">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="1fec8-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1fec8-120">Enregistrement d’hôte pour le pool de directeurs à charge équilibrée DNS</span><span class="sxs-lookup"><span data-stu-id="1fec8-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fec8-121">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="1fec8-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1fec8-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fec8-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1fec8-123">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="1fec8-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1fec8-124">Protocole SIP (Session Initiation Protocol) entrant à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="1fec8-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fec8-125">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="1fec8-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1fec8-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fec8-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1fec8-127">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="1fec8-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1fec8-128">Services web de numérotation publiés avec charge matérielle équilibrée à partir d’un proxy inverse</span><span class="sxs-lookup"><span data-stu-id="1fec8-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fec8-129">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="1fec8-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1fec8-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fec8-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1fec8-131">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="1fec8-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1fec8-132">Services web de conférence publiés avec charge matérielle équilibrée à partir d’un proxy inverse</span><span class="sxs-lookup"><span data-stu-id="1fec8-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fec8-133">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="1fec8-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1fec8-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fec8-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1fec8-135">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="1fec8-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="1fec8-136">Services web externes de tickets web publiés et définis par le proxy inverse avec charge matérielle équilibrée pour le pool de directeurs</span><span class="sxs-lookup"><span data-stu-id="1fec8-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

