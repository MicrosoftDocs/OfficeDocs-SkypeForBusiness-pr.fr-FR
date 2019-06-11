---
title: 'Affichage Lync Server 2013: ConferenceMessageCount'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0324c9913a607057c4e1cd161a9040b83d6bd29b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="8253a-102">Affichage ConferenceMessageCount dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8253a-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8253a-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8253a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8253a-104">Le mode ConferenceMessageCount stocke les informations sur le nombre de messages envoyés par un utilisateur à une conférence.</span><span class="sxs-lookup"><span data-stu-id="8253a-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="8253a-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8253a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8253a-106">Le mode ConferenceMessageCount contient toutes les colonnes de la <A href="lync-server-2013-conferencesessiondetails-view.md">vue ConferenceSessionDetails dans Lync Server 2013</A> , en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8253a-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8253a-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="8253a-107">Column</span></span></th>
<th><span data-ttu-id="8253a-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="8253a-108">Data Type</span></span></th>
<th><span data-ttu-id="8253a-109">Détails</span><span class="sxs-lookup"><span data-stu-id="8253a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8253a-110"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="8253a-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="8253a-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8253a-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8253a-112">URI de l’utilisateur qui a envoyé le message.</span><span class="sxs-lookup"><span data-stu-id="8253a-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8253a-113"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="8253a-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="8253a-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8253a-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8253a-115">Type d’URI de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="8253a-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="8253a-116">Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8253a-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8253a-117"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="8253a-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="8253a-118">identificateur</span><span class="sxs-lookup"><span data-stu-id="8253a-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="8253a-119">Client de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="8253a-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="8253a-120">Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8253a-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8253a-121"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="8253a-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="8253a-122">type</span><span class="sxs-lookup"><span data-stu-id="8253a-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="8253a-123">Nombre de messages envoyés par l’utilisateur au cours de la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="8253a-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

