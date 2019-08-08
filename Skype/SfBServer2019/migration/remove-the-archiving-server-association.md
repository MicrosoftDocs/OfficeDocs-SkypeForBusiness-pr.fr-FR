---
title: Supprimer l’association au serveur d’archivage
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Pour supprimer un serveur d’archivage, vous devez modifier ou effacer la dépendance sur le pool frontal associé, le serveur frontal, l’unité de branchement Survivable et le serveur de succursales survivant. Vous pouvez modifier les propriétés du pool frontal, du serveur frontal, de l’unité de branchement Survivable et du serveur de succursales survivant pour supprimer la dépendance. Une fois que vous avez effacé les dépendances et que vous avez supprimé le serveur dans le générateur de topologie, vous êtes informé que l’objet du magasin de base de données associé dans le générateur de topologie sera également supprimé.
ms.openlocfilehash: d6d7b7f53f9997b17893db079090e1837ce77f4d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244183"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="ffdcf-105">Supprimer l’association au serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="ffdcf-105">Remove the Archiving server association</span></span>

<span data-ttu-id="ffdcf-106">Pour supprimer un serveur d’archivage, vous devez modifier ou effacer le niveau de dépendance du pool frontal associé, du serveur frontal, de l’unité de branchement Survivable et du serveur de succursales survivant.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="ffdcf-107">Vous pouvez modifier les propriétés du pool frontal, du serveur frontal, de l’unité de branchement survivant et du serveur de succursales survivant pour supprimer la dépendance.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="ffdcf-108">Dès lors que vous effacez la dépendance et que vous avez supprimé le serveur dans le générateur de topologie, vous êtes informé que l’objet magasin de base de données associé dans le générateur de topologie sera également supprimé.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="ffdcf-109">Pour supprimer l’Association du serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="ffdcf-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="ffdcf-110">Sur le serveur frontal Skype entreprise Server 2019, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="ffdcf-111">Accédez au nœud d’installation hérité.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="ffdcf-112">Dans le générateur de topologie, développez **Pools front end Edition**, **serveurs front end Standard Edition**ou **sites**de succursales, selon l’emplacement de définition du serveur d’archivage.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="ffdcf-113">Si vous avez un serveur de succursales Survivable associé, développez **sites**de succursales, développez le nom du site de la succursale, puis développez **appareils de branchement survivables**.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ffdcf-114">Les **appareils de branchement survivables** dans l’interface utilisateur s’appliquent à la fois au serveur de succursales survivant et au dispositif de branchement survivant.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="ffdcf-115">Cliquez avec le bouton droit sur le pool, le serveur ou l’appareil associé au serveur d’archivage, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="ffdcf-116">Dans la boîte de **dialogue Modifier les propriétés**, sous**associations** **générales** > , désactivez la case à cocher **Associate Server** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="ffdcf-117">Répétez l’étape précédente pour tout autre serveur ou pool associé au serveur d’archivage que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="ffdcf-118">Cliquez avec le bouton droit sur le serveur d’archivage, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="ffdcf-119">Sur **Supprimer les magasins**dépendants, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="ffdcf-120">Publiez la topologie, vérifiez l’état de la connexion, puis exécutez l’Assistant Déploiement de Skype entreprise Server selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="ffdcf-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

