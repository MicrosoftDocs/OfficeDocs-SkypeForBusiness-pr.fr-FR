---
title: 'Lync Server 2013 : Préparation de l’infrastructure et des systèmes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="680f3-102">Préparation de l’infrastructure et des systèmes pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="680f3-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="680f3-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="680f3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="680f3-104">Le déploiement de Lync Server 2013 nécessite l’utilisation du générateur de topologie pour définir et publier la conception topologique.</span><span class="sxs-lookup"><span data-stu-id="680f3-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="680f3-105">Pour identifier les composants requis pour votre topologie, utilisez le générateur de topologie pour créer et enregistrer une conception de topologie.</span><span class="sxs-lookup"><span data-stu-id="680f3-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="680f3-106">Avant de publier votre topologie dans le générateur de topologie, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="680f3-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="680f3-107">Obtenez et installez le matériel de chaque composant de la conception topologique que vous avez créé et enregistré à l’aide du générateur de topologie, y compris tous les ordinateurs requis (serveurs exécutant Lync Server 2013, serveurs de base de données, serveurs exécutant Internet Information Services ( IIS) et inversez les serveurs proxy, selon le cas), les cartes réseau, les équilibreurs de charge matérielle et les périphériques de stockage (par exemple, les serveurs de fichiers).</span><span class="sxs-lookup"><span data-stu-id="680f3-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="680f3-108">Pour plus d’informations sur la définition d’une topologie spécifiant les composants nécessaires à votre déploiement, reportez-vous à la rubrique [définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="680f3-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="680f3-109">Pour plus d’informations sur la configuration matérielle requise pour les serveurs, voir [matériel compatible pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="680f3-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="680f3-110">Assurez-vous que l’infrastructure réseau répond à la configuration requise.</span><span class="sxs-lookup"><span data-stu-id="680f3-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="680f3-111">Pour plus d’informations, voir [Configuration requise pour l’infrastructure réseau pour Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="680f3-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="680f3-112">Configurez les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="680f3-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="680f3-113">Pour publier et activer la topologie, vous avez besoin que les serveurs internes soient représentés par des comptes d’ordinateur dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="680f3-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="680f3-114">Pour cela, il suffit de joindre les ordinateurs à AD DS.</span><span class="sxs-lookup"><span data-stu-id="680f3-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="680f3-115">Pour plus d’informations sur la préparation d’AD DS, voir [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="680f3-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="680f3-116">Créer un partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="680f3-116">Create a file share.</span></span> <span data-ttu-id="680f3-117">Les serveurs Standard Edition peuvent héberger le partage de fichiers du fichier requis, lors d’un déploiement d’entreprise, le partage de fichier ne peut pas être hébergé sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="680f3-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="680f3-118">Les autorisations et appartenances aux groupes requises pour le déploiement et la configuration de la liste de contrôle d’accès (ACL) sur le dossier et du partage doivent être correctement configurées pour que le générateur de topologie s’exécute correctement.</span><span class="sxs-lookup"><span data-stu-id="680f3-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="680f3-119">Assurez-vous que la personne exécutant le générateur de topologie dispose des autorisations et des appartenances aux groupes suivantes :</span><span class="sxs-lookup"><span data-stu-id="680f3-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="680f3-120">Membre du groupe administrateurs locaux</span><span class="sxs-lookup"><span data-stu-id="680f3-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="680f3-121">Membre du domaine utilisateurs</span><span class="sxs-lookup"><span data-stu-id="680f3-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="680f3-122">Contrôle total sur le partage et le dossier du magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="680f3-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="680f3-123">Pour Enterprise Edition, installez et configurez SQL Server.</span><span class="sxs-lookup"><span data-stu-id="680f3-123">For Enterprise Edition, install and configure SQL Server.</span></span> <span data-ttu-id="680f3-124">Pour que le programme d’installation de SQL Server réussisse, le serveur SQL Server doit être connecté et la personne qui publie la topologie doit être un administrateur local sur le serveur SQL Server et doit être membre du groupe SQL Server sysadmin sur l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="680f3-124">For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="680f3-125">Une fois toutes les tâches de préparation effectuées comme décrit dans cette rubrique, mais avant la publication de la topologie, vous devez effectuer les autres tâches de préparation, y compris l’installation des systèmes d’exploitation Windows et d’autres logiciels requis, configuration Services Internet et configuration DNS.</span><span class="sxs-lookup"><span data-stu-id="680f3-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="680f3-126">Pour plus d’informations sur ces tâches, voir [Configuration système requise pour les serveurs exécutant Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [configurer IIS pour Lync Server 2013](lync-server-2013-configure-iis.md)et [préparer l’infrastructure et les systèmes pour Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span><span class="sxs-lookup"><span data-stu-id="680f3-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="680f3-127">Par ailleurs, vous devez vous familiariser avec les clients et les exigences clientes.</span><span class="sxs-lookup"><span data-stu-id="680f3-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="680f3-128">Pour plus d’informations, reportez-vous à la section [déploiement de clients et d’appareils dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="680f3-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="680f3-129">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="680f3-129">In This Section</span></span>

  - [<span data-ttu-id="680f3-130">Configuration matérielle pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="680f3-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="680f3-131">Configuration logicielle pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="680f3-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="680f3-132">Préparation des services de domaine Active Directory pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="680f3-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="680f3-133">Configuration de SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="680f3-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="680f3-134">Configuration des enregistrements DNS dans Lync Server 2013 pour un pool frontal ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="680f3-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="680f3-135">Installation des outils d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="680f3-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

