---
title: 'Affichage Lync Server 2013: ClientVersions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d219b8666afc0684b0d61f02f06618ea6ef60f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="2a2dc-102">Affichage ClientVersions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a2dc-102">ClientVersions view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a2dc-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2a2dc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2a2dc-104">Le mode ClientVersions stocke les informations sur les différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2a2dc-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="2a2dc-105">Chaque enregistrement dans la vue représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="2a2dc-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="2a2dc-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a2dc-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a2dc-107">Il peut y avoir plusieurs enregistrements pour certaines colonnes.</span><span class="sxs-lookup"><span data-stu-id="2a2dc-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a2dc-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="2a2dc-108">Column</span></span></th>
<th><span data-ttu-id="2a2dc-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="2a2dc-109">Data Type</span></span></th>
<th><span data-ttu-id="2a2dc-110">Détails</span><span class="sxs-lookup"><span data-stu-id="2a2dc-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a2dc-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="2a2dc-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="2a2dc-112">int</span><span class="sxs-lookup"><span data-stu-id="2a2dc-112">int</span></span></p></td>
<td><p><span data-ttu-id="2a2dc-113">Numéro unique identifiant ce type et version de client.</span><span class="sxs-lookup"><span data-stu-id="2a2dc-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a2dc-114"><strong>Version</strong></span><span class="sxs-lookup"><span data-stu-id="2a2dc-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="2a2dc-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2a2dc-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2a2dc-116">Représente l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2a2dc-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a2dc-117"><strong>TypeClient</strong></span><span class="sxs-lookup"><span data-stu-id="2a2dc-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="2a2dc-118">int</span><span class="sxs-lookup"><span data-stu-id="2a2dc-118">int</span></span></p></td>
<td><p><span data-ttu-id="2a2dc-119">Type de client.</span><span class="sxs-lookup"><span data-stu-id="2a2dc-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a2dc-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="2a2dc-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="2a2dc-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2a2dc-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="2a2dc-122">Catégorie à laquelle le client appartient.</span><span class="sxs-lookup"><span data-stu-id="2a2dc-122">Category that the client belongs to.</span></span> <span data-ttu-id="2a2dc-123">Par exemple, le client Conferencing_Attendant_ 1.0 appartient au CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="2a2dc-123">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

