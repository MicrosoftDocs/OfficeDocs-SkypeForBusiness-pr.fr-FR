---
title: Vérifier l’environnement hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Avant de déployer Skype entreprise Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés. Il est important d’identifier les services et fonctionnalités clés qui existent dans votre environnement hérité, avant de déployer un pool de pilotes Skype entreprise Server 2019. Avant de déployer Microsoft Skype entreprise Server 2019 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré qui utilise la configuration XMPP héritée. annexes.
ms.openlocfilehash: 9495c68085f3fc3495d4c2ced05be8b20039eb4e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280659"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="776e0-105">Vérifier l’environnement hérité</span><span class="sxs-lookup"><span data-stu-id="776e0-105">Verify the legacy environment</span></span>

<span data-ttu-id="776e0-106">Avant de déployer Skype entreprise Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés.</span><span class="sxs-lookup"><span data-stu-id="776e0-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="776e0-107">Il est important d’identifier les services et fonctionnalités clés qui existent dans votre environnement hérité avant de déployer un pool de pilotes Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="776e0-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="776e0-108">Avant de déployer Microsoft Skype entreprise Server 2019 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré de la fonction XMPP héritée. la configuration est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="776e0-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="776e0-109">La vérification de votre déploiement hérité implique les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="776e0-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="776e0-110">Vérification du démarrage des services hérités</span><span class="sxs-lookup"><span data-stu-id="776e0-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="776e0-111">Examen de la topologie et des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="776e0-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="776e0-112">Vérification des paramètres de serveur de Fédération et de périphérie</span><span class="sxs-lookup"><span data-stu-id="776e0-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="776e0-113">Vérification des services XMPP et des partenaires fédérés</span><span class="sxs-lookup"><span data-stu-id="776e0-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="776e0-114">Vérifier la mise en route des services hérités</span><span class="sxs-lookup"><span data-stu-id="776e0-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="776e0-115">À partir du serveur frontal antérieur, accédez à l’applet d’administration Tools\Services.</span><span class="sxs-lookup"><span data-stu-id="776e0-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="776e0-116">Vérifiez que les services suivants s’exécutent sur le serveur frontal:</span><span class="sxs-lookup"><span data-stu-id="776e0-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![Liste des services s’exécutant sur un serveur frontal](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="776e0-118">Passer en revue la topologie héritée dans le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="776e0-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="776e0-119">Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’admistrateur CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="776e0-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="776e0-120">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="776e0-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="776e0-121">Sélectionnez **topologie**.</span><span class="sxs-lookup"><span data-stu-id="776e0-121">Select **Topology**.</span></span> <span data-ttu-id="776e0-122">Vérifiez que les différents serveurs dans votre déploiement hérité sont répertoriés.</span><span class="sxs-lookup"><span data-stu-id="776e0-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![Page Topology du panneau de configuration](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="776e0-124">Examiner les anciens utilisateurs dans le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="776e0-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="776e0-125">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="776e0-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="776e0-126">Sélectionnez **utilisateurs**, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="776e0-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="776e0-127">Vérifiez que la colonne **pool d’inscriptions** pointe vers le pool hérité de chaque utilisateur répertorié.</span><span class="sxs-lookup"><span data-stu-id="776e0-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![Liste des utilisateurs dans le panneau de configuration](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="776e0-129">Vérifier les paramètres de bord et de Fédération hérités</span><span class="sxs-lookup"><span data-stu-id="776e0-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="776e0-130">Démarrer le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="776e0-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="776e0-131">Sélectionnez **Télécharger la topologie à partir du déploiement existant**.</span><span class="sxs-lookup"><span data-stu-id="776e0-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="776e0-132">Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="776e0-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="776e0-133">Développez le nœud installations héritées pour afficher les différents rôles serveur du déploiement.</span><span class="sxs-lookup"><span data-stu-id="776e0-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="776e0-134">Sélectionnez le nœud site et vérifiez qu’une valeur d’attribution de l' **itinéraire de Fédération de site** est définie.</span><span class="sxs-lookup"><span data-stu-id="776e0-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![Générateur de topologie, itinéraire de Fédération de site](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="776e0-136">Sélectionnez la liste frontale Standard Edition Server ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="776e0-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="776e0-137">Déterminez s’il est configuré pour le contenu multimédia inférieur aux **associations**.</span><span class="sxs-lookup"><span data-stu-id="776e0-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![Générateur de topologie affichant des serveurs et des groupes](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="776e0-139">Sélectionnez le pool de bords et déterminez si un pool de prochains tronçons est configuré en dessous de l' **option tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="776e0-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![Générateur de topologie, sélection du tronçon suivant](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="776e0-141">Vérification de la configuration de partenaire fédéré hérité de XMPP</span><span class="sxs-lookup"><span data-stu-id="776e0-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="776e0-142">À partir du serveur XMPP hérité, accédez à l’applet d’administration Tools\Services.</span><span class="sxs-lookup"><span data-stu-id="776e0-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="776e0-143">Vérifiez que le service de passerelle XMPP d’Office Communications Server est démarré.</span><span class="sxs-lookup"><span data-stu-id="776e0-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Service de passerelle Office Communications Server XMPP](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

