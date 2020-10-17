---
title: 'Lync Server 2013 : vue ConferenceMessageCount'
description: 'Lync Server 2013 : vue ConferenceMessageCount.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 212d6e1a346253809fb70806424350cc7fc0dfe2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561610"
---
# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="36ce3-103">Vue ConferenceMessageCount dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36ce3-103">ConferenceMessageCount view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36ce3-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="36ce3-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="36ce3-105">L’affichage ConferenceMessageCount stocke les informations relatives au nombre de messages envoyés par un utilisateur à une conférence.</span><span class="sxs-lookup"><span data-stu-id="36ce3-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="36ce3-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="36ce3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36ce3-107">La vue ConferenceMessageCount contient toutes les colonnes de la <A href="lync-server-2013-conferencesessiondetails-view.md">vue ConferenceSessionDetails dans Lync Server 2013</A> , en plus des colonnes indiquées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="36ce3-107">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36ce3-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="36ce3-108">Column</span></span></th>
<th><span data-ttu-id="36ce3-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="36ce3-109">Data Type</span></span></th>
<th><span data-ttu-id="36ce3-110">Détails</span><span class="sxs-lookup"><span data-stu-id="36ce3-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36ce3-111"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="36ce3-111"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="36ce3-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="36ce3-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="36ce3-113">URI de l’utilisateur qui a envoyé le message.</span><span class="sxs-lookup"><span data-stu-id="36ce3-113">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ce3-114"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="36ce3-114"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="36ce3-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="36ce3-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="36ce3-116">Type d’URI de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="36ce3-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="36ce3-117">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ce3-117">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="36ce3-118"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="36ce3-118"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="36ce3-119">unique</span><span class="sxs-lookup"><span data-stu-id="36ce3-119">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="36ce3-120">Locataire de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="36ce3-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="36ce3-121">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="36ce3-121">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="36ce3-122"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="36ce3-122"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="36ce3-123">type</span><span class="sxs-lookup"><span data-stu-id="36ce3-123">smallint</span></span></p></td>
<td><p><span data-ttu-id="36ce3-124">Nombre de messages envoyés par l’utilisateur pendant la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="36ce3-124">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

