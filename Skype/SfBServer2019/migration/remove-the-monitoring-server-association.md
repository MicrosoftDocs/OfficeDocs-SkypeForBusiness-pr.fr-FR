---
title: Supprimer l’association du serveur de surveillance
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Pour supprimer le serveur de surveillance, vous devez modifier ou supprimer la dépendance au pool frontal associé, le serveur frontal, Survivable Branch Appliance et serveur Survivable Branch Server. Vous modifiez les propriétés du pool frontal, serveur frontal et serveur Survivable Branch Server Survivable Branch Appliance pour supprimer la dépendance. Une fois que vous désactivez la dépendance et supprimez le serveur dans le Générateur de topologie, vous êtes averti que l’objet de magasin de base de données associée dans le Générateur de topologie est également supprimé.
ms.openlocfilehash: 01fb53a054da8f9e39dbbfbdd1ddfc08f345a1c2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030384"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="5b6e0-105">Supprimer l’association du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="5b6e0-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="5b6e0-106">Pour supprimer le serveur de surveillance, vous devez modifier ou supprimer la dépendance associée Front-End pool, serveur frontal, Survivable Branch Appliance, les Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="5b6e0-107">Vous modifiez les propriétés du pool frontal, serveur frontal, Survivable Branch Appliance et serveur Survivable Branch Server permet de supprimer la dépendance.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="5b6e0-108">Une fois que vous désactivez la dépendance et supprimez le serveur dans le Générateur de topologie, vous êtes averti que l’objet de magasin de base de données associée dans le Générateur de topologie est également supprimé.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="5b6e0-109">Pour supprimer l’association du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="5b6e0-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="5b6e0-110">Sur Skype pour Business Server 2019 serveur frontal, ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="5b6e0-111">Naviguez jusqu’au nœud de l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="5b6e0-112">Dans le Générateur de topologie, développez **pools frontaux Enterprise Edition**, **Standard Edition serveurs frontaux**ou **sites de succursale**, selon l’emplacement où le serveur de surveillance est défini.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="5b6e0-113">Si vous avez un serveur Survivable Branch Server associé, développez **sites de succursale**, développez le nom de site de succursale, puis développez **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5b6e0-114">**Survivable Branch Appliances** dans l’interface utilisateur s’applique à la fois un serveur Survivable Branch Server et Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="5b6e0-115">Cliquez sur le pool, le serveur ou le périphérique qui est associé avec le serveur de surveillance, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="5b6e0-116">Dans **Modifier les propriétés**, sous **Général** > **Associations**, désactivez la case à cocher **Associer un serveur de surveillance** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="5b6e0-117">Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé avec le serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="5b6e0-118">Cliquez sur le serveur de surveillance, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="5b6e0-119">**Supprimer les magasins dépendants**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="5b6e0-120">Publiez la topologie, vérifiez le statut de réplication et exécuter la Skype pour l’Assistant de déploiement de serveur Business selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="5b6e0-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

