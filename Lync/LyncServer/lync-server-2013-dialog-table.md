---
title: 'Lync Server 2013 : boîte de dialogue'
description: 'Lync Server 2013 : boîte de dialogue.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ae93b8ca9f1146b7dc164803f27cbeeadc66777
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559720"
---
# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="09b57-103">Table Dialog dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09b57-103">Dialog table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09b57-104">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="09b57-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="09b57-105">La table Dialog est une table de prise en charge ; chaque enregistrement représente un dialogue SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="09b57-105">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b57-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="09b57-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="09b57-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="09b57-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="09b57-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="09b57-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="09b57-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="09b57-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b57-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="09b57-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="09b57-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="09b57-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="09b57-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="09b57-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="09b57-p101">Heure à laquelle l’agent QoE (Quality of Excellence) reçoit le premier rapport de l’appelant ou de l’appelé. Utilisé conjointement avec SessionSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="09b57-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b57-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="09b57-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="09b57-116">int</span><span class="sxs-lookup"><span data-stu-id="09b57-116">int</span></span></p></td>
<td><p><span data-ttu-id="09b57-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="09b57-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="09b57-118">Numéro de séquence pour différencier les sessions lorsqu’elles ont le même paramètre ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="09b57-118">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b57-119"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="09b57-119"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="09b57-120">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="09b57-120">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="09b57-121">ID du dialogue qui est unique à l’échelle globale.</span><span class="sxs-lookup"><span data-stu-id="09b57-121">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b57-122"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="09b57-122"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="09b57-123">int</span><span class="sxs-lookup"><span data-stu-id="09b57-123">int</span></span></p></td>
<td><p><span data-ttu-id="09b57-124">Index</span><span class="sxs-lookup"><span data-stu-id="09b57-124">index</span></span></p></td>
<td><p><span data-ttu-id="09b57-125">Somme de contrôle de l’ID du dialogue.</span><span class="sxs-lookup"><span data-stu-id="09b57-125">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

