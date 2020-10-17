---
title: 'Lync Server 2013 : services de domaine Active Directory pour Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a4e548f68f68a65ac4ecfb2e4ddc532b5f337c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529711"
---
# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="bdb3c-102">Services de domaine Active Directory pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdb3c-102">Active Directory Domain Services for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdb3c-103">_**Dernière modification de la rubrique :** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="bdb3c-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="bdb3c-104">Les services de domaine Active Directory sont des fonctions de service d’annuaire pour les réseaux Windows Server 2003, Windows Server 2008, Windows Server 2012 et Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="bdb3c-105">Les services de domaine Active Directory servent également de base à la création de l’infrastructure de sécurité Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="bdb3c-106">L’objectif de cette section est de décrire comment Lync Server 2013 utilise les services de domaine Active Directory pour créer un environnement de confiance pour la messagerie instantanée, la conférence Web, les médias et la voix.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="bdb3c-107">Pour plus d’informations sur les extensions Lync Server aux services de domaine Active Directory et sur la préparation de votre environnement pour les services de domaine Active Directory, voir [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="bdb3c-108">Pour des détails sur le rôle des services de domaine Active Directory dans les réseaux Windows Server, voir la documentation concernant votre version du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="bdb3c-109">Lync Server 2013 utilise les services de domaine Active Directory pour stocker les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="bdb3c-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="bdb3c-110">Paramètres globaux requis par tous les serveurs exécutant Lync Server 2013 dans une forêt.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="bdb3c-111">Informations de service qui identifient les rôles de tous les serveurs exécutant Lync Server 2013 dans une forêt.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="bdb3c-112">Certains paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="bdb3c-113">Infrastructure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bdb3c-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="bdb3c-114">Les conditions d’infrastructure requises pour Active Directory incluent les suivantes :</span><span class="sxs-lookup"><span data-stu-id="bdb3c-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="bdb3c-115">Configuration de système d’exploitation requise pour les contrôleurs de domaine</span><span class="sxs-lookup"><span data-stu-id="bdb3c-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="bdb3c-116">Configuration requise de niveau fonctionnel du domaine ou de la forêt</span><span class="sxs-lookup"><span data-stu-id="bdb3c-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="bdb3c-117">Configuration de catalogue global requise</span><span class="sxs-lookup"><span data-stu-id="bdb3c-117">Global catalog domain requirements</span></span>

<span data-ttu-id="bdb3c-118">Pour plus d’informations, voir [Active Directory infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="bdb3c-119">Préparation des services de domaine Active Directory</span><span class="sxs-lookup"><span data-stu-id="bdb3c-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bdb3c-120">Nous vous recommandons de déployer les paramètres globaux du conteneur système au lieu du conteneur de configuration.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="bdb3c-121">Cela n’améliore pas la sécurité, mais peut induire des améliorations en termes d’extensibilité pour certaines topologies de service de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="bdb3c-122">Si vous effectuez une migration à partir de Microsoft Office Communications Server 2007 et que vous avez utilisé le conteneur système mais que vous envisagez d’utiliser le conteneur de configuration, vous devez déplacer les paramètres dans le conteneur système avant de procéder à une mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="bdb3c-123">Pour migrer vos paramètres de conteneur système vers le conteneur de configuration, reportez-vous à l’outil de migration des paramètres globaux d’Office Communications Server 2007 à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A> .</span><span class="sxs-lookup"><span data-stu-id="bdb3c-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="bdb3c-124">Lors du déploiement de Lync Server 2013, la première étape consiste à préparer les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="bdb3c-125">La préparation des services de domaine Active Directory pour Lync Server 2013 comprend les trois étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="bdb3c-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="bdb3c-126">**Préparer le schéma**.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-126">**Prepare Schema**.</span></span> <span data-ttu-id="bdb3c-127">Cette tâche étend le schéma dans les services de domaine Active Directory pour inclure des classes et des attributs spécifiques à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="bdb3c-128">Pour plus d’informations sur la préparation du schéma, voir exécution de la [préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-running-schema-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="bdb3c-129">Pour plus d’informations, reportez-vous à [migration d’Office Communications Server 2007 R2 vers Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="bdb3c-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="bdb3c-130">**Préparer la forêt**.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-130">**Prepare Forest**.</span></span> <span data-ttu-id="bdb3c-131">Cette tâche crée les paramètres globaux et les objets dans le domaine racine de la forêt, conjointement aux groupes d’administration et de service universels qui gouvernent l’accès à ces paramètres et objets.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="bdb3c-132">Pour plus d’informations sur la préparation de la forêt, voir exécution de la [préparation de la forêt pour Lync Server 2013](lync-server-2013-running-forest-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="bdb3c-133">**Préparer le domaine**.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-133">**Prepare Domain**.</span></span> <span data-ttu-id="bdb3c-134">Cette tâche ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui accordent les autorisations pour héberger et gérer les utilisateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="bdb3c-135">Cette tâche doit être exécutée dans tous les domaines où vous souhaitez déployer des serveurs exécutant Lync Server 2013 et tous les domaines où les utilisateurs de Lync Server sont hébergés.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="bdb3c-136">Pour plus d’informations sur la préparation du domaine, voir [Running Domain Preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="bdb3c-137">Pour obtenir une vue d’ensemble du processus complet de préparation d’Active Directory et des droits et autorisations requis pour effectuer chaque étape, voir [Active Directory infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="bdb3c-138">Groupes universels</span><span class="sxs-lookup"><span data-stu-id="bdb3c-138">Universal Groups</span></span>

<span data-ttu-id="bdb3c-139">Lors de la préparation de la forêt, Lync Server 2013 crée plusieurs groupes universels dans les services de domaine Active Directory qui ont l’autorisation d’accéder aux paramètres globaux et de les gérer.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="bdb3c-140">Ces groupes universels incluent les suivants :</span><span class="sxs-lookup"><span data-stu-id="bdb3c-140">These universal groups include:</span></span>

  - <span data-ttu-id="bdb3c-141">**Groupes d’administration**.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-141">**Administrative groups**.</span></span> <span data-ttu-id="bdb3c-142">Ces groupes définissent les rôles d’administrateur fondamentaux d’un réseau Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="bdb3c-143">Lors de la préparation de la forêt, ces groupes d’administrateurs sont ajoutés aux groupes d’infrastructure Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="bdb3c-144">**Groupes de services**</span><span class="sxs-lookup"><span data-stu-id="bdb3c-144">**Service groups**.</span></span> <span data-ttu-id="bdb3c-145">Ces groupes sont des comptes de service qui sont requis pour accéder aux différents services fournis par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="bdb3c-146">**Groupes d’infrastructure**.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-146">**Infrastructure groups**.</span></span> <span data-ttu-id="bdb3c-147">Ces groupes fournissent l’autorisation d’accéder à des zones spécifiques de l’infrastructure Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="bdb3c-148">Elles fonctionnent comme des composants de groupes d’administration et vous ne devez pas les modifier ni y ajouter des utilisateurs directement.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="bdb3c-149">Lors de la préparation de la forêt, des groupes de service et d’administration spécifiques sont ajoutés aux groupes d’infrastructure appropriés.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="bdb3c-150">Pour plus d’informations sur les groupes universels spécifiques créés lors de la préparation d’AD pour Lync Server, ainsi que les groupes de service et d’administration qui sont ajoutés aux groupes d’infrastructure, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bdb3c-151">Lync Server 2013 prend en charge les groupes universels dans le Windows Server 2012 pour les serveurs exécutant Lync Server 2013, ainsi que les systèmes d’exploitation Windows Server 2003 pour les contrôleurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="bdb3c-152">Les membres des groupes universels peuvent inclure d’autres groupes et comptes provenant de n’importe quel domaine de l’arborescence de domaine ou de la forêt et peuvent se voir attribuer des autorisations dans n’importe quel domaine de l’arborescence de domaine ou de la forêt.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="bdb3c-153">La prise en charge de groupes universels, combinée à la délégation d’administrateur, simplifie la gestion d’un déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="bdb3c-154">Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre pour permettre à un administrateur de gérer les deux.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="bdb3c-155">Contrôle d’accès basé sur un rôle</span><span class="sxs-lookup"><span data-stu-id="bdb3c-155">Role-Based Access Control</span></span>

<span data-ttu-id="bdb3c-156">En plus de créer des groupes de service et d’administration universels et d’ajouter des groupes de service et d’administration aux groupes universels appropriés, la préparation de forêt crée également des groupes de contrôle d’accès Role-Based (RBAC).</span><span class="sxs-lookup"><span data-stu-id="bdb3c-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="bdb3c-157">Pour plus d’informations sur les groupes RBAC spécifiques créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="bdb3c-158">Pour plus d’informations sur les groupes RBAC, voir [Role-Based Access Control (RBAC) pour Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="bdb3c-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="bdb3c-159">Entrées de contrôle d’accès (ACE) et héritage</span><span class="sxs-lookup"><span data-stu-id="bdb3c-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="bdb3c-160">La préparation de la forêt crée des ACE privées et publiques et ajoute des ACE pour les groupes universels qu’elle crée.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="bdb3c-161">Il crée des ACE privées spécifiques sur le conteneur de paramètres globaux utilisé par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="bdb3c-162">Ce conteneur est utilisé uniquement par Lync Server et se trouve dans le conteneur de configuration ou dans le conteneur système du domaine racine, en fonction de l’emplacement de stockage des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="bdb3c-p114">L’étape de préparation du domaine ajoute les entrées de contrôle d’accès nécessaires aux groupes universels qui accordent les autorisations d’hébergement et de gestion des utilisateurs dans le domaine. La préparation du domaine créé des entrées de contrôle d’accès sur la racine du domaine et dans trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="bdb3c-165">Pour plus d’informations sur les ACE publiques créées et ajoutées par la préparation de la forêt et la préparation du domaine, voir [modifications apportées par la préparation de la forêt dans Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) et les [modifications apportées par la préparation du domaine dans Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="bdb3c-166">Les organisations verrouillent souvent les services de domaine Active Directory (AD DS) dans le but de réduire les risques liés à la sécurité.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="bdb3c-167">Toutefois, un environnement Active Directory verrouillé peut limiter les autorisations requises par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="bdb3c-168">Cela peut inclure la suppression des entrées de contrôle d’accès des conteneurs et des unités d’organisation ou la désactivation de l’héritage des autorisations sur les objets Utilisateur, Contact, InetOrgPerson ou Ordinateur.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="bdb3c-169">Dans un environnement Active Directory verrouillé, les autorisations doivent être manuellement définies sur les conteneurs et les unités d’organisation qui les requièrent.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="bdb3c-170">Pour plus d’informations, reportez-vous à la rubrique [préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="bdb3c-171">Informations relatives aux serveurs</span><span class="sxs-lookup"><span data-stu-id="bdb3c-171">Server Information</span></span>

<span data-ttu-id="bdb3c-172">Lors de l’activation, Lync Server 2013 publie des informations sur le serveur aux trois emplacements suivants dans les services de domaine Active Directory :</span><span class="sxs-lookup"><span data-stu-id="bdb3c-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="bdb3c-173">Un point de connexion de service (SCP) sur chaque objet ordinateur Active Directory correspondant à un ordinateur physique sur lequel Lync Server 2013 est installé.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="bdb3c-174">les objets serveur créés dans le conteneur de la classe **msRTCSIP-Pools** ;</span><span class="sxs-lookup"><span data-stu-id="bdb3c-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="bdb3c-175">Serveurs approuvés spécifiés dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="bdb3c-176">Points de connexion de service</span><span class="sxs-lookup"><span data-stu-id="bdb3c-176">Service Connection Points</span></span>

<span data-ttu-id="bdb3c-177">Chaque objet Lync Server 2013 dans les services de domaine Active Directory possède un SCP appelé services RTC, qui, à son tour, contient un certain nombre d’attributs qui identifient chaque ordinateur et spécifient les services qu’il fournit.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="bdb3c-178">Les principaux attributs d’un point de connexion de service sont notamment *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* et *serviceBindingInformation*.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="bdb3c-179">Les applications tierces de gestion des actifs peuvent obtenir des informations sur les serveurs d’un déploiement en recherchant ces attributs, ainsi que d’autres attributs de point de connexion de service.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="bdb3c-180">Objets serveur Active Directory</span><span class="sxs-lookup"><span data-stu-id="bdb3c-180">Active Directory Server Objects</span></span>

<span data-ttu-id="bdb3c-181">Chaque rôle serveur Lync Server 2013 possède un objet Active Directory correspondant dont les attributs définissent les services fournis par ce rôle.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="bdb3c-182">En outre, lorsqu’un serveur Standard Edition est activé, ou lorsqu’un pool Enterprise Edition est créé, Lync Server 2013 crée un nouvel objet **msRTCSIP-pool** dans le conteneur **msRTCSIP-pools** .</span><span class="sxs-lookup"><span data-stu-id="bdb3c-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="bdb3c-183">La classe **msRTCSIP-Pool** définit le nom de domaine complet (FQDN) du pool, de même que l’association entre les composants frontal et principal du pool.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="bdb3c-184">(Un serveur Standard Edition Server est considéré comme un pool logique dont les composants frontal et principal sont colocalisés sur un même ordinateur.)</span><span class="sxs-lookup"><span data-stu-id="bdb3c-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="bdb3c-185">Serveurs approuvés</span><span class="sxs-lookup"><span data-stu-id="bdb3c-185">Trusted Servers</span></span>

<span data-ttu-id="bdb3c-186">Dans Lync Server 2013, les serveurs de confiance sont ceux qui sont spécifiés lorsque vous exécutez le générateur de topologies et que vous publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="bdb3c-187">La topologie publiée, avec toutes les informations sur les serveurs, est stockée dans le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="bdb3c-188">Seuls les serveurs définis dans le magasin central de gestion sont approuvés.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="bdb3c-189">Dans Lync Server 2013, un serveur approuvé est un serveur qui répond aux critères suivants :</span><span class="sxs-lookup"><span data-stu-id="bdb3c-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="bdb3c-190">Le nom de domaine complet (FQDN) du serveur existe dans la topologie stockée dans le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="bdb3c-191">Le serveur présente un certificat valide émanant d’une autorité de certification approuvée.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="bdb3c-192">Pour plus d’informations, reportez-vous à [Certificate infrastructure Requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdb3c-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="bdb3c-p120">Si un de ces critères n’est pas respecté, le serveur n’est pas approuvé et la connexion au serveur est refusée. Cette double exigence permet de contrer une attaque, peu probable, au cours de laquelle un serveur non autorisé tente de s’approprier le nom de domaine complet d’un serveur valide.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="bdb3c-195">De plus, pour permettre aux déploiements de Microsoft Office Communications Server 2007 R2 et de Microsoft Office Communications Server 2007 de communiquer avec des serveurs Lync Server 2013, Lync Server 2013 crée des conteneurs lors de la préparation de la forêt pour les listes de serveurs approuvés pour les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="bdb3c-196">Le tableau ci-dessous décrit les conteneurs créés dans un but de compatibilité avec les déploiements précédents.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="bdb3c-197">Listes de serveurs approuvés et leurs conteneurs Active Directory pour compatibilité avec les éditions précédentes</span><span class="sxs-lookup"><span data-stu-id="bdb3c-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdb3c-198">Liste des serveurs approuvés</span><span class="sxs-lookup"><span data-stu-id="bdb3c-198">Trusted server list</span></span></th>
<th><span data-ttu-id="bdb3c-199">Conteneur Active Directory</span><span class="sxs-lookup"><span data-stu-id="bdb3c-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdb3c-200">Serveurs Standard Edition Server et serveurs frontaux de pool d’entreprise</span><span class="sxs-lookup"><span data-stu-id="bdb3c-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="bdb3c-201">Service RTC/Paramètres globaux</span><span class="sxs-lookup"><span data-stu-id="bdb3c-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb3c-202">Serveurs de conférence</span><span class="sxs-lookup"><span data-stu-id="bdb3c-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="bdb3c-203">RTC Service/Serveurs MCU approuvés (Trusted MCUs)</span><span class="sxs-lookup"><span data-stu-id="bdb3c-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb3c-204">Serveurs de composants web</span><span class="sxs-lookup"><span data-stu-id="bdb3c-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="bdb3c-205">Service RTC/Serveurs de composants web approuvés</span><span class="sxs-lookup"><span data-stu-id="bdb3c-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdb3c-206">Serveurs de médiation et serveurs Communicator Web Access, serveur d’application, serveur d’inscriptions avec QoE, service de conférence A/V (également serveurs SIP tiers)</span><span class="sxs-lookup"><span data-stu-id="bdb3c-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="bdb3c-207">Service RTC/Services approuvés</span><span class="sxs-lookup"><span data-stu-id="bdb3c-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdb3c-208">Serveurs proxy</span><span class="sxs-lookup"><span data-stu-id="bdb3c-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="bdb3c-209">Lync Server 2013 ne prend pas en charge la compatibilité descendante pour les serveurs proxy</span><span class="sxs-lookup"><span data-stu-id="bdb3c-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bdb3c-210">Pour prendre en charge les serveurs de confiance des versions précédentes, vous devez exécuter l’outil Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="bdb3c-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="bdb3c-211">Pour plus d’informations sur l’exécution de Best Practices Analyzer, reportez-vous à la rubrique [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633) .</span><span class="sxs-lookup"><span data-stu-id="bdb3c-211">For details about running the best practices analyzer, see [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

