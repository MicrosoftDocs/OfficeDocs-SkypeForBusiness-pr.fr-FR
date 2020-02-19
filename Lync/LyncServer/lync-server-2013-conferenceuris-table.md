---
title: 'Lync Server 2013 : table ConferenceUris'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2215eb030f237e8d238310e6f6b7fe223088c02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="3c499-102">Table ConferenceUris dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c499-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c499-103">_**Dernière modification de la rubrique :** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="3c499-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="3c499-p101">La table ConferenceUris est une table de prise en charge qui stocke une liste des différentes URI de conférence qui ont participé aux sessions de conférence enregistrées dans la base de données. Chaque enregistrement dans le tableau représente une URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="3c499-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c499-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="3c499-106">Column</span></span></th>
<th><span data-ttu-id="3c499-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="3c499-107">Data Type</span></span></th>
<th><span data-ttu-id="3c499-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="3c499-108">Key/Index</span></span></th>
<th><span data-ttu-id="3c499-109">Détails</span><span class="sxs-lookup"><span data-stu-id="3c499-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c499-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="3c499-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="3c499-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="3c499-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="3c499-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="3c499-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3c499-113">Horodatage pour utilisation interne.</span><span class="sxs-lookup"><span data-stu-id="3c499-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c499-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="3c499-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c499-115">int</span><span class="sxs-lookup"><span data-stu-id="3c499-115">int</span></span></p></td>
<td><p><span data-ttu-id="3c499-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="3c499-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="3c499-117">Numéro unique identifiant cette URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="3c499-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c499-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="3c499-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3c499-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3c499-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c499-120">URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="3c499-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c499-121"><strong>Somme de contrôle</strong></span><span class="sxs-lookup"><span data-stu-id="3c499-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="3c499-122">int</span><span class="sxs-lookup"><span data-stu-id="3c499-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c499-p102">Checksum de ConferenceUri. Sert à augmenter la vitesse des recherches dans les bases de données.</span><span class="sxs-lookup"><span data-stu-id="3c499-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c499-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="3c499-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c499-126">int</span><span class="sxs-lookup"><span data-stu-id="3c499-126">int</span></span></p></td>
<td><p><span data-ttu-id="3c499-127">Etranger</span><span class="sxs-lookup"><span data-stu-id="3c499-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c499-128">Type d’URI, tel que conf:chat pour une conférence de messagerie instantanée ou conf:audio-video pour une conférence audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="3c499-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="3c499-129">Pour plus d’informations, reportez-vous à la table <a href="lync-server-2013-uritypes-table.md">UriTypes dans la table Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="3c499-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

