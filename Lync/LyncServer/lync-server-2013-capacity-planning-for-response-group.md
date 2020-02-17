---
title: 'Lync Server 2013 : planification de la capacité pour Response Group'
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
ms.openlocfilehash: 4e5724978347b50db2790e4d5798aace8489acbb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="ee76a-102">Planification de la capacité pour Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee76a-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee76a-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ee76a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="ee76a-104">Le tableau suivant décrit le modèle utilisateur Response Group que vous pouvez utiliser comme base pour les exigences de planification de capacité.</span><span class="sxs-lookup"><span data-stu-id="ee76a-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee76a-p101">Les chiffres du tableau suivant supposent que vous utilisez des fichiers 16 kHz, mono, 16 bits (.wav) pour tous les fichiers audio Response Group. Si vous utilisez d’autres formats de fichier, tels que Windows Media Audio (.wma), les chiffres peuvent changer.</span><span class="sxs-lookup"><span data-stu-id="ee76a-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ee76a-107">N’oubliez pas que pour la planification de capacité de récupération d’urgence, chaque pool d’un pool associé doit être capable de gérer les charges de travail de tous les groupes de réponse des deux pools.</span><span class="sxs-lookup"><span data-stu-id="ee76a-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="ee76a-108">Modèle utilisateur de Response Group</span><span class="sxs-lookup"><span data-stu-id="ee76a-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee76a-109">Liées</span><span class="sxs-lookup"><span data-stu-id="ee76a-109">Metric</span></span></th>
<th><span data-ttu-id="ee76a-110">Par pool Enterprise Edition (avec 8 serveurs frontaux)</span><span class="sxs-lookup"><span data-stu-id="ee76a-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="ee76a-111">Par serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ee76a-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee76a-112">Appels entrants par seconde</span><span class="sxs-lookup"><span data-stu-id="ee76a-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="ee76a-113">16 </span><span class="sxs-lookup"><span data-stu-id="ee76a-113">16</span></span></p></td>
<td><p><span data-ttu-id="ee76a-114">n°2</span><span class="sxs-lookup"><span data-stu-id="ee76a-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee76a-115">Appels simultanés connectés à la réponse vocale interactive ou à l’attente musicale</span><span class="sxs-lookup"><span data-stu-id="ee76a-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="ee76a-116">480</span><span class="sxs-lookup"><span data-stu-id="ee76a-116">480</span></span></p></td>
<td><p><span data-ttu-id="ee76a-117">60</span><span class="sxs-lookup"><span data-stu-id="ee76a-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee76a-118">Sessions anonymes simultanées (sans messagerie instantanée)</span><span class="sxs-lookup"><span data-stu-id="ee76a-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="ee76a-119">224</span><span class="sxs-lookup"><span data-stu-id="ee76a-119">224</span></span></p></td>
<td><p><span data-ttu-id="ee76a-120">vingt</span><span class="sxs-lookup"><span data-stu-id="ee76a-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee76a-121">Sessions anonymes simultanées (avec messagerie instantanée)</span><span class="sxs-lookup"><span data-stu-id="ee76a-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="ee76a-122">64</span><span class="sxs-lookup"><span data-stu-id="ee76a-122">64</span></span></p></td>
<td><p><span data-ttu-id="ee76a-123">8 </span><span class="sxs-lookup"><span data-stu-id="ee76a-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee76a-124">Agents actifs (formels et informels)</span><span class="sxs-lookup"><span data-stu-id="ee76a-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="ee76a-125">1200</span><span class="sxs-lookup"><span data-stu-id="ee76a-125">1200</span></span></p></td>
<td><p><span data-ttu-id="ee76a-126">1200</span><span class="sxs-lookup"><span data-stu-id="ee76a-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee76a-127">Nombre de groupes de recherche</span><span class="sxs-lookup"><span data-stu-id="ee76a-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="ee76a-128">400</span><span class="sxs-lookup"><span data-stu-id="ee76a-128">400</span></span></p></td>
<td><p><span data-ttu-id="ee76a-129">400</span><span class="sxs-lookup"><span data-stu-id="ee76a-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee76a-130">Nombre de groupes de réponse vocale interactive (utilisation de la reconnaissance vocale)</span><span class="sxs-lookup"><span data-stu-id="ee76a-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="ee76a-131">200</span><span class="sxs-lookup"><span data-stu-id="ee76a-131">200</span></span></p></td>
<td><p><span data-ttu-id="ee76a-132">200</span><span class="sxs-lookup"><span data-stu-id="ee76a-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

