---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-directeur unique'
description: 'Lync Server 2013 : Résumé des enregistrements DNS-directeur unique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78ef19383df45644ad951ca5da69ef893b231980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553230"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="c9e9d-103">Résumé des enregistrements DNS-directeur unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9e9d-103">DNS summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9e9d-104">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c9e9d-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c9e9d-105">Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge le directeur unique.</span><span class="sxs-lookup"><span data-stu-id="c9e9d-105">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="c9e9d-106">Le rôle du directeur requiert des enregistrements DNS similaires comme serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c9e9d-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="c9e9d-107">Le nombre d’enregistrements nécessaires est reflété dans les autres noms du sujet requis sur le certificat directeur.</span><span class="sxs-lookup"><span data-stu-id="c9e9d-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="c9e9d-108">Différent du serveur frontal, le directeur n’héberge pas les comptes d’utilisateur ou n’héberge pas les services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="c9e9d-108">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="c9e9d-109">Enregistrements DNS requis pour le directeur</span><span class="sxs-lookup"><span data-stu-id="c9e9d-109">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9e9d-110">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="c9e9d-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="c9e9d-111">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="c9e9d-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="c9e9d-112">Adresse IP/Nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="c9e9d-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="c9e9d-113">Mappe vers/Commentaires</span><span class="sxs-lookup"><span data-stu-id="c9e9d-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9e9d-114">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="c9e9d-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c9e9d-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-116">Directeur</span><span class="sxs-lookup"><span data-stu-id="c9e9d-116">Director</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-117">Enregistrement d’hôte directeur utilisé pour la réplication et le serveur vers le serveur</span><span class="sxs-lookup"><span data-stu-id="c9e9d-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9e9d-118">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="c9e9d-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-119">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9e9d-119">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-120">Directeur</span><span class="sxs-lookup"><span data-stu-id="c9e9d-120">Director</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-121">Protocole SIP (Session Initiation Protocol) entrant à partir de l’interface Edge interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="c9e9d-121">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9e9d-122">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="c9e9d-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-123">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9e9d-123">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-124">Directeur</span><span class="sxs-lookup"><span data-stu-id="c9e9d-124">Director</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-125">Services web d’accès à distance publiés depuis le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="c9e9d-125">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9e9d-126">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="c9e9d-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-127">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9e9d-127">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-128">Directeur</span><span class="sxs-lookup"><span data-stu-id="c9e9d-128">Director</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-129">Services web de réunion publiés depuis le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="c9e9d-129">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9e9d-130">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="c9e9d-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-131">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9e9d-131">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-132">Directeur</span><span class="sxs-lookup"><span data-stu-id="c9e9d-132">Director</span></span></p></td>
<td><p><span data-ttu-id="c9e9d-133">Publié et défini par les services Web externes de ticket Web de proxy inverse pour le directeur</span><span class="sxs-lookup"><span data-stu-id="c9e9d-133">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

