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
ms.openlocfilehash: 3976cb18336477c00a901116a125149b8c67ddeb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="133eb-102">tblPreference dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="133eb-102">tblPreference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="133eb-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="133eb-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="133eb-104">La table tblPreference contient les préférences des utilisateurs pour les clients.</span><span class="sxs-lookup"><span data-stu-id="133eb-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="133eb-105">Elle est généralement utilisée par les clients antérieurs à Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="133eb-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="133eb-106">Columns</span><span class="sxs-lookup"><span data-stu-id="133eb-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="133eb-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="133eb-107">Column</span></span></th>
<th><span data-ttu-id="133eb-108">Type</span><span class="sxs-lookup"><span data-stu-id="133eb-108">Type</span></span></th>
<th><span data-ttu-id="133eb-109">Description</span><span class="sxs-lookup"><span data-stu-id="133eb-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="133eb-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="133eb-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="133eb-111">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="133eb-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="133eb-112">Étiquette avec un format tel que : &lt;URI&gt;SIP de l’utilisateur | nom d’utilisateur. &lt;jeu&gt;de préférences.</span><span class="sxs-lookup"><span data-stu-id="133eb-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133eb-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="133eb-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="133eb-114">int, non null</span><span class="sxs-lookup"><span data-stu-id="133eb-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="133eb-115">Numéro séquentiel (par étiquette) à des fins de contrôle de version.</span><span class="sxs-lookup"><span data-stu-id="133eb-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="133eb-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="133eb-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="133eb-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="133eb-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="133eb-118">Contenu codé.</span><span class="sxs-lookup"><span data-stu-id="133eb-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133eb-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="133eb-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="133eb-120">entier, non null</span><span class="sxs-lookup"><span data-stu-id="133eb-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="133eb-121">ID du principal qui à mis à jour la préférence.</span><span class="sxs-lookup"><span data-stu-id="133eb-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="133eb-122">Clé</span><span class="sxs-lookup"><span data-stu-id="133eb-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="133eb-123">Colonne</span><span class="sxs-lookup"><span data-stu-id="133eb-123">Column</span></span></th>
<th><span data-ttu-id="133eb-124">Description</span><span class="sxs-lookup"><span data-stu-id="133eb-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="133eb-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="133eb-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="133eb-126">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="133eb-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

