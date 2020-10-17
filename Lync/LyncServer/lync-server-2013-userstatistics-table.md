---
title: 'Lync Server 2013 : table UserStatistics'
description: 'Lync Server 2013 : table UserStatistics.'
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
ms.openlocfilehash: 75b34fa3c34af4cc9cf2cacc6ae7feb4d217114c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548530"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="48129-103">Table UserStatistics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48129-103">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48129-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="48129-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="48129-105">La table UserStatistics est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="48129-105">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="48129-106">Chaque enregistrement dans la table stocke les informations sur l’utilisation individuelle d’un utilisateur du système.</span><span class="sxs-lookup"><span data-stu-id="48129-106">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="48129-107">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48129-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48129-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="48129-108">Column</span></span></th>
<th><span data-ttu-id="48129-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="48129-109">Data Type</span></span></th>
<th><span data-ttu-id="48129-110">Clé/index</span><span class="sxs-lookup"><span data-stu-id="48129-110">Key/Index</span></span></th>
<th><span data-ttu-id="48129-111">Détails</span><span class="sxs-lookup"><span data-stu-id="48129-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48129-112"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="48129-112"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="48129-113">int</span><span class="sxs-lookup"><span data-stu-id="48129-113">int</span></span></p></td>
<td><p><span data-ttu-id="48129-114">Primaire</span><span class="sxs-lookup"><span data-stu-id="48129-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="48129-115">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="48129-115">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48129-116"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="48129-116"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="48129-117">DateHeure</span><span class="sxs-lookup"><span data-stu-id="48129-117">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48129-118">Heure de la dernière connexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="48129-118">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48129-119"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="48129-119"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="48129-120">DateHeure</span><span class="sxs-lookup"><span data-stu-id="48129-120">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48129-121">Heure de la dernière organisation d’une conférence par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="48129-121">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48129-122"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="48129-122"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="48129-123">DateHeure</span><span class="sxs-lookup"><span data-stu-id="48129-123">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48129-124">Heure du dernier échec d’appel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="48129-124">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48129-125"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="48129-125"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="48129-126">DateHeure</span><span class="sxs-lookup"><span data-stu-id="48129-126">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48129-127">Heure du dernier échec d’appel de l’utilisateur en tant qu’organisateur de conférence.</span><span class="sxs-lookup"><span data-stu-id="48129-127">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

