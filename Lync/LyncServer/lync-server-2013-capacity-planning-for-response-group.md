---
title: 'Lync Server 2013 : planification de la capacité pour Response Group'
description: 'Lync Server 2013 : planification de la capacité pour Response Group.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544430"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="030a4-103">Planification de la capacité pour Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="030a4-103">Capacity planning for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="030a4-104">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="030a4-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="030a4-105">Le tableau suivant décrit le modèle utilisateur Response Group que vous pouvez utiliser comme base pour les exigences de planification de capacité.</span><span class="sxs-lookup"><span data-stu-id="030a4-105">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="030a4-p101">Les chiffres du tableau suivant supposent que vous utilisez des fichiers 16 kHz, mono, 16 bits (.wav) pour tous les fichiers audio Response Group. Si vous utilisez d’autres formats de fichier, tels que Windows Media Audio (.wma), les chiffres peuvent changer.</span><span class="sxs-lookup"><span data-stu-id="030a4-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="030a4-108">N’oubliez pas que pour la planification de capacité de récupération d’urgence, chaque pool d’un pool associé doit être capable de gérer les charges de travail de tous les groupes de réponse des deux pools.</span><span class="sxs-lookup"><span data-stu-id="030a4-108">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="030a4-109">Modèle utilisateur de Response Group</span><span class="sxs-lookup"><span data-stu-id="030a4-109">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="030a4-110">Métrique</span><span class="sxs-lookup"><span data-stu-id="030a4-110">Metric</span></span></th>
<th><span data-ttu-id="030a4-111">Par pool Enterprise Edition (avec 8 serveurs frontaux)</span><span class="sxs-lookup"><span data-stu-id="030a4-111">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="030a4-112">Par serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="030a4-112">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="030a4-113">Appels entrants par seconde</span><span class="sxs-lookup"><span data-stu-id="030a4-113">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="030a4-114">16 </span><span class="sxs-lookup"><span data-stu-id="030a4-114">16</span></span></p></td>
<td><p><span data-ttu-id="030a4-115">n°2</span><span class="sxs-lookup"><span data-stu-id="030a4-115">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="030a4-116">Appels simultanés connectés à la réponse vocale interactive ou à l’attente musicale</span><span class="sxs-lookup"><span data-stu-id="030a4-116">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="030a4-117">480</span><span class="sxs-lookup"><span data-stu-id="030a4-117">480</span></span></p></td>
<td><p><span data-ttu-id="030a4-118">60</span><span class="sxs-lookup"><span data-stu-id="030a4-118">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="030a4-119">Sessions anonymes simultanées (sans messagerie instantanée)</span><span class="sxs-lookup"><span data-stu-id="030a4-119">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="030a4-120">224</span><span class="sxs-lookup"><span data-stu-id="030a4-120">224</span></span></p></td>
<td><p><span data-ttu-id="030a4-121">vingt</span><span class="sxs-lookup"><span data-stu-id="030a4-121">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="030a4-122">Sessions anonymes simultanées (avec messagerie instantanée)</span><span class="sxs-lookup"><span data-stu-id="030a4-122">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="030a4-123">64</span><span class="sxs-lookup"><span data-stu-id="030a4-123">64</span></span></p></td>
<td><p><span data-ttu-id="030a4-124">8 </span><span class="sxs-lookup"><span data-stu-id="030a4-124">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="030a4-125">Agents actifs (formels et informels)</span><span class="sxs-lookup"><span data-stu-id="030a4-125">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="030a4-126">1200</span><span class="sxs-lookup"><span data-stu-id="030a4-126">1200</span></span></p></td>
<td><p><span data-ttu-id="030a4-127">1200</span><span class="sxs-lookup"><span data-stu-id="030a4-127">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="030a4-128">Nombre de groupes de recherche</span><span class="sxs-lookup"><span data-stu-id="030a4-128">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="030a4-129">400</span><span class="sxs-lookup"><span data-stu-id="030a4-129">400</span></span></p></td>
<td><p><span data-ttu-id="030a4-130">400</span><span class="sxs-lookup"><span data-stu-id="030a4-130">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="030a4-131">Nombre de groupes de réponse vocale interactive (utilisation de la reconnaissance vocale)</span><span class="sxs-lookup"><span data-stu-id="030a4-131">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="030a4-132">200</span><span class="sxs-lookup"><span data-stu-id="030a4-132">200</span></span></p></td>
<td><p><span data-ttu-id="030a4-133">200</span><span class="sxs-lookup"><span data-stu-id="030a4-133">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

