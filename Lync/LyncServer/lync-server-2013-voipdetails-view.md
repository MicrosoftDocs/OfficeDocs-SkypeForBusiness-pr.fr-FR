---
title: 'Affichage Lync Server 2013: VoIPDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9553be13dcd73f89ba8d6ab051602d378bf353da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="2b3e5-102">Affichage VoIPDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b3e5-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b3e5-103">_**Dernière modification de la rubrique:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2b3e5-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2b3e5-104">Le mode VoIPDetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="2b3e5-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b3e5-106">Le mode VoIPDetails contient toutes les colonnes de la <A href="lync-server-2013-sessiondetails-view.md">vue SessionDetails dans Lync Server 2013</A> , en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b3e5-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="2b3e5-107">Column</span></span></th>
<th><span data-ttu-id="2b3e5-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="2b3e5-108">Data Type</span></span></th>
<th><span data-ttu-id="2b3e5-109">Détails</span><span class="sxs-lookup"><span data-stu-id="2b3e5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b3e5-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="2b3e5-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2b3e5-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b3e5-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b3e5-112">URI du téléphone de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b3e5-113"><strong>À la une</strong></span><span class="sxs-lookup"><span data-stu-id="2b3e5-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2b3e5-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b3e5-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b3e5-115">URI de téléphone de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b3e5-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="2b3e5-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b3e5-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b3e5-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b3e5-118">URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b3e5-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2b3e5-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b3e5-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2b3e5-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b3e5-121">Type d’URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="2b3e5-122">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="2b3e5-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b3e5-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2b3e5-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2b3e5-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2b3e5-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b3e5-125">Client de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b3e5-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="2b3e5-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2b3e5-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b3e5-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b3e5-128">URI de téléphone de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b3e5-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="2b3e5-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2b3e5-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2b3e5-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b3e5-131">Serveur de médiation utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b3e5-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="2b3e5-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2b3e5-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2b3e5-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b3e5-134">Serveur de médiation utilisé par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b3e5-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="2b3e5-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="2b3e5-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2b3e5-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b3e5-137">Passerelle utilisée par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b3e5-138"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="2b3e5-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="2b3e5-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2b3e5-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b3e5-140">Passerelle utilisée par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="2b3e5-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

