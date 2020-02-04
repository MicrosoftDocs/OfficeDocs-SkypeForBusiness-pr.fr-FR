---
title: 'Affichage Lync Server 2013 : VoIPDetails'
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
ms.openlocfilehash: db65da0af7c34d1121e97436af47750186706b68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="b3bfa-102">Affichage VoIPDetails dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3bfa-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3bfa-103">_**Dernière modification de la rubrique :** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b3bfa-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b3bfa-104">Le mode VoIPDetails stocke des informations sur les sessions d’égal à égal, où au moins un utilisateur est un utilisateur VoIP.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="b3bfa-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3bfa-106">Le mode VoIPDetails contient toutes les colonnes de la <A href="lync-server-2013-sessiondetails-view.md">vue SessionDetails dans Lync Server 2013</A> , en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3bfa-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="b3bfa-107">Column</span></span></th>
<th><span data-ttu-id="b3bfa-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="b3bfa-108">Data Type</span></span></th>
<th><span data-ttu-id="b3bfa-109">Détails</span><span class="sxs-lookup"><span data-stu-id="b3bfa-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3bfa-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="b3bfa-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bfa-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3bfa-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b3bfa-112">URI du téléphone de l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3bfa-113"><strong>À la une</strong></span><span class="sxs-lookup"><span data-stu-id="b3bfa-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bfa-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3bfa-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b3bfa-115">URI de téléphone de l’utilisateur qui a rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3bfa-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="b3bfa-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bfa-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3bfa-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b3bfa-118">URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3bfa-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b3bfa-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bfa-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b3bfa-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3bfa-121">Type d’URI de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="b3bfa-122">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b3bfa-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3bfa-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b3bfa-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bfa-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b3bfa-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3bfa-125">Client de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3bfa-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="b3bfa-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bfa-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3bfa-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b3bfa-128">URI de téléphone de l’utilisateur qui a déconnecté la session.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3bfa-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="b3bfa-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bfa-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b3bfa-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3bfa-131">Serveur de médiation utilisé par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3bfa-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="b3bfa-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bfa-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b3bfa-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3bfa-134">Serveur de médiation utilisé par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3bfa-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="b3bfa-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bfa-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b3bfa-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3bfa-137">Passerelle utilisée par l’utilisateur qui a démarré la session.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3bfa-138"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="b3bfa-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="b3bfa-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b3bfa-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3bfa-140">Passerelle utilisée par l’utilisateur ayant rejoint la session.</span><span class="sxs-lookup"><span data-stu-id="b3bfa-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

