---
title: Déploiement d’un serveur Edge pilote
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
description: Cette rubrique présente les paramètres de configuration que vous devez prendre en compte avant de déployer votre serveur Edge 2019 Skype entreprise Server. Le processus de déploiement et de configuration de Skype entreprise Server 2019 est très similaire à celui de Skype entreprise Server 2015. Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool pilote. Pour plus d’informations, reportez-vous à la rubrique déploiement d’un accès utilisateur externe dans Skype entreprise Server 2019 dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.
ms.openlocfilehash: c2beb22e2cce608b692884ad9b49fef40cb87058
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813652"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="aabb9-106">Déploiement d’un serveur Edge pilote</span><span class="sxs-lookup"><span data-stu-id="aabb9-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="aabb9-107">Cette rubrique présente les paramètres de configuration que vous devez prendre en compte avant de déployer votre serveur Edge 2019 Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="aabb9-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="aabb9-108">Le processus de déploiement et de configuration de Skype entreprise Server 2019 est très similaire à celui de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="aabb9-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="aabb9-109">Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool pilote.</span><span class="sxs-lookup"><span data-stu-id="aabb9-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="aabb9-110">À mesure que vous parcourez l’Assistant **définir un nouveau pool de bords** , passez en revue les paramètres de configuration clés indiqués dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="aabb9-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="aabb9-111">Notez que seules quelques pages de l’Assistant **définir un nouveau pool de bords** sont affichées.</span><span class="sxs-lookup"><span data-stu-id="aabb9-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="aabb9-112">Pour définir un pool de bords</span><span class="sxs-lookup"><span data-stu-id="aabb9-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="aabb9-113">Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="aabb9-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="aabb9-114">Accédez au nœud Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="aabb9-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="aabb9-115">Cliquez avec le bouton droit sur **pools de bords**, puis cliquez sur **nouvelle liste de bord**.</span><span class="sxs-lookup"><span data-stu-id="aabb9-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Boîte de dialogue définir la nouvelle réserve de bords](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="aabb9-117">Un pool Edge peut être un pool d' **ordinateurs** ou un **pool d’ordinateurs unique**.</span><span class="sxs-lookup"><span data-stu-id="aabb9-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Définir la boîte de dialogue nom de domaine complet du pool de bords](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="aabb9-119">Dans la page **Sélectionner des fonctionnalités** , n’activez pas la Fédération de Fédération ou XMPP.</span><span class="sxs-lookup"><span data-stu-id="aabb9-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="aabb9-120">Les fédérations de Fédération et XMPP sont actuellement routées via le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="aabb9-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="aabb9-121">Ces fonctionnalités seront configurées lors de la phase de migration ultérieure.</span><span class="sxs-lookup"><span data-stu-id="aabb9-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="aabb9-122">Continuez à remplir les pages suivantes de l’Assistant : noms de **domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.</span><span class="sxs-lookup"><span data-stu-id="aabb9-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="aabb9-123">Dans la page **définir le serveur du tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de bords antérieurs.</span><span class="sxs-lookup"><span data-stu-id="aabb9-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Boîte de dialogue définir le saut suivant](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="aabb9-125">Dans la page **Associate front end ou pools de médiation** , n’associez pas un pool à ce pool d’arêtes pour le moment.</span><span class="sxs-lookup"><span data-stu-id="aabb9-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="aabb9-126">Le trafic de médias externes est actuellement acheminé via le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="aabb9-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="aabb9-127">Ce paramètre sera configuré lors de la phase de migration ultérieure.</span><span class="sxs-lookup"><span data-stu-id="aabb9-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Boîte de dialogue Associate](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="aabb9-129">Cliquez sur **Terminer**, puis **publiez** la topologie.</span><span class="sxs-lookup"><span data-stu-id="aabb9-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="aabb9-130">Suivez les étapes décrites dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer des certificats et démarrer les services.</span><span class="sxs-lookup"><span data-stu-id="aabb9-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="aabb9-131">Il est très important de suivre les recommandations des rubriques de la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="aabb9-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="aabb9-132">Cette section fournit uniquement des recommandations en matière de paramètres de configuration lors de l’installation de ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="aabb9-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="aabb9-133">Vous devez maintenant disposer d’un serveur Edge hérité déployé en parallèle avec un déploiement de serveur Edge Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="aabb9-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="aabb9-134">Vérifiez que les deux déploiements s’exécutent correctement, que les services sont démarrés et que vous pouvez gérer chaque déploiement avant de passer à la phase suivante.</span><span class="sxs-lookup"><span data-stu-id="aabb9-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

