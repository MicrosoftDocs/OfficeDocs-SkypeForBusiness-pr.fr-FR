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
ms.openlocfilehash: 4ac4b4da954fd792559d2160ce457aec91cb0ac6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="31bfd-102">Services de domaine Active Directory pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31bfd-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31bfd-103">_**Dernière modification de la rubrique :** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="31bfd-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="31bfd-104">Les fonctions des services de domaine Active Directory comme service d’annuaire pour Windows Server 2003, Windows Server 2008, Windows Server 2012 et les réseaux Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="31bfd-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="31bfd-105">Les services de domaine Active Directory servent également de base sur l’infrastructure de sécurité de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31bfd-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="31bfd-106">Cette section décrit la façon dont Lync Server 2013 utilise les services de domaine Active Directory (AD FS) pour créer un environnement digne de confiance pour la messagerie instantanée, les conférences Web, les médias et la voix.</span><span class="sxs-lookup"><span data-stu-id="31bfd-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="31bfd-107">Pour plus d’informations sur les extensions serveur Lync aux services de domaine Active Directory et sur la préparation de votre environnement pour les services de domaine Active Directory, voir [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="31bfd-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="31bfd-108">Pour plus d’informations sur le rôle des services de domaine Active Directory dans les réseaux Windows Server, voir la documentation relative à la version du système d’exploitation que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="31bfd-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="31bfd-109">Lync Server 2013 utilise les services de domaine Active Directory pour stocker les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="31bfd-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="31bfd-110">Paramètres globaux pour lesquels tous les serveurs exécutant Lync Server 2013 dans une forêt nécessitent.</span><span class="sxs-lookup"><span data-stu-id="31bfd-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="31bfd-111">Des informations de service qui identifient les rôles de tous les serveurs exécutant Lync Server 2013 dans une forêt.</span><span class="sxs-lookup"><span data-stu-id="31bfd-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="31bfd-112">Certains paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31bfd-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="31bfd-113">Infrastructure Active Directory</span><span class="sxs-lookup"><span data-stu-id="31bfd-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="31bfd-114">Les exigences en matière d’infrastructure pour Active Directory sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="31bfd-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="31bfd-115">Systèmes d’exploitation requis pour les contrôleurs de domaine</span><span class="sxs-lookup"><span data-stu-id="31bfd-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="31bfd-116">Exigences de niveau fonctionnel de domaine et de forêt</span><span class="sxs-lookup"><span data-stu-id="31bfd-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="31bfd-117">Exigences de domaine de catalogue global</span><span class="sxs-lookup"><span data-stu-id="31bfd-117">Global catalog domain requirements</span></span>

<span data-ttu-id="31bfd-118">Pour plus d’informations, voir [Configuration requise pour l’infrastructure Active Directory pour Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="31bfd-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="31bfd-119">Préparation des services de domaine Active Directory</span><span class="sxs-lookup"><span data-stu-id="31bfd-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31bfd-120">Nous vous recommandons de déployer des paramètres globaux sur le conteneur de configuration au lieu du conteneur système.</span><span class="sxs-lookup"><span data-stu-id="31bfd-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="31bfd-121">Cela ne renforce pas la sécurité, mais peut entraîner des améliorations de l’extensibilité pour certaines topologies de services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="31bfd-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="31bfd-122">Si vous effectuez une migration à partir de Microsoft Office Communications Server 2007 et que vous avez utilisé le conteneur système mais que vous envisagez d’utiliser le conteneur de configuration, vous devez déplacer les paramètres dans le conteneur système avant de procéder à des préparations de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="31bfd-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="31bfd-123">Pour migrer vos paramètres de conteneur système vers le conteneur de configuration, voir l’outil de migration des paramètres <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>globaux d’Office Communications Server 2007 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="31bfd-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="31bfd-124">Lors du déploiement de Lync Server 2013, la première étape consiste à préparer les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="31bfd-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="31bfd-125">La préparation des services de domaine Active Directory pour Lync Server 2013 comprend les trois étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="31bfd-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="31bfd-126">**Préparer le schéma**.</span><span class="sxs-lookup"><span data-stu-id="31bfd-126">**Prepare Schema**.</span></span> <span data-ttu-id="31bfd-127">Cette tâche étend le schéma dans les services de domaine Active Directory pour inclure des classes et des attributs spécifiques à Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31bfd-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="31bfd-128">Pour plus d’informations sur la préparation du schéma, voir exécution de la [préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-running-schema-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="31bfd-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="31bfd-129">Pour plus d’informations, reportez-vous à [migration d’Office Communications Server 2007 R2 vers Lync server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="31bfd-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="31bfd-130">**Préparer la forêt**.</span><span class="sxs-lookup"><span data-stu-id="31bfd-130">**Prepare Forest**.</span></span> <span data-ttu-id="31bfd-131">Cette tâche crée des paramètres globaux et des objets dans le domaine racine de la forêt, ainsi que les groupes de services et d’administration universels régissant l’accès à ces paramètres et aux objets.</span><span class="sxs-lookup"><span data-stu-id="31bfd-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="31bfd-132">Pour plus d’informations sur la préparation de la forêt, voir exécution de la [préparation de la forêt pour Lync Server 2013](lync-server-2013-running-forest-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="31bfd-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="31bfd-133">**Préparer le domaine**.</span><span class="sxs-lookup"><span data-stu-id="31bfd-133">**Prepare Domain**.</span></span> <span data-ttu-id="31bfd-134">Cette tâche ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui accordent des autorisations d’hébergement et de gestion des utilisateurs au sein du domaine.</span><span class="sxs-lookup"><span data-stu-id="31bfd-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="31bfd-135">Cette tâche doit être effectuée dans tous les domaines dans lesquels vous souhaitez déployer des serveurs exécutant Lync Server 2013 et les domaines dans lesquels résident les utilisateurs de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31bfd-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="31bfd-136">Pour plus d’informations sur la préparation du domaine, voir exécution de la [préparation du domaine pour Lync Server 2013](lync-server-2013-running-domain-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="31bfd-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="31bfd-137">Pour obtenir une vue d’ensemble du processus complet de préparation d’Active Directory et des droits et autorisations nécessaires à chaque étape, voir la [Configuration requise en matière d’infrastructure Active Directory pour Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="31bfd-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="31bfd-138">Groupes universels</span><span class="sxs-lookup"><span data-stu-id="31bfd-138">Universal Groups</span></span>

<span data-ttu-id="31bfd-139">Lors de la préparation de la forêt, Lync Server 2013 crée divers groupes universelles dans les services de domaine Active Directory, qui sont autorisés à accéder à des services globaux et à gérer les services et les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="31bfd-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="31bfd-140">Ces groupes universels incluent :</span><span class="sxs-lookup"><span data-stu-id="31bfd-140">These universal groups include:</span></span>

  - <span data-ttu-id="31bfd-141">**Groupes administratifs**.</span><span class="sxs-lookup"><span data-stu-id="31bfd-141">**Administrative groups**.</span></span> <span data-ttu-id="31bfd-142">Ces groupes définissent les rôles d’administrateur de base pour un réseau Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31bfd-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="31bfd-143">Lors de la préparation de la forêt, ces groupes d’administrateurs sont ajoutés aux groupes d’infrastructure de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31bfd-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="31bfd-144">**Groupes de service**.</span><span class="sxs-lookup"><span data-stu-id="31bfd-144">**Service groups**.</span></span> <span data-ttu-id="31bfd-145">Il s’agit des comptes de service nécessaires pour accéder aux différents services fournis par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31bfd-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="31bfd-146">**Groupes d’infrastructure**.</span><span class="sxs-lookup"><span data-stu-id="31bfd-146">**Infrastructure groups**.</span></span> <span data-ttu-id="31bfd-147">Ces groupes fournissent l’autorisation d’accéder à des zones spécifiques de l’infrastructure du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="31bfd-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="31bfd-148">Ils fonctionnent comme des composants de groupes administratifs et vous ne devez pas les modifier ni leur ajouter directement des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="31bfd-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="31bfd-149">Lors de la préparation de la forêt, des groupes de service et d’administration spécifiques sont ajoutés aux groupes d’infrastructure appropriés.</span><span class="sxs-lookup"><span data-stu-id="31bfd-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="31bfd-150">Pour plus d’informations sur les groupes universels spécifiques créés lors de la préparation d’AD pour Lync Server, ainsi que les groupes de services et d’administration qui sont ajoutés aux groupes d’infrastructure, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="31bfd-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31bfd-151">Lync Server 2013 prend en charge les groupes universels dans Windows Server 2012 pour les serveurs exécutant Lync Server 2013, ainsi que les systèmes d’exploitation Windows Server 2003 pour les contrôleurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="31bfd-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="31bfd-152">Les membres de groupes universels peuvent inclure d’autres groupes et comptes provenant de n’importe quel domaine de l’arbre ou de la forêt de domaines et peuvent se voir attribuer des autorisations dans n’importe quel domaine également.</span><span class="sxs-lookup"><span data-stu-id="31bfd-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="31bfd-153">La prise en charge des groupes universels, combinée à la délégation d’administrateur, simplifie la gestion d’un déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31bfd-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="31bfd-154">Par exemple, il n’est pas nécessaire d’ajouter un domaine à un autre domaine pour permettre à un administrateur de les gérer tous les deux.</span><span class="sxs-lookup"><span data-stu-id="31bfd-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="31bfd-155">Contrôle d’accès basé sur un rôle</span><span class="sxs-lookup"><span data-stu-id="31bfd-155">Role-Based Access Control</span></span>

<span data-ttu-id="31bfd-156">En plus de créer des groupes de service et d’administration universels et d’ajouter des groupes de service et d’administration aux groupes universels appropriés, la préparation de forêt crée également des groupes de Contrôle d’accès basé sur un rôle (RBAC).</span><span class="sxs-lookup"><span data-stu-id="31bfd-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="31bfd-157">Pour plus d’informations sur les groupes RBAC spécifiques créés par la préparation de la forêt, voir [modifications apportées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="31bfd-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="31bfd-158">Pour plus d’informations sur les groupes RBAC, voir [contrôle de contrôle d’accès basé sur les rôles (RBAC) pour Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="31bfd-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="31bfd-159">Entrées de contrôle d’accès (ACE) et héritage</span><span class="sxs-lookup"><span data-stu-id="31bfd-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="31bfd-160">La préparation de la forêt crée des ACE privées et publiques et ajoute des ACE pour les groupes universels qu’elle crée.</span><span class="sxs-lookup"><span data-stu-id="31bfd-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="31bfd-161">Il crée des entrées ACE privées spécifiques sur le conteneur de paramètres globaux utilisé par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31bfd-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="31bfd-162">Ce conteneur est utilisé uniquement par Lync Server et réside dans le conteneur de configuration ou dans le conteneur système du domaine racine, en fonction de l’emplacement de stockage des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="31bfd-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="31bfd-p114">L’étape de préparation du domaine ajoute les entrées de contrôle d’accès (ACE) nécessaires aux groupes universels qui permettent d’héberger et de gérer les utilisateurs au sein du domaine. La préparation de domaine crée des ACE à la racine du domaine et dans trois conteneurs intégrés : Utilisateur, Ordinateurs et Contrôleurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="31bfd-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="31bfd-165">Pour plus d’informations sur les ACE publiques créées et ajoutées par la préparation de la forêt et la préparation du domaine, voir [modifications apportées par la préparation de la forêt dans Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) et [modifications apportées par la préparation du domaine dans Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="31bfd-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="31bfd-166">Les organisations verrouillent souvent les services de domaine Active Directory (AD DS) pour réduire les risques liés à la sécurité.</span><span class="sxs-lookup"><span data-stu-id="31bfd-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="31bfd-167">Toutefois, un environnement Active Directory verrouillé peut limiter les autorisations requises par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31bfd-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="31bfd-168">Ceci peut inclure la suppression des ACE des conteneurs et des unités d’organisation (OU) et la désactivation de l’héritage des autorisations sur les objets Utilisateur, Contact, InetOrgPerson ou Ordinateur.</span><span class="sxs-lookup"><span data-stu-id="31bfd-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="31bfd-169">Dans un environnement Active Directory verrouillé, les autorisations doivent être définies manuellement sur les conteneurs et les unités d’organisation qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="31bfd-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="31bfd-170">Pour plus d’informations, reportez-vous à la rubrique [préparation d’un service de domaine Active Directory verrouillé dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="31bfd-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="31bfd-171">Informations du serveur</span><span class="sxs-lookup"><span data-stu-id="31bfd-171">Server Information</span></span>

<span data-ttu-id="31bfd-172">Au cours de l’activation, Lync Server 2013 publie les informations du serveur aux trois emplacements suivants dans les services de domaine Active Directory (AD FS) :</span><span class="sxs-lookup"><span data-stu-id="31bfd-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="31bfd-173">Un point de connexion de service (SCP) sur chaque objet d’ordinateur Active Directory correspondant à un ordinateur physique sur lequel Lync Server 2013 est installé.</span><span class="sxs-lookup"><span data-stu-id="31bfd-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="31bfd-174">Les objets Serveur créés dans le conteneur de la classe **msRTCSIP-Pools**.</span><span class="sxs-lookup"><span data-stu-id="31bfd-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="31bfd-175">Serveurs de confiance spécifiés dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="31bfd-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="31bfd-176">Points de connexion de service</span><span class="sxs-lookup"><span data-stu-id="31bfd-176">Service Connection Points</span></span>

<span data-ttu-id="31bfd-177">Chaque objet Lync Server 2013 dans les services de domaine Active Directory possède un SCP appelé services RTC, qui à son tour contient un certain nombre d’attributs identifiant chaque ordinateur et spécifiant les services qu’il fournit.</span><span class="sxs-lookup"><span data-stu-id="31bfd-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="31bfd-178">Parmi les attributs des points de connexion de service les plus importants se trouvent \*serviceDNSName \*, \*serviceDNSNameType \*, \*serviceClassname \* et \*serviceBindingInformation \*.</span><span class="sxs-lookup"><span data-stu-id="31bfd-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="31bfd-179">Les applications de gestion des actifs tiers peuvent récupérer les informations du serveur sur un déploiement en émettant des requêtes concernant ces données et d’autres attributs de points de connexion de service.</span><span class="sxs-lookup"><span data-stu-id="31bfd-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="31bfd-180">Objets serveur Active Directory</span><span class="sxs-lookup"><span data-stu-id="31bfd-180">Active Directory Server Objects</span></span>

<span data-ttu-id="31bfd-181">Chaque rôle serveur Lync Server 2013 possède un objet Active Directory correspondant dont les attributs définissent les services fournis par ce rôle.</span><span class="sxs-lookup"><span data-stu-id="31bfd-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="31bfd-182">Par ailleurs, lorsqu’un serveur Standard Edition Server est activé ou qu’un pool Enterprise Edition est créé, Lync Server 2013 crée un nouvel objet de **pool msRTCSIP** dans le conteneur **msRTCSIP-pools** .</span><span class="sxs-lookup"><span data-stu-id="31bfd-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="31bfd-183">La classe \*\*msRTCSIP-Pool \*\* spécifie le nom de domaine complet (FQDN) du pool, ainsi que l’association entre les composants frontaux et principaux du pool.</span><span class="sxs-lookup"><span data-stu-id="31bfd-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="31bfd-184">(Un serveur Standard Edition Server est considéré comme une réserve logique dont les extrémités avant et arrière sont colocalisées sur un seul ordinateur.)</span><span class="sxs-lookup"><span data-stu-id="31bfd-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="31bfd-185">Serveurs approuvés</span><span class="sxs-lookup"><span data-stu-id="31bfd-185">Trusted Servers</span></span>

<span data-ttu-id="31bfd-186">Dans Lync Server 2013, les serveurs de confiance sont ceux spécifiés lors de l’exécution du générateur de topologie et de la publication de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="31bfd-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="31bfd-187">La topologie publiée, y compris toutes les informations du serveur, est enregistrée dans le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="31bfd-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="31bfd-188">Seuls les serveurs définis dans le magasin central de gestion sont approuvés.</span><span class="sxs-lookup"><span data-stu-id="31bfd-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="31bfd-189">Dans Lync Server 2013, un serveur approuvé est l’un des critères suivants :</span><span class="sxs-lookup"><span data-stu-id="31bfd-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="31bfd-190">Le nom de domaine complet (FQDN) du serveur se trouve dans la topologie enregistrée dans le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="31bfd-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="31bfd-191">Le serveur présente un certificat valide d’une autorité de certification approuvée.</span><span class="sxs-lookup"><span data-stu-id="31bfd-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="31bfd-192">Pour plus d’informations, voir [Configuration requise en matière d’infrastructure de certificats pour Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31bfd-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="31bfd-p120">Si l’un de ces critères est manquant, le serveur n’est pas approuvé et la connexion avec celui-ci est refusée. Cette double exigence évite une attaque éventuelle, mais peu probable, dans laquelle un serveur malveillant tente de s’emparer du nom de domaine complet d’un serveur valide.</span><span class="sxs-lookup"><span data-stu-id="31bfd-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="31bfd-195">Par ailleurs, pour permettre aux déploiements de Microsoft Office Communications Server 2007 R2 et de Microsoft Office Communications Server 2007 de communiquer avec des serveurs Lync Server 2013, Lync Server 2013 crée des conteneurs lors de la préparation de la forêt pour les listes de serveurs de confiance pour les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="31bfd-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="31bfd-196">Le tableau suivant décrit les conteneurs créés pour permettre la compatibilité avec les déploiements précédents.</span><span class="sxs-lookup"><span data-stu-id="31bfd-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="31bfd-197">Listes de serveurs approuvés et leurs conteneurs Active Directory pour la compatibilité avec les versions précédentes</span><span class="sxs-lookup"><span data-stu-id="31bfd-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31bfd-198">Liste des serveurs approuvés</span><span class="sxs-lookup"><span data-stu-id="31bfd-198">Trusted server list</span></span></th>
<th><span data-ttu-id="31bfd-199">Conteneur Active Directory</span><span class="sxs-lookup"><span data-stu-id="31bfd-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31bfd-200">Serveurs Standard Edition et serveurs frontaux du pool d’entreprise</span><span class="sxs-lookup"><span data-stu-id="31bfd-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="31bfd-201">RTC Service/Paramètres globaux</span><span class="sxs-lookup"><span data-stu-id="31bfd-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31bfd-202">Serveurs de conférence</span><span class="sxs-lookup"><span data-stu-id="31bfd-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="31bfd-203">RTC Service/MCU approuvés</span><span class="sxs-lookup"><span data-stu-id="31bfd-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31bfd-204">Serveurs de composants Web</span><span class="sxs-lookup"><span data-stu-id="31bfd-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="31bfd-205">RTC Service/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="31bfd-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31bfd-206">Serveurs de médiation et serveurs Communicator Web Access, serveur d’application, serveur d’inscriptions avec QoE, service de conférence A/V (également serveurs SIP tiers)</span><span class="sxs-lookup"><span data-stu-id="31bfd-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="31bfd-207">RTC Service/Services approuvés</span><span class="sxs-lookup"><span data-stu-id="31bfd-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31bfd-208">Serveurs proxy</span><span class="sxs-lookup"><span data-stu-id="31bfd-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="31bfd-209">Lync Server 2013 ne prend pas en charge la compatibilité descendante pour les serveurs proxy</span><span class="sxs-lookup"><span data-stu-id="31bfd-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="31bfd-210">Pour prendre en charge des serveurs de confiance de versions précédentes, vous devez exécuter l’outil d’analyse des pratiques recommandées.</span><span class="sxs-lookup"><span data-stu-id="31bfd-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="31bfd-211">Pour plus d’informations sur l’exécution de l’analyseur [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)de recommandations, voir.</span><span class="sxs-lookup"><span data-stu-id="31bfd-211">For details about running the best practices analyzer, see [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

