---
title: 'Lync Server 2013 : Définition de la configuration requise pour le serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68f9195a91a4f8334933d1fce7ffd3a5dceb564c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="5b09e-102">Définition de la configuration requise pour l’organisation du serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b09e-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b09e-103">_**Dernière modification de la rubrique:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="5b09e-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="5b09e-104">Avant de déployer le serveur de chat permanent pour votre organisation, il est essentiel de tenir compte des principales questions suivantes pour optimiser votre déploiement:</span><span class="sxs-lookup"><span data-stu-id="5b09e-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="5b09e-105">Qui (profil utilisateur) doit être activé pour le serveur Chat permanent?</span><span class="sxs-lookup"><span data-stu-id="5b09e-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="5b09e-106">Le serveur Chat permanent est activé par une stratégie qui peut être définie au niveau global, de site, de pool ou d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5b09e-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="5b09e-107">Combien d’utilisateurs (échelle) doivent être activés pour le serveur de chat permanent?</span><span class="sxs-lookup"><span data-stu-id="5b09e-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="5b09e-108">Le serveur Chat permanent prend en charge les utilisateurs approvisionnés 150 000 (activés par stratégie) et un maximum d' 80 000 utilisateurs simultanés utilisant le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="5b09e-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="5b09e-109">Un seul serveur de conversation permanente peut prendre en charge 20 000 utilisateurs connectés, et un seul pool de serveur de conversation permanente peut comporter jusqu’à 4 serveurs actifs pour un total de 80 000 utilisateurs connectés simultanément.</span><span class="sxs-lookup"><span data-stu-id="5b09e-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="5b09e-110">Vous effectuez une migration à partir d’une version précédente du serveur de discussion de groupe ou vous déployez le serveur de chat permanent pour la première fois?</span><span class="sxs-lookup"><span data-stu-id="5b09e-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="5b09e-111">Est-il impératif de conformité?</span><span class="sxs-lookup"><span data-stu-id="5b09e-111">Are there compliance requirements?</span></span> <span data-ttu-id="5b09e-112">Le serveur Chat permanent prend en charge la conformité.</span><span class="sxs-lookup"><span data-stu-id="5b09e-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="5b09e-113">Le service de conformité s’exécute sur le serveur frontal de chat permanent du serveur et non sur la configuration requise pour un autre ordinateur dans les déploiements de serveurs de discussion de groupe précédents.</span><span class="sxs-lookup"><span data-stu-id="5b09e-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="5b09e-114">La conformité est facultative, et si elle est activée, une base de données de conformité doit être configurée pour stocker les données et événements de conformité.</span><span class="sxs-lookup"><span data-stu-id="5b09e-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="5b09e-115">Il est possible que vous souhaitiez également configurer un adaptateur pour utiliser les données de la base de données de conformité et convertir dans un autre format (par exemple, des fichiers XML ou des archives hébergées sur Exchange).</span><span class="sxs-lookup"><span data-stu-id="5b09e-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="5b09e-116">Comment contrôler les étendues, les limites éthiques et l’accès ?</span><span class="sxs-lookup"><span data-stu-id="5b09e-116">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="5b09e-117">Vous pouvez définir des **catégories** pour dissocier ces frontières, et choisir qui est autorisé à se trouver dans des salles créées dans chacune de ces catégories.</span><span class="sxs-lookup"><span data-stu-id="5b09e-117">You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="5b09e-118">Comment voulez-vous déterminer qui peut créer des salles ?</span><span class="sxs-lookup"><span data-stu-id="5b09e-118">How do you want to control who can create rooms?</span></span> <span data-ttu-id="5b09e-119">Vous pouvez configurer des **créateurs**en fonction de vos catégories, qui peuvent créer des salles.</span><span class="sxs-lookup"><span data-stu-id="5b09e-119">You can configure **Creators**, appropriate to your categories, who can create rooms.</span></span> <span data-ttu-id="5b09e-120">Les créateurs peuvent affecter d’autres membres comme **gestionnaires de salle de conversation** pour la gestion en continu des salles (en ajoutant ou en supprimant des membres supplémentaires), en fonction de l’étendue de **AllowedMembers/DeniedMembers** configurées par la catégorie.</span><span class="sxs-lookup"><span data-stu-id="5b09e-120">Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="5b09e-121">Comment créer des salles ?</span><span class="sxs-lookup"><span data-stu-id="5b09e-121">How do you want to create rooms?</span></span> <span data-ttu-id="5b09e-122">Le serveur Chat permanent fournit une fonctionnalité basée sur le Web pour la création et la gestion d’une salle.</span><span class="sxs-lookup"><span data-stu-id="5b09e-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="5b09e-123">Ce problème peut être lancé à partir du client 2013 Lync.</span><span class="sxs-lookup"><span data-stu-id="5b09e-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="5b09e-124">Vous pouvez choisir de définir une solution personnalisée (à l’aide du kit de développement logiciel (SDK) serveur Chat permanent qui implémente les exigences et flux de travail de votre entreprise, et configure le serveur de chat permanent pour diriger les utilisateurs vers votre solution personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5b09e-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="5b09e-125">Quel genre de compléments voulez-vous approvisionner ?</span><span class="sxs-lookup"><span data-stu-id="5b09e-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="5b09e-126">\*\*\*\* Les compléments améliorent l’environnement dans la salle en tirant parti du volet Extensibility dans le client 2013 de Lync afin de fournir un contexte pertinent pour la salle.</span><span class="sxs-lookup"><span data-stu-id="5b09e-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="5b09e-127">Vous pouvez choisir les compléments généraux les plus utiles à vos yeux (par exemple, le site de votre entreprise, des documents de collaboration internes, etc.).</span><span class="sxs-lookup"><span data-stu-id="5b09e-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="5b09e-128">Les gestionnaires de salles de conversation peuvent choisir l’un des compléments inscrits et l’associer à leurs salles, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="5b09e-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="5b09e-129">Quels sont vos besoins en matière de haute disponibilité et de récupération d’urgence ?</span><span class="sxs-lookup"><span data-stu-id="5b09e-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="5b09e-130">Le serveur Chat permanent prend en charge la mise en miroir SQL Server et SQL Server clustering pour une haute disponibilité et prend en charge jusqu’à 8 serveurs (4 en veille d’un niveau actif et 4) dans un pool étendu avec l’envoi du journal SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b09e-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="5b09e-131">Existe-t-il des exigences réglementaires ?</span><span class="sxs-lookup"><span data-stu-id="5b09e-131">Are there regulatory requirements?</span></span> <span data-ttu-id="5b09e-132">Si votre société se trouve dans un pays ou une région où les données doivent être conservées dans le pays, vous devrez peut-être déployer plusieurs pools de serveurs de chat permanent, chacun d’eux étant local.</span><span class="sxs-lookup"><span data-stu-id="5b09e-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="5b09e-133">Une salle, une catégorie ou un complément n’étend pas de pools, ce qui n’est qu’une seule liste de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="5b09e-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="5b09e-134">Vous pouvez gérer l’ensemble des catégories, des compléments et des salles pour chaque pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="5b09e-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="5b09e-135">Les utilisateurs peuvent être configurés de manière à avoir accès à des salles dans un ou plusieurs pools en utilisant l’étendue de la catégorie AllowedMembers ou l’étendue de l’appartenance de la salle, selon la façon dont vous concevez vos catégories.</span><span class="sxs-lookup"><span data-stu-id="5b09e-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5b09e-136">L’utilisation de plusieurs pools de serveurs de chat permanent ne vous offre pas de nouvelles mises à l’échelle (vous pouvez toujours avoir uniquement 80 000 connecté aux utilisateurs de tous vos pools de serveurs de chat permanent).</span><span class="sxs-lookup"><span data-stu-id="5b09e-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="5b09e-137">La principale raison de la prise en charge de plusieurs pools de serveurs de chat permanent est de prendre en charge les préoccupations réglementaires.</span><span class="sxs-lookup"><span data-stu-id="5b09e-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

