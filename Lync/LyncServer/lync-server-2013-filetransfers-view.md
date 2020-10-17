---
title: 'Lync Server 2013 : vue FileTransfers'
description: 'Lync Server 2013 : vue FileTransfers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd2b084274a4d5daa093f2269617214f703ac03e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552620"
---
# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="373eb-103">Vue FileTransfers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="373eb-103">FileTransfers view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="373eb-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="373eb-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="373eb-105">L’affichage FileTransfer stocke des informations sur les sessions de transfert de fichiers P2P.</span><span class="sxs-lookup"><span data-stu-id="373eb-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="373eb-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="373eb-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="373eb-107">La vue FileTransfers contient toutes les colonnes de la <A href="lync-server-2013-sessiondetails-view.md">vue SessionDetails dans Lync Server 2013</A> , en plus des colonnes indiquées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="373eb-107">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="373eb-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="373eb-108">Column</span></span></th>
<th><span data-ttu-id="373eb-109">Type de données</span><span class="sxs-lookup"><span data-stu-id="373eb-109">Data Type</span></span></th>
<th><span data-ttu-id="373eb-110">Détails</span><span class="sxs-lookup"><span data-stu-id="373eb-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="373eb-111"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="373eb-111"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="373eb-112">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="373eb-112">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="373eb-113">Nom du fichier transféré.</span><span class="sxs-lookup"><span data-stu-id="373eb-113">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373eb-114"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="373eb-114"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="373eb-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="373eb-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="373eb-116">Utilisé pour identifier chaque message de suivi comme étant associé à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="373eb-116">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373eb-117"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="373eb-117"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="373eb-118">unique</span><span class="sxs-lookup"><span data-stu-id="373eb-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="373eb-119">Identificateur unique permettant de différencier les transferts de fichiers concernant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="373eb-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373eb-120"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="373eb-120"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="373eb-121">légèrement</span><span class="sxs-lookup"><span data-stu-id="373eb-121">bit</span></span></p></td>
<td><p><span data-ttu-id="373eb-p102">Peut-être TRUE ou NULL. Si TRUE, alors Reject et Cancel seront NULL.</span><span class="sxs-lookup"><span data-stu-id="373eb-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="373eb-124"><strong>Rejeter</strong></span><span class="sxs-lookup"><span data-stu-id="373eb-124"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="373eb-125">légèrement</span><span class="sxs-lookup"><span data-stu-id="373eb-125">bit</span></span></p></td>
<td><p><span data-ttu-id="373eb-p103">Peut-être TRUE ou NULL. Si TRUE, alors Accept et Cancel seront NULL.</span><span class="sxs-lookup"><span data-stu-id="373eb-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="373eb-128"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="373eb-128"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="373eb-129">légèrement</span><span class="sxs-lookup"><span data-stu-id="373eb-129">bit</span></span></p></td>
<td><p><span data-ttu-id="373eb-p104">Peut-être TRUE ou NULL. Si TRUE, alors Accept et Reject seront NULL.</span><span class="sxs-lookup"><span data-stu-id="373eb-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

