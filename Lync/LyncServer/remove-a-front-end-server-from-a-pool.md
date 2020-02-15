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
ms.openlocfilehash: e3f8e2b2e395058d58d201177d2da08672a8d03f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="1337a-102">Supprimer un serveur frontal d’un pool</span><span class="sxs-lookup"><span data-stu-id="1337a-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1337a-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="1337a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="1337a-104">Le serveur frontal Microsoft Lync Server 2010 Enterprise Edition ne peut pas exister en tant qu’ordinateur autonome.</span><span class="sxs-lookup"><span data-stu-id="1337a-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="1337a-105">Il doit être défini en tant que pool frontal, même s’il n’y a qu’un seul ordinateur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="1337a-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="1337a-106">Cette rubrique vous guide tout au long du processus de suppression d’un serveur frontal individuel d’un pool frontal existant.</span><span class="sxs-lookup"><span data-stu-id="1337a-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="1337a-107">Si le serveur frontal est le dernier serveur du pool ou si vous supprimez complètement le pool, reportez-vous à la rubrique [supprimer un pool frontal ou un serveur Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="1337a-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="1337a-108">Il n’est pas nécessaire de supprimer les serveurs frontaux individuels avant de supprimer le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="1337a-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="1337a-109">Lorsque vous supprimez le pool, vous supprimez tous les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="1337a-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="1337a-110">Pour supprimer un serveur frontal d’un pool</span><span class="sxs-lookup"><span data-stu-id="1337a-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="1337a-111">Ouvrez le serveur frontal Lync Server 2013, puis ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="1337a-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="1337a-112">Accédez au nœud Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1337a-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="1337a-113">Développez **Pools frontaux Enterprise Edition**, développez le pool frontal avec le serveur frontal que vous souhaitez supprimer, cliquez avec le bouton droit sur le serveur frontal que vous souhaitez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1337a-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

