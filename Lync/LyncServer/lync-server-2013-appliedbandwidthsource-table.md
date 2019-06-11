---
title: 'Lync Server 2013 : Table AppliedBandwidthSource'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f4c7d78353a60ad4c3bf9a7ff3efb363bd01c82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="e330e-102">Table AppliedBandwidthSource dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e330e-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e330e-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e330e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e330e-104">La table AppliedBandwidthSource est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="e330e-104">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="e330e-105">Chaque enregistrement représente une source.</span><span class="sxs-lookup"><span data-stu-id="e330e-105">Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e330e-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="e330e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e330e-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="e330e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e330e-108"><strong>Clé/Index</strong></span><span class="sxs-lookup"><span data-stu-id="e330e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e330e-109"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="e330e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e330e-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="e330e-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e330e-111">int</span><span class="sxs-lookup"><span data-stu-id="e330e-111">int</span></span></p></td>
<td><p><span data-ttu-id="e330e-112">Principal</span><span class="sxs-lookup"><span data-stu-id="e330e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e330e-113">Numéro unique identifiant la source.</span><span class="sxs-lookup"><span data-stu-id="e330e-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e330e-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="e330e-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="e330e-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e330e-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e330e-116">Différent</span><span class="sxs-lookup"><span data-stu-id="e330e-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="e330e-117">Il s’agit de la source de la bande passante qui est imposée.</span><span class="sxs-lookup"><span data-stu-id="e330e-117">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="e330e-118">Il décrit l’emplacement vers lequel la limite de bande passante provient (par exemple, «serveur de stratégie», «activer le serveur» ou «modalité»).</span><span class="sxs-lookup"><span data-stu-id="e330e-118">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

