---
title: 'Lync Server 2013 : tblPreference'
description: 'Lync Server 2013 : tblPreference.'
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
ms.openlocfilehash: 86e8b81a6af93e9bf1d7673e54492579a1bed08e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547510"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="c63d5-103">tblPreference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c63d5-103">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c63d5-104">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="c63d5-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="c63d5-105">La table tblPreference contient les préférences des utilisateurs pour les clients.</span><span class="sxs-lookup"><span data-stu-id="c63d5-105">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="c63d5-106">Elle est généralement utilisée par les clients antérieurs à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c63d5-106">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="c63d5-107">Colonnes</span><span class="sxs-lookup"><span data-stu-id="c63d5-107">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c63d5-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="c63d5-108">Column</span></span></th>
<th><span data-ttu-id="c63d5-109">Type</span><span class="sxs-lookup"><span data-stu-id="c63d5-109">Type</span></span></th>
<th><span data-ttu-id="c63d5-110">Description</span><span class="sxs-lookup"><span data-stu-id="c63d5-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c63d5-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="c63d5-111">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="c63d5-112">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="c63d5-112">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="c63d5-113">Étiquette avec un format tel que : &lt; URI SIP de l’utilisateur &gt; | nom d’utilisateur. &lt; jeu de préférences &gt; .</span><span class="sxs-lookup"><span data-stu-id="c63d5-113">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63d5-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="c63d5-114">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="c63d5-115">entier, non null</span><span class="sxs-lookup"><span data-stu-id="c63d5-115">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c63d5-116">Numéro séquentiel (par étiquette) à des fins de contrôle de version.</span><span class="sxs-lookup"><span data-stu-id="c63d5-116">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63d5-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="c63d5-117">prefContent</span></span></p></td>
<td><p><span data-ttu-id="c63d5-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="c63d5-118">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="c63d5-119">Contenu codé.</span><span class="sxs-lookup"><span data-stu-id="c63d5-119">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63d5-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="c63d5-120">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="c63d5-121">entier, non null</span><span class="sxs-lookup"><span data-stu-id="c63d5-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c63d5-122">ID du principal qui à mis à jour la préférence.</span><span class="sxs-lookup"><span data-stu-id="c63d5-122">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="c63d5-123">Clé</span><span class="sxs-lookup"><span data-stu-id="c63d5-123">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c63d5-124">Colonne</span><span class="sxs-lookup"><span data-stu-id="c63d5-124">Column</span></span></th>
<th><span data-ttu-id="c63d5-125">Description</span><span class="sxs-lookup"><span data-stu-id="c63d5-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c63d5-126">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="c63d5-126">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="c63d5-127">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="c63d5-127">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

