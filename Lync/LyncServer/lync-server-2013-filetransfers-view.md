---
title: 'Affichage Lync Server 2013: FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4228bbe42f2e7bcf88b26f9147e514f09c106ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="ef329-102">Affichage FileTransfers dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef329-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef329-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ef329-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ef329-104">Le mode FileTransfer stocke les informations sur les sessions d’égal à égal de transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ef329-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="ef329-105">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef329-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef329-106">Le mode FileTransfers contient toutes les colonnes de la <A href="lync-server-2013-sessiondetails-view.md">vue SessionDetails dans Lync Server 2013</A> , en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ef329-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef329-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="ef329-107">Column</span></span></th>
<th><span data-ttu-id="ef329-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="ef329-108">Data Type</span></span></th>
<th><span data-ttu-id="ef329-109">Détails</span><span class="sxs-lookup"><span data-stu-id="ef329-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef329-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="ef329-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="ef329-111">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ef329-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ef329-112">Nom du fichier transféré.</span><span class="sxs-lookup"><span data-stu-id="ef329-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef329-113"><strong>Sans</strong></span><span class="sxs-lookup"><span data-stu-id="ef329-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="ef329-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ef329-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ef329-115">Permet de détecter chaque message de suivi associé à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="ef329-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef329-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="ef329-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="ef329-117">identificateur</span><span class="sxs-lookup"><span data-stu-id="ef329-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ef329-118">Identificateur unique permettant de faire la distinction entre les transferts de fichiers impliquant le même nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="ef329-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef329-119"><strong>Valide</strong></span><span class="sxs-lookup"><span data-stu-id="ef329-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="ef329-120">bit</span><span class="sxs-lookup"><span data-stu-id="ef329-120">bit</span></span></p></td>
<td><p><span data-ttu-id="ef329-121">Peut être vrai ou nul.</span><span class="sxs-lookup"><span data-stu-id="ef329-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="ef329-122">Si vrai, l’argument refuser et annuler est nul.</span><span class="sxs-lookup"><span data-stu-id="ef329-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef329-123"><strong>Rejeter</strong></span><span class="sxs-lookup"><span data-stu-id="ef329-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="ef329-124">bit</span><span class="sxs-lookup"><span data-stu-id="ef329-124">bit</span></span></p></td>
<td><p><span data-ttu-id="ef329-125">Peut être vrai ou nul.</span><span class="sxs-lookup"><span data-stu-id="ef329-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="ef329-126">Si vrai, l’argument accepter et annuler est nul.</span><span class="sxs-lookup"><span data-stu-id="ef329-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef329-127"><strong>Annuler</strong></span><span class="sxs-lookup"><span data-stu-id="ef329-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="ef329-128">bit</span><span class="sxs-lookup"><span data-stu-id="ef329-128">bit</span></span></p></td>
<td><p><span data-ttu-id="ef329-129">Peut être vrai ou nul.</span><span class="sxs-lookup"><span data-stu-id="ef329-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="ef329-130">Si vrai, l’argument accepter et refuser est nul.</span><span class="sxs-lookup"><span data-stu-id="ef329-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

