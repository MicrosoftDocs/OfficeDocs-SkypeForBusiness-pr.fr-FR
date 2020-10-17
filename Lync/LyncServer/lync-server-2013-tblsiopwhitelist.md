---
title: 'Lync Server 2013 : tblSiopWhiteList'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48183310
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cac704c6f62903c502ae5a4345ee0848c775d6f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536211"
---
# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="dc07c-102">tblSiopWhiteList dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc07c-102">tblSiopWhiteList in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc07c-103">_**Dernière modification de la rubrique :** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="dc07c-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="dc07c-104">tblSiopWhiteList représente la liste des compléments inscrits qui peuvent être associés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="dc07c-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="dc07c-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="dc07c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc07c-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="dc07c-106">Column</span></span></th>
<th><span data-ttu-id="dc07c-107">Type</span><span class="sxs-lookup"><span data-stu-id="dc07c-107">Type</span></span></th>
<th><span data-ttu-id="dc07c-108">Description</span><span class="sxs-lookup"><span data-stu-id="dc07c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc07c-109">siopID</span><span class="sxs-lookup"><span data-stu-id="dc07c-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="dc07c-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="dc07c-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="dc07c-111">GUID du complément.</span><span class="sxs-lookup"><span data-stu-id="dc07c-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc07c-112">siopName</span><span class="sxs-lookup"><span data-stu-id="dc07c-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="dc07c-113">nvarchar (50), non null</span><span class="sxs-lookup"><span data-stu-id="dc07c-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="dc07c-114">Nom d’affichage du complément.</span><span class="sxs-lookup"><span data-stu-id="dc07c-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc07c-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="dc07c-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="dc07c-116">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="dc07c-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="dc07c-117">URL du complément.</span><span class="sxs-lookup"><span data-stu-id="dc07c-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="dc07c-118">Clé</span><span class="sxs-lookup"><span data-stu-id="dc07c-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc07c-119">Colonne</span><span class="sxs-lookup"><span data-stu-id="dc07c-119">Column</span></span></th>
<th><span data-ttu-id="dc07c-120">Description</span><span class="sxs-lookup"><span data-stu-id="dc07c-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc07c-121">siopID</span><span class="sxs-lookup"><span data-stu-id="dc07c-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="dc07c-122">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="dc07c-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

