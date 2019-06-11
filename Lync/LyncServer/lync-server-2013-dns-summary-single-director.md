---
title: 'Lync Server 2013 : Résumé des enregistrements DNS - Un directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca7fea825267dcdc5aa03a2e6c3c9fb3fc26a84b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="edc13-102">Résumé des enregistrements DNS - Un directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edc13-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edc13-103">_**Dernière modification de la rubrique:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="edc13-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="edc13-104">Le tableau suivant contient un résumé des enregistrements DNS requis pour la prise en charge du réalisateur unique.</span><span class="sxs-lookup"><span data-stu-id="edc13-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="edc13-105">Le rôle du directeur nécessite des enregistrements DNS similaires comme serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="edc13-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="edc13-106">Le nombre d’enregistrements nécessaires est reflété dans les autres noms d’objet requis sur le certificat de réalisateur.</span><span class="sxs-lookup"><span data-stu-id="edc13-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="edc13-107">Différent du serveur frontal, le directeur n’héberge pas les comptes d’utilisateurs ou n’héberge pas les services de mobilité.</span><span class="sxs-lookup"><span data-stu-id="edc13-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="edc13-108">Enregistrements DNS requis pour le directeur</span><span class="sxs-lookup"><span data-stu-id="edc13-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edc13-109">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="edc13-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="edc13-110">Nom de domaine complet/enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="edc13-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="edc13-111">IP address/FQDN</span><span class="sxs-lookup"><span data-stu-id="edc13-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="edc13-112">Cartes sur/Commentaires</span><span class="sxs-lookup"><span data-stu-id="edc13-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edc13-113">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="edc13-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="edc13-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="edc13-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="edc13-115">directeur</span><span class="sxs-lookup"><span data-stu-id="edc13-115">Director</span></span></p></td>
<td><p><span data-ttu-id="edc13-116">Enregistrement hôte de Director utilisé pour la réplication et le serveur vers serveur</span><span class="sxs-lookup"><span data-stu-id="edc13-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edc13-117">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="edc13-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="edc13-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edc13-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="edc13-119">directeur</span><span class="sxs-lookup"><span data-stu-id="edc13-119">Director</span></span></p></td>
<td><p><span data-ttu-id="edc13-120">Protocole SIP (Session Initiation Protocol) à partir de l’interface latérale interne du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="edc13-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edc13-121">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="edc13-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="edc13-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edc13-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="edc13-123">directeur</span><span class="sxs-lookup"><span data-stu-id="edc13-123">Director</span></span></p></td>
<td><p><span data-ttu-id="edc13-124">A publié les services Web de numérotation à partir du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="edc13-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edc13-125">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="edc13-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="edc13-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edc13-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="edc13-127">directeur</span><span class="sxs-lookup"><span data-stu-id="edc13-127">Director</span></span></p></td>
<td><p><span data-ttu-id="edc13-128">Publié les services Web à partir du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="edc13-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edc13-129">DNS interne/A</span><span class="sxs-lookup"><span data-stu-id="edc13-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="edc13-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="edc13-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="edc13-131">directeur</span><span class="sxs-lookup"><span data-stu-id="edc13-131">Director</span></span></p></td>
<td><p><span data-ttu-id="edc13-132">Publié et défini par les services Web externes du proxy inverse pour le directeur</span><span class="sxs-lookup"><span data-stu-id="edc13-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

