---
title: 'Lync Server 2013 : table de boîtes de dialogue'
description: 'Lync Server 2013 : table Dialogs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c2c9cf9ec59fc48f7f5ffc6232980e3f8aa68c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559700"
---
# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="15cba-103">Table Dialogs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15cba-103">Dialogs table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15cba-104">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="15cba-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="15cba-105">Le tableau Dialogs est une table de prise en charge qui stocke les informations sur DialogIDs pour les sessions d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="15cba-105">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15cba-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="15cba-106">Column</span></span></th>
<th><span data-ttu-id="15cba-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="15cba-107">Data Type</span></span></th>
<th><span data-ttu-id="15cba-108">Clé/index</span><span class="sxs-lookup"><span data-stu-id="15cba-108">Key/Index</span></span></th>
<th><span data-ttu-id="15cba-109">Détails</span><span class="sxs-lookup"><span data-stu-id="15cba-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15cba-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="15cba-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="15cba-111">DateHeure</span><span class="sxs-lookup"><span data-stu-id="15cba-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="15cba-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="15cba-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="15cba-113">Heure de la demande de session ; utilisé conjointement avec SessionIDSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="15cba-113">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15cba-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="15cba-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="15cba-115">int</span><span class="sxs-lookup"><span data-stu-id="15cba-115">int</span></span></p></td>
<td><p><span data-ttu-id="15cba-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="15cba-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="15cba-117">Numéro d’ID identifiant la session.</span><span class="sxs-lookup"><span data-stu-id="15cba-117">ID number to identify the session.</span></span> <span data-ttu-id="15cba-118">Utilisé conjointement avec SessionIDTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="15cba-118">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15cba-119"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="15cba-119"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="15cba-120">int</span><span class="sxs-lookup"><span data-stu-id="15cba-120">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15cba-121">Checksum du ExternalID.</span><span class="sxs-lookup"><span data-stu-id="15cba-121">Checksum of the ExternalID.</span></span> <span data-ttu-id="15cba-122">Ce champ est utilisé pour augmenter la vitesse des recherches dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="15cba-122">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15cba-123"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="15cba-123"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="15cba-124">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="15cba-124">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15cba-125">ID de boîte de dialogue SIP, stocké sous forme de fichier binaire.</span><span class="sxs-lookup"><span data-stu-id="15cba-125">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="15cba-126">Le format du fichier binaire est le suivant :</span><span class="sxs-lookup"><span data-stu-id="15cba-126">The format of the binary is:</span></span></p>
<p><span data-ttu-id="15cba-127">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="15cba-127">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="15cba-128">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="15cba-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

