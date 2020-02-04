---
title: 'Lync Server 2013 : tblPreference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd45dcbd6ade83d6c4404346e1752c1f78254e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="24bc5-102">tblPreference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24bc5-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24bc5-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="24bc5-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="24bc5-104">tblPreference contient les préférences client de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="24bc5-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="24bc5-105">Il est généralement utilisé par les clients antérieurs à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="24bc5-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="24bc5-106">Celles</span><span class="sxs-lookup"><span data-stu-id="24bc5-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24bc5-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="24bc5-107">Column</span></span></th>
<th><span data-ttu-id="24bc5-108">Type</span><span class="sxs-lookup"><span data-stu-id="24bc5-108">Type</span></span></th>
<th><span data-ttu-id="24bc5-109">Description</span><span class="sxs-lookup"><span data-stu-id="24bc5-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24bc5-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="24bc5-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="24bc5-111">nvarchar (255), pas null</span><span class="sxs-lookup"><span data-stu-id="24bc5-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="24bc5-112">Étiquette avec un format tel que : &lt;URI&gt;SIP utilisateur | nom d’utilisateur. &lt;option définie&gt;.</span><span class="sxs-lookup"><span data-stu-id="24bc5-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24bc5-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="24bc5-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="24bc5-114">ent, non null</span><span class="sxs-lookup"><span data-stu-id="24bc5-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="24bc5-115">Un numéro séquentiel (par étiquette) à des fins de contrôle de version.</span><span class="sxs-lookup"><span data-stu-id="24bc5-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24bc5-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="24bc5-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="24bc5-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="24bc5-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="24bc5-118">Contenu encodé.</span><span class="sxs-lookup"><span data-stu-id="24bc5-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24bc5-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="24bc5-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="24bc5-120">ent, non null</span><span class="sxs-lookup"><span data-stu-id="24bc5-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="24bc5-121">ID de l’objet principal qui a mis à jour la préférence.</span><span class="sxs-lookup"><span data-stu-id="24bc5-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="24bc5-122">Clé</span><span class="sxs-lookup"><span data-stu-id="24bc5-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24bc5-123">Colonne</span><span class="sxs-lookup"><span data-stu-id="24bc5-123">Column</span></span></th>
<th><span data-ttu-id="24bc5-124">Description</span><span class="sxs-lookup"><span data-stu-id="24bc5-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24bc5-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="24bc5-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="24bc5-126">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="24bc5-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

