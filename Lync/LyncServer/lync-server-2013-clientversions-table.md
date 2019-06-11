---
title: 'Lync Server 2013 : Table ClientVersions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba578209ca6c22360da73c2317334ecf77da569
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="c0655-102">Table ClientVersions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0655-102">ClientVersions table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0655-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c0655-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c0655-104">La table ClientVersions est une table qui contient une liste des différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c0655-104">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c0655-105">Chaque enregistrement de la table représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="c0655-105">Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0655-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="c0655-106">Column</span></span></th>
<th><span data-ttu-id="c0655-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="c0655-107">Data Type</span></span></th>
<th><span data-ttu-id="c0655-108">Clé/Index</span><span class="sxs-lookup"><span data-stu-id="c0655-108">Key/Index</span></span></th>
<th><span data-ttu-id="c0655-109">Détails</span><span class="sxs-lookup"><span data-stu-id="c0655-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0655-110"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="c0655-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="c0655-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="c0655-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="c0655-112">Principal</span><span class="sxs-lookup"><span data-stu-id="c0655-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c0655-113">Numéro unique identifiant ce type et version de client.</span><span class="sxs-lookup"><span data-stu-id="c0655-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0655-114"><strong>Version</strong></span><span class="sxs-lookup"><span data-stu-id="c0655-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="c0655-115"><strong>nvarchar(256)</strong></span><span class="sxs-lookup"><span data-stu-id="c0655-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0655-116">Nom de la version.</span><span class="sxs-lookup"><span data-stu-id="c0655-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0655-117"><strong>TypeClient</strong></span><span class="sxs-lookup"><span data-stu-id="c0655-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c0655-118">int</span><span class="sxs-lookup"><span data-stu-id="c0655-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c0655-119">Spécifie le type de client utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="c0655-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="c0655-120">Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c0655-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="c0655-121">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c0655-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

