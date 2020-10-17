---
title: 'Lync Server 2013 : Résumé DNS-pool directeur mis à l’ampleur, équilibreur de charge matérielle'
description: 'Lync Server 2013 : Résumé DNS-pool directeur mis à l’ampleur, équilibreur de charge matérielle.'
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
ms.openlocfilehash: 7198e6a97feed8ce70cb16753ad1f21d58ef246c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555880"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="3a4f9-103">Résumé DNS-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a4f9-103">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a4f9-104">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="3a4f9-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="3a4f9-105">Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge le directeur avec équilibrage de la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-105">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="3a4f9-106">Le rôle du directeur requiert des enregistrements DNS similaires comme serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="3a4f9-107">Le nombre d’enregistrements nécessaires est reflété dans les autres noms du sujet requis sur le certificat directeur.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="3a4f9-108">Différent du serveur frontal, le pool directeur n’héberge pas les comptes d’utilisateur ou n’héberge pas les services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="3a4f9-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="3a4f9-109">Enregistrements DNS requis pour le pool directeur à l’aide d’un programme d’équilibrage de la charge matérielle et de l’équilibrage de la charge DNS</span><span class="sxs-lookup"><span data-stu-id="3a4f9-109">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a4f9-110">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="3a4f9-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="3a4f9-111">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="3a4f9-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="3a4f9-112">Adresse IP/Nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="3a4f9-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="3a4f9-113">Mappe vers/Commentaires</span><span class="sxs-lookup"><span data-stu-id="3a4f9-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a4f9-114">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="3a4f9-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="3a4f9-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-116">Directeur</span><span class="sxs-lookup"><span data-stu-id="3a4f9-116">Director</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-117">Enregistrement d’hôte directeur utilisé pour la communication de réplication et de serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="3a4f9-117">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a4f9-118">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="3a4f9-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="3a4f9-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-120">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="3a4f9-120">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-121">Enregistrement d’hôte pour le pool de directeurs à charge équilibrée DNS</span><span class="sxs-lookup"><span data-stu-id="3a4f9-121">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a4f9-122">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="3a4f9-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a4f9-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-124">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="3a4f9-124">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-125">Protocole SIP (Session Initiation Protocol) entrant à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="3a4f9-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a4f9-126">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="3a4f9-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a4f9-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-128">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="3a4f9-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-129">Services web de numérotation publiés avec charge matérielle équilibrée à partir d’un proxy inverse</span><span class="sxs-lookup"><span data-stu-id="3a4f9-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a4f9-130">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="3a4f9-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a4f9-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-132">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="3a4f9-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-133">Services web de conférence publiés avec charge matérielle équilibrée à partir d’un proxy inverse</span><span class="sxs-lookup"><span data-stu-id="3a4f9-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a4f9-134">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="3a4f9-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a4f9-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-136">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="3a4f9-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="3a4f9-137">Services web externes de tickets web publiés et définis par le proxy inverse avec charge matérielle équilibrée pour le pool de directeurs</span><span class="sxs-lookup"><span data-stu-id="3a4f9-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

