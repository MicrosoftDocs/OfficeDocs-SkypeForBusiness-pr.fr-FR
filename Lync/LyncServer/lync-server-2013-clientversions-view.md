---
title: 'Affichage Lync Server 2013 : ClientVersions'
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
ms.openlocfilehash: 8fd25da49e8a3b6ad7838ff27a4472e711b97421
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="4a1fb-102">Affichage ClientVersions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a1fb-102">ClientVersions view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a1fb-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4a1fb-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4a1fb-104">Le mode ClientVersions stocke les informations sur les différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="4a1fb-105">Chaque enregistrement dans la vue représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="4a1fb-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a1fb-107">Il peut y avoir plusieurs enregistrements pour certaines colonnes.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a1fb-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="4a1fb-108">Column</span></span></th>
<th><span data-ttu-id="4a1fb-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="4a1fb-109">Data Type</span></span></th>
<th><span data-ttu-id="4a1fb-110">Détails</span><span class="sxs-lookup"><span data-stu-id="4a1fb-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a1fb-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="4a1fb-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a1fb-112">int</span><span class="sxs-lookup"><span data-stu-id="4a1fb-112">int</span></span></p></td>
<td><p><span data-ttu-id="4a1fb-113">Numéro unique identifiant ce type et version de client.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a1fb-114"><strong>Version</strong></span><span class="sxs-lookup"><span data-stu-id="4a1fb-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="4a1fb-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4a1fb-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4a1fb-116">Représente l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a1fb-117"><strong>TypeClient</strong></span><span class="sxs-lookup"><span data-stu-id="4a1fb-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="4a1fb-118">int</span><span class="sxs-lookup"><span data-stu-id="4a1fb-118">int</span></span></p></td>
<td><p><span data-ttu-id="4a1fb-119">Type de client.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a1fb-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="4a1fb-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="4a1fb-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4a1fb-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4a1fb-122">Catégorie à laquelle le client appartient.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-122">Category that the client belongs to.</span></span> <span data-ttu-id="4a1fb-123">Par exemple, le client Conferencing_Attendant_1.0 appartient au CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="4a1fb-123">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

