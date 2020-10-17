---
title: 'Lync Server 2013 : configuration matérielle'
description: 'Lync Server 2013 : configuration matérielle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e798ce32c1f89bba40ad9245426492b0489e7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552910"
---
# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="c9506-103">Configuration matérielle de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9506-103">Hardware setup for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9506-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c9506-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c9506-105">Pour configurer le matériel et les autres composants requis dans l’infrastructure nécessaire à l’implémentation de votre topologie, vous devez, avant de publier votre topologie dans le générateur de topologie, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c9506-105">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="c9506-106">Installez le matériel de chaque composant de la conception de la topologie que vous avez créé et enregistré à l’aide du générateur de topologies, y compris tous les ordinateurs requis (serveurs exécutant Lync Server 2013, serveurs de bases de données, serveurs exécutant les services Internet (IIS) et serveurs proxy inverses, selon le cas), cartes réseau, programmes d’équilibrage de la charge matérielle</span><span class="sxs-lookup"><span data-stu-id="c9506-106">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="c9506-107">Confirmez que vous avez suivi les recommandations pour le nombre et la vitesse des cartes réseau.</span><span class="sxs-lookup"><span data-stu-id="c9506-107">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="c9506-108">Si vous utilisez des programmes d’équilibrage de la charge matérielle, vérifiez que vous disposez des informations appropriées du fournisseur pour les configurer en vue d’une utilisation avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9506-108">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="c9506-109">Si vous utilisez un serveur de fichiers ou un autre serveur pour héberger le partage de fichiers requis par Lync Server, assurez-vous que le serveur est disponible et prêt pour la configuration du partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c9506-109">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="c9506-110">Pour plus d’informations sur la définition d’une topologie qui spécifie les composants nécessaires à votre déploiement, reportez-vous à [la rubrique Defining and Configuring the Topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="c9506-110">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="c9506-111">Pour plus d’informations sur la configuration matérielle requise pour les serveurs, voir [matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c9506-111">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="c9506-112">Assurez-vous que l’infrastructure réseau répond à la configuration requise.</span><span class="sxs-lookup"><span data-stu-id="c9506-112">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="c9506-113">Pour plus d’informations, reportez-vous à [Network infrastructure Requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c9506-113">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="c9506-114">Configurez les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c9506-114">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="c9506-115">La configuration des services de domaine Active Directory (AD DS) inclut leur préparation, ainsi que la définition de tous les composants que vous souhaitez déployer dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="c9506-115">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="c9506-116">Pour plus d’informations sur la préparation des services AD DS, voir [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c9506-116">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="c9506-117">Configurez les autorisations nécessaires à la création du partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c9506-117">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="c9506-118">Les autorisations d’utilisation des partages de fichiers par Lync Server 2013 sont automatiquement configurées par le générateur de topologies lorsque vous publiez votre topologie.</span><span class="sxs-lookup"><span data-stu-id="c9506-118">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="c9506-119">Toutefois, le compte d’utilisateur utilisé pour publier la topologie doit disposer d’un contrôle total (lecture/écriture/modification) sur le partage de fichiers afin que le générateur de topologies configure les autorisations requises.</span><span class="sxs-lookup"><span data-stu-id="c9506-119">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="c9506-120">Pour vous assurer que le partage de fichiers peut être correctement géré pendant le processus de publication du générateur de topologie, l’utilisateur ou le groupe de domaines dont l’utilisateur est membre doit être membre du groupe Administrateurs local sur l’ordinateur où se trouve le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c9506-120">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="c9506-121">Dans un scénario multidomaine, l’utilisateur ou le groupe du domaine A devrait devenir membre du groupe d’administrateurs local sur l’ordinateur du domaine B où se trouve le partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c9506-121">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="c9506-122">Pour plus d’informations sur la mise à jour à l’aide de partages de fichiers dans un système de fichiers DFS, voir [configurer le stockage de fichiers pour Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="c9506-122">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c9506-123">Le partage de fichiers pour Lync Server 2013, Enterprise Edition ne peut pas se trouver sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="c9506-123">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="c9506-124">Installez et configurez l’équilibreur de la charge matérielle pour les services Web.</span><span class="sxs-lookup"><span data-stu-id="c9506-124">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="c9506-125">Si l’équilibrage de la charge DNS (Domain Name System) est déployé, vous devez tout de même utiliser des programmes d’équilibrage de la charge matérielle pour ces pools, mais uniquement pour le trafic HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c9506-125">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="c9506-126">Les programmes d’équilibrage de la charge matérielle sont utilisés pour le trafic HTTPS provenant des clients et transitant via les ports 443 et 80.</span><span class="sxs-lookup"><span data-stu-id="c9506-126">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="c9506-127">Bien que le recours à ces programmes soit toujours nécessaire pour vos pools de serveurs, leur configuration et leur administration concernera avant tout le trafic HTTP/HTTPS avec lequel les administrateurs des programmes d’équilibrage de la charge matérielle sont familiarisés..</span><span class="sxs-lookup"><span data-stu-id="c9506-127">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="c9506-128">Lorsque vous avez terminé toutes les tâches de préparation décrites dans cette rubrique et avant de publier la topologie, vous devez également effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="c9506-128">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="c9506-129">Installer les systèmes d’exploitation et les logiciels prérequis sur les serveurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9506-129">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="c9506-130">Configurer les services Internet (IIS) pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9506-130">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="c9506-131">Configuration de SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9506-131">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="c9506-132">Configurer des enregistrements DNS dans Lync Server 2013 pour un pool frontal ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c9506-132">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

