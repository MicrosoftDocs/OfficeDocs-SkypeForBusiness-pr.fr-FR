---
title: 'Lync Server 2013 : tblComplianceFanout'
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
ms.openlocfilehash: 6bb9ab36bbbec83ea706231d2a3fa6dd890fb1e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="42ed1-102">tblComplianceFanout dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42ed1-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42ed1-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="42ed1-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="42ed1-104">La table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="42ed1-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="42ed1-105">Columns</span><span class="sxs-lookup"><span data-stu-id="42ed1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42ed1-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="42ed1-106">Column</span></span></th>
<th><span data-ttu-id="42ed1-107">Type</span><span class="sxs-lookup"><span data-stu-id="42ed1-107">Type</span></span></th>
<th><span data-ttu-id="42ed1-108">Description</span><span class="sxs-lookup"><span data-stu-id="42ed1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42ed1-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="42ed1-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="42ed1-110">int</span><span class="sxs-lookup"><span data-stu-id="42ed1-110">int</span></span></p></td>
<td><p><span data-ttu-id="42ed1-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="42ed1-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42ed1-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="42ed1-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="42ed1-113">int</span><span class="sxs-lookup"><span data-stu-id="42ed1-113">int</span></span></p></td>
<td><p><span data-ttu-id="42ed1-114">Identité du serveur (correspondant à la table tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="42ed1-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="42ed1-115">Clé</span><span class="sxs-lookup"><span data-stu-id="42ed1-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42ed1-116">Colonne</span><span class="sxs-lookup"><span data-stu-id="42ed1-116">Column</span></span></th>
<th><span data-ttu-id="42ed1-117">Description</span><span class="sxs-lookup"><span data-stu-id="42ed1-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42ed1-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="42ed1-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="42ed1-119">Clé étrangère avec recherche dans la table tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="42ed1-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

