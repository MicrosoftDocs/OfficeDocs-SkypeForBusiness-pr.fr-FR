---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-directeur unique'
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
ms.openlocfilehash: 76fe7663e0af8eeeb049ca80f1dd92a7cc882b98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="b9802-102">Résumé des enregistrements DNS-directeur unique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9802-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9802-103">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b9802-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b9802-104">Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge le directeur unique.</span><span class="sxs-lookup"><span data-stu-id="b9802-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="b9802-105">Le rôle du directeur requiert des enregistrements DNS similaires comme serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b9802-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="b9802-106">Le nombre d’enregistrements nécessaires est reflété dans les autres noms du sujet requis sur le certificat directeur.</span><span class="sxs-lookup"><span data-stu-id="b9802-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="b9802-107">Différent du serveur frontal, le directeur n’héberge pas les comptes d’utilisateur ou n’héberge pas les services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="b9802-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="b9802-108">Enregistrements DNS requis pour le directeur</span><span class="sxs-lookup"><span data-stu-id="b9802-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9802-109">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="b9802-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b9802-110">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="b9802-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="b9802-111">Adresse IP/Nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="b9802-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="b9802-112">Mappe vers/Commentaires</span><span class="sxs-lookup"><span data-stu-id="b9802-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9802-113">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="b9802-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b9802-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b9802-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b9802-115">48000b</span><span class="sxs-lookup"><span data-stu-id="b9802-115">Director</span></span></p></td>
<td><p><span data-ttu-id="b9802-116">Enregistrement d’hôte directeur utilisé pour la réplication et le serveur vers le serveur</span><span class="sxs-lookup"><span data-stu-id="b9802-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9802-117">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="b9802-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b9802-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9802-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b9802-119">48000b</span><span class="sxs-lookup"><span data-stu-id="b9802-119">Director</span></span></p></td>
<td><p><span data-ttu-id="b9802-120">Protocole SIP (Session Initiation Protocol) entrant à partir de l’interface Edge interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="b9802-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9802-121">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="b9802-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b9802-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9802-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b9802-123">48000b</span><span class="sxs-lookup"><span data-stu-id="b9802-123">Director</span></span></p></td>
<td><p><span data-ttu-id="b9802-124">Services web d’accès à distance publiés depuis le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="b9802-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9802-125">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="b9802-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b9802-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9802-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b9802-127">48000b</span><span class="sxs-lookup"><span data-stu-id="b9802-127">Director</span></span></p></td>
<td><p><span data-ttu-id="b9802-128">Services web de réunion publiés depuis le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="b9802-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9802-129">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="b9802-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b9802-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b9802-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b9802-131">48000b</span><span class="sxs-lookup"><span data-stu-id="b9802-131">Director</span></span></p></td>
<td><p><span data-ttu-id="b9802-132">Publié et défini par les services Web externes de ticket Web de proxy inverse pour le directeur</span><span class="sxs-lookup"><span data-stu-id="b9802-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

