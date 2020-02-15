---
title: 'Lync Server 2013 : présentation du processus de sauvegarde et de restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9d5e2700065444691dee1041ff210768e9bade7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="f4640-102">Vue d’ensemble du processus de sauvegarde et de restauration pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4640-102">Backup and restoration process overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4640-103">_**Dernière modification de la rubrique :** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="f4640-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="f4640-104">Cette section fournit une vue d’ensemble du fonctionnement du processus de sauvegarde et de restauration pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4640-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="f4640-105">Vous utilisez la même procédure pour tous les serveurs Standard Edition Server et Enterprise Edition, quel que soit leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="f4640-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="f4640-106">En règle générale, le processus de sauvegarde fonctionne comme suit :</span><span class="sxs-lookup"><span data-stu-id="f4640-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="f4640-107">Vous créez un emplacement de sauvegarde en tant que dossier partagé sur un ordinateur autonome qui ne fait partie d’aucun pool.</span><span class="sxs-lookup"><span data-stu-id="f4640-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="f4640-108">L’emplacement de la sauvegarde est référencé dans **$Backup**.</span><span class="sxs-lookup"><span data-stu-id="f4640-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="f4640-109">De manière régulière et planifiée, vous sauvegardez toutes les bases de données Lync Server et tous les magasins de fichiers décrits dans la rubrique Configuration de la [sauvegarde et de la restauration dans Lync server 2013 : données](lync-server-2013-backup-and-restoration-requirements-data.md) en suivant les procédures décrites dans la rubrique [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) le magasin central de gestion inclut tous les paramètres et configurations du serveur.</span><span class="sxs-lookup"><span data-stu-id="f4640-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="f4640-110">Chaque fois que vous exécutez une sauvegarde ultérieure, vous créez un nouveau dossier partagé et modifiez le chemin d’accès que **$Backup** référence.</span><span class="sxs-lookup"><span data-stu-id="f4640-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="f4640-111">En règle générale, le processus de restauration fonctionne comme suit :</span><span class="sxs-lookup"><span data-stu-id="f4640-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="f4640-112">Lorsqu’une défaillance ou une panne se produit, vous restaurez les données à l’emplacement référencé par **$Backup** sur des ordinateurs nouveaux ou nettoyés.</span><span class="sxs-lookup"><span data-stu-id="f4640-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f4640-113">Ce processus de restauration ne restaure pas les données dans un état de serveur existant.</span><span class="sxs-lookup"><span data-stu-id="f4640-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="f4640-114">Autrement dit, ce processus nécessite que le serveur soit propre ou nouveau.</span><span class="sxs-lookup"><span data-stu-id="f4640-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="f4640-115">Pour que vos informations d’utilisateur et de conférence soient récupérables au point de défaillance, vous pouvez implémenter une topologie de récupération d’urgence avec des pools frontaux couplés, comme décrit dans [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="f4640-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="f4640-116">La configuration DNS (Domain Name System), la configuration du protocole DHCP (Dynamic Host Configuration Protocol), les noms de domaine, les noms de domaine complets (FQDN), les chemins d’accès aux magasins de fichiers, etc., doivent être identiques au moment de la restauration Recule.</span><span class="sxs-lookup"><span data-stu-id="f4640-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="f4640-117">Si un serveur exécutant Lync Server tombe en panne, la récupération inclut les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f4640-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="f4640-118">Installez le système d’exploitation sur un ordinateur nouveau ou nettoyé avec le même nom de domaine complet que l’ordinateur défaillant.</span><span class="sxs-lookup"><span data-stu-id="f4640-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="f4640-119">Réinstallez les certificats.</span><span class="sxs-lookup"><span data-stu-id="f4640-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="f4640-120">Si le serveur hébergeait une base de données, installez Microsoft SQL Server 2012 ou Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="f4640-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="f4640-121">En général, si le serveur hébergeait une base de données, exécutez le générateur de topologie pour créer et installer la base de données, puis configurez les listes de contrôle d’accès (ACL).</span><span class="sxs-lookup"><span data-stu-id="f4640-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="f4640-122">En général, si le serveur hébergeait un rôle serveur, exécutez les étapes 1 à 4 de l’Assistant Déploiement de Lync Server pour installer les fichiers de configuration locaux, installer les composants de rôle serveur, assigner des certificats et démarrer les services.</span><span class="sxs-lookup"><span data-stu-id="f4640-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f4640-123">Si le serveur hébergeait une base de données colocalisée avec le rôle serveur, l’étape 2 de l’Assistant Déploiement de Lync Server recrée la base de données.</span><span class="sxs-lookup"><span data-stu-id="f4640-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="f4640-124">Si le serveur hébergeait une base de données, restaurez les données sauvegardées.</span><span class="sxs-lookup"><span data-stu-id="f4640-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

