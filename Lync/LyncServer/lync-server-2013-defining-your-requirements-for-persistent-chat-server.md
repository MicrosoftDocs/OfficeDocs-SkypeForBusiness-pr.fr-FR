---
title: 'Lync Server 2013 : définition de la configuration requise pour le serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63e7af0dca758f6ac543bb0373d2cbb0d953ba0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504301"
---
# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="279cf-102">Définition des besoins de votre organisation pour le serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="279cf-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="279cf-103">_**Dernière modification de la rubrique :** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="279cf-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="279cf-104">Avant de déployer le serveur de conversation permanente pour votre organisation, il est essentiel de prendre en compte les principales questions suivantes pour optimiser votre déploiement :</span><span class="sxs-lookup"><span data-stu-id="279cf-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="279cf-105">Qui (profil utilisateur) doit être activé pour le serveur de conversation permanente ?</span><span class="sxs-lookup"><span data-stu-id="279cf-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="279cf-106">Le serveur de conversation permanente est activé par une stratégie qui peut être définie au niveau global, de site, de pool ou d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="279cf-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="279cf-107">Combien d’utilisateurs (mise à l’ampleur) doivent être activés pour le serveur de conversation permanente ?</span><span class="sxs-lookup"><span data-stu-id="279cf-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="279cf-108">Le serveur de conversation permanente prend en charge 150 000 utilisateurs configurés (activés par stratégie) et un maximum de 80 000 utilisateurs simultanés utilisant le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="279cf-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="279cf-109">Un seul serveur de conversation permanente peut prendre en charge 20 000 utilisateurs connectés et un seul pool de serveurs de conversation permanente peut avoir jusqu’à 4 serveurs actifs pour un total de 80 000 utilisateurs connectés simultanément.</span><span class="sxs-lookup"><span data-stu-id="279cf-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="279cf-110">Effectuez-vous une migration à partir d’une version précédente du serveur de conversation de groupe ou déployez-vous le serveur de conversation permanente pour la première fois ?</span><span class="sxs-lookup"><span data-stu-id="279cf-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="279cf-111">Existe-t-il des exigences de conformité ?</span><span class="sxs-lookup"><span data-stu-id="279cf-111">Are there compliance requirements?</span></span> <span data-ttu-id="279cf-112">Le serveur de conversation permanente prend en charge la conformité.</span><span class="sxs-lookup"><span data-stu-id="279cf-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="279cf-113">Le service de conformité s’exécute sous colocalisé sur le serveur frontal de serveur de conversation permanente, par opposition à la nécessité d’un autre ordinateur dans les déploiements de serveurs de conversation de groupe précédents.</span><span class="sxs-lookup"><span data-stu-id="279cf-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="279cf-114">La conformité est facultative et, si elle est choisie, elle nécessite une base de données de conformité qui doit être configurée pour stocker les données de conformité et les événements.</span><span class="sxs-lookup"><span data-stu-id="279cf-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="279cf-115">Vous pouvez également configurer un adaptateur pour qu’il prenne les données de la base de données de conformité et les convertit dans un autre format (par exemple, des fichiers XML ou des archives hébergées par Exchange).</span><span class="sxs-lookup"><span data-stu-id="279cf-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="279cf-p104">Comment contrôler les étendues, les limites éthiques et l’accès ? Vous pouvez définir des **catégories** afin d’établir des limites et choisir les personnes autorisées à être présentes dans les salles créées dans chacune de ces catégories.</span><span class="sxs-lookup"><span data-stu-id="279cf-p104">How do you want to control scopes, ethical boundaries, and access? You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="279cf-p105">Comment contrôler les personnes autorisées à créer des salles ? Vous pouvez configurer des **créateurs** en fonction de vos catégories pour créer des salles. Les créateurs peuvent affecter d’autres membres (tels que les **gestionnaires de salles de conversation**) pour la gestion permanente des salles (par ajout ou suppression de membres), en fonction de l’étendue de **AllowedMembers/DeniedMembers** configurée par la catégorie.</span><span class="sxs-lookup"><span data-stu-id="279cf-p105">How do you want to control who can create rooms? You can configure **Creators**, appropriate to your categories, who can create rooms. Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="279cf-121">Comment créer des salles ?</span><span class="sxs-lookup"><span data-stu-id="279cf-121">How do you want to create rooms?</span></span> <span data-ttu-id="279cf-122">Le serveur de conversation permanente fournit une fonctionnalité Web pour la création et la gestion de salle.</span><span class="sxs-lookup"><span data-stu-id="279cf-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="279cf-123">Elle peut être lancée à partir du client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="279cf-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="279cf-124">Vous pouvez choisir de définir une solution personnalisée (en utilisant le kit de développement logiciel (SDK) du serveur de conversation permanente) qui implémente les flux de travail et les besoins de votre entreprise, et configure le serveur de conversation permanente pour qu’il dirige les utilisateurs vers votre solution personnalisée.</span><span class="sxs-lookup"><span data-stu-id="279cf-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="279cf-125">Quel genre de compléments voulez-vous approvisionner ?</span><span class="sxs-lookup"><span data-stu-id="279cf-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="279cf-126">Les **compléments** améliorent l’expérience dans la salle en tirant parti du volet d’extensibilité du client Lync 2013 pour fournir un contexte pertinent pour la salle.</span><span class="sxs-lookup"><span data-stu-id="279cf-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="279cf-127">Vous pouvez choisir les compléments généraux les plus utiles à vos yeux (par exemple, le site de votre entreprise, des documents de collaboration internes, etc.).</span><span class="sxs-lookup"><span data-stu-id="279cf-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="279cf-128">Les gestionnaires de salles de conversation peuvent choisir l’un des compléments inscrits et l’associer à leurs salles, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="279cf-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="279cf-129">Quels sont les types d’exigences en matière de haute disponibilité et de récupération d’urgence ?</span><span class="sxs-lookup"><span data-stu-id="279cf-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="279cf-130">Le serveur de conversation permanente prend en charge la mise en miroir SQL Server et le clustering SQL Server pour une haute disponibilité et prend en charge jusqu’à 8 serveurs (4 active et 4 Standby) dans un pool étiré avec la copie des journaux de transaction SQL Server pour la récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="279cf-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="279cf-131">Existe-t-il des exigences en matière de réglementation ?</span><span class="sxs-lookup"><span data-stu-id="279cf-131">Are there regulatory requirements?</span></span> <span data-ttu-id="279cf-132">Si votre société se trouve dans un pays/une région où les données doivent être conservées dans le pays, vous devrez peut-être déployer plusieurs pools de serveurs de conversation permanente, chacun d’eux étant local à une géographie spécifique.</span><span class="sxs-lookup"><span data-stu-id="279cf-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="279cf-133">Une salle, une catégorie ou un complément ne couvre pas les pools ; il n’appartient qu’à un seul pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="279cf-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="279cf-134">Vous pouvez gérer l’ensemble des catégories, des compléments et des salles pour chaque pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="279cf-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="279cf-135">Les utilisateurs peuvent être configurés pour accéder aux salles d’un ou de plusieurs pools à l’aide de la catégorie AllowedMembers ou de l’étendue d’appartenance de la salle, en fonction de la conception de vos catégories.</span><span class="sxs-lookup"><span data-stu-id="279cf-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="279cf-136">Le fait de disposer de plusieurs pools de serveurs de conversation permanente ne vous offre pas une plus grande échelle (vous pouvez toujours avoir seulement 80 000 utilisateurs connectés simultanément sur tous vos pools de serveurs de conversation permanente).</span><span class="sxs-lookup"><span data-stu-id="279cf-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="279cf-137">La principale raison de la prise en charge de plusieurs pools de serveurs de conversation permanente est de prendre en charge les préoccupations réglementaires.</span><span class="sxs-lookup"><span data-stu-id="279cf-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

