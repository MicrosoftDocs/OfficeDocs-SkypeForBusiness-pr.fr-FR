---
title: 'Lync Server 2013 : vue ConferenceMessageCount'
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
ms.openlocfilehash: 2a35b1f223c16c1a490197a11206ea972816c94e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="406fa-102">Vue ConferenceMessageCount dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="406fa-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="406fa-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="406fa-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="406fa-104">L’affichage ConferenceMessageCount stocke les informations relatives au nombre de messages envoyés par un utilisateur à une conférence.</span><span class="sxs-lookup"><span data-stu-id="406fa-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="406fa-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="406fa-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="406fa-106">La vue ConferenceMessageCount contient toutes les colonnes de la <A href="lync-server-2013-conferencesessiondetails-view.md">vue ConferenceSessionDetails dans Lync Server 2013</A> , en plus des colonnes indiquées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="406fa-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="406fa-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="406fa-107">Column</span></span></th>
<th><span data-ttu-id="406fa-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="406fa-108">Data Type</span></span></th>
<th><span data-ttu-id="406fa-109">Détails</span><span class="sxs-lookup"><span data-stu-id="406fa-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="406fa-110"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="406fa-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="406fa-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="406fa-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="406fa-112">URI de l’utilisateur qui a envoyé le message.</span><span class="sxs-lookup"><span data-stu-id="406fa-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="406fa-113"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="406fa-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="406fa-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="406fa-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="406fa-115">Type d’URI de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="406fa-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="406fa-116">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="406fa-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="406fa-117"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="406fa-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="406fa-118">unique</span><span class="sxs-lookup"><span data-stu-id="406fa-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="406fa-119">Locataire de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="406fa-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="406fa-120">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="406fa-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="406fa-121"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="406fa-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="406fa-122">type</span><span class="sxs-lookup"><span data-stu-id="406fa-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="406fa-123">Nombre de messages envoyés par l’utilisateur pendant la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="406fa-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

