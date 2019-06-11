---
title: 'Lync Server 2013 : Table Dialog'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d47744cf17d3459c16e382c3551b427aa45b5ce6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="9dc21-102">Table Dialog dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dc21-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dc21-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9dc21-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9dc21-104">Le tableau de boîte de dialogue est une table de prise en charge. chaque enregistrement représente une boîte de dialogue SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="9dc21-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dc21-105"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="9dc21-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9dc21-106"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="9dc21-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9dc21-107"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="9dc21-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9dc21-108"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="9dc21-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dc21-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="9dc21-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9dc21-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="9dc21-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9dc21-111">Principal</span><span class="sxs-lookup"><span data-stu-id="9dc21-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="9dc21-112">Temps pendant lequel l’agent de qualité d’excellence reçoit le premier rapport de l’appelant ou du destinataire.</span><span class="sxs-lookup"><span data-stu-id="9dc21-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="9dc21-113">Utilisé conjointement avec SessionSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="9dc21-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dc21-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9dc21-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9dc21-115">int</span><span class="sxs-lookup"><span data-stu-id="9dc21-115">int</span></span></p></td>
<td><p><span data-ttu-id="9dc21-116">Principal</span><span class="sxs-lookup"><span data-stu-id="9dc21-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="9dc21-117">Numéro séquentiel pour différencier les sessions lorsqu’elles ont la même ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="9dc21-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dc21-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="9dc21-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="9dc21-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9dc21-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9dc21-120">ID de boîte de dialogue globalement unique.</span><span class="sxs-lookup"><span data-stu-id="9dc21-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dc21-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="9dc21-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="9dc21-122">int</span><span class="sxs-lookup"><span data-stu-id="9dc21-122">int</span></span></p></td>
<td><p><span data-ttu-id="9dc21-123">index</span><span class="sxs-lookup"><span data-stu-id="9dc21-123">index</span></span></p></td>
<td><p><span data-ttu-id="9dc21-124">Checksum de l’ID de boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9dc21-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

