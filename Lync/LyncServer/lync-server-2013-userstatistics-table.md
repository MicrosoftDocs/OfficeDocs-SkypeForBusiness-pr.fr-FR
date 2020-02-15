---
title: 'Lync Server 2013 : table UserStatistics'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98c24093f332f568daadfb0cd336f0d5fde3eb35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="db7a3-102">Table UserStatistics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db7a3-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db7a3-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="db7a3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="db7a3-104">La table UserStatistics est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="db7a3-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="db7a3-105">Chaque enregistrement dans la table stocke les informations sur l’utilisation individuelle d’un utilisateur du système.</span><span class="sxs-lookup"><span data-stu-id="db7a3-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="db7a3-106">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db7a3-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db7a3-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="db7a3-107">Column</span></span></th>
<th><span data-ttu-id="db7a3-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="db7a3-108">Data Type</span></span></th>
<th><span data-ttu-id="db7a3-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="db7a3-109">Key/Index</span></span></th>
<th><span data-ttu-id="db7a3-110">Détails</span><span class="sxs-lookup"><span data-stu-id="db7a3-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db7a3-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="db7a3-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="db7a3-112">int</span><span class="sxs-lookup"><span data-stu-id="db7a3-112">int</span></span></p></td>
<td><p><span data-ttu-id="db7a3-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="db7a3-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="db7a3-114">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="db7a3-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db7a3-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="db7a3-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db7a3-116">DateHeure</span><span class="sxs-lookup"><span data-stu-id="db7a3-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="db7a3-117">Heure de la dernière connexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="db7a3-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db7a3-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="db7a3-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db7a3-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="db7a3-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="db7a3-120">Heure de la dernière organisation d’une conférence par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="db7a3-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db7a3-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="db7a3-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db7a3-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="db7a3-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="db7a3-123">Heure du dernier échec d’appel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="db7a3-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db7a3-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="db7a3-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="db7a3-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="db7a3-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="db7a3-126">Heure du dernier échec d’appel de l’utilisateur en tant qu’organisateur de conférence.</span><span class="sxs-lookup"><span data-stu-id="db7a3-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

