---
title: Supprimer un serveur frontal d’un pool
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Le serveur frontal ne peut exister qu’un ordinateur autonome. Il doit être défini comme un pool frontal, même si le pool ne contient qu’un seul ordinateur.
ms.openlocfilehash: a9f0adc991355b6f79b20365795ffaf92fa230e2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028942"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="b31a5-104">Supprimer un serveur frontal d’un pool</span><span class="sxs-lookup"><span data-stu-id="b31a5-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="b31a5-105">Le serveur frontal ne peut exister qu’un ordinateur autonome.</span><span class="sxs-lookup"><span data-stu-id="b31a5-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="b31a5-106">Il doit être défini comme un pool frontal, même si le pool ne contient qu’un seul ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b31a5-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="b31a5-107">Cette rubrique vous guide tout au long du processus de suppression d’un serveur frontal individuels à partir d’un pool frontal existant.</span><span class="sxs-lookup"><span data-stu-id="b31a5-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="b31a5-108">Si le serveur frontal est le dernier serveur du pool ou si vous supprimez entièrement le pool, voir [Supprimer le pool frontal ou Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="b31a5-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="b31a5-109">Il n’est pas nécessaire de supprimer les serveurs frontaux individuels avant de supprimer le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="b31a5-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="b31a5-110">Lorsque vous supprimez le pool, vous supprimez chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b31a5-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="b31a5-111">Pour supprimer un serveur frontal d’un pool</span><span class="sxs-lookup"><span data-stu-id="b31a5-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="b31a5-112">Sur Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b31a5-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="b31a5-113">Accédez au nœud installer hérité.</span><span class="sxs-lookup"><span data-stu-id="b31a5-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="b31a5-114">Développez **pools frontaux Enterprise Edition**, développez le pool frontal avec le serveur frontal que vous souhaitez supprimer, cliquez sur le serveur frontal que vous souhaitez supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b31a5-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

