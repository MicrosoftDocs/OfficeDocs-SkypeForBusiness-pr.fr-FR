---
title: Déploiement d’un serveur Edge pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre Skype pour Business Server 2019 Edge Server. Les processus de déploiement et configuration pour Skype pour Business Server 2019 sont très similaires aux Skype pour Business Server 2015. Cette section met en évidence uniquement les points clés que vous devez prendre en compte dans le cadre de votre déploiement du pool pilote. Pour obtenir la procédure détaillée, consultez Déploiement de l’accès des utilisateurs externes dans Skype pour Business Server 2019 dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.
ms.openlocfilehash: 5b755d0ba8802c47a176cb3375a87b6523f35fad
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32239854"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="9579c-106">Déploiement d’un serveur Edge pilote</span><span class="sxs-lookup"><span data-stu-id="9579c-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="9579c-107">Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre Skype pour Business Server 2019 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="9579c-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="9579c-108">Les processus de déploiement et configuration pour Skype pour Business Server 2019 sont très similaires aux Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9579c-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="9579c-109">Cette section met en évidence uniquement les points clés que vous devez prendre en compte dans le cadre de votre déploiement du pool pilote.</span><span class="sxs-lookup"><span data-stu-id="9579c-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="9579c-110">Lorsque vous naviguez dans l’Assistant **Définir un nouveau Pool Edge** , passez en revue les paramètres de configuration de la clé indiqués dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="9579c-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="9579c-111">Notez que seuls quelques pages de l’Assistant **Définir un nouveau Pool Edge** sont affichées.</span><span class="sxs-lookup"><span data-stu-id="9579c-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="9579c-112">Pour définir un Pool de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="9579c-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="9579c-113">Ouvrez une session l’ordinateur où le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9579c-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="9579c-114">Accédez à la Skype Business Server 2019 nœud.</span><span class="sxs-lookup"><span data-stu-id="9579c-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="9579c-115">**Pools de serveurs Edge**d’avec le bouton droit, puis cliquez sur **pool de serveurs Edge de nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9579c-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![Définir la boîte de dialogue Nouveau Pool Edge](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="9579c-117">Un pool Edge peut être un **pool de plusieurs ordinateurs** ou un **seul ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="9579c-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![Définir la boîte de dialogue Nom complet du Pool de serveur Edge](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="9579c-119">Dans la page **Sélectionner les fonctionnalités** , n’activez pas la fédération ou la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="9579c-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="9579c-120">Fédération et la fédération XMPP sont les deux actuellement acheminés via le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="9579c-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="9579c-121">Ces fonctionnalités vont être configurées dans une phase ultérieure de la migration.</span><span class="sxs-lookup"><span data-stu-id="9579c-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="9579c-122">Continuez à remplir les pages suivantes de l’Assistant : **Noms de domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.</span><span class="sxs-lookup"><span data-stu-id="9579c-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="9579c-123">Dans la page **définir le serveur du tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="9579c-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![Définir la boîte de dialogue tronçon suivant](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="9579c-125">Dans la page **associer Front-End ou des pools de médiation** , n’associez pas un pool à ce pool Edge à ce stade.</span><span class="sxs-lookup"><span data-stu-id="9579c-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="9579c-126">Le trafic multimédia externe n’est actuellement routé via le serveur Edge hérité.</span><span class="sxs-lookup"><span data-stu-id="9579c-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="9579c-127">Ce paramètre de configuration dans une phase ultérieure de la migration.</span><span class="sxs-lookup"><span data-stu-id="9579c-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![Associer la boîte de dialogue Pools frontaux](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="9579c-129">Cliquez sur **Terminer**, puis sur **Publier** la topologie.</span><span class="sxs-lookup"><span data-stu-id="9579c-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="9579c-130">Suivez les étapes décrites dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur de périphérie, configurer des certificats et démarrer les services.</span><span class="sxs-lookup"><span data-stu-id="9579c-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="9579c-131">Il est très important que vous suivez les instructions fournies dans les rubriques de la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="9579c-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="9579c-132">Cette section fournie simplement des conseils sur les paramètres de configuration lors de l’installation de ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="9579c-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="9579c-133">Vous devez voir apparaître un serveur Edge hérité déployés en parallèle avec un Skype pour un déploiement de serveur Edge Server 2019 Business server.</span><span class="sxs-lookup"><span data-stu-id="9579c-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="9579c-134">Vérifiez que les deux déploiements fonctionnent correctement, les services sont démarrés et vous pouvez administrer chaque déploiement avant de passer à la phase suivante.</span><span class="sxs-lookup"><span data-stu-id="9579c-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

