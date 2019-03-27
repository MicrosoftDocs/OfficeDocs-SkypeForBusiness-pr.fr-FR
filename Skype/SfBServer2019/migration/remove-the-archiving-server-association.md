---
title: Supprimer l’association au serveur d’archivage
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Pour supprimer un serveur d’archivage, vous devez modifier ou supprimer la dépendance au pool frontal associé, le serveur frontal, Survivable Branch Appliance et serveur Survivable Branch Server. Vous modifiez les propriétés du pool frontal, serveur frontal et serveur Survivable Branch Server Survivable Branch Appliance pour supprimer la dépendance. Une fois que vous désactivez la dépendance et vous supprimez le serveur dans le Générateur de topologie, vous êtes averti que l’objet de magasin de base de données associée dans le Générateur de topologie est également supprimé.
ms.openlocfilehash: 15e6b33decb11ce7ed4550b0d84cc346a0baf073
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884399"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="93958-105">Supprimer l’association au serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="93958-105">Remove the Archiving server association</span></span>

<span data-ttu-id="93958-106">Pour supprimer un serveur d’archivage, vous devez modifier ou supprimer la dépendance associée Front-End pool, serveur frontal, Survivable Branch Appliance, les Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="93958-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="93958-107">Vous modifiez les propriétés du pool frontal, serveur frontal, Survivable Branch Appliance et serveur Survivable Branch Server permet de supprimer la dépendance.</span><span class="sxs-lookup"><span data-stu-id="93958-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="93958-108">Une fois que vous désactivez la dépendance et supprimez le serveur dans le Générateur de topologie, vous êtes averti que l’objet de magasin de base de données associée dans le Générateur de topologie est également supprimé.</span><span class="sxs-lookup"><span data-stu-id="93958-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="93958-109">Pour supprimer l’association du serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="93958-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="93958-110">Sur Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="93958-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="93958-111">Accédez au nœud installer hérité.</span><span class="sxs-lookup"><span data-stu-id="93958-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="93958-112">Dans le Générateur de topologie, développez **pools frontaux Enterprise Edition**, **Standard Edition serveurs frontaux**ou **sites de succursale**, selon l’emplacement où le serveur d’archivage est défini.</span><span class="sxs-lookup"><span data-stu-id="93958-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="93958-113">Si vous avez un serveur Survivable Branch Server associé, développez **sites de succursale**, développez le nom de site de succursale, puis développez **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="93958-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="93958-114">**Survivable Branch Appliances** dans l’interface utilisateur s’applique à la fois un serveur Survivable Branch Server et Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="93958-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="93958-115">Cliquez sur le pool, le serveur ou le périphérique qui est associé avec le serveur d’archivage, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="93958-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="93958-116">Dans **Modifier les propriétés**, sous **Général** > **Associations**, désactivez la case à cocher **Associer un serveur d’archivage** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="93958-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="93958-117">Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé avec le serveur d’archivage que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="93958-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="93958-118">Cliquez sur le serveur d’archivage, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="93958-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="93958-119">**Supprimer les magasins dépendants**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="93958-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="93958-120">Publier la topologie, vérifiez le statut de réplication et exécutez le Skype pour l’Assistant de déploiement Business Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="93958-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

