---
title: Supprimer l’association au serveur de surveillance
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
description: Pour supprimer le serveur de surveillance, vous devez modifier ou effacer la dépendance sur le pool frontal, le serveur frontal, le Survivable Branch Appliance et le serveur Survivable Branch Server associés. Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server pour supprimer la dépendance. Après avoir effacé la dépendance et supprimé le serveur dans le Générateur de topologie, vous êtes informé que l’objet magasin de bases de données associé dans le Générateur de topologie sera également supprimé.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753416"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="5a537-105">Supprimer l’association au serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="5a537-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="5a537-106">Pour supprimer le serveur de surveillance, vous devez modifier ou effacer la dépendance vis-à-vis du pool frontal, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server associés.</span><span class="sxs-lookup"><span data-stu-id="5a537-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="5a537-107">Vous modifiez les propriétés du pool frontal, du serveur frontal, du Survivable Branch Appliance et du serveur Survivable Branch Server pour supprimer la dépendance.</span><span class="sxs-lookup"><span data-stu-id="5a537-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="5a537-108">Après avoir effacé la dépendance et supprimé le serveur dans le Générateur de topologie, vous êtes informé que l’objet magasin de bases de données associé dans le Générateur de topologie sera également supprimé.</span><span class="sxs-lookup"><span data-stu-id="5a537-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="5a537-109">Pour supprimer l’association du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="5a537-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="5a537-110">Sur le serveur frontal Skype Entreprise Server 2019, ouvrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="5a537-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="5a537-111">Accédez au nœud d’installation hérité.</span><span class="sxs-lookup"><span data-stu-id="5a537-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="5a537-112">Dans le Générateur de topologie, développez les pools frontux **Enterprise Edition,** les serveurs frontux **Standard Edition** ou les **sites** de succursale, en fonction de l’emplacement où le serveur de surveillance est défini.</span><span class="sxs-lookup"><span data-stu-id="5a537-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="5a537-113">Si vous avez un serveur Survivable Branch Server associé, développez sites de **succursale,** développez le nom du site de succursale, puis développez **Survivable Branch Appliances**.</span><span class="sxs-lookup"><span data-stu-id="5a537-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5a537-114">**Les Survivable Branch Appliances de** l’interface utilisateur s’appliquent au Serveur Survivable Branch Server et au Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="5a537-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="5a537-115">Cliquez avec le bouton droit sur le pool, le serveur ou l’appareil associé au serveur de surveillance, puis cliquez sur **Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="5a537-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="5a537-116">Dans **Modifier les propriétés,** sous **Associations**  >  **générales,** cochez la case Associer un serveur de surveillance, puis cliquez sur **OK.** </span><span class="sxs-lookup"><span data-stu-id="5a537-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="5a537-117">Répétez l’étape précédente pour tout autre pool, serveur ou périphérique associé au serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="5a537-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="5a537-118">Cliquez avec le bouton droit sur le serveur de surveillance, puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="5a537-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="5a537-119">Dans **Supprimer les magasins dépendants**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a537-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="5a537-120">Publiez la topologie, vérifiez l’état de la réplication et exécutez l’Assistant Déploiement de Skype Entreprise Server si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5a537-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

