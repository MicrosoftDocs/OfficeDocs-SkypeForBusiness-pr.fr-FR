---
title: Supprimer l’association au serveur de surveillance
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
description: Pour supprimer le serveur de surveillance, vous devez modifier ou effacer la dépendance sur le pool frontal associé, le serveur frontal, l’unité de branchement Survivable et le serveur de succursales survivant. Vous pouvez modifier les propriétés du pool frontal, du serveur frontal, de l’unité de branchement Survivable et du serveur de succursales survivant pour supprimer la dépendance. Dès lors que vous effacez la dépendance et que vous avez supprimé le serveur dans le générateur de topologie, vous êtes informé que l’objet magasin de base de données associé dans le générateur de topologie sera également supprimé.
ms.openlocfilehash: aed16d60fbdae2413cb7890e38895bf6930cd4fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812862"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="60cb1-105">Supprimer l’association au serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="60cb1-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="60cb1-106">Pour supprimer le serveur de surveillance, vous devez modifier ou effacer la dépendance sur le pool frontal associé, le serveur frontal, l’unité de branchement Survivable et le serveur de succursales survivant.</span><span class="sxs-lookup"><span data-stu-id="60cb1-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="60cb1-107">Vous pouvez modifier les propriétés du pool frontal, du serveur frontal, de l’unité de branchement survivant et du serveur de succursales survivant pour supprimer la dépendance.</span><span class="sxs-lookup"><span data-stu-id="60cb1-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="60cb1-108">Dès lors que vous effacez la dépendance et que vous avez supprimé le serveur dans le générateur de topologie, vous êtes informé que l’objet magasin de base de données associé dans le générateur de topologie sera également supprimé.</span><span class="sxs-lookup"><span data-stu-id="60cb1-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="60cb1-109">Pour supprimer l’Association du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="60cb1-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="60cb1-110">Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="60cb1-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="60cb1-111">Accédez au nœud installations héritées.</span><span class="sxs-lookup"><span data-stu-id="60cb1-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="60cb1-112">Dans le générateur de topologie, développez **Pools front end Edition**, **serveurs front end Standard Edition**ou **sites de succursale**, selon l’endroit où le serveur de surveillance est défini.</span><span class="sxs-lookup"><span data-stu-id="60cb1-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="60cb1-113">Si vous avez un serveur de succursales Survivable associé, développez **sites de succursales**, développez le nom du site de la succursale, puis développez **appareils de branchement survivables**.</span><span class="sxs-lookup"><span data-stu-id="60cb1-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="60cb1-114">Les **appareils de branchement survivables** dans l’interface utilisateur s’appliquent à la fois au serveur de succursales survivant et au dispositif de branchement survivant.</span><span class="sxs-lookup"><span data-stu-id="60cb1-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="60cb1-115">Cliquez avec le bouton droit sur le pool, le serveur ou l’appareil associé au serveur de surveillance, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="60cb1-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="60cb1-116">Dans la boîte de **dialogue Modifier les propriétés**, sous**associations** **générales** > , désactivez la case à cocher **associer le serveur de suivi** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="60cb1-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="60cb1-117">Répétez l’étape précédente pour tout autre serveur ou pool associé au serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="60cb1-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="60cb1-118">Cliquez avec le bouton droit sur le serveur de surveillance, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="60cb1-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="60cb1-119">Sur **Supprimer les magasins dépendants**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="60cb1-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="60cb1-120">Publiez la topologie, vérifiez l’état de la réplication et exécutez l’Assistant Déploiement de Skype entreprise Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="60cb1-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

