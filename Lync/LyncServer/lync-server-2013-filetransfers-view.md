---
title: 'Lync Server 2013 : vue FileTransfers'
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
ms.openlocfilehash: 95cc6790766d68ee478cf1b80326c974f7c15f1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="7f4ae-102">Vue FileTransfers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f4ae-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f4ae-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7f4ae-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7f4ae-104">L’affichage FileTransfer stocke des informations sur les sessions de transfert de fichiers P2P.</span><span class="sxs-lookup"><span data-stu-id="7f4ae-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="7f4ae-105">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f4ae-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7f4ae-106">La vue FileTransfers contient toutes les colonnes de la <A href="lync-server-2013-sessiondetails-view.md">vue SessionDetails dans Lync Server 2013</A> , en plus des colonnes indiquées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7f4ae-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f4ae-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="7f4ae-107">Column</span></span></th>
<th><span data-ttu-id="7f4ae-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="7f4ae-108">Data Type</span></span></th>
<th><span data-ttu-id="7f4ae-109">Détails</span><span class="sxs-lookup"><span data-stu-id="7f4ae-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f4ae-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="7f4ae-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="7f4ae-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7f4ae-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7f4ae-112">Nom du fichier transféré.</span><span class="sxs-lookup"><span data-stu-id="7f4ae-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f4ae-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="7f4ae-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="7f4ae-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="7f4ae-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7f4ae-115">Utilisé pour identifier chaque message de suivi comme étant associé à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="7f4ae-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f4ae-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="7f4ae-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="7f4ae-117">unique</span><span class="sxs-lookup"><span data-stu-id="7f4ae-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="7f4ae-118">Identificateur unique permettant de différencier les transferts de fichiers concernant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="7f4ae-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f4ae-119"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="7f4ae-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="7f4ae-120">légèrement</span><span class="sxs-lookup"><span data-stu-id="7f4ae-120">bit</span></span></p></td>
<td><p><span data-ttu-id="7f4ae-p102">Peut-être TRUE ou NULL. Si TRUE, alors Reject et Cancel seront NULL.</span><span class="sxs-lookup"><span data-stu-id="7f4ae-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f4ae-123"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="7f4ae-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="7f4ae-124">légèrement</span><span class="sxs-lookup"><span data-stu-id="7f4ae-124">bit</span></span></p></td>
<td><p><span data-ttu-id="7f4ae-p103">Peut-être TRUE ou NULL. Si TRUE, alors Accept et Cancel seront NULL.</span><span class="sxs-lookup"><span data-stu-id="7f4ae-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f4ae-127"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="7f4ae-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="7f4ae-128">légèrement</span><span class="sxs-lookup"><span data-stu-id="7f4ae-128">bit</span></span></p></td>
<td><p><span data-ttu-id="7f4ae-p104">Peut-être TRUE ou NULL. Si TRUE, alors Accept et Reject seront NULL.</span><span class="sxs-lookup"><span data-stu-id="7f4ae-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

