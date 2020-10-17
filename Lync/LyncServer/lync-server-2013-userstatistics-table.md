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
ms.openlocfilehash: 55df55ba8c9953a1efce25269c24b43328472d7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529991"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="2e3fc-102">Table UserStatistics dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e3fc-102">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e3fc-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2e3fc-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2e3fc-104">La table UserStatistics est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="2e3fc-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="2e3fc-105">Chaque enregistrement dans la table stocke les informations sur l’utilisation individuelle d’un utilisateur du système.</span><span class="sxs-lookup"><span data-stu-id="2e3fc-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="2e3fc-106">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e3fc-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e3fc-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="2e3fc-107">Column</span></span></th>
<th><span data-ttu-id="2e3fc-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="2e3fc-108">Data Type</span></span></th>
<th><span data-ttu-id="2e3fc-109">Clé/index</span><span class="sxs-lookup"><span data-stu-id="2e3fc-109">Key/Index</span></span></th>
<th><span data-ttu-id="2e3fc-110">Détails</span><span class="sxs-lookup"><span data-stu-id="2e3fc-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e3fc-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fc-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="2e3fc-112">int</span><span class="sxs-lookup"><span data-stu-id="2e3fc-112">int</span></span></p></td>
<td><p><span data-ttu-id="2e3fc-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="2e3fc-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="2e3fc-114">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2e3fc-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e3fc-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fc-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2e3fc-116">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2e3fc-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2e3fc-117">Heure de la dernière connexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2e3fc-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e3fc-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fc-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2e3fc-119">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2e3fc-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2e3fc-120">Heure de la dernière organisation d’une conférence par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2e3fc-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e3fc-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fc-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2e3fc-122">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2e3fc-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2e3fc-123">Heure du dernier échec d’appel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2e3fc-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e3fc-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="2e3fc-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2e3fc-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2e3fc-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2e3fc-126">Heure du dernier échec d’appel de l’utilisateur en tant qu’organisateur de conférence.</span><span class="sxs-lookup"><span data-stu-id="2e3fc-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

