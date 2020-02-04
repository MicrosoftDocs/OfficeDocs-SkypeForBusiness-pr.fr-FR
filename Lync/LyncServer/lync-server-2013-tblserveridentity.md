---
title: 'Lync Server 2013 : tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2379622ee5b1121367c35b4baac98d6c79d61023
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="e3e8b-102">tblServerIdentity dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3e8b-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3e8b-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e3e8b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e3e8b-104">tblServerIdentity contient les serveurs de chat actifs dans le pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="e3e8b-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="e3e8b-105">Celles</span><span class="sxs-lookup"><span data-stu-id="e3e8b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3e8b-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="e3e8b-106">Column</span></span></th>
<th><span data-ttu-id="e3e8b-107">Type</span><span class="sxs-lookup"><span data-stu-id="e3e8b-107">Type</span></span></th>
<th><span data-ttu-id="e3e8b-108">Description</span><span class="sxs-lookup"><span data-stu-id="e3e8b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3e8b-109">serverID</span><span class="sxs-lookup"><span data-stu-id="e3e8b-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="e3e8b-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="e3e8b-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e3e8b-111">ID du serveur.</span><span class="sxs-lookup"><span data-stu-id="e3e8b-111">Server ID.</span></span> <span data-ttu-id="e3e8b-112">Correspond à l’ID de l’instance du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="e3e8b-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3e8b-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="e3e8b-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="e3e8b-114">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="e3e8b-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="e3e8b-115">Adresse du serveur à l’aide de l’adresse Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="e3e8b-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3e8b-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="e3e8b-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="e3e8b-117">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e3e8b-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3e8b-118">Dernière mise à jour de cette ligne par le serveur de canal pour indiquer qu’il est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="e3e8b-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e3e8b-119">Clé</span><span class="sxs-lookup"><span data-stu-id="e3e8b-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3e8b-120">Colonne</span><span class="sxs-lookup"><span data-stu-id="e3e8b-120">Column</span></span></th>
<th><span data-ttu-id="e3e8b-121">Description</span><span class="sxs-lookup"><span data-stu-id="e3e8b-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3e8b-122">serverID</span><span class="sxs-lookup"><span data-stu-id="e3e8b-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="e3e8b-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="e3e8b-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

