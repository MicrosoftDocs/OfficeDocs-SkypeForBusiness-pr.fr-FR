---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-équilibrage de charge DNS et charge matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11128cb1989bfc2863fe52fe27d0c86eb4b468a9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="37a05-102">Résumé des enregistrements DNS-charge DNS et charge matérielle équilibrée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37a05-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37a05-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="37a05-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="37a05-104">Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge le directeur de charge DNS et le directeur équilibré par la charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="37a05-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="37a05-105">Le rôle du directeur requiert des enregistrements DNS similaires comme serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="37a05-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="37a05-106">Le nombre d’enregistrements nécessaires est reflété dans les autres noms du sujet requis sur le certificat directeur.</span><span class="sxs-lookup"><span data-stu-id="37a05-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="37a05-107">Différent du serveur frontal, le pool directeur n’héberge pas les comptes d’utilisateur ou n’héberge pas les services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="37a05-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="37a05-108">Enregistrements DNS nécessaires pour le pool de directeurs en utilisant l’équilibrage de la charge DNS et le programme d’équilibrage de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="37a05-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37a05-109">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="37a05-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="37a05-110">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="37a05-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="37a05-111">Adresse IP/Nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="37a05-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="37a05-112">Mappe vers/Commentaires</span><span class="sxs-lookup"><span data-stu-id="37a05-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37a05-113">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="37a05-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="37a05-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="37a05-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="37a05-115">48000b</span><span class="sxs-lookup"><span data-stu-id="37a05-115">Director</span></span></p></td>
<td><p><span data-ttu-id="37a05-116">Enregistrement d’hôte directeur utilisé pour la réplication et le serveur vers le serveur</span><span class="sxs-lookup"><span data-stu-id="37a05-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37a05-117">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="37a05-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="37a05-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="37a05-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="37a05-119">pool directeur</span><span class="sxs-lookup"><span data-stu-id="37a05-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="37a05-120">Enregistrement d’hôte pour le pool directeur à charge DNS équilibrée pour le serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="37a05-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37a05-121">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="37a05-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="37a05-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a05-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="37a05-123">pool directeur</span><span class="sxs-lookup"><span data-stu-id="37a05-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="37a05-124">Protocole SIP (Session Initiation Protocol) entrant à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="37a05-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37a05-125">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="37a05-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="37a05-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a05-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="37a05-127">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="37a05-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="37a05-128">Services web de numérotation publiés avec charge matérielle équilibrée à partir d’un proxy inverse</span><span class="sxs-lookup"><span data-stu-id="37a05-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37a05-129">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="37a05-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="37a05-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a05-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="37a05-131">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="37a05-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="37a05-132">Services web de conférence publiés avec charge matérielle équilibrée à partir d’un proxy inverse</span><span class="sxs-lookup"><span data-stu-id="37a05-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37a05-133">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="37a05-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="37a05-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a05-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="37a05-135">Pool directeur charge matérielle VIP</span><span class="sxs-lookup"><span data-stu-id="37a05-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="37a05-136">Services web externes de tickets web publiés et définis par le proxy inverse avec charge matérielle équilibrée pour le pool de directeurs</span><span class="sxs-lookup"><span data-stu-id="37a05-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

