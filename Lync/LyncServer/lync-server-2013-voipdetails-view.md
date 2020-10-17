---
title: 'Lync Server 2013 : vue VoIPDetails'
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
ms.openlocfilehash: 0dc01632579c6455c47113f34e181f6598b7c781
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535381"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="5fcf9-102">Vue VoIPDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fcf9-102">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fcf9-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5fcf9-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5fcf9-104">La vue VoIPDetails stocke des informations sur les sessions égal à égal, où au moins un utilisateur est un utilisateur VoIP.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="5fcf9-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5fcf9-106">La vue VoIPDetails contient toutes les colonnes de la <A href="lync-server-2013-sessiondetails-view.md">vue SessionDetails dans Lync Server 2013</A> , en plus des colonnes indiquées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fcf9-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="5fcf9-107">Column</span></span></th>
<th><span data-ttu-id="5fcf9-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="5fcf9-108">Data Type</span></span></th>
<th><span data-ttu-id="5fcf9-109">Détails</span><span class="sxs-lookup"><span data-stu-id="5fcf9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fcf9-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="5fcf9-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="5fcf9-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5fcf9-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5fcf9-112">URI du téléphone de l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fcf9-113"><strong>Aiguis</strong></span><span class="sxs-lookup"><span data-stu-id="5fcf9-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="5fcf9-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5fcf9-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5fcf9-115">URI du téléphone de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fcf9-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="5fcf9-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5fcf9-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5fcf9-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5fcf9-118">URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fcf9-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5fcf9-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5fcf9-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5fcf9-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5fcf9-121">Type de URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="5fcf9-122">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="5fcf9-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fcf9-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5fcf9-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5fcf9-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5fcf9-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5fcf9-125">Client de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fcf9-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="5fcf9-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="5fcf9-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5fcf9-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5fcf9-128">URI du téléphone de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fcf9-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="5fcf9-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5fcf9-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5fcf9-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5fcf9-131">Serveur de médiation utilisé par l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fcf9-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="5fcf9-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5fcf9-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5fcf9-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5fcf9-134">Serveur de médiation utilisé par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fcf9-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="5fcf9-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="5fcf9-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5fcf9-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5fcf9-137">Passerelle utilisée par l’utilisateur qui a initié la session.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fcf9-138"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="5fcf9-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="5fcf9-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5fcf9-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5fcf9-140">Passerelle utilisée par l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="5fcf9-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

