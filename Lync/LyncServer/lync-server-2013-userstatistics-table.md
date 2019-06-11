---
title: 'Tableau Lync Server 2013: UserStatistics'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0f684850625f61ca72bbcc9c4bc53b56fcc6b38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="bb9a4-102">Table UserStatistics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb9a4-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb9a4-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bb9a4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bb9a4-104">La table UserStatistics est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="bb9a4-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="bb9a4-105">Chaque enregistrement de la table stocke des informations sur l’utilisation individuelle du système par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb9a4-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="bb9a4-106">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb9a4-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb9a4-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="bb9a4-107">Column</span></span></th>
<th><span data-ttu-id="bb9a4-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="bb9a4-108">Data Type</span></span></th>
<th><span data-ttu-id="bb9a4-109">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="bb9a4-109">Key/Index</span></span></th>
<th><span data-ttu-id="bb9a4-110">Détails</span><span class="sxs-lookup"><span data-stu-id="bb9a4-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb9a4-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="bb9a4-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="bb9a4-112">int</span><span class="sxs-lookup"><span data-stu-id="bb9a4-112">int</span></span></p></td>
<td><p><span data-ttu-id="bb9a4-113">Principal</span><span class="sxs-lookup"><span data-stu-id="bb9a4-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="bb9a4-114">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb9a4-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb9a4-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb9a4-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb9a4-116">DateHeure</span><span class="sxs-lookup"><span data-stu-id="bb9a4-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb9a4-117">Dernière connexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bb9a4-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb9a4-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb9a4-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb9a4-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="bb9a4-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb9a4-120">Dernière organisation d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="bb9a4-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb9a4-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb9a4-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb9a4-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="bb9a4-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb9a4-123">Dernière fois que l’utilisateur a rencontré un échec de l’appel.</span><span class="sxs-lookup"><span data-stu-id="bb9a4-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb9a4-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb9a4-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb9a4-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="bb9a4-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb9a4-126">Dernière fois que l’utilisateur a rencontré un appel d’organisateur en tant qu’organisateur de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="bb9a4-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

