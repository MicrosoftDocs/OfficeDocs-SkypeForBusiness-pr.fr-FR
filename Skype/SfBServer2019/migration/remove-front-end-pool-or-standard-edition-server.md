---
title: Supprimer un pool frontal ou un serveur Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cette rubrique vous guide tout au long du processus de suppression d’un pool frontal ou un serveur Standard Edition serveur frontal. Lorsque vous supprimez un pool frontal, vous supprimez chaque serveur frontal qui appartient au pool dans le cadre du processus de suppression de pool. Lorsque vous supprimez un serveur Standard Edition serveur frontal, vous devez supprimer la définition d’un magasin SQL du Générateur de topologie.
ms.openlocfilehash: 394edcd6f5c89478ed98abebe0be29720d009107
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231545"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="c3000-105">Supprimer un pool frontal ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c3000-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="c3000-106">Cet article vous guide tout au long du processus de suppression d’un pool frontal ou un serveur Standard Edition serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c3000-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="c3000-107">Lorsque vous supprimez un pool frontal, vous supprimez chaque serveur frontal qui appartient au pool dans le cadre du processus de suppression de pool.</span><span class="sxs-lookup"><span data-stu-id="c3000-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="c3000-108">Lorsque vous supprimez un serveur Standard Edition serveur frontal, vous devez supprimer la définition d’un magasin SQL du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c3000-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="c3000-109">Pour supprimer un pool de serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="c3000-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="c3000-110">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c3000-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="c3000-111">Naviguez jusqu’au nœud hérité.</span><span class="sxs-lookup"><span data-stu-id="c3000-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="c3000-112">Développez **pools frontaux Enterprise Edition**, développez le pool frontal, cliquez sur le pool frontal que vous souhaitez supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="c3000-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="c3000-113">Publiez la topologie, vérifier l’état de réplication, puis exécutez l’Assistant de déploiement hérité selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="c3000-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="c3000-114">Pour supprimer un serveur frontal Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c3000-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="c3000-115">Ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="c3000-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="c3000-116">Naviguez jusqu’au nœud de l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="c3000-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="c3000-117">Développez **serveurs frontaux Standard Edition**, cliquez sur le serveur frontal que vous souhaitez supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="c3000-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="c3000-118">Développez **SQL stocke**, avec le bouton droit de la base de données SQL Server qui est associé avec le serveur Standard Edition serveur frontal, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="c3000-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c3000-119">Vous devez supprimer la définition des bases de données SQL Server COLOCALISÉES de Standard Edition serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c3000-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="c3000-120">Publiez la topologie, vérifier l’état de réplication, puis exécutez l’Assistant Déploiement selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="c3000-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

