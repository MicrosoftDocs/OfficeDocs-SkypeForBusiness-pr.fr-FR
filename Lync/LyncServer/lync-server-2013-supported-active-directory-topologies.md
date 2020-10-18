---
title: 'Lync Server 2013 : topologies Active Directory prises en charge'
description: 'Lync Server 2013 : topologies Active Directory prises en charge.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ce820a36cb033933b423e01deb5a3049ed3ea2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575310"
---
# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="3022b-103">Topologies Active Directory prises en charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3022b-103">Supported Active Directory topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3022b-104">_**Dernière modification de la rubrique :** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="3022b-104">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="3022b-105">Lync Server 2013 prend en charge les mêmes topologies de services de domaine Active Directory que Microsoft Lync Server 2010 et Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3022b-105">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="3022b-106">Les topologies suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="3022b-106">The following topologies are supported:</span></span>

  - <span data-ttu-id="3022b-107">Forêt unique avec domaine unique</span><span class="sxs-lookup"><span data-stu-id="3022b-107">Single forest with single domain</span></span>

  - <span data-ttu-id="3022b-108">Forêt unique avec un arbre unique et plusieurs domaines</span><span class="sxs-lookup"><span data-stu-id="3022b-108">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="3022b-109">Forêt unique avec plusieurs arbres et des espaces de noms disjoints</span><span class="sxs-lookup"><span data-stu-id="3022b-109">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="3022b-110">Plusieurs forêts dans une topologie de forêt centrale</span><span class="sxs-lookup"><span data-stu-id="3022b-110">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="3022b-111">Plusieurs forêts dans une topologie de forêt de ressources</span><span class="sxs-lookup"><span data-stu-id="3022b-111">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="3022b-112">Plusieurs forêts dans une topologie de forêt de ressources Lync avec Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3022b-112">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="3022b-113">L’illustration suivante identifie les icônes utilisées dans les illustrations de cette section.</span><span class="sxs-lookup"><span data-stu-id="3022b-113">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="3022b-114">**Éléments des illustrations de topologie**</span><span class="sxs-lookup"><span data-stu-id="3022b-114">**Key to topology illustrations**</span></span>

<span data-ttu-id="3022b-115">![Éléments des illustrations de topologie](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Éléments des illustrations de topologie")</span><span class="sxs-lookup"><span data-stu-id="3022b-115">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="3022b-116">Forêt unique, domaine unique</span><span class="sxs-lookup"><span data-stu-id="3022b-116">Single Forest, Single Domain</span></span>

<span data-ttu-id="3022b-117">La topologie Active Directory la plus simple prise en charge par Lync Server, une forêt de domaine unique, est une topologie commune.</span><span class="sxs-lookup"><span data-stu-id="3022b-117">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="3022b-118">La figure suivante illustre un déploiement de Lync Server dans une topologie Active Directory à domaine unique.</span><span class="sxs-lookup"><span data-stu-id="3022b-118">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="3022b-119">**Topologie à domaine unique**</span><span class="sxs-lookup"><span data-stu-id="3022b-119">**Single domain topology**</span></span>

<span data-ttu-id="3022b-120">![Topologie à domaine unique](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologie à domaine unique")</span><span class="sxs-lookup"><span data-stu-id="3022b-120">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="3022b-121">Une seule forêt, plusieurs domaines</span><span class="sxs-lookup"><span data-stu-id="3022b-121">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="3022b-122">Une autre topologie Active Directory prise en charge par Lync Server est une forêt unique qui se compose d’un domaine racine et d’un ou plusieurs domaines enfants.</span><span class="sxs-lookup"><span data-stu-id="3022b-122">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="3022b-123">Dans ce type de topologie Active Directory, le domaine dans lequel vous créez les utilisateurs peut être différent du domaine dans lequel vous déployez Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3022b-123">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="3022b-124">Toutefois, si vous déployez un pool frontal, vous devez déployer tous les serveurs frontaux dans le pool au sein d’un seul domaine.</span><span class="sxs-lookup"><span data-stu-id="3022b-124">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="3022b-125">La prise en charge de Lync Server pour les groupes d’administrateurs universels Windows permet l’administration entre domaines.</span><span class="sxs-lookup"><span data-stu-id="3022b-125">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="3022b-126">L’illustration suivante montre un déploiement dans une seule forêt avec plusieurs domaines.</span><span class="sxs-lookup"><span data-stu-id="3022b-126">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="3022b-127">Dans cette illustration, une icône utilisateur indique le domaine dans lequel le compte d’utilisateur est hébergé et la flèche pointe vers le domaine où se trouve le pool Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3022b-127">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="3022b-128">Les comptes d’utilisateur sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3022b-128">User accounts include the following:</span></span>

  - <span data-ttu-id="3022b-129">Comptes d’utilisateur dans le même domaine que le pool Lync Server</span><span class="sxs-lookup"><span data-stu-id="3022b-129">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="3022b-130">Comptes d’utilisateur dans un domaine différent du pool Lync Server</span><span class="sxs-lookup"><span data-stu-id="3022b-130">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="3022b-131">Comptes d’utilisateur dans un domaine enfant du domaine avec le pool Lync Server</span><span class="sxs-lookup"><span data-stu-id="3022b-131">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="3022b-132">**Forêt unique avec plusieurs domaines**</span><span class="sxs-lookup"><span data-stu-id="3022b-132">**Single forest with multiple domains**</span></span>

<span data-ttu-id="3022b-133">![Forêt unique avec plusieurs domaines](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Forêt unique avec plusieurs domaines")</span><span class="sxs-lookup"><span data-stu-id="3022b-133">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="3022b-134">Une seule forêt, plusieurs arbres</span><span class="sxs-lookup"><span data-stu-id="3022b-134">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="3022b-135">Une topologie de forêt à plusieurs arbres comporte au moins deux domaines qui définissent des arborescences indépendantes et des espaces de noms Active Directory distincts.</span><span class="sxs-lookup"><span data-stu-id="3022b-135">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="3022b-136">L’illustration suivante montre une forêt unique avec plusieurs arbres.</span><span class="sxs-lookup"><span data-stu-id="3022b-136">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="3022b-137">Dans cette illustration, une icône utilisateur indique le domaine dans lequel le compte d’utilisateur est hébergé, une ligne pleine pointe vers un pool Lync Server qui se trouve dans le même domaine ou un domaine différent, et une ligne en pointillés pointe vers le pool Lync Server qui réside dans une autre arborescence.</span><span class="sxs-lookup"><span data-stu-id="3022b-137">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="3022b-138">Les comptes d’utilisateur sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3022b-138">User accounts include the following:</span></span>

  - <span data-ttu-id="3022b-139">Comptes d’utilisateur dans le même domaine que le pool Lync Server</span><span class="sxs-lookup"><span data-stu-id="3022b-139">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="3022b-140">Les comptes d’utilisateur dans un domaine différent, à partir de la même arborescence que le pool Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3022b-140">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="3022b-141">Comptes d’utilisateur dans une arborescence différente du pool Lync Server</span><span class="sxs-lookup"><span data-stu-id="3022b-141">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="3022b-142">**Forêt unique avec plusieurs arbres**</span><span class="sxs-lookup"><span data-stu-id="3022b-142">**Single forest with multiple trees**</span></span>

<span data-ttu-id="3022b-143">![Forêt unique avec plusieurs arbres](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Forêt unique avec plusieurs arbres")</span><span class="sxs-lookup"><span data-stu-id="3022b-143">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="3022b-144">Plusieurs forêts, forêt centrale</span><span class="sxs-lookup"><span data-stu-id="3022b-144">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="3022b-145">Lync Server prend en charge plusieurs forêts configurées dans une topologie de forêt centrale.</span><span class="sxs-lookup"><span data-stu-id="3022b-145">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="3022b-146">Les topologies de forêt centrale utilisent des objets contact dans la forêt centrale pour représenter des utilisateurs dans les autres forêts.</span><span class="sxs-lookup"><span data-stu-id="3022b-146">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="3022b-147">La forêt centrale héberge également des comptes d’utilisateur pour tout utilisateur de cette forêt.</span><span class="sxs-lookup"><span data-stu-id="3022b-147">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="3022b-148">Une application de synchronisation d’annuaires, tel que Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateur dans l’organisation : lorsqu’un nouveau compte d’utilisateur est créé dans l’une des forêts ou lorsqu’un compte d’utilisateur est supprimé d’une forêt, l’application de synchronisation d’annuaires synchronise le contact correspondant dans la forêt centrale.</span><span class="sxs-lookup"><span data-stu-id="3022b-148">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="3022b-149">Une forêt centrale présente les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="3022b-149">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="3022b-150">Les serveurs exécutant Lync Server sont centralisés au sein d’une forêt unique.</span><span class="sxs-lookup"><span data-stu-id="3022b-150">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="3022b-151">Les utilisateurs peuvent rechercher et communiquer avec d’autres utilisateurs dans n’importe quelle forêt.</span><span class="sxs-lookup"><span data-stu-id="3022b-151">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="3022b-152">Les utilisateurs peuvent voir la présence d’autres utilisateurs dans n’importe quelle forêt.</span><span class="sxs-lookup"><span data-stu-id="3022b-152">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="3022b-153">L’application de synchronisation d’annuaires automatise l’ajout et la suppression d’objets contact dans la forêt centrale à mesure que des comptes d’utilisateur sont créés ou supprimés.</span><span class="sxs-lookup"><span data-stu-id="3022b-153">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="3022b-154">L’illustration suivante illustre une topologie de forêt centrale.</span><span class="sxs-lookup"><span data-stu-id="3022b-154">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="3022b-155">Dans cette figure, il existe des relations d’approbation bidirectionnelles entre le domaine qui héberge Lync Server, qui se trouve dans la forêt centrale et chaque domaine User-only, qui se trouve dans une forêt distincte.</span><span class="sxs-lookup"><span data-stu-id="3022b-155">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="3022b-156">Le schéma dans les différentes forêts d’utilisateurs ne doit pas être étendu.</span><span class="sxs-lookup"><span data-stu-id="3022b-156">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="3022b-157">**Topologie de forêt centrale**</span><span class="sxs-lookup"><span data-stu-id="3022b-157">**Central forest topology**</span></span>

<span data-ttu-id="3022b-158">![Topologie de forêt centrale](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologie de forêt centrale")</span><span class="sxs-lookup"><span data-stu-id="3022b-158">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="3022b-159">Plusieurs forêts, forêt de ressources</span><span class="sxs-lookup"><span data-stu-id="3022b-159">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="3022b-160">Dans une topologie de forêt de ressources, une forêt est dédiée à l’exécution d’applications serveur, telles que Microsoft Exchange Server et Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3022b-160">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="3022b-161">La forêt de ressources héberge les applications serveur et une représentation synchronisée de l’objet utilisateur actif, mais elle ne contient aucun compte d’utilisateur pour lequel l’ouverture de session est activée.</span><span class="sxs-lookup"><span data-stu-id="3022b-161">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="3022b-162">La forêt de ressources joue le rôle d’un environnement de services partagés pour les autres forêts dans lesquelles résident les objets utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3022b-162">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="3022b-163">Les forêts d’utilisateurs ont une relation de confiance au niveau de la forêt avec la forêt de ressources.</span><span class="sxs-lookup"><span data-stu-id="3022b-163">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="3022b-164">Lorsque vous déployez Lync Server dans ce type de topologie, vous créez un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3022b-164">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="3022b-165">Si Microsoft Exchange est déjà déployé dans la forêt de ressources, il se peut que les comptes d’utilisateurs désactivés existent déjà.</span><span class="sxs-lookup"><span data-stu-id="3022b-165">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="3022b-166">Une application de synchronisation d’annuaires, tel que MIIS, Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3022b-166">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="3022b-167">Lorsqu’un nouveau compte d’utilisateurs est créé dans l’une des forêts d’utilisateurs ou lorsqu’un compte d’utilisateur est supprimé d’une forêt, l’application de synchronisation d’annuaires synchronise la représentation d’utilisateur correspondante dans la forêt de ressources.</span><span class="sxs-lookup"><span data-stu-id="3022b-167">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="3022b-p108">Cette topologie peut être utilisée pour fournir une infrastructure partagée pour les services dans les organisations qui gèrent plusieurs forêts ou pour administrer séparément les objets Active Directory. Les entreprises qui doivent isoler l’administration Active Directory pour des raisons de sécurité choisissent souvent cette topologie.</span><span class="sxs-lookup"><span data-stu-id="3022b-p108">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration. Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="3022b-170">Cette topologie évite de devoir étendre le schéma Active Directory à une forêt unique (c’est-à-dire la forêt de ressources).</span><span class="sxs-lookup"><span data-stu-id="3022b-170">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="3022b-171">Le diagramme suivant illustre une topologie de forêt de ressources.</span><span class="sxs-lookup"><span data-stu-id="3022b-171">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="3022b-172">**Topologie de forêt de ressources**</span><span class="sxs-lookup"><span data-stu-id="3022b-172">**Resource forest topology**</span></span>

<span data-ttu-id="3022b-173">![Topologie de forêt de ressources Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topologie de forêt de ressources Active Directory")</span><span class="sxs-lookup"><span data-stu-id="3022b-173">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="3022b-174">Plusieurs forêts dans une topologie de forêt de ressources Lync avec Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3022b-174">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="3022b-175">Dans cette topologie, une ou plusieurs forêts sont situées sur site et sont dédiées à l’hébergement des comptes d’utilisateur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3022b-175">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="3022b-176">La forêt de ressources se trouve hors site et est gérée par un fournisseur d’hébergement tiers.</span><span class="sxs-lookup"><span data-stu-id="3022b-176">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="3022b-177">La forêt de ressources contient uniquement le déploiement Lync Server et une réplication synchronisée des comptes d’utilisateur à partir des forêts de comptes d’utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="3022b-177">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="3022b-178">Il ne contient pas de comptes d’utilisateur à extension connexion.</span><span class="sxs-lookup"><span data-stu-id="3022b-178">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="3022b-179">Exchange est déployé dans les forêts de compte d’utilisateur locales intégrées avec Exchange Online (hybride), ou les services de messagerie pour les comptes d’utilisateur locaux sont fournis exclusivement par Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3022b-179">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="3022b-180">La forêt de ressources agit comme un environnement de services partagés pour les forêts Active Directory locales où les objets utilisateur résident.</span><span class="sxs-lookup"><span data-stu-id="3022b-180">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="3022b-181">Les forêts de compte d’utilisateur ont une relation d’approbation de niveau forêt unidirectionnelle avec la forêt de ressources.</span><span class="sxs-lookup"><span data-stu-id="3022b-181">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="3022b-182">Lorsque vous déployez Lync Server dans ce type de topologie, vous créez un objet utilisateur désactivé dans la forêt de ressources pour chaque compte d’utilisateur dans les forêts d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3022b-182">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="3022b-183">Une application de synchronisation d’annuaires, tel que MIIS, Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gère le cycle de vie des comptes d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3022b-183">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="3022b-184">Lorsqu’un nouveau compte d’utilisateurs est créé dans l’une des forêts d’utilisateurs ou lorsqu’un compte d’utilisateur est supprimé d’une forêt, l’application de synchronisation d’annuaires synchronise la représentation d’utilisateur correspondante dans la forêt de ressources.</span><span class="sxs-lookup"><span data-stu-id="3022b-184">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="3022b-185">Pour plus d’informations sur la configuration d’un déploiement à forêts multiples, reportez-vous à la rubrique [Deploying Lync in a multi-Forest architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span><span class="sxs-lookup"><span data-stu-id="3022b-185">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

