---
title: Vérifier l’environnement Lync Server 2010
description: Vérifier l’environnement Lync Server 2010.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 570fd2a9efdc90899ff4f91146b7aeb1991f6764
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555580"
---
# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="9dba2-103">Vérifier l’environnement Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9dba2-103">Verify Lync Server 2010 environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dba2-104">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9dba2-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9dba2-105">Avant de déployer Lync Server 2013 dans un état de coexistence avec Lync Server 2010, vous devez vérifier que les services Lync Server 2010 ont été configurés et démarrés.</span><span class="sxs-lookup"><span data-stu-id="9dba2-105">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="9dba2-106">Il est important d’identifier les services et les fonctionnalités clés qui existent dans votre environnement hérité, avant de déployer un pool pilote Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9dba2-106">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="9dba2-107">Avant de déployer Microsoft Lync Server 2013 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré qui prend en charge la configuration XMPP héritée.</span><span class="sxs-lookup"><span data-stu-id="9dba2-107">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="9dba2-108">La vérification de votre déploiement hérité de Lync Server 2010 implique les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9dba2-108">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="9dba2-109">Vérification du démarrage des services Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9dba2-109">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="9dba2-110">Examen de la topologie et des utilisateurs dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9dba2-110">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="9dba2-111">Vérification des paramètres de fédération et du serveur Edge</span><span class="sxs-lookup"><span data-stu-id="9dba2-111">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="9dba2-112">Vérification des services XMPP et des partenaires fédérés</span><span class="sxs-lookup"><span data-stu-id="9dba2-112">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="9dba2-113">**Vérifier que les services Lync Server 2010 sont démarrés**</span><span class="sxs-lookup"><span data-stu-id="9dba2-113">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="9dba2-114">À partir du serveur frontal Lync Server 2010, accédez à l' \\ applet Services d’administration.</span><span class="sxs-lookup"><span data-stu-id="9dba2-114">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="9dba2-115">Vérifiez que les services suivants sont exécutés sur le serveur frontal :</span><span class="sxs-lookup"><span data-stu-id="9dba2-115">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="9dba2-116">![Liste des services exécutés sur un serveur frontal](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Liste des services exécutés sur un serveur frontal")</span><span class="sxs-lookup"><span data-stu-id="9dba2-116">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="9dba2-117">**Consultez la topologie Lync Server 2010 dans le panneau de configuration Lync Server**</span><span class="sxs-lookup"><span data-stu-id="9dba2-117">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="9dba2-118">Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9dba2-118">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="9dba2-119">Ouvrez le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9dba2-119">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="9dba2-120">Sélectionnez **Topologie**.</span><span class="sxs-lookup"><span data-stu-id="9dba2-120">Select **Topology**.</span></span> <span data-ttu-id="9dba2-121">Vérifiez que les différents serveurs de votre déploiement Lync Server 2010 sont répertoriés.</span><span class="sxs-lookup"><span data-stu-id="9dba2-121">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="9dba2-122">![Page topologie du panneau de configuration Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Page topologie du panneau de configuration Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="9dba2-122">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="9dba2-123">**Pour consulter les utilisateurs de Lync Server 2010 dans le panneau de configuration Lync Server**</span><span class="sxs-lookup"><span data-stu-id="9dba2-123">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="9dba2-124">Ouvrez le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9dba2-124">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="9dba2-125">Sélectionnez **Utilisateurs**, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="9dba2-125">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="9dba2-126">Vérifiez que la colonne pool de serveurs d' **inscriptions** pointe vers le pool Lync Server 2010 pour chaque utilisateur mentionné.</span><span class="sxs-lookup"><span data-stu-id="9dba2-126">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="9dba2-127">![Panneau de configuration Lync Server 2010 répertoriant les utilisateurs](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Panneau de configuration Lync Server 2010 répertoriant les utilisateurs")</span><span class="sxs-lookup"><span data-stu-id="9dba2-127">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="9dba2-128">**Pour vérifier les paramètres de Fédération et de périmètre Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="9dba2-128">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="9dba2-129">Démarrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="9dba2-129">Start Topology Builder.</span></span>

2.  <span data-ttu-id="9dba2-130">Sélectionnez **Télécharger la topologie à partir du déploiement existant**.</span><span class="sxs-lookup"><span data-stu-id="9dba2-130">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="9dba2-131">Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier par défaut (.tbxml).</span><span class="sxs-lookup"><span data-stu-id="9dba2-131">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="9dba2-132">Développez le nœud Lync Server 2010 pour afficher les différents rôles serveur dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="9dba2-132">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="9dba2-133">Sélectionnez le nœud du site et vérifiez si l’option **Attribution de l’itinéraire de fédération du site** est définie.</span><span class="sxs-lookup"><span data-stu-id="9dba2-133">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="9dba2-134">![Générateur de topologies, itinéraire de Fédération du site](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Générateur de topologies, itinéraire de Fédération du site")</span><span class="sxs-lookup"><span data-stu-id="9dba2-134">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="9dba2-p103">Sélectionnez ensuite le serveur Standard Edition ou le pool frontal Enterprise Edition. Vérifiez si un pool Edge a été configuré pour les médias sous **Associations**.</span><span class="sxs-lookup"><span data-stu-id="9dba2-p103">Next, select the Standard Edition Server or Enterprise Edition front end pool. Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="9dba2-137">![Générateur de topologies affichant les serveurs et les pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Générateur de topologies affichant les serveurs et les pools")</span><span class="sxs-lookup"><span data-stu-id="9dba2-137">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="9dba2-138">Enfin, sélectionnez le pool Edge et vérifiez si un pool de tronçon suivant est configuré sous **Sélection du tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="9dba2-138">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="9dba2-139">![Générateur de topologies, sélection du tronçon suivant](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Générateur de topologies, sélection du tronçon suivant")</span><span class="sxs-lookup"><span data-stu-id="9dba2-139">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="9dba2-140">**Vérifiez la configuration de partenaire fédéré XMPP héritée**</span><span class="sxs-lookup"><span data-stu-id="9dba2-140">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="9dba2-141">À partir du serveur XMPP hérité, accédez à l’application outils d’administration \\ services.</span><span class="sxs-lookup"><span data-stu-id="9dba2-141">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="9dba2-142">Vérifiez que le service de passerelle XMPP Office Communications Server est démarré.</span><span class="sxs-lookup"><span data-stu-id="9dba2-142">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="9dba2-143">![Service de passerelle XMPP Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Service de passerelle XMPP Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="9dba2-143">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

