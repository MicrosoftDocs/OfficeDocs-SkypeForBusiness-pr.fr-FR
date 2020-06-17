---
title: Supprimer l’association au serveur d’archivage
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
description: Pour supprimer un serveur d’archivage, vous devez modifier ou supprimer la dépendance sur le pool frontal associé, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server. Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch appliance et du serveur Survivable Branch Server pour supprimer la dépendance. Une fois que vous avez effacé la dépendance et supprimé le serveur dans le générateur de topologies, vous êtes informé que l’objet de magasin de bases de données associé dans le générateur de topologies est également supprimé.
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752136"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="30597-105">Supprimer l’association au serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="30597-105">Remove the Archiving server association</span></span>

<span data-ttu-id="30597-106">Pour supprimer un serveur d’archivage, vous devez modifier ou supprimer la dépendance sur le pool frontal associé, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="30597-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="30597-107">Vous modifiez les propriétés du pool frontal, le serveur frontal, le Survivable Branch appliance et le serveur Survivable Branch Server pour supprimer la dépendance.</span><span class="sxs-lookup"><span data-stu-id="30597-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="30597-108">Une fois que vous avez effacé la dépendance et supprimé le serveur dans le générateur de topologies, vous êtes informé que l’objet de magasin de bases de données associé dans le générateur de topologies est également supprimé.</span><span class="sxs-lookup"><span data-stu-id="30597-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="30597-109">Pour supprimer l’association au serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="30597-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="30597-110">Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="30597-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="30597-111">Naviguez jusqu’au nœud d’installation hérité.</span><span class="sxs-lookup"><span data-stu-id="30597-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="30597-112">Dans le générateur de topologies, développez **Pools frontaux Enterprise Edition**, **serveurs frontaux Standard Edition**ou **sites de succursale**, en fonction de l’emplacement où est défini le serveur d’archivage.</span><span class="sxs-lookup"><span data-stu-id="30597-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="30597-113">Si vous avez un serveur Survivable Branch Server associé, développez **sites de succursale**, développez le nom du site de succursale, puis développez **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="30597-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="30597-114">**Survivable Branch Appliances** dans l’interface utilisateur s’applique aux serveurs Survivable Branch Server et Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="30597-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="30597-115">Cliquez avec le bouton droit sur le pool, le serveur ou le périphérique associé au serveur d’archivage, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="30597-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="30597-116">Dans **modifier les propriétés**, **General**sous  >  **associations**générales, désactivez la case à cocher associer un **serveur d’archivage** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="30597-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="30597-117">Répétez l’étape précédente pour tout autre pool, serveur ou appareil associé au serveur d’archivage que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="30597-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="30597-118">Cliquez avec le bouton droit sur le serveur d’archivage, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="30597-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="30597-119">Dans **Supprimer les magasins dépendants**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="30597-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="30597-120">Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Skype entreprise Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="30597-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

