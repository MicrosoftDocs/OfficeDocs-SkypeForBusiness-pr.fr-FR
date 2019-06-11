---
title: 'Lync Server 2013 : Résumé des enregistrements DNS - Équilibrage de charge DNS et matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceccb52a8ef9fae810821ffe6b52b763dd8904c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="f02f1-102">Résumé des enregistrements DNS - Équilibrage de charge DNS et matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f02f1-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f02f1-103">_**Dernière modification de la rubrique:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f02f1-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f02f1-104">Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge le système de répartition de charge DNS et le directeur équilibré de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="f02f1-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="f02f1-105">Le rôle du directeur nécessite des enregistrements DNS similaires comme serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="f02f1-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="f02f1-106">Le nombre d’enregistrements nécessaires est reflété dans les autres noms d’objet requis sur le certificat de réalisateur.</span><span class="sxs-lookup"><span data-stu-id="f02f1-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="f02f1-107">Différent du serveur frontal, le pool de directeurs n’héberge pas les comptes d’utilisateurs ou n’héberge pas les services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="f02f1-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="f02f1-108">Enregistrements DNS requis pour le pool de directeurs à l’aide de l’équilibrage de charge DNS et de l’équilibrage de charge matérielle</span><span class="sxs-lookup"><span data-stu-id="f02f1-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f02f1-109">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="f02f1-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f02f1-110">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="f02f1-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="f02f1-111">IP address/FQDN</span><span class="sxs-lookup"><span data-stu-id="f02f1-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="f02f1-112">Cartes sur/Commentaires</span><span class="sxs-lookup"><span data-stu-id="f02f1-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f02f1-113">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="f02f1-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f02f1-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f02f1-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f02f1-115">directeur</span><span class="sxs-lookup"><span data-stu-id="f02f1-115">Director</span></span></p></td>
<td><p><span data-ttu-id="f02f1-116">Enregistrement hôte de Director utilisé pour la réplication et le serveur vers serveur</span><span class="sxs-lookup"><span data-stu-id="f02f1-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f02f1-117">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="f02f1-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f02f1-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f02f1-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f02f1-119">pool de directeurs</span><span class="sxs-lookup"><span data-stu-id="f02f1-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="f02f1-120">Enregistrement hôte du pool de directeurs d’équilibrage de charge DNS pour serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="f02f1-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f02f1-121">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="f02f1-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f02f1-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f02f1-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f02f1-123">pool de directeurs</span><span class="sxs-lookup"><span data-stu-id="f02f1-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="f02f1-124">Protocole SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="f02f1-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f02f1-125">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="f02f1-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f02f1-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f02f1-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f02f1-127">HLB VIP du pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="f02f1-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f02f1-128">Équilibrage de charge matérielle publié services Web de numérotation à partir du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="f02f1-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f02f1-129">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="f02f1-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f02f1-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f02f1-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f02f1-131">HLB VIP du pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="f02f1-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f02f1-132">Équilibrage de charge matérielle publié avec les services Web à partir du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="f02f1-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f02f1-133">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="f02f1-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f02f1-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f02f1-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f02f1-135">HLB VIP du pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="f02f1-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f02f1-136">Équilibrage de la charge matérielle publié et définie par les services Web externes du ticket de proxy inverse pour le pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="f02f1-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

