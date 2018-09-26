---
title: Vérification de l’environnement hérité
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Avant de déployer Skype pour Business Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés. Il est important d’identifier les principaux services et fonctionnalités qui existent dans votre environnement hérité, avant de déployer un Skype pour le pool pilote Business Server 2019. Avant de déployer Microsoft Skype pour Business Server 2019 XMPP dans un état de la coexistence avec un déploiement XMPP hérité, vous devez vérifier les services XMPP hérités ont été configurés et démarrés et identifier les partenaires fédérés est la configuration XMPP héritée prise en charge.
ms.openlocfilehash: d6e4585e127009117345d1220458196b5b461b6a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030426"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="a5606-105">Vérification de l’environnement hérité</span><span class="sxs-lookup"><span data-stu-id="a5606-105">Verify the legacy environment</span></span>

<span data-ttu-id="a5606-106">Avant de déployer Skype pour Business Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés.</span><span class="sxs-lookup"><span data-stu-id="a5606-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="a5606-107">Il est important d’identifier les principaux services et fonctionnalités qui existent dans votre environnement avant de déployer un Skype pour le pool pilote Business Server 2019 hérité.</span><span class="sxs-lookup"><span data-stu-id="a5606-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="a5606-108">Avant de déployer Microsoft Skype pour Business Server 2019 XMPP dans un état de la coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés et identifier qui partenaire les XMPP hérité fédéré prise en charge de la configuration.</span><span class="sxs-lookup"><span data-stu-id="a5606-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="a5606-109">Vérification de votre déploiement hérité implique les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5606-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="a5606-110">Vérification que les services hérités sont démarrés.</span><span class="sxs-lookup"><span data-stu-id="a5606-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="a5606-111">Examen de la topologie et les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a5606-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="a5606-112">Vérification de la fédération et les paramètres du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="a5606-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="a5606-113">Vérification des services XMPP et des partenaires fédérés</span><span class="sxs-lookup"><span data-stu-id="a5606-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="a5606-114">Vérifiez que les services hérités sont démarrés</span><span class="sxs-lookup"><span data-stu-id="a5606-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="a5606-115">Hérité serveur frontal, accédez à l’applet outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="a5606-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="a5606-116">Vérifiez que les services suivants sont en cours d’exécution sur le serveur frontal :</span><span class="sxs-lookup"><span data-stu-id="a5606-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Liste des services s’exécutant sur le serveur frontal](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a5606-118">Passez en revue la topologie héritée dans Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="a5606-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a5606-119">Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’administrateur CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a5606-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="a5606-120">Ouvrez le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a5606-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a5606-121">Sélectionnez **la topologie**.</span><span class="sxs-lookup"><span data-stu-id="a5606-121">Select **Topology**.</span></span> <span data-ttu-id="a5606-122">Vérifiez que les différents serveurs dans votre déploiement hérité sont répertoriés.</span><span class="sxs-lookup"><span data-stu-id="a5606-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Page de la topologie du Panneau de configuration de contrôle](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a5606-124">Passez en revue les utilisateurs hérités dans Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="a5606-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a5606-125">Ouvrez le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a5606-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="a5606-126">Sélectionnez **les utilisateurs**, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="a5606-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="a5606-127">Vérifiez que la colonne **Pool de serveurs d’inscriptions** pointe vers le pool hérité pour chaque utilisateur répertorié.</span><span class="sxs-lookup"><span data-stu-id="a5606-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Le panneau de configuration répertoriant les utilisateurs](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="a5606-129">Vérifiez les paramètres de fédération et Edge hérités</span><span class="sxs-lookup"><span data-stu-id="a5606-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="a5606-130">Démarrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="a5606-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="a5606-131">Sélectionnez **Télécharger la topologie à partir du déploiement existant**.</span><span class="sxs-lookup"><span data-stu-id="a5606-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="a5606-132">Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier .tbxml par défaut.</span><span class="sxs-lookup"><span data-stu-id="a5606-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="a5606-133">Développez le nœud installe hérité pour afficher les différents rôles de serveur dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5606-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="a5606-134">Sélectionnez le nœud du site et vérifiez qu’une valeur de **l’attribution itinéraire de fédération du Site** est définie.</span><span class="sxs-lookup"><span data-stu-id="a5606-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Générateur de topologies, itinéraire de fédération de Site](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="a5606-136">Sélectionnez le pool frontal Standard Edition Server ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a5606-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="a5606-137">Déterminer si un pool de serveurs Edge a été configuré pour le média sous **Associations**.</span><span class="sxs-lookup"><span data-stu-id="a5606-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Générateur de topologie indiquant les serveurs et pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="a5606-139">Sélectionnez le pool Edge et déterminer si un pool du tronçon suivant est configuré sous **sélection du tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="a5606-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Sélection du tronçon suivant du Générateur de topologie](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="a5606-141">Vérifiez le partenaire fédéré XMPP hérité Configuration</span><span class="sxs-lookup"><span data-stu-id="a5606-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="a5606-142">Le serveur XMPP hérité, accédez à l’applet outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="a5606-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="a5606-143">Vérifiez que le service de passerelle XMPP de Office Communications Server est démarré.</span><span class="sxs-lookup"><span data-stu-id="a5606-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Service de passerelle XMPP Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

