---
title: 'Lync Server 2013 : planification de la capacité pour le parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dd9ba479fff51491c1240ec42941615f7c476da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="18c0e-102">Planification de la capacité pour le parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18c0e-102">Capacity planning for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18c0e-103">_**Dernière modification de la rubrique :** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="18c0e-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="18c0e-104">Le tableau suivant décrit le modèle utilisateur de parcage d’appel que vous pouvez utiliser comme base pour les exigences de planification de capacité.</span><span class="sxs-lookup"><span data-stu-id="18c0e-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="18c0e-105">N’oubliez pas que, pour la planification de la capacité de récupération d’urgence, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail des services de parcage d’appel dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="18c0e-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="18c0e-106">Modèle utilisateur de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="18c0e-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18c0e-107">Liées</span><span class="sxs-lookup"><span data-stu-id="18c0e-107">Metric</span></span></th>
<th><span data-ttu-id="18c0e-108">Par pool frontal (avec 8 serveurs frontaux)</span><span class="sxs-lookup"><span data-stu-id="18c0e-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="18c0e-109">Par serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="18c0e-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18c0e-110">Taux de parcage</span><span class="sxs-lookup"><span data-stu-id="18c0e-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="18c0e-111">8 par minute</span><span class="sxs-lookup"><span data-stu-id="18c0e-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="18c0e-112">1 par minute</span><span class="sxs-lookup"><span data-stu-id="18c0e-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c0e-113">Taux d’appels parqués récupérés</span><span class="sxs-lookup"><span data-stu-id="18c0e-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="18c0e-114">8 par minute</span><span class="sxs-lookup"><span data-stu-id="18c0e-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="18c0e-115">1 par minute</span><span class="sxs-lookup"><span data-stu-id="18c0e-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c0e-116">Durée moyenne de parcage</span><span class="sxs-lookup"><span data-stu-id="18c0e-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="18c0e-117">60 secondes</span><span class="sxs-lookup"><span data-stu-id="18c0e-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="18c0e-118">60 secondes</span><span class="sxs-lookup"><span data-stu-id="18c0e-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

