---
title: 'Lync Server 2013 : tblComplianceState'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84608b7cb701fe4c394ed413539759d9469a5a4e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509411"
---
# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="d55a4-102">tblComplianceState dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d55a4-102">tblComplianceState in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d55a4-103">_**Dernière modification de la rubrique :** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="d55a4-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="d55a4-104">tblComplianceState contient des informations d’état de conformité à l’échelle du pool.</span><span class="sxs-lookup"><span data-stu-id="d55a4-104">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="d55a4-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="d55a4-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d55a4-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="d55a4-106">Column</span></span></th>
<th><span data-ttu-id="d55a4-107">Type</span><span class="sxs-lookup"><span data-stu-id="d55a4-107">Type</span></span></th>
<th><span data-ttu-id="d55a4-108">Description</span><span class="sxs-lookup"><span data-stu-id="d55a4-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d55a4-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="d55a4-109">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="d55a4-110">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="d55a4-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="d55a4-111">ID du dernier événement de conformité traité.</span><span class="sxs-lookup"><span data-stu-id="d55a4-111">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d55a4-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="d55a4-112">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="d55a4-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="d55a4-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d55a4-114">ID du serveur de conformité contenant le verrou exclusif sur la base de données, ou-1 si aucun.</span><span class="sxs-lookup"><span data-stu-id="d55a4-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d55a4-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="d55a4-115">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="d55a4-116">datetime2, non null</span><span class="sxs-lookup"><span data-stu-id="d55a4-116">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="d55a4-117">Délai d’expiration du verrouillage (si activeServerID n’est pas-1).</span><span class="sxs-lookup"><span data-stu-id="d55a4-117">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

