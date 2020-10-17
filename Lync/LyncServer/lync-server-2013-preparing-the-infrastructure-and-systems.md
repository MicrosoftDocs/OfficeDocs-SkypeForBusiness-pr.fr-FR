---
title: 'Lync Server 2013 : préparation de l’infrastructure et des systèmes'
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
ms.openlocfilehash: b1391d57232d261edcdfcdd7c4668ee025b1420b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506841"
---
# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="39b56-102">Préparation de l’infrastructure et des systèmes pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b56-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39b56-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="39b56-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="39b56-104">Le déploiement de Lync Server 2013 nécessite l’utilisation du générateur de topologies pour définir et publier la conception de la topologie.</span><span class="sxs-lookup"><span data-stu-id="39b56-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="39b56-105">Pour identifier les composants requis pour votre topologie, vous utilisez le générateur de topologies pour créer et enregistrer une conception de topologie.</span><span class="sxs-lookup"><span data-stu-id="39b56-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="39b56-106">Avant de publier votre topologie dans le Générateur de topologie, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="39b56-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="39b56-107">Procurez-vous et installez le matériel pour chaque composant de la conception de la topologie que vous avez créé et enregistré à l’aide du générateur de topologie, y compris tous les ordinateurs requis (serveurs exécutant Lync Server 2013, les serveurs de bases de données, les serveurs exécutant les services Internet (IIS) et les serveurs proxy inverses, selon le cas)</span><span class="sxs-lookup"><span data-stu-id="39b56-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="39b56-108">Pour plus d’informations sur la définition d’une topologie qui spécifie les composants nécessaires à votre déploiement, reportez-vous à [la rubrique Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="39b56-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="39b56-109">Pour plus d’informations sur la configuration matérielle requise pour les serveurs, voir [matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="39b56-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="39b56-110">Assurez-vous que l’infrastructure réseau répond à la configuration requise.</span><span class="sxs-lookup"><span data-stu-id="39b56-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="39b56-111">Pour plus d’informations, reportez-vous à [Network infrastructure Requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="39b56-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="39b56-112">Configurez les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="39b56-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="39b56-113">Pour publier et activer la topologie, les serveurs internes doivent être représentés par des comptes d’ordinateur dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="39b56-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="39b56-114">Il suffit pour cela de joindre les ordinateurs aux services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="39b56-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="39b56-115">Pour plus d’informations sur la préparation des services AD DS, voir [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="39b56-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="39b56-116">Créez un partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="39b56-116">Create a file share.</span></span> <span data-ttu-id="39b56-117">Les serveurs Standard Edition peuvent héberger le partage de fichiers pour le fichier requis, tandis que dans un déploiement d’entreprise, le partage de fichiers ne peut pas être hébergé sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="39b56-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="39b56-118">Les autorisations et les appartenances à un groupe requises pour le déploiement et la définition de la liste de contrôle d’accès (ACL) sur le dossier et le partage doivent être configurées de manière adéquate pour que le Générateur de topologie s’exécute correctement.</span><span class="sxs-lookup"><span data-stu-id="39b56-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="39b56-119">Assurez-vous que la personne qui exécute le générateur de topologie dispose des autorisations et appartenances de groupe suivantes :</span><span class="sxs-lookup"><span data-stu-id="39b56-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="39b56-120">Membre du groupe Administrateurs local</span><span class="sxs-lookup"><span data-stu-id="39b56-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="39b56-121">Membre des utilisateurs du domaine</span><span class="sxs-lookup"><span data-stu-id="39b56-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="39b56-122">Contrôle total du partage et du dossier du magasin de fichiers</span><span class="sxs-lookup"><span data-stu-id="39b56-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="39b56-p106">Pour Enterprise Edition, installez et configurez SQL Server. Pour que la configuration de SQL Server réussisse, le serveur SQL Server doit être en ligne et la personne chargée de la publication de la topologie doit être un administrateur local sur le serveur SQL Server et membre du groupe SQL Server sysadmin sur l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="39b56-p106">For Enterprise Edition, install and configure SQL Server. For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="39b56-125">Lorsque vous avez terminé toutes les tâches de préparation décrites dans cette rubrique et avant de publier la topologie, vous devez également exécuter les autres tâches de préparation telles que l’installation des systèmes d’exploitation Windows et d’autres logiciels requis, la configuration IIS et la configuration du DNS.</span><span class="sxs-lookup"><span data-stu-id="39b56-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="39b56-126">Pour plus d’informations sur ces tâches, reportez-vous à la rubrique [Configuration requise pour les serveurs exécutant Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configuration des services Internet (IIS) pour Lync Server 2013](lync-server-2013-configure-iis.md)et [préparation de l’infrastructure et des systèmes pour Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span><span class="sxs-lookup"><span data-stu-id="39b56-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="39b56-127">De plus, vous devez prendre connaissance des clients et de leurs besoins.</span><span class="sxs-lookup"><span data-stu-id="39b56-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="39b56-128">Pour plus d’informations, reportez-vous à la rubrique [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="39b56-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="39b56-129">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="39b56-129">In This Section</span></span>

  - [<span data-ttu-id="39b56-130">Configuration matérielle de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b56-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="39b56-131">Configuration logicielle pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b56-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="39b56-132">Préparation des services de domaine Active Directory pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b56-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="39b56-133">Configuration de SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b56-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="39b56-134">Configurer des enregistrements DNS dans Lync Server 2013 pour un pool frontal ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="39b56-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="39b56-135">Installer les outils d’administration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b56-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

