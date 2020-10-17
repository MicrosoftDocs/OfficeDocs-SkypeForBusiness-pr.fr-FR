---
title: 'Lync Server 2013 : enregistrements d’utilisation RTC'
description: 'Lync Server 2013 : enregistrements d’utilisation RTC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f8ff428dc2fa5cf8cf0f10e37f0f79c38d70d70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565580"
---
# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="21d67-103">Enregistrements d’utilisation PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d67-103">PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21d67-104">_**Dernière modification de la rubrique :** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="21d67-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="21d67-p101">La planification des enregistrements d’utilisation PSTN consiste principalement à répertorier toutes les autorisations d’appel actuellement en vigueur dans votre organisation, du PDG aux travailleurs temporaires, consultants et subordonnés. Ce processus donne également la possibilité de revérifier les autorisations d’appel existantes et de les modifier. Vous pouvez créer des enregistrements d’utilisation PSTN uniquement pour les autorisations qui s’appliquent aux utilisateurs Voix Entreprise prévus, mais une meilleure solution à long terme peut consister à créer des enregistrements d’utilisation PSTN pour toutes les autorisations d’appel, même si certaines d’entre elles peuvent ne pas s’appliquer actuellement au groupe d’utilisateurs à activer pour Voix Entreprise. Si les autorisations d’appel changent ou que de nouveaux utilisateurs avec des autorisations d’appel différentes sont ajoutés, vous aurez déjà créé les enregistrements d’utilisation PSTN requis.</span><span class="sxs-lookup"><span data-stu-id="21d67-p101">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff. This process also provides an opportunity to reexamine existing call permissions and revise them. You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice. If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="21d67-109">Le tableau suivant présente un exemple d’utilisation PSTN standard :</span><span class="sxs-lookup"><span data-stu-id="21d67-109">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="21d67-110">Enregistrements d’utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="21d67-110">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21d67-111">Attribut de téléphone</span><span class="sxs-lookup"><span data-stu-id="21d67-111">Phone attribute</span></span></th>
<th><span data-ttu-id="21d67-112">Description</span><span class="sxs-lookup"><span data-stu-id="21d67-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21d67-113">Local</span><span class="sxs-lookup"><span data-stu-id="21d67-113">Local</span></span></p></td>
<td><p><span data-ttu-id="21d67-114">Appels locaux</span><span class="sxs-lookup"><span data-stu-id="21d67-114">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21d67-115">Long-Distance</span><span class="sxs-lookup"><span data-stu-id="21d67-115">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="21d67-116">Appels longue distance</span><span class="sxs-lookup"><span data-stu-id="21d67-116">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21d67-117">International</span><span class="sxs-lookup"><span data-stu-id="21d67-117">International</span></span></p></td>
<td><p><span data-ttu-id="21d67-118">Appels internationaux</span><span class="sxs-lookup"><span data-stu-id="21d67-118">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21d67-119">Delhi</span><span class="sxs-lookup"><span data-stu-id="21d67-119">Delhi</span></span></p></td>
<td><p><span data-ttu-id="21d67-120">Employés à temps plein à Delhi</span><span class="sxs-lookup"><span data-stu-id="21d67-120">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21d67-121">Redmond</span><span class="sxs-lookup"><span data-stu-id="21d67-121">Redmond</span></span></p></td>
<td><p><span data-ttu-id="21d67-122">Employés à temps plein à Redmond</span><span class="sxs-lookup"><span data-stu-id="21d67-122">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21d67-123">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="21d67-123">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="21d67-124">Employés temporaires à Redmond</span><span class="sxs-lookup"><span data-stu-id="21d67-124">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21d67-125">Zurich</span><span class="sxs-lookup"><span data-stu-id="21d67-125">Zurich</span></span></p></td>
<td><p><span data-ttu-id="21d67-126">Employés à temps plein à Zurich</span><span class="sxs-lookup"><span data-stu-id="21d67-126">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="21d67-p102">Les enregistrements d’utilisation PSTN n’effectuent aucune action par eux-mêmes. Pour qu’ils fonctionnent, vous devez les associer aux éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="21d67-p102">By themselves, PSTN usage records do not do anything. For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="21d67-129">des stratégies de voix, qui sont assignées aux utilisateurs ;</span><span class="sxs-lookup"><span data-stu-id="21d67-129">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="21d67-130">des itinéraires, qui sont assignés aux numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="21d67-130">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="21d67-131">Pour plus d’informations sur les stratégies de voix et les itinéraires, consultez la rubrique [Voice Policies in Lync server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="21d67-131">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="21d67-132">Pour plus d’informations sur la façon de les créer et de les configurer, reportez-vous à la rubrique [Configuration des itinéraires vocaux pour les appels sortants dans Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="21d67-132">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

