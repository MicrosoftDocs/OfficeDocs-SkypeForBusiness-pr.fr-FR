---
title: Déploiement d’un serveur Edge pilote
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
description: Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre serveur Edge Skype entreprise Server 2019. Les processus de déploiement et de configuration de Skype entreprise Server 2019 sont très similaires à ceux de Skype entreprise Server 2015. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. Pour obtenir la procédure détaillée, voir Deploying External User Access in Skype for Business Server 2019 dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752866"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="221c2-106">Déploiement d’un serveur Edge pilote</span><span class="sxs-lookup"><span data-stu-id="221c2-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="221c2-107">Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre serveur Edge Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="221c2-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="221c2-108">Les processus de déploiement et de configuration de Skype entreprise Server 2019 sont très similaires à ceux de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="221c2-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="221c2-109">Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote.</span><span class="sxs-lookup"><span data-stu-id="221c2-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="221c2-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span><span class="sxs-lookup"><span data-stu-id="221c2-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="221c2-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span><span class="sxs-lookup"><span data-stu-id="221c2-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="221c2-112">Pour définir un pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="221c2-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="221c2-113">Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="221c2-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="221c2-114">Accédez au nœud Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="221c2-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="221c2-115">Cliquez avec le bouton droit sur **Pools Edge**, puis cliquez sur **Nouveau pool de serveurs Edge**.</span><span class="sxs-lookup"><span data-stu-id="221c2-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Boîte de dialogue définir le nouveau pool Edge](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="221c2-117">Un pool Edge peut être un **pool de plusieurs ordinateurs** ou un **pool d’un seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="221c2-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Boîte de dialogue définir le nom de domaine complet du pool Edge](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="221c2-119">Dans la page **Sélectionner les fonctionnalités**, n’activez pas la fédération ni la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="221c2-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="221c2-120">Fédération et la Fédération XMPP sont actuellement routées via le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="221c2-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="221c2-121">Ces fonctionnalités seront configurées lors d’une phase ultérieure de la migration.</span><span class="sxs-lookup"><span data-stu-id="221c2-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="221c2-122">Continuez à remplir les pages suivantes de l’Assistant : noms de **domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.</span><span class="sxs-lookup"><span data-stu-id="221c2-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="221c2-123">Sur la page **définir le serveur du tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de serveurs de périphérie hérité.</span><span class="sxs-lookup"><span data-stu-id="221c2-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Boîte de dialogue définir le tronçon suivant](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="221c2-125">Dans la page **associer des pools frontaux ou des pools de médiation** , n’associez pas un pool à ce pool Edge pour le moment.</span><span class="sxs-lookup"><span data-stu-id="221c2-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="221c2-126">Le trafic multimédia externe est actuellement routé via le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="221c2-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="221c2-127">Ce paramètre sera configuré lors d’une phase ultérieure de la migration.</span><span class="sxs-lookup"><span data-stu-id="221c2-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Boîte de dialogue pools frontaux associés](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="221c2-129">Cliquez sur **Terminer**, puis **publiez** la topologie.</span><span class="sxs-lookup"><span data-stu-id="221c2-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="221c2-130">Suivez les étapes décrites dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer les certificats et démarrer les services.</span><span class="sxs-lookup"><span data-stu-id="221c2-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="221c2-131">Il est très important de suivre les instructions des rubriques de la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="221c2-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="221c2-132">Cette section ne fait que fournir des recommandations concernant les paramètres de configuration lors de l’installation de ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="221c2-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="221c2-133">Un serveur Edge hérité doit maintenant être déployé en parallèle avec un déploiement de serveur Edge Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="221c2-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="221c2-134">Vérifiez que les deux déploiements fonctionnent correctement, que les services ont démarré et que vous pouvez administrer chaque déploiement avant de passer à la phase suivante.</span><span class="sxs-lookup"><span data-stu-id="221c2-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

