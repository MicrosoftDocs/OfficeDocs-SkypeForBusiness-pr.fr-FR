---
title: 'Lync Server 2013 : tblComplianceFanout'
description: 'Lync Server 2013 : tblComplianceFanout.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cb94fff579c504598f027c8c68c7dde00a5a516
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568570"
---
# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="27e36-103">tblComplianceFanout dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27e36-103">tblComplianceFanout in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27e36-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="27e36-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="27e36-105">La table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="27e36-105">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="27e36-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="27e36-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e36-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="27e36-107">Column</span></span></th>
<th><span data-ttu-id="27e36-108">Type</span><span class="sxs-lookup"><span data-stu-id="27e36-108">Type</span></span></th>
<th><span data-ttu-id="27e36-109">Description</span><span class="sxs-lookup"><span data-stu-id="27e36-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e36-110">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="27e36-110">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="27e36-111">int</span><span class="sxs-lookup"><span data-stu-id="27e36-111">int</span></span></p></td>
<td><p><span data-ttu-id="27e36-112">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="27e36-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27e36-113">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="27e36-113">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="27e36-114">int</span><span class="sxs-lookup"><span data-stu-id="27e36-114">int</span></span></p></td>
<td><p><span data-ttu-id="27e36-115">Identité du serveur (correspondant à la table tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="27e36-115">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="27e36-116">Clé</span><span class="sxs-lookup"><span data-stu-id="27e36-116">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27e36-117">Colonne</span><span class="sxs-lookup"><span data-stu-id="27e36-117">Column</span></span></th>
<th><span data-ttu-id="27e36-118">Description</span><span class="sxs-lookup"><span data-stu-id="27e36-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27e36-119">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="27e36-119">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="27e36-120">Clé étrangère avec recherche dans la table tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="27e36-120">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

