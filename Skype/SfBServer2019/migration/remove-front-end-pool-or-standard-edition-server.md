---
title: Supprimer un pool frontal ou un serveur Standard Edition
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cette rubrique vous guide tout au long du processus de suppression d’un pool frontal ou d’un serveur frontal Standard Edition. Lorsque vous supprimez un pool frontal, vous supprimez tous les serveurs frontaux qui appartiennent au pool dans le cadre du processus de suppression du pool. Lorsque vous supprimez un serveur frontal Standard Edition, vous devez supprimer la définition du magasin SQL du générateur de topologies.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752276"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="6c836-105">Supprimer un pool frontal ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6c836-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="6c836-106">Cet article vous guide tout au long du processus de suppression d’un pool frontal ou d’un serveur frontal Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6c836-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="6c836-107">Lorsque vous supprimez un pool frontal, vous supprimez tous les serveurs frontaux qui appartiennent au pool dans le cadre du processus de suppression du pool.</span><span class="sxs-lookup"><span data-stu-id="6c836-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="6c836-108">Lorsque vous supprimez un serveur frontal Standard Edition, vous devez supprimer la définition du magasin SQL du générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="6c836-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="6c836-109">Pour supprimer un pool de serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="6c836-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="6c836-110">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="6c836-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="6c836-111">Accédez au nœud hérité.</span><span class="sxs-lookup"><span data-stu-id="6c836-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="6c836-112">Développez **Pools frontaux Enterprise Edition**, développez le pool frontal, cliquez avec le bouton droit sur le pool frontal que vous souhaitez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6c836-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="6c836-113">Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement hérité selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6c836-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="6c836-114">Pour supprimer un serveur frontal Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6c836-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="6c836-115">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="6c836-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="6c836-116">Accédez au nœud installations héritées.</span><span class="sxs-lookup"><span data-stu-id="6c836-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="6c836-117">Développez **serveurs frontaux Standard Edition**, cliquez avec le bouton droit sur le serveur frontal que vous souhaitez supprimer, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6c836-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="6c836-118">Développez **magasins SQL**, cliquez avec le bouton droit sur la base de données SQL Server associée au serveur frontal Standard Edition, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6c836-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6c836-119">Vous devez supprimer la définition des bases de données SQL Server colocalisées à partir du serveur frontal Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6c836-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="6c836-120">Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6c836-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

