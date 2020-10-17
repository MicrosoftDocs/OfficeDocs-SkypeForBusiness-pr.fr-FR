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
ms.openlocfilehash: 3df687926940aa98f3bf803f9a991527f19fa58f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509441"
---
# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="a9c44-102">tblComplianceFanout dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9c44-102">tblComplianceFanout in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9c44-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a9c44-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a9c44-104">La table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="a9c44-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="a9c44-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="a9c44-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9c44-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="a9c44-106">Column</span></span></th>
<th><span data-ttu-id="a9c44-107">Type</span><span class="sxs-lookup"><span data-stu-id="a9c44-107">Type</span></span></th>
<th><span data-ttu-id="a9c44-108">Description</span><span class="sxs-lookup"><span data-stu-id="a9c44-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9c44-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="a9c44-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="a9c44-110">int</span><span class="sxs-lookup"><span data-stu-id="a9c44-110">int</span></span></p></td>
<td><p><span data-ttu-id="a9c44-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="a9c44-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9c44-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="a9c44-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="a9c44-113">int</span><span class="sxs-lookup"><span data-stu-id="a9c44-113">int</span></span></p></td>
<td><p><span data-ttu-id="a9c44-114">Identité du serveur (correspondant à la table tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="a9c44-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="a9c44-115">Clé</span><span class="sxs-lookup"><span data-stu-id="a9c44-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9c44-116">Colonne</span><span class="sxs-lookup"><span data-stu-id="a9c44-116">Column</span></span></th>
<th><span data-ttu-id="a9c44-117">Description</span><span class="sxs-lookup"><span data-stu-id="a9c44-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9c44-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="a9c44-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="a9c44-119">Clé étrangère avec recherche dans la table tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="a9c44-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

