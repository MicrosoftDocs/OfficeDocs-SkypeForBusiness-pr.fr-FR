---
title: 'Lync Server 2013 : configurer le clustering SQL Server'
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
ms.openlocfilehash: 0cb7db93813bdc7ed06398ce73d00f51ce5a60fe
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="1db7b-102">Configurer le clustering SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1db7b-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1db7b-103">_**Dernière modification de la rubrique :** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="1db7b-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="1db7b-104">Microsoft Lync Server 2013 prend en charge la mise en cluster pour SQL Server 2012 et SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="1db7b-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="1db7b-105">Pour plus d’informations sur les éléments pris en charge, consultez la rubrique [prise en charge logicielle des bases de données dans Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="1db7b-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="1db7b-106">Vous devez installer et configurer le cluster SQL Server avant d’installer et de déployer le serveur frontal et la base de données principale Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="1db7b-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="1db7b-107">Pour obtenir les meilleures pratiques et des instructions de configuration pour le clustering de basculement dans SQL Server 2012, reportez-vous <https://technet.microsoft.com/library/hh231721.aspx>à.</span><span class="sxs-lookup"><span data-stu-id="1db7b-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="1db7b-108">Pour le clustering de basculement dans SQL Server <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>2008, reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="1db7b-108">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="1db7b-109">Lorsque vous installez SQL Server, pensez à installer SQL Server Management Studio pour la gestion des emplacements des fichiers de la base de données et des fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="1db7b-109">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="1db7b-110">SQL Server Management Studio est installé en tant que composant facultatif lors de l’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1db7b-110">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1db7b-111">Pour installer et déployer des bases de données sur un serveur SQL Server, vous devez être membre du groupe SQL Server sysadmin pour le serveur SQL Server sur lequel vous installez les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="1db7b-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="1db7b-112">Si vous ne l’êtes pas, vous devez demander à être ajouté au groupe jusqu’à ce que les fichiers de base de données soient déployés.</span><span class="sxs-lookup"><span data-stu-id="1db7b-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="1db7b-113">Si vous ne pouvez pas devenir membre du groupe sysadmin, transmettez le script de configuration et de déploiement des bases de données à l’administrateur des bases de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1db7b-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="1db7b-114">Pour plus d’informations sur les droits d’utilisateur et les autorisations nécessaires pour effectuer les procédures, voir <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment Permissions for SQL Server in Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1db7b-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="1db7b-115">Pour configurer le clustering SQL Server</span><span class="sxs-lookup"><span data-stu-id="1db7b-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="1db7b-116">Une fois que vous avez terminé l’installation et la configuration du clustering SQL Server, vous définissez le magasin SQL Server dans le générateur de topologie à l’aide du nom de cluster virtuel de l’instance SQL Server (tel que configuré dans le programme d’installation du clustering SQL Server) et de l’instance nom de la base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1db7b-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="1db7b-117">À partir d’un autre serveur SQL Server unique, vous allez utiliser le nom de domaine complet (FQDN) du nœud virtuel d’un serveur SQL Server en cluster.</span><span class="sxs-lookup"><span data-stu-id="1db7b-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1db7b-118">Il n’est pas nécessaire que les nœuds de cluster Windows Server individuels soient configurés pour le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="1db7b-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="1db7b-119">Vous n’allez utiliser que le nom du cluster SQL Server virtuel.</span><span class="sxs-lookup"><span data-stu-id="1db7b-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="1db7b-120">Si vous utilisez le générateur de topologie pour déployer vos bases de données, vous devez être membre du groupe sysadmin SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1db7b-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="1db7b-121">Si vous êtes membre du groupe sysadmin SQL Server, mais que vous n’avez pas de privilèges dans le domaine (par exemple, un rôle d’administrateur de base de données SQL Server), vous disposez des droits pour créer les bases de données, mais pas pour lire les informations nécessaires dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1db7b-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="1db7b-122">Pour plus d’informations sur les droits utilisateur et les autorisations nécessaires au déploiement de Lync Server, reportez-vous à la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1db7b-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="1db7b-p108">Vérifiez que les paramètres par défaut du dossier de la base de données et des fichiers journaux sont correctement mappés sur les disques partagés dans le cluster SQL Server à l’aide de SQL Server Management Studio. Cette procédure est nécessaire si vous créez des bases de données à l’aide du Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="1db7b-p108">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio. This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1db7b-125">Si vous n’avez pas installé SQL Server Management Studio, vous pouvez le faire en réexécutant le programme d’installation de SQL Server, puis en sélectionnant l’outil de gestion en tant que fonctionnalité à ajouter au déploiement SQL Server existant.</span><span class="sxs-lookup"><span data-stu-id="1db7b-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="1db7b-126">Installez les bases de données pour le serveur basé sur SQL Server à l’aide du générateur de topologie ou des applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1db7b-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="1db7b-127">Pour utiliser le générateur de topologie, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="1db7b-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="1db7b-128">Pour utiliser les applets de commande Windows PowerShell, voir [installation de base de données à l’aide de Lync Server Management Shell dans Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="1db7b-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="1db7b-129">Pour créer des bases de données à l’aide du générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="1db7b-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="1db7b-130">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1db7b-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1db7b-131">La procédure suivante suppose que vous ayez défini et configuré votre topologie dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="1db7b-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="1db7b-132">Pour plus d’informations sur la définition de votre topologie, reportez-vous à<A href="lync-server-2013-defining-and-configuring-the-topology.md">la rubrique Defining and Configuring the Topology in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1db7b-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="1db7b-133">Pour publier et configurer la base de données à l’aide du Générateur de topologies, vous devez ouvrir une session avec un compte d’utilisateur disposant des droits et appartenances aux groupes qui conviennent.</span><span class="sxs-lookup"><span data-stu-id="1db7b-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="1db7b-134">Pour plus d’informations sur les droits requis et les appartenances aux groupes, voir <A href="lync-server-2013-deployment-permissions-for-sql-server.md">autorisations de déploiement pour SQL Server dans Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1db7b-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="1db7b-135">Dans le générateur de topologie, lorsque vous publiez la topologie, dans la page **créer des bases de données** , cliquez sur **avancé**.</span><span class="sxs-lookup"><span data-stu-id="1db7b-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="1db7b-p111">La page **Sélectionner un emplacement de fichier de base de données** comporte deux options qui déterminent la façon dont les fichiers de base de données sont déployés sur le cluster SQL Server. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="1db7b-p111">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster. Select one of the following:</span></span>
    
      - <span data-ttu-id="1db7b-138">**Déterminer automatiquement l’emplacement du fichier de base de données.**</span><span class="sxs-lookup"><span data-stu-id="1db7b-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="1db7b-139">L’emplacement des fichiers journaux de base de données est déterminé à l’aide d’un algorithme en fonction de la configuration des disques du serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1db7b-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="1db7b-140">Les fichiers sont répartis de sorte à privilégier les performances.</span><span class="sxs-lookup"><span data-stu-id="1db7b-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="1db7b-141">Utiliser les valeurs par défaut de l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1db7b-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="1db7b-142">Si vous sélectionnez cette option, les fichiers journaux et de données sont installés en fonction des paramètres de l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1db7b-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="1db7b-143">Une fois les fichiers de base de données déployés sur le serveur SQL Server, l’administrateur de la base de données SQL Server souhaitera peut-être les déplacer pour optimiser les performances selon les spécificités de votre configuration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1db7b-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="1db7b-144">Terminez la publication de la topologie et confirmez qu’aucune erreur ne s’est produite au cours de cette opération.</span><span class="sxs-lookup"><span data-stu-id="1db7b-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

