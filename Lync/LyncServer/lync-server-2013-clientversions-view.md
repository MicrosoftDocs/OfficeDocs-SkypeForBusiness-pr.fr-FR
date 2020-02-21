---
title: 'Lync Server 2013 : vue ClientVersions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c668f56cfa1d4fdf1c2a189199a6faa960073ff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="be115-102">Vue ClientVersions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be115-102">ClientVersions view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be115-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="be115-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="be115-104">L’affichage ClientVersions stocke des informations sur les différents types et versions de clients qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="be115-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="be115-105">Chaque enregistrement de la vue représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="be115-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="be115-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="be115-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be115-107">Il peut y avoir plusieurs enregistrements pour certaines colonnes.</span><span class="sxs-lookup"><span data-stu-id="be115-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be115-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="be115-108">Column</span></span></th>
<th><span data-ttu-id="be115-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="be115-109">Data Type</span></span></th>
<th><span data-ttu-id="be115-110">Détails</span><span class="sxs-lookup"><span data-stu-id="be115-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be115-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="be115-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="be115-112">int</span><span class="sxs-lookup"><span data-stu-id="be115-112">int</span></span></p></td>
<td><p><span data-ttu-id="be115-113">Numéro unique identifiant le type et la version de ce client.</span><span class="sxs-lookup"><span data-stu-id="be115-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be115-114"><strong>Version</strong></span><span class="sxs-lookup"><span data-stu-id="be115-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="be115-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="be115-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="be115-116">Représente l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="be115-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be115-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="be115-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="be115-118">int</span><span class="sxs-lookup"><span data-stu-id="be115-118">int</span></span></p></td>
<td><p><span data-ttu-id="be115-119">Type de client.</span><span class="sxs-lookup"><span data-stu-id="be115-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be115-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="be115-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="be115-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="be115-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="be115-122">Catégorie à laquelle appartient le client.</span><span class="sxs-lookup"><span data-stu-id="be115-122">Category that the client belongs to.</span></span> <span data-ttu-id="be115-123">Par exemple, le client Conferencing_Attendant_1.0 appartient au ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="be115-123">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

