---
title: 'Lync Server 2013 : Résumé DNS - Pool directeur mis à l’échelle, équilibreur de charge matérielle'
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
ms.openlocfilehash: 891b69339416c81d81e72e43edf5f09bbf9da3e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="4d487-102">Résumé DNS - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d487-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d487-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="4d487-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="4d487-104">Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge le directeur d’équilibrage de charge matérielle.</span><span class="sxs-lookup"><span data-stu-id="4d487-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="4d487-105">Le rôle du directeur nécessite des enregistrements DNS similaires comme serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="4d487-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="4d487-106">Le nombre d’enregistrements nécessaires est reflété dans les autres noms d’objet requis sur le certificat de réalisateur.</span><span class="sxs-lookup"><span data-stu-id="4d487-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="4d487-107">Différent du serveur frontal, le pool de directeurs n’héberge pas les comptes d’utilisateurs ou n’héberge pas les services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="4d487-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="4d487-108">Enregistrements DNS requis pour le pool de directeurs à l’aide d’un équilibreur de charge matériel et de l’équilibrage de charge DNS</span><span class="sxs-lookup"><span data-stu-id="4d487-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d487-109">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="4d487-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4d487-110">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="4d487-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="4d487-111">IP address/FQDN</span><span class="sxs-lookup"><span data-stu-id="4d487-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="4d487-112">Cartes sur/Commentaires</span><span class="sxs-lookup"><span data-stu-id="4d487-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d487-113">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="4d487-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d487-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4d487-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4d487-115">directeur</span><span class="sxs-lookup"><span data-stu-id="4d487-115">Director</span></span></p></td>
<td><p><span data-ttu-id="4d487-116">Enregistrement hôte de Director utilisé pour les communications de réplication et de serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="4d487-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d487-117">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="4d487-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d487-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4d487-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4d487-119">HLB VIP du pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="4d487-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="4d487-120">Enregistrement hôte pour le pool de directeurs d’équilibrage de charge DNS</span><span class="sxs-lookup"><span data-stu-id="4d487-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d487-121">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="4d487-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d487-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d487-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d487-123">HLB VIP du pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="4d487-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="4d487-124">Protocole SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="4d487-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d487-125">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="4d487-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d487-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d487-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d487-127">HLB VIP du pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="4d487-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="4d487-128">Équilibrage de charge matérielle publié services Web de numérotation à partir du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="4d487-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d487-129">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="4d487-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d487-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d487-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d487-131">HLB VIP du pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="4d487-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="4d487-132">Équilibrage de charge matérielle publié avec les services Web à partir du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="4d487-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d487-133">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="4d487-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4d487-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4d487-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4d487-135">HLB VIP du pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="4d487-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="4d487-136">Équilibrage de la charge matérielle publié et définie par les services Web externes du ticket de proxy inverse pour le pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="4d487-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

