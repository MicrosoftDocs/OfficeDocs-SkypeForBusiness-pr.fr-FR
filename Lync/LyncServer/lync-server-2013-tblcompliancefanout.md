---
title: 'Lync Server 2013 : tblComplianceFanout'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6edae4c6e37f5abb6714e7c6863c80b7a6e7756b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="2b746-102">tblComplianceFanout dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b746-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b746-103">_**Dernière modification de la rubrique:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2b746-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2b746-104">tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="2b746-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="2b746-105">Celles</span><span class="sxs-lookup"><span data-stu-id="2b746-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b746-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="2b746-106">Column</span></span></th>
<th><span data-ttu-id="2b746-107">Type</span><span class="sxs-lookup"><span data-stu-id="2b746-107">Type</span></span></th>
<th><span data-ttu-id="2b746-108">Description</span><span class="sxs-lookup"><span data-stu-id="2b746-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b746-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="2b746-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="2b746-110">int</span><span class="sxs-lookup"><span data-stu-id="2b746-110">int</span></span></p></td>
<td><p><span data-ttu-id="2b746-111">ID de l’événement.</span><span class="sxs-lookup"><span data-stu-id="2b746-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b746-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="2b746-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="2b746-113">int</span><span class="sxs-lookup"><span data-stu-id="2b746-113">int</span></span></p></td>
<td><p><span data-ttu-id="2b746-114">Identité du serveur (correspondant à la table tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="2b746-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="2b746-115">Clé</span><span class="sxs-lookup"><span data-stu-id="2b746-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b746-116">Colonne</span><span class="sxs-lookup"><span data-stu-id="2b746-116">Column</span></span></th>
<th><span data-ttu-id="2b746-117">Description</span><span class="sxs-lookup"><span data-stu-id="2b746-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b746-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="2b746-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="2b746-119">Clé étrangère avec recherche dans la table tblComplianceData. cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="2b746-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

