---
title: 'Lync Server 2013 : configurer le regroupement SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63d338e630da93c90b573ac098d47e0929f0d84
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="dca6e-102">Configurer le regroupement SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dca6e-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dca6e-103">_**Dernière modification de la rubrique :** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="dca6e-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="dca6e-104">Microsoft Lync Server 2013 prend en charge la mise en cluster pour SQL Server 2012 et SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="dca6e-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="dca6e-105">Pour plus d’informations sur les fonctionnalités prises en charge, voir [prise en charge de logiciels de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="dca6e-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="dca6e-106">Vous devez configurer et configurer le cluster SQL Server avant d’installer et de déployer le serveur frontal et la base de données principale d’Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="dca6e-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="dca6e-107">Pour obtenir des recommandations et des instructions de configuration pour la mise en cluster de basculement dans SQL Server 2012, voir <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span><span class="sxs-lookup"><span data-stu-id="dca6e-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="dca6e-108">Pour la mise en cluster de basculement dans SQL <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>Server 2008, voir.</span><span class="sxs-lookup"><span data-stu-id="dca6e-108">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="dca6e-p103">Lorsque vous installez SQL Server, vous devez installer SQL Server Management Studio pour gérer les emplacements des bases de données et des fichiers journaux. SQL Server Management Studio est installé en tant que composant facultatif lorsque vous installez SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dca6e-p103">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations. SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dca6e-111">Pour installer et déployer les bases de données sur le serveur SQL Server, vous devez être membre du groupe SQL Server sysadmin pour le serveur SQL Server sur lequel vous installez les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="dca6e-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="dca6e-112">Si vous n’êtes pas membre du groupe SQL Server sysadmin, vous devez demander à l’ajouter au groupe jusqu’à ce que les fichiers de la base de données soient déployés.</span><span class="sxs-lookup"><span data-stu-id="dca6e-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="dca6e-113">Si vous ne pouvez pas être membre du groupe sysadmin, vous devez fournir à votre administrateur de base de données SQL Server le script de configuration et de déploiement de celles-ci.</span><span class="sxs-lookup"><span data-stu-id="dca6e-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="dca6e-114">Pour plus d’informations sur les droits d’utilisateur et les autorisations nécessaires pour accomplir ces procédures, voir <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorisations de déploiement pour SQL Server dans Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dca6e-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="dca6e-115">Pour configurer le regroupement SQL Server</span><span class="sxs-lookup"><span data-stu-id="dca6e-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="dca6e-116">Après avoir effectué l’installation et la configuration de la mise en cluster de SQL Server, vous définissez SQL Server Store dans le générateur de topologie à l’aide du nom de cluster virtuel de l’instance SQL Server (configuré dans le programme d’installation de SQL Server clustering) et de l’instance. nom de la base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dca6e-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="dca6e-117">Différent d’un serveur SQL Server unique, vous devez utiliser le nom de domaine complet (FQDN) du nœud virtuel pour un serveur SQL Server groupé.</span><span class="sxs-lookup"><span data-stu-id="dca6e-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dca6e-118">Il n’est pas nécessaire de configurer les nœuds de cluster Windows Server individuels pour le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="dca6e-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="dca6e-119">Vous utiliserez uniquement le nom du cluster SQL Server virtuel.</span><span class="sxs-lookup"><span data-stu-id="dca6e-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="dca6e-120">Si vous utilisez le générateur de topologie pour déployer vos bases de données, vous devez être membre du groupe SQL Server sysadmin.</span><span class="sxs-lookup"><span data-stu-id="dca6e-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="dca6e-121">Si vous êtes membre du groupe SQL Server sysadmin, mais que vous n’avez pas de privilèges sur le domaine (par exemple, un rôle d’administrateur de base de données SQL Server), vous disposez des droits nécessaires pour créer les bases de données, mais pas pour lire les informations nécessaires dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dca6e-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="dca6e-122">Pour plus d’informations sur les droits d’utilisateur et les autorisations nécessaires au déploiement de Lync Server, reportez-vous à la section [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dca6e-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="dca6e-123">Assurez-vous que le dossier de base de données et les fichiers journaux par défaut sont mappés correctement aux disques partagés dans le groupe SQL Server en utilisant SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="dca6e-123">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio.</span></span> <span data-ttu-id="dca6e-124">Il s’agit d’une procédure obligatoire si vous créez des bases de données à l’aide du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="dca6e-124">This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dca6e-125">Si vous n’avez pas installé SQL Server Management Studio, vous pouvez l’installer en réexécutant le programme d’installation de SQL Server, puis en sélectionnant l’outil de gestion en tant que composant supplémentaire pour le déploiement SQL Server existant.</span><span class="sxs-lookup"><span data-stu-id="dca6e-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="dca6e-126">Installez les bases de données pour le serveur SQL Server à l’aide du générateur de topologie ou des cmdlets Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dca6e-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="dca6e-127">Pour utiliser le générateur de topologie, utilisez la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="dca6e-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="dca6e-128">Pour utiliser les applets de cmdlet Windows PowerShell, consultez l' [installation de la base de données à l’aide de Lync Server Management Shell dans Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="dca6e-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="dca6e-129">Pour créer des bases de données à l’aide du générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="dca6e-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="dca6e-130">Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dca6e-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="dca6e-131">La procédure suivante suppose que vous avez défini et configuré votre topologie dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="dca6e-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="dca6e-132">Pour plus d’informations sur la définition de votre topologie, voir<A href="lync-server-2013-defining-and-configuring-the-topology.md">définition et configuration de la topologie dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dca6e-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="dca6e-133">Pour utiliser le générateur de topologie afin de publier la topologie et de configurer la base de données, vous devez vous connecter en tant qu’utilisateur disposant des droits d’utilisateur et des appartenances aux groupes appropriés.</span><span class="sxs-lookup"><span data-stu-id="dca6e-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="dca6e-134">Pour plus d’informations sur les droits et les appartenances aux groupes requis, voir <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorisations de déploiement pour SQL Server dans Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dca6e-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="dca6e-135">Dans le générateur de topologie, lorsque vous publiez la topologie, dans la page **créer des bases de données** , cliquez sur **avancé**.</span><span class="sxs-lookup"><span data-stu-id="dca6e-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="dca6e-136">La page **Sélectionner l’emplacement du fichier de base de données** propose deux options qui déterminent le mode de déploiement des fichiers de base de données sur le cluster SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dca6e-136">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster.</span></span> <span data-ttu-id="dca6e-137">Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="dca6e-137">Select one of the following:</span></span>
    
      - <span data-ttu-id="dca6e-138">**Déterminez automatiquement l’emplacement du fichier de base de données.**</span><span class="sxs-lookup"><span data-stu-id="dca6e-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="dca6e-139">Cette sélection utilise un algorithme pour déterminer les emplacements du journal de la base de données et des fichiers de données en fonction de la configuration du lecteur sur le serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dca6e-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="dca6e-140">Les fichiers seront distribués de telle sorte qu’ils puissent essayer d’offrir des performances optimales.</span><span class="sxs-lookup"><span data-stu-id="dca6e-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="dca6e-141">Utilisez les valeurs par défaut des instances SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dca6e-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="dca6e-142">Si vous sélectionnez cette option, les fichiers journaux et de données seront installés conformément aux paramètres de l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dca6e-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="dca6e-143">Après le déploiement des fichiers de base de données sur le serveur SQL Server, l’administrateur de votre base de données SQL Server a besoin de replacer les fichiers pour optimiser les performances de votre configuration spécifique de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dca6e-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="dca6e-144">Achevez la publication de la topologie et vérifiez qu’il n’y a pas eu d’erreur pendant l’opération.</span><span class="sxs-lookup"><span data-stu-id="dca6e-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

