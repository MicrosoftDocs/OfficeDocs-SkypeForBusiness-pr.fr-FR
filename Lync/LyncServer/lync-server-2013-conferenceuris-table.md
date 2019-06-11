---
title: 'Lync Server 2013 : Table ConferenceUris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1ab44b564d649b6c8fb812077645c6dc13093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="f3f42-102">Table ConferenceUris dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3f42-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3f42-103">_**Dernière modification de la rubrique:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="f3f42-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="f3f42-104">La table ConfereneUris est une table qui contient une liste des différents URI de conférence ayant participé à des sessions de conférence enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="f3f42-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="f3f42-105">Chaque enregistrement de la table représente un URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="f3f42-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3f42-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="f3f42-106">Column</span></span></th>
<th><span data-ttu-id="f3f42-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="f3f42-107">Data Type</span></span></th>
<th><span data-ttu-id="f3f42-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="f3f42-108">Key/Index</span></span></th>
<th><span data-ttu-id="f3f42-109">Détails</span><span class="sxs-lookup"><span data-stu-id="f3f42-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3f42-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="f3f42-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f3f42-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f3f42-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f3f42-112">Principal</span><span class="sxs-lookup"><span data-stu-id="f3f42-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f3f42-113">Date et heure d’utilisation internes.</span><span class="sxs-lookup"><span data-stu-id="f3f42-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3f42-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="f3f42-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="f3f42-115">int</span><span class="sxs-lookup"><span data-stu-id="f3f42-115">int</span></span></p></td>
<td><p><span data-ttu-id="f3f42-116">Principal</span><span class="sxs-lookup"><span data-stu-id="f3f42-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f3f42-117">Numéro unique identifiant cet URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="f3f42-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3f42-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="f3f42-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f3f42-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f3f42-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f3f42-120">URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="f3f42-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3f42-121"><strong>1018</strong></span><span class="sxs-lookup"><span data-stu-id="f3f42-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="f3f42-122">int</span><span class="sxs-lookup"><span data-stu-id="f3f42-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f3f42-123">Checksum de ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="f3f42-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="f3f42-124">Permet d’augmenter la vitesse de recherche de la base de données.</span><span class="sxs-lookup"><span data-stu-id="f3f42-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3f42-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="f3f42-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="f3f42-126">int</span><span class="sxs-lookup"><span data-stu-id="f3f42-126">int</span></span></p></td>
<td><p><span data-ttu-id="f3f42-127">Externes</span><span class="sxs-lookup"><span data-stu-id="f3f42-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f3f42-128">Type d’URI (par exemple, conf: chat pour une conférence par messagerie instantanée, ou conf: audio-vidéo pour les conférences audio/vidéo).</span><span class="sxs-lookup"><span data-stu-id="f3f42-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="f3f42-129">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans la table Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="f3f42-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

