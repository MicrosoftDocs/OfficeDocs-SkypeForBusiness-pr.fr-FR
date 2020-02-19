---
title: 'Lync Server 2013 : table de boîtes de dialogue'
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
ms.openlocfilehash: bf2f23e9c82c1c6d4dd21519f1193b902c8e6434
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="96867-102">Table Dialogs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96867-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96867-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="96867-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="96867-104">Le tableau Dialogs est une table de prise en charge qui stocke les informations sur DialogIDs pour les sessions d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="96867-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96867-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="96867-105">Column</span></span></th>
<th><span data-ttu-id="96867-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="96867-106">Data Type</span></span></th>
<th><span data-ttu-id="96867-107">Clé/index</span><span class="sxs-lookup"><span data-stu-id="96867-107">Key/Index</span></span></th>
<th><span data-ttu-id="96867-108">Détails</span><span class="sxs-lookup"><span data-stu-id="96867-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96867-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="96867-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96867-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="96867-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="96867-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="96867-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="96867-112">Heure de la demande de session ; utilisé conjointement avec SessionIDSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="96867-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96867-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="96867-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="96867-114">int</span><span class="sxs-lookup"><span data-stu-id="96867-114">int</span></span></p></td>
<td><p><span data-ttu-id="96867-115">Primaire</span><span class="sxs-lookup"><span data-stu-id="96867-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="96867-116">Numéro d’ID identifiant la session.</span><span class="sxs-lookup"><span data-stu-id="96867-116">ID number to identify the session.</span></span> <span data-ttu-id="96867-117">Utilisé conjointement avec SessionIDTime pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="96867-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96867-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="96867-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="96867-119">int</span><span class="sxs-lookup"><span data-stu-id="96867-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96867-120">Checksum du ExternalID.</span><span class="sxs-lookup"><span data-stu-id="96867-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="96867-121">Ce champ est utilisé pour augmenter la vitesse des recherches dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="96867-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96867-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="96867-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="96867-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="96867-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96867-124">ID de boîte de dialogue SIP, stocké sous forme de fichier binaire.</span><span class="sxs-lookup"><span data-stu-id="96867-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="96867-125">Le format du fichier binaire est le suivant :</span><span class="sxs-lookup"><span data-stu-id="96867-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="96867-126">boîte de dialogue ; balise ; à-tag</span><span class="sxs-lookup"><span data-stu-id="96867-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="96867-127">Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="96867-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

