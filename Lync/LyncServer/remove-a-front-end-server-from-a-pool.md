---
title: Supprimer un serveur frontal d’un pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0637754c6e7b1a03c233025703297c182dc3099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="8977d-102">Supprimer un serveur frontal d’un pool</span><span class="sxs-lookup"><span data-stu-id="8977d-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8977d-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="8977d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="8977d-104">Le serveur principal Microsoft Lync Server 2010 Enterprise Edition ne peut pas exister en tant qu’ordinateur autonome.</span><span class="sxs-lookup"><span data-stu-id="8977d-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="8977d-105">Elle doit être définie en tant que pool frontal, même s’il n’y a qu’un seul ordinateur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="8977d-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="8977d-106">Cette rubrique vous guide tout au long du processus de suppression d’un serveur frontal individuel d’un pool frontal existant.</span><span class="sxs-lookup"><span data-stu-id="8977d-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="8977d-107">Si le serveur frontal est le dernier serveur du pool ou si vous supprimez entièrement le pool, voir supprimer le [pool frontal ou le serveur Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="8977d-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="8977d-108">Il n’est pas nécessaire de supprimer les serveurs front-end individuels avant de supprimer le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="8977d-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="8977d-109">Lorsque vous supprimez le pool, vous supprimez chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="8977d-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="8977d-110">Pour supprimer un serveur frontal d’un pool</span><span class="sxs-lookup"><span data-stu-id="8977d-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="8977d-111">Ouvrez le serveur frontal Lync Server 2013, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="8977d-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="8977d-112">Accédez au nœud Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8977d-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="8977d-113">Développez **Pools front-end Enterprise Edition**, développez le pool frontal du serveur frontal que vous voulez supprimer, cliquez avec le bouton droit sur le serveur frontal que vous voulez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="8977d-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

