---
title: Supprimer un serveur frontal d’un pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Le serveur frontal ne peut pas exister en tant qu’ordinateur autonome. Elle doit être définie en tant que pool frontal, même s’il n’y a qu’un seul ordinateur dans le pool.
ms.openlocfilehash: 93df9e293f7a1876d4a8b1f172472f708556f67f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813032"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="72975-104">Supprimer un serveur frontal d’un pool</span><span class="sxs-lookup"><span data-stu-id="72975-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="72975-105">Le serveur frontal ne peut pas exister en tant qu’ordinateur autonome.</span><span class="sxs-lookup"><span data-stu-id="72975-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="72975-106">Elle doit être définie en tant que pool frontal, même s’il n’y a qu’un seul ordinateur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="72975-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="72975-107">Cette rubrique vous guide tout au long du processus de suppression d’un serveur frontal individuel d’un pool frontal existant.</span><span class="sxs-lookup"><span data-stu-id="72975-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="72975-108">Si le serveur frontal est le dernier serveur du pool ou si vous supprimez entièrement le pool, voir supprimer le [pool frontal ou le serveur Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="72975-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="72975-109">Il n’est pas nécessaire de supprimer les serveurs front-end individuels avant de supprimer le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="72975-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="72975-110">Lorsque vous supprimez le pool, vous supprimez chaque serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="72975-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="72975-111">Pour supprimer un serveur frontal d’un pool</span><span class="sxs-lookup"><span data-stu-id="72975-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="72975-112">Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="72975-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="72975-113">Accédez au nœud d’installation hérité.</span><span class="sxs-lookup"><span data-stu-id="72975-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="72975-114">Développez **Pools front-end Enterprise Edition**, développez le pool frontal du serveur frontal que vous voulez supprimer, cliquez avec le bouton droit sur le serveur frontal que vous voulez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="72975-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

