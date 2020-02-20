---
title: 'Lync Server 2013 : tblPreference'
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
ms.openlocfilehash: a9d91a11f6813bfc7ef86eaf5efded41c7af0c63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="5a9b2-102">tblPreference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a9b2-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a9b2-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="5a9b2-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="5a9b2-104">La table tblPreference contient les préférences des utilisateurs pour les clients.</span><span class="sxs-lookup"><span data-stu-id="5a9b2-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="5a9b2-105">Elle est généralement utilisée par les clients antérieurs à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5a9b2-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="5a9b2-106">Columns</span><span class="sxs-lookup"><span data-stu-id="5a9b2-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a9b2-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="5a9b2-107">Column</span></span></th>
<th><span data-ttu-id="5a9b2-108">Type</span><span class="sxs-lookup"><span data-stu-id="5a9b2-108">Type</span></span></th>
<th><span data-ttu-id="5a9b2-109">Description</span><span class="sxs-lookup"><span data-stu-id="5a9b2-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a9b2-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="5a9b2-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="5a9b2-111">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="5a9b2-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="5a9b2-112">Étiquette avec un format tel que : &lt;URI&gt;SIP de l’utilisateur | nom d’utilisateur. &lt;jeu&gt;de préférences.</span><span class="sxs-lookup"><span data-stu-id="5a9b2-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a9b2-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="5a9b2-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="5a9b2-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="5a9b2-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5a9b2-115">Numéro séquentiel (par étiquette) à des fins de contrôle de version.</span><span class="sxs-lookup"><span data-stu-id="5a9b2-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a9b2-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="5a9b2-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="5a9b2-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5a9b2-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="5a9b2-118">Contenu codé.</span><span class="sxs-lookup"><span data-stu-id="5a9b2-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a9b2-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="5a9b2-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="5a9b2-120">entier, non null</span><span class="sxs-lookup"><span data-stu-id="5a9b2-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5a9b2-121">ID du principal qui à mis à jour la préférence.</span><span class="sxs-lookup"><span data-stu-id="5a9b2-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5a9b2-122">Clé</span><span class="sxs-lookup"><span data-stu-id="5a9b2-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a9b2-123">Colonne</span><span class="sxs-lookup"><span data-stu-id="5a9b2-123">Column</span></span></th>
<th><span data-ttu-id="5a9b2-124">Description</span><span class="sxs-lookup"><span data-stu-id="5a9b2-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a9b2-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="5a9b2-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="5a9b2-126">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="5a9b2-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

