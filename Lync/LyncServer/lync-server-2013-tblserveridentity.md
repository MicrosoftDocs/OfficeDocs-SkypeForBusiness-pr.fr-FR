---
title: 'Lync Server 2013 : tblServerIdentity'
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
ms.openlocfilehash: 206efe412712d2acb311b951bd0554bed3c9f650
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536231"
---
# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="9c134-102">tblServerIdentity dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c134-102">tblServerIdentity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c134-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9c134-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9c134-104">tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="9c134-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="9c134-105">Colonnes</span><span class="sxs-lookup"><span data-stu-id="9c134-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c134-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="9c134-106">Column</span></span></th>
<th><span data-ttu-id="9c134-107">Type</span><span class="sxs-lookup"><span data-stu-id="9c134-107">Type</span></span></th>
<th><span data-ttu-id="9c134-108">Description</span><span class="sxs-lookup"><span data-stu-id="9c134-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c134-109">serverID</span><span class="sxs-lookup"><span data-stu-id="9c134-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="9c134-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="9c134-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9c134-111">ID de serveur.</span><span class="sxs-lookup"><span data-stu-id="9c134-111">Server ID.</span></span> <span data-ttu-id="9c134-112">Correspond à l’ID d’instance dans le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="9c134-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c134-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="9c134-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="9c134-114">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="9c134-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="9c134-115">Adresse de serveur utilisant l’adresse WCF (Windows Communication Foundation).</span><span class="sxs-lookup"><span data-stu-id="9c134-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c134-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="9c134-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="9c134-117">DateHeure</span><span class="sxs-lookup"><span data-stu-id="9c134-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c134-118">Dernière fois où le serveur de canal a mis à jour cette ligne pour faire la preuve de son exécution.</span><span class="sxs-lookup"><span data-stu-id="9c134-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="9c134-119">Clé</span><span class="sxs-lookup"><span data-stu-id="9c134-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c134-120">Colonne</span><span class="sxs-lookup"><span data-stu-id="9c134-120">Column</span></span></th>
<th><span data-ttu-id="9c134-121">Description</span><span class="sxs-lookup"><span data-stu-id="9c134-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c134-122">serverID</span><span class="sxs-lookup"><span data-stu-id="9c134-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="9c134-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="9c134-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

