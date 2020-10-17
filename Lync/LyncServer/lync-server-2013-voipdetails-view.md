---
title: 'Lync Server 2013 : vue VoIPDetails'
description: 'Lync Server 2013 : vue VoIPDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ecd34be0c8568eef29d773f088e8503a8065743
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566200"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="27381-103">Vue VoIPDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27381-103">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27381-104">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="27381-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="27381-105">La vue VoIPDetails stocke des informations sur les sessions égal à égal, où au moins un utilisateur est un utilisateur VoIP.</span><span class="sxs-lookup"><span data-stu-id="27381-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="27381-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="27381-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="27381-107">La vue VoIPDetails contient toutes les colonnes de la <A href="lync-server-2013-sessiondetails-view.md">vue SessionDetails dans Lync Server 2013</A> , en plus des colonnes indiquées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="27381-107">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27381-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="27381-108">Column</span></span></th>
<th><span data-ttu-id="27381-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="27381-109">Data Type</span></span></th>
<th><span data-ttu-id="27381-110">Détails</span><span class="sxs-lookup"><span data-stu-id="27381-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27381-111"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="27381-111"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="27381-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="27381-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="27381-113">URI du téléphone de l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="27381-113">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27381-114"><strong>Aiguis</strong></span><span class="sxs-lookup"><span data-stu-id="27381-114"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="27381-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="27381-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="27381-116">URI du téléphone de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="27381-116">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27381-117"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="27381-117"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="27381-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="27381-118">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="27381-119">URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="27381-119">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27381-120"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="27381-120"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="27381-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27381-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="27381-122">Type de URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="27381-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="27381-123">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="27381-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27381-124"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="27381-124"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="27381-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27381-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="27381-126">Client de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="27381-126">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27381-127"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="27381-127"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="27381-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="27381-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="27381-129">URI du téléphone de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="27381-129">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27381-130"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="27381-130"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="27381-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27381-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="27381-132">Serveur de médiation utilisé par l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="27381-132">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27381-133"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="27381-133"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="27381-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27381-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="27381-135">Serveur de médiation utilisé par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="27381-135">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27381-136"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="27381-136"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="27381-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27381-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="27381-138">Passerelle utilisée par l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="27381-138">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27381-139"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="27381-139"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="27381-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="27381-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="27381-141">Passerelle utilisée par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="27381-141">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

