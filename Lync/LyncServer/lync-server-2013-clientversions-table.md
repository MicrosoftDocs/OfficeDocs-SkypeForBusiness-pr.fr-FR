---
title: 'Lync Server 2013 : table ClientVersions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96e8f035dbc0005bb331a188a308f456992f091
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="9b7c7-102">Table ClientVersions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b7c7-102">ClientVersions table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b7c7-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9b7c7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9b7c7-p101">La table ClientVersions est une table de prise en charge qui stocke la liste des divers types et versions de clients ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version de client.</span><span class="sxs-lookup"><span data-stu-id="9b7c7-p101">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b7c7-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="9b7c7-106">Column</span></span></th>
<th><span data-ttu-id="9b7c7-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="9b7c7-107">Data Type</span></span></th>
<th><span data-ttu-id="9b7c7-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="9b7c7-108">Key/Index</span></span></th>
<th><span data-ttu-id="9b7c7-109">Détails</span><span class="sxs-lookup"><span data-stu-id="9b7c7-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b7c7-110"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="9b7c7-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="9b7c7-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="9b7c7-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="9b7c7-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="9b7c7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9b7c7-113">Numéro unique identifiant le type et la version de ce client.</span><span class="sxs-lookup"><span data-stu-id="9b7c7-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b7c7-114"><strong>Version</strong></span><span class="sxs-lookup"><span data-stu-id="9b7c7-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="9b7c7-115"><strong>nvarchar (256)</strong></span><span class="sxs-lookup"><span data-stu-id="9b7c7-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b7c7-116">Nom de la version.</span><span class="sxs-lookup"><span data-stu-id="9b7c7-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b7c7-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9b7c7-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9b7c7-118">int</span><span class="sxs-lookup"><span data-stu-id="9b7c7-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b7c7-119">Spécifie le type de client utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="9b7c7-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="9b7c7-120">Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9b7c7-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="9b7c7-121">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9b7c7-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

