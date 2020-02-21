---
title: 'Lync Server 2013 : table table sessioncorrelation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0f3f7636354915e858016a55389a993f16ec988
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="dc3d0-102">Table table sessioncorrelation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc3d0-102">SessionCorrelation table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc3d0-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="dc3d0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="dc3d0-104">La table table sessioncorrelation est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="dc3d0-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="dc3d0-105">Chaque enregistrement représente une corrélation qui est utilisée pour corréler plusieurs sessions.</span><span class="sxs-lookup"><span data-stu-id="dc3d0-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc3d0-106"><strong>Colonne</strong></span><span class="sxs-lookup"><span data-stu-id="dc3d0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="dc3d0-107"><strong>Type de données</strong></span><span class="sxs-lookup"><span data-stu-id="dc3d0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="dc3d0-108"><strong>Clé/index</strong></span><span class="sxs-lookup"><span data-stu-id="dc3d0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="dc3d0-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="dc3d0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc3d0-110"><strong>Somme de contrôle</strong></span><span class="sxs-lookup"><span data-stu-id="dc3d0-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="dc3d0-111">int</span><span class="sxs-lookup"><span data-stu-id="dc3d0-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc3d0-112"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="dc3d0-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="dc3d0-113">int</span><span class="sxs-lookup"><span data-stu-id="dc3d0-113">int</span></span></p></td>
<td><p><span data-ttu-id="dc3d0-114">Primaire</span><span class="sxs-lookup"><span data-stu-id="dc3d0-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="dc3d0-115">Numéro unique identifiant ce serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="dc3d0-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc3d0-116"><strong>Corrélation</strong></span><span class="sxs-lookup"><span data-stu-id="dc3d0-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="dc3d0-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dc3d0-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dc3d0-118">Uniques</span><span class="sxs-lookup"><span data-stu-id="dc3d0-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="dc3d0-119">Les sessions corrélées auront le même ID de corrélation.</span><span class="sxs-lookup"><span data-stu-id="dc3d0-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc3d0-120"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="dc3d0-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="dc3d0-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dc3d0-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="dc3d0-122">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="dc3d0-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

