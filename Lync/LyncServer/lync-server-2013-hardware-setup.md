---
title: 'Lync Server 2013 : Configuration matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e2d05db28ffa61ea25dbb237c388c37a87ac5a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="99220-102">Configuration matérielle pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99220-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99220-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="99220-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="99220-104">Pour configurer le matériel et d’autres composants requis dans l’infrastructure dont vous avez besoin pour implémenter votre topologie, avant de publier votre topologie dans le générateur de topologie, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="99220-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="99220-105">Installez le matériel de chaque composant de la conception topologique que vous avez créé et enregistré à l’aide du générateur de topologie, y compris tous les ordinateurs requis (serveurs exécutant Lync Server 2013, serveurs de base de données, serveurs exécutant Internet Information Services (IIS) et inversez les serveurs proxy, selon le cas), cartes réseau, équilibreurs de charge matérielle et périphériques de stockage (par exemple, serveurs de fichiers).</span><span class="sxs-lookup"><span data-stu-id="99220-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="99220-106">Vérifiez que vous avez suivi les recommandations en matière de nombre et de vitesse pour les cartes réseau.</span><span class="sxs-lookup"><span data-stu-id="99220-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="99220-107">Si vous utilisez des équilibreurs de charge matérielle, assurez-vous que vous disposez des informations appropriées du fournisseur pour les configurer pour une utilisation avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="99220-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="99220-108">Si vous utilisez un serveur de fichiers ou un autre serveur pour mettre en place le partage de fichiers requis par Lync Server, assurez-vous que le serveur est disponible et qu’il est prêt pour la configuration du partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="99220-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="99220-109">Pour plus d’informations sur la définition d’une topologie spécifiant les composants nécessaires à votre déploiement, reportez-vous à la rubrique [définition et configuration de la topologie dans Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="99220-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="99220-110">Pour plus d’informations sur la configuration matérielle requise pour les serveurs, voir [matériel compatible pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="99220-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="99220-111">Assurez-vous que l’infrastructure réseau répond à la configuration requise.</span><span class="sxs-lookup"><span data-stu-id="99220-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="99220-112">Pour plus d’informations, voir [Configuration requise pour l’infrastructure réseau pour Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="99220-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="99220-113">Configurez les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99220-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="99220-114">La configuration de AD DS inclut la préparation de AD DS et la définition de tous les composants que vous voulez déployer dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="99220-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="99220-115">Pour plus d’informations sur la préparation d’AD DS, voir [préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="99220-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="99220-116">Définissez les autorisations requises pour la création du partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="99220-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="99220-117">Les autorisations d’utilisation des partages de fichiers par Lync Server 2013 sont automatiquement configurées par le générateur de topologie lors de la publication de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="99220-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="99220-118">Toutefois, le compte d’utilisateur utilisé pour publier la topologie doit avoir le contrôle total (lecture/écriture/modification) sur le partage de fichiers pour permettre au générateur de topologie de configurer les autorisations requises.</span><span class="sxs-lookup"><span data-stu-id="99220-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="99220-119">Pour vous assurer que le partage de fichiers peut être géré correctement lors du processus de publication du générateur de topologie, le groupe d’utilisateurs ou de domaines dont l’utilisateur est membre doit être membre du groupe Administrateurs local sur l’ordinateur où se trouve le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="99220-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="99220-120">Dans un scénario multi-domaine, le domaine d’un utilisateur ou d’un groupe doit être membre du groupe Administrateurs local sur l’ordinateur du domaine B où se trouve le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="99220-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="99220-121">Pour plus d’informations sur la mise à jour de l’utilisation des partages de fichiers dans un système de fichiers DFS, voir [configurer le stockage de fichiers pour Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="99220-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="99220-122">Le partage de fichiers pour Lync Server 2013 entreprise Edition ne peut pas être localisé sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="99220-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="99220-123">Installer et configurer l’équilibrage de charge matérielle pour les services Web.</span><span class="sxs-lookup"><span data-stu-id="99220-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="99220-124">Après le déploiement de l’équilibrage de charge DNS (Domain Name System), vous devez également utiliser des équilibreurs de charge matérielle pour ces pools, mais uniquement pour le trafic HTTP/HTTPs.</span><span class="sxs-lookup"><span data-stu-id="99220-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="99220-125">L’équilibrage de charge matérielle est utilisé pour le trafic HTTPs des clients sur les ports 443 et 80.</span><span class="sxs-lookup"><span data-stu-id="99220-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="99220-126">Même si vous avez encore besoin d’équilibreurs de charge matérielle pour ces pools, leur configuration et leur administration seront essentiellement destinées au trafic HTTP/HTTPs, que les administrateurs des équilibreurs de charge matérielle sont habitués.</span><span class="sxs-lookup"><span data-stu-id="99220-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="99220-127">Une fois toutes les tâches de préparation effectuées comme décrit dans cette rubrique, vous devez également procéder comme suit:</span><span class="sxs-lookup"><span data-stu-id="99220-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="99220-128">Installation des systèmes d’exploitaition et des logiciels prérequis sur les serveurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99220-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="99220-129">Configuration des services Internet (IIS) pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99220-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="99220-130">Configuration de SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99220-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="99220-131">Configuration des enregistrements DNS dans Lync Server 2013 pour un pool frontal ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="99220-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

