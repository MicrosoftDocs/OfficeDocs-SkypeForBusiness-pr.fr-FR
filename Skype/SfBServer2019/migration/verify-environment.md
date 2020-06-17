---
title: Vérifier l’environnement hérité
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
description: Avant de déployer Skype entreprise Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés. Il est important d’identifier les services et les fonctionnalités clés qui existent dans votre environnement hérité, avant de déployer un pool pilote Skype entreprise Server 2019. Avant de déployer Microsoft Skype entreprise Server 2019 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré qui prend en charge la configuration XMPP héritée.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751676"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="a0853-105">Vérifier l’environnement hérité</span><span class="sxs-lookup"><span data-stu-id="a0853-105">Verify the legacy environment</span></span>

<span data-ttu-id="a0853-106">Avant de déployer Skype entreprise Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés.</span><span class="sxs-lookup"><span data-stu-id="a0853-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="a0853-107">Il est important d’identifier les services et les fonctionnalités clés qui existent dans votre environnement hérité avant de déployer un pool pilote Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a0853-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="a0853-108">Avant de déployer Microsoft Skype entreprise Server 2019 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré qui prend en charge la configuration XMPP héritée.</span><span class="sxs-lookup"><span data-stu-id="a0853-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="a0853-109">La vérification de votre déploiement hérité implique les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a0853-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="a0853-110">Vérification du démarrage des services hérités</span><span class="sxs-lookup"><span data-stu-id="a0853-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="a0853-111">Examen de la topologie et des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a0853-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="a0853-112">Vérification des paramètres de Fédération et du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="a0853-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="a0853-113">Vérification des services XMPP et des partenaires fédérés</span><span class="sxs-lookup"><span data-stu-id="a0853-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="a0853-114">Vérifier que les services hérités sont démarrés</span><span class="sxs-lookup"><span data-stu-id="a0853-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="a0853-115">À partir du serveur frontal hérité, accédez à l’applet Administration\services. d’administration.</span><span class="sxs-lookup"><span data-stu-id="a0853-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="a0853-116">Vérifiez que les services suivants sont exécutés sur le serveur frontal :</span><span class="sxs-lookup"><span data-stu-id="a0853-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Liste des services exécutés sur un serveur frontal](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a0853-118">Examiner la topologie héritée dans le panneau de configuration de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a0853-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a0853-119">Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a0853-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="a0853-120">Ouvrez le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a0853-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a0853-121">Sélectionnez **Topologie**.</span><span class="sxs-lookup"><span data-stu-id="a0853-121">Select **Topology**.</span></span> <span data-ttu-id="a0853-122">Vérifiez que les différents serveurs de votre déploiement hérité sont répertoriés.</span><span class="sxs-lookup"><span data-stu-id="a0853-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Page topologie du panneau de configuration](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a0853-124">Examiner les utilisateurs hérités dans le panneau de configuration de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a0853-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a0853-125">Ouvrez le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a0853-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="a0853-126">Sélectionnez **utilisateurs**, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="a0853-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="a0853-127">Vérifiez que la colonne pool de serveurs d' **inscriptions** pointe vers le pool hérité pour chaque utilisateur mentionné.</span><span class="sxs-lookup"><span data-stu-id="a0853-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Liste des utilisateurs dans le panneau de configuration](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="a0853-129">Vérifier les paramètres de serveur Edge et de Fédération hérités</span><span class="sxs-lookup"><span data-stu-id="a0853-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="a0853-130">Démarrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="a0853-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="a0853-131">Sélectionnez **Télécharger la topologie à partir du déploiement existant**.</span><span class="sxs-lookup"><span data-stu-id="a0853-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="a0853-132">Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="a0853-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="a0853-133">Développez le nœud installations héritées pour afficher les différents rôles serveur dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="a0853-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="a0853-134">Sélectionnez le nœud de site et vérifiez qu’une valeur d’attribution de l' **itinéraire de Fédération du site** est définie.</span><span class="sxs-lookup"><span data-stu-id="a0853-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Générateur de topologies, itinéraire de Fédération du site](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="a0853-136">Sélectionnez le serveur Standard Edition ou le pool frontal Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a0853-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="a0853-137">Déterminez si un pool de serveurs Edge a été configuré pour les médias sous les **associations**.</span><span class="sxs-lookup"><span data-stu-id="a0853-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Générateur de topologies affichant les serveurs et les pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="a0853-139">Sélectionnez le pool de serveurs Edge et déterminez si un pool de tronçons suivant est configuré en dessous de **sélection du tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="a0853-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Générateur de topologies, sélection du tronçon suivant](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="a0853-141">Vérifier la configuration des partenaires fédérés XMPP hérités</span><span class="sxs-lookup"><span data-stu-id="a0853-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="a0853-142">À partir du serveur XMPP hérité, naviguez vers l’applet Outils/Services d’administration.</span><span class="sxs-lookup"><span data-stu-id="a0853-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="a0853-143">Vérifiez que le service de passerelle XMPP Office Communications Server est démarré.</span><span class="sxs-lookup"><span data-stu-id="a0853-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Service de passerelle XMPP Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

