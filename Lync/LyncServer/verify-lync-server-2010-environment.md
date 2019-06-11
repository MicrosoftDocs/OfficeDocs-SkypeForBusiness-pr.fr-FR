---
title: Vérification de l’environnement Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 248d779bc43b7c3e220728222aca030036f17e00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a><span data-ttu-id="efada-102">Vérification de l’environnement Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="efada-102">Verify Lync Server 2010 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efada-103">_**Dernière modification de la rubrique:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="efada-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="efada-104">Avant de déployer Lync Server 2013 dans un état de coexistence avec Lync Server 2010, vous devez vérifier que les services Lync Server 2010 ont été configurés et démarrés.</span><span class="sxs-lookup"><span data-stu-id="efada-104">Before deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you need to verify that Lync Server 2010 services have been configured and started.</span></span> <span data-ttu-id="efada-105">Il est important d’identifier les services et fonctionnalités clés qui existent dans votre environnement hérité, avant de déployer un pool de pilotes 2013 Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efada-105">It is important to identify key services and features that exist in your legacy environment, prior to deploying a Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="efada-106">Avant de déployer Microsoft Lync Server 2013 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré qui prend en charge la configuration XMPP héritée.</span><span class="sxs-lookup"><span data-stu-id="efada-106">Before deploying Microsoft Lync Server 2013 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="efada-107">La vérification de votre déploiement hérité de Lync Server 2010 implique les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="efada-107">Verifying your legacy Lync Server 2010 deployment entails the following:</span></span>

  - <span data-ttu-id="efada-108">Vérification du démarrage des services 2010 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="efada-108">Verifying the Lync Server 2010 services are started</span></span>

  - <span data-ttu-id="efada-109">Examen de la topologie et des utilisateurs dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="efada-109">Reviewing the topology and users in Lync Server 2010.</span></span>

  - <span data-ttu-id="efada-110">Vérification des paramètres de serveur de Fédération et de périmètre.</span><span class="sxs-lookup"><span data-stu-id="efada-110">Verifying the federation and Edge server settings.</span></span>

  - <span data-ttu-id="efada-111">Vérification des services XMPP et des partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="efada-111">Verifying XMPP services and federated partners.</span></span>

<span data-ttu-id="efada-112">**Vérifier le démarrage des services Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="efada-112">**Verify Lync Server 2010 Services are started**</span></span>

1.  <span data-ttu-id="efada-113">À partir du serveur frontal Lync Server 2010, accédez à l’applet\\services d’administration.</span><span class="sxs-lookup"><span data-stu-id="efada-113">From the Lync Server 2010 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="efada-114">Vérifiez que les services suivants s’exécutent sur le serveur frontal:</span><span class="sxs-lookup"><span data-stu-id="efada-114">Verify that the following services are running on the Front End Server:</span></span>
    
    <span data-ttu-id="efada-115">![Liste des services s’exécutant sur un serveur frontal] (images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Liste des services s’exécutant sur un serveur frontal")</span><span class="sxs-lookup"><span data-stu-id="efada-115">![List of services running on Front End Server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "List of services running on Front End Server")</span></span>

<span data-ttu-id="efada-116">**Passez en revue la topologie Lync Server 2010 dans le panneau de configuration de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="efada-116">**Review the Lync Server 2010 topology in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="efada-117">Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’admistrateur CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="efada-117">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="efada-118">Ouvrez le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efada-118">Open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="efada-119">Sélectionnez **topologie**.</span><span class="sxs-lookup"><span data-stu-id="efada-119">Select **Topology**.</span></span> <span data-ttu-id="efada-120">Vérifiez que les différents serveurs de votre déploiement de Lync Server 2010 sont répertoriés.</span><span class="sxs-lookup"><span data-stu-id="efada-120">Verify that the various servers in your Lync Server 2010 deployment are listed.</span></span>
    
    <span data-ttu-id="efada-121">![Page Topology du panneau de configuration de Lync Server 2010] (images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Page Topology du panneau de configuration de Lync Server 2010")</span><span class="sxs-lookup"><span data-stu-id="efada-121">![Lync Server 2010 Control Panel topology page](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Lync Server 2010 Control Panel topology page")</span></span>

<span data-ttu-id="efada-122">**Pour passer en revue les utilisateurs de Lync Server 2010 dans le panneau de configuration de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="efada-122">**To review Lync Server 2010 users in Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="efada-123">Ouvrez le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efada-123">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="efada-124">Sélectionnez **utilisateurs** , puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="efada-124">Select **Users** and then click **Find**.</span></span>

3.  <span data-ttu-id="efada-125">Vérifiez que la colonne **pool d’inscriptions** pointe vers le pool Lync Server 2010 pour chaque utilisateur répertorié.</span><span class="sxs-lookup"><span data-stu-id="efada-125">Verify that the **Registrar Pool** column points to the Lync Server 2010 pool for each user listed.</span></span>
    
    <span data-ttu-id="efada-126">![Lync Server 2010-panneau de configuration avec liste des utilisateurs] (images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010-panneau de configuration avec liste des utilisateurs")</span><span class="sxs-lookup"><span data-stu-id="efada-126">![Lync Server 2010 Control Panel listing users](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Lync Server 2010 Control Panel listing users")</span></span>

<span data-ttu-id="efada-127">**Pour vérifier les paramètres de périphérie et de Fédération de Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="efada-127">**To verify Lync Server 2010 Edge and Federation Settings**</span></span>

1.  <span data-ttu-id="efada-128">Démarrer le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="efada-128">Start Topology Builder.</span></span>

2.  <span data-ttu-id="efada-129">Sélectionnez **Télécharger la topologie à partir du déploiement existant**.</span><span class="sxs-lookup"><span data-stu-id="efada-129">Select **Download Topology from existing deployment**.</span></span>

3.  <span data-ttu-id="efada-130">Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="efada-130">Choose a file name and save the topology with the default .tbxml file type.</span></span>

4.  <span data-ttu-id="efada-131">Développez le nœud Lync Server 2010 pour révéler les différents rôles de serveur du déploiement.</span><span class="sxs-lookup"><span data-stu-id="efada-131">Expand the Lync Server 2010 node to reveal the various server roles in the deployment.</span></span>

5.  <span data-ttu-id="efada-132">Sélectionnez le nœud site et vérifiez qu’une valeur d' **attribution d’itinéraire de Fédération de site** est définie.</span><span class="sxs-lookup"><span data-stu-id="efada-132">Select the site node and verify if a **Site federation route assignment** value is set.</span></span>
    
    <span data-ttu-id="efada-133">![Générateur de topologie, itinéraire de Fédération de site] (images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Générateur de topologie, itinéraire de Fédération de site")</span><span class="sxs-lookup"><span data-stu-id="efada-133">![Topology Builder, Site Federation Route](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Topology Builder, Site Federation Route")</span></span>

6.  <span data-ttu-id="efada-134">Sélectionnez ensuite le pool frontal Standard Edition Server ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="efada-134">Next, select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="efada-135">Déterminez si un pool de périphérie a été configuré pour \*\*\*\* les médias suivants.</span><span class="sxs-lookup"><span data-stu-id="efada-135">Determine if an Edge pool has been configured for Media below **Associations**.</span></span>
    
    <span data-ttu-id="efada-136">![Générateur de topologie affichant des serveurs et des groupes] (images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Générateur de topologie affichant des serveurs et des groupes")</span><span class="sxs-lookup"><span data-stu-id="efada-136">![Topology Builder showing servers and pools](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Topology Builder showing servers and pools")</span></span>

7.  <span data-ttu-id="efada-137">Enfin, sélectionnez le pool de bords et déterminez si un pool de prochains tronçons est configuré en dessous de la **sélection du tronçon suivant**.</span><span class="sxs-lookup"><span data-stu-id="efada-137">Finally, select the Edge pool and identify if a Next hop pool is configured below **Next hop selection**.</span></span>
    
    <span data-ttu-id="efada-138">![Générateur de topologie, sélection du tronçon suivant] (images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Générateur de topologie, sélection du tronçon suivant")</span><span class="sxs-lookup"><span data-stu-id="efada-138">![Topology Builder, Next hop selection](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Topology Builder, Next hop selection")</span></span>

<span data-ttu-id="efada-139">**Vérification de la configuration de partenaire fédéré hérité de XMPP**</span><span class="sxs-lookup"><span data-stu-id="efada-139">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="efada-140">À partir du serveur XMPP hérité, accédez à l’applet\\services des outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="efada-140">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="efada-141">Vérifiez que le service de passerelle XMPP d’Office Communications Server est démarré.</span><span class="sxs-lookup"><span data-stu-id="efada-141">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="efada-142">![Service de passerelle Office Communications Server XMPP] (images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Service de passerelle Office Communications Server XMPP")</span><span class="sxs-lookup"><span data-stu-id="efada-142">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

