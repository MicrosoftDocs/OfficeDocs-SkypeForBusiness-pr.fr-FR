---
title: 'Lync Server 2013 : Table Dialog'
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
ms.openlocfilehash: 2f0ef564ad1224ba9970b7cceb5db60e0eb344da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="9be3b-102">Table Dialog dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9be3b-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9be3b-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9be3b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9be3b-104">Le tableau de boîte de dialogue est une table de prise en charge. chaque enregistrement représente une boîte de dialogue SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="9be3b-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9be3b-105"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="9be3b-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9be3b-106"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="9be3b-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9be3b-107"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="9be3b-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9be3b-108"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="9be3b-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9be3b-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="9be3b-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9be3b-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="9be3b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9be3b-111">Principal</span><span class="sxs-lookup"><span data-stu-id="9be3b-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="9be3b-112">Temps pendant lequel l’agent de qualité d’excellence reçoit le premier rapport de l’appelant ou du destinataire.</span><span class="sxs-lookup"><span data-stu-id="9be3b-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="9be3b-113">Utilisé conjointement avec SessionSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="9be3b-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be3b-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9be3b-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9be3b-115">int</span><span class="sxs-lookup"><span data-stu-id="9be3b-115">int</span></span></p></td>
<td><p><span data-ttu-id="9be3b-116">Principal</span><span class="sxs-lookup"><span data-stu-id="9be3b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="9be3b-117">Numéro séquentiel pour différencier les sessions lorsqu’elles ont la même ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="9be3b-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9be3b-118"><strong>DialogID</strong></span><span class="sxs-lookup"><span data-stu-id="9be3b-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="9be3b-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9be3b-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9be3b-120">ID de boîte de dialogue globalement unique.</span><span class="sxs-lookup"><span data-stu-id="9be3b-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be3b-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="9be3b-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="9be3b-122">int</span><span class="sxs-lookup"><span data-stu-id="9be3b-122">int</span></span></p></td>
<td><p><span data-ttu-id="9be3b-123">index</span><span class="sxs-lookup"><span data-stu-id="9be3b-123">index</span></span></p></td>
<td><p><span data-ttu-id="9be3b-124">Checksum de l’ID de boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="9be3b-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

