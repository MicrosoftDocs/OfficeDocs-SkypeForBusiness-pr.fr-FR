---
title: 'Lync Server 2013 : tblConfig'
description: 'Lync Server 2013 : tblConfig.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8990e0b2c8724a5e90c36e706b92f9985f288772
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550430"
---
# <a name="tblconfig-in-lync-server-2013"></a><span data-ttu-id="dfded-103">tblConfig dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfded-103">tblConfig in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfded-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="dfded-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="dfded-105">tblConfig contient une configuration non prise en charge par le serveur de conversation permanente, dans une ligne.</span><span class="sxs-lookup"><span data-stu-id="dfded-105">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>

### <a name="columns"></a><span data-ttu-id="dfded-106">Colonnes</span><span class="sxs-lookup"><span data-stu-id="dfded-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfded-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="dfded-107">Column</span></span></th>
<th><span data-ttu-id="dfded-108">Type</span><span class="sxs-lookup"><span data-stu-id="dfded-108">Type</span></span></th>
<th><span data-ttu-id="dfded-109">Description</span><span class="sxs-lookup"><span data-stu-id="dfded-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfded-110">configLabel</span><span class="sxs-lookup"><span data-stu-id="dfded-110">configLabel</span></span></p></td>
<td><p><span data-ttu-id="dfded-111">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="dfded-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="dfded-112">Contient le &quot; pool.&quot;</span><span class="sxs-lookup"><span data-stu-id="dfded-112">Contains &quot;pool.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfded-113">configContent</span><span class="sxs-lookup"><span data-stu-id="dfded-113">configContent</span></span></p></td>
<td><p><span data-ttu-id="dfded-114">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="dfded-114">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="dfded-115">Contenu de configuration.</span><span class="sxs-lookup"><span data-stu-id="dfded-115">Configuration content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfded-116">configPoolID</span><span class="sxs-lookup"><span data-stu-id="dfded-116">configPoolID</span></span></p></td>
<td><p><span data-ttu-id="dfded-117">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="dfded-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="dfded-118">ID unique de l’instance de base de données.</span><span class="sxs-lookup"><span data-stu-id="dfded-118">Unique ID of the database instance.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="dfded-119">Clé</span><span class="sxs-lookup"><span data-stu-id="dfded-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfded-120">Colonne</span><span class="sxs-lookup"><span data-stu-id="dfded-120">Column</span></span></th>
<th><span data-ttu-id="dfded-121">Description</span><span class="sxs-lookup"><span data-stu-id="dfded-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfded-122">configLabel</span><span class="sxs-lookup"><span data-stu-id="dfded-122">configLabel</span></span></p></td>
<td><p><span data-ttu-id="dfded-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="dfded-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

