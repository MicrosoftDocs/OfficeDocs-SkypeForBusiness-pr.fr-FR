---
title: 'Lync Server 2013 : Installation de la base de données avec Lync Server Management Shell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fd9f07b979f89a28b6fa545f3a43009402f4ed1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="b7928-102">Installation de la base de données avec Lync Server Management Shell dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7928-102">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7928-103">_**Dernière modification de la rubrique:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="b7928-103">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="b7928-104">La séparation des rôles et des responsabilités entre les administrateurs du serveur et les administrateurs SQL Server peut entraîner des retards de l’implémentation.</span><span class="sxs-lookup"><span data-stu-id="b7928-104">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="b7928-105">Lync Server 2013 utilise le contrôle de contrôle d’accès basé sur les rôles (RBAC) pour limiter ces difficultés.</span><span class="sxs-lookup"><span data-stu-id="b7928-105">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="b7928-106">Dans certains cas, l’administrateur SQL Server doit gérer l’installation de bases de données sur le serveur SQL Server en dehors de RBAC.</span><span class="sxs-lookup"><span data-stu-id="b7928-106">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="b7928-107">Lync Server 2013 Management Shell permet à l’administrateur SQL Server d’exécuter des cmdlets Windows PowerShell conçues pour configurer les bases de données avec les données et les fichiers journaux appropriés.</span><span class="sxs-lookup"><span data-stu-id="b7928-107">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="b7928-108">Pour plus d’informations, reportez-vous à la section [autorisations de déploiement pour SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b7928-108">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="b7928-109">La procédure suivante suppose que, au minimum, 2013 le client SQL Server Native Client (sqlncli. msi) Microsoft SQL Server 2012 Management objets, les types CLR pour Microsoft SQL Server 2012 et Microsoft SQL Server 2012 ADOMD.NET sont installés.</span><span class="sxs-lookup"><span data-stu-id="b7928-109">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="b7928-110">OCSCore. msi se trouve sur le média d’installation dans le répertoire \Setup\AMD64\Setup.</span><span class="sxs-lookup"><span data-stu-id="b7928-110">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="b7928-111">Les composants restants se trouvent dans \Setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="b7928-111">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="b7928-112">Par ailleurs, la préparation d’Active Directory pour Lync Server 2013 a été effectuée avec succès.</span><span class="sxs-lookup"><span data-stu-id="b7928-112">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="b7928-113">**Install-CsDatabase** est l’applet de la cmdlet Windows PowerShell que vous utilisez pour installer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="b7928-113">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="b7928-114">L’applet de l’applet de **CsDatabase installation-** a un grand nombre de paramètres, dont seuls quelques sont décrits ici.</span><span class="sxs-lookup"><span data-stu-id="b7928-114">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="b7928-115">Pour plus d’informations sur les paramètres possibles, voir la documentation Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7928-115">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="b7928-116">Pour éviter les problèmes de performances et de délais éventuels, utilisez toujours des noms de domaine complets lorsque vous faites référence à des serveurs SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7928-116">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="b7928-117">Évitez d’utiliser des références de nom d’hôte uniquement.</span><span class="sxs-lookup"><span data-stu-id="b7928-117">Avoid using host name-only references.</span></span> <span data-ttu-id="b7928-118">Par exemple, utilisez sqlbe01.contoso.net, mais évitez d’utiliser SQLBE01.</span><span class="sxs-lookup"><span data-stu-id="b7928-118">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="b7928-119">Pour l’installation de bases de données, **install-CsDatabase** utilise trois méthodes principales de placement des bases de données sur le serveur SQL Server préparé:</span><span class="sxs-lookup"><span data-stu-id="b7928-119">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="b7928-120">Exécutez **install-CsDatabase** sans DatabasePaths ou UseDefaultSqlPath.</span><span class="sxs-lookup"><span data-stu-id="b7928-120">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="b7928-121">L’applet de connexion utilise un algorithme intégré pour déterminer le meilleur emplacement pour les fichiers journaux et les fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="b7928-121">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="b7928-122">L’algorithme fonctionne uniquement pour les implémentations SQL Server autonomes.</span><span class="sxs-lookup"><span data-stu-id="b7928-122">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="b7928-123">Exécutez **install-CsDatabase** avec le paramètre DatabasePaths.</span><span class="sxs-lookup"><span data-stu-id="b7928-123">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="b7928-124">L’algorithme intégré pour optimiser les emplacements des fichiers journaux et des fichiers de données n’est pas utilisé si le paramètre DatabasePaths est défini.</span><span class="sxs-lookup"><span data-stu-id="b7928-124">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="b7928-125">Ce paramètre vous permet de définir les emplacements dans lesquels les fichiers de données et de journaux seront déployés.</span><span class="sxs-lookup"><span data-stu-id="b7928-125">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="b7928-126">Exécutez **install-CsDatabase** avec UseDefaultSqlPaths.</span><span class="sxs-lookup"><span data-stu-id="b7928-126">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="b7928-127">Cette option n’utilise pas l’algorithme intégré pour optimiser les emplacements du journal et des fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="b7928-127">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="b7928-128">Le fichier journal et les fichiers de données sont déployés conformément aux paramètres par défaut définis par l’administrateur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7928-128">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="b7928-129">Ces chemins d’accès sont généralement définis pour l’utilisation de l’administration automatique de fichiers de journaux et de données sur le serveur SQL Server à l’avance, et ne sont pas associés à l’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7928-129">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="b7928-130">Le paramètre DatabasePathMap peut également être utilisé pour spécifier explicitement un emplacement pour chaque base de données et son fichier journal respectif.</span><span class="sxs-lookup"><span data-stu-id="b7928-130">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="b7928-131">Pour utiliser des cmdlets Windows PowerShell pour configurer le magasin de gestion SQL Server central</span><span class="sxs-lookup"><span data-stu-id="b7928-131">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="b7928-132">Sur n’importe quel ordinateur, connectez-vous avec des informations d’identification d’administrateur pour créer les bases de données sur le serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7928-132">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="b7928-133">Pour plus d’informations, reportez-vous à la section [autorisations de déploiement pour SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b7928-133">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="b7928-134">Ouvrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7928-134">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="b7928-135">Si vous n’avez pas ajusté la stratégie d’exécution pour Windows PowerShell, vous devez ajuster la stratégie pour autoriser l’exécution des scripts Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7928-135">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="b7928-136">Pour plus d’informations, consultez la section «examen de [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)la stratégie d’exécution».</span><span class="sxs-lookup"><span data-stu-id="b7928-136">For details, see “Examining the Execution Policy” at [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="b7928-137">Utilisez l’applet de passe **install-CsDatabase** pour installer le centre de gestion central.</span><span class="sxs-lookup"><span data-stu-id="b7928-137">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b7928-138">Le paramètre de rapport est facultatif, mais il est utile si vous documentez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="b7928-138">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="b7928-139">**Install-CsDatabase – DatabasePaths** peut utiliser jusqu’à six paramètres de chemin d’accès, chacun définissant les chemins d’accès pour les lecteurs tels qu’ils sont définis dans les données SQL Server et l’emplacement des fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="b7928-139">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="b7928-140">Conformément aux règles logiques de la configuration de la base de données dans Lync Server 2013, les lecteurs sont analysés en compartiments de deux, quatre ou six.</span><span class="sxs-lookup"><span data-stu-id="b7928-140">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="b7928-141">En fonction de votre configuration SQL Server et du nombre de compartiments, vous fournissez deux chemins d’accès, quatre chemins d’accès ou six chemins.</span><span class="sxs-lookup"><span data-stu-id="b7928-141">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="b7928-142">Si vous avez trois lecteurs, le journal est prioritaire et les fichiers de données sont distribués après.</span><span class="sxs-lookup"><span data-stu-id="b7928-142">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="b7928-143">Exemple pour un serveur SQL Server configuré sur six lecteurs:</span><span class="sxs-lookup"><span data-stu-id="b7928-143">An example for a SQL Server-based server configured with six drives:</span></span>
    
        Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"

5.  <span data-ttu-id="b7928-144">À l’issue de l’installation de la base de données, vous pouvez fermer Lync Server 2013 Management Shell ou procéder à l’installation des bases de données configurées Lync Server 2013 définies dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b7928-144">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="b7928-145">Pour utiliser des cmdlets Windows PowerShell pour configurer la base de données configurée de topologie SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7928-145">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="b7928-146">Pour installer les bases de données configurées du générateur de topologie pour Lync Server 2013, l’administrateur 2013 du serveur Lync doit publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="b7928-146">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="b7928-147">Pour plus d’informations, reportez-vous à la rubrique [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b7928-147">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="b7928-148">Sur n’importe quel ordinateur, connectez-vous avec des informations d’identification d’administrateur pour créer les bases de données sur le serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7928-148">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="b7928-149">Voir la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b7928-149">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b7928-150">Pour être en mesure de configurer les bases de données SQL Server, assurez-vous que le compte d’administrateur SQL Server utilisé pour exécuter les étapes décrites ci-après est également membre du groupe sysadmins (ou équivalent) sur le serveur exécutant SQL Server et disposant de la gestion centrale Rôle du serveur.</span><span class="sxs-lookup"><span data-stu-id="b7928-150">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="b7928-151">C’est particulièrement important de rechercher d’autres pools Lync Server 2013 qui nécessitent une installation ou une configuration de la base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7928-151">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="b7928-152">Par exemple, si vous déployez un deuxième pool (pool02), mais que le rôle serveur central de gestion est maintenu par pool01.</span><span class="sxs-lookup"><span data-stu-id="b7928-152">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="b7928-153">Le groupe SQL Server sysadmin (ou équivalent) doit avoir des autorisations sur les bases de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7928-153">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="b7928-154">Ouvrez Lync Server 2013 Management Shell, s’il n’est pas déjà ouvert.</span><span class="sxs-lookup"><span data-stu-id="b7928-154">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="b7928-155">Utilisez l’applet de cmdlet **install-CsDatabase** pour installer les bases de données configurées du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b7928-155">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b7928-156">Le paramètre de rapport est facultatif, mais il est utile si vous documentez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="b7928-156">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="b7928-157">À la fin de l’installation de la base de données, fermez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7928-157">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="b7928-158">Pour utiliser des cmdlets Windows PowerShell pour configurer la topologie SQL Server à l’aide du paramètre DatabasePathMap</span><span class="sxs-lookup"><span data-stu-id="b7928-158">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="b7928-159">Pour installer des bases de données pour Lync Server 2013, l’administrateur du serveur Lync doit créer les chemins d’accès et déployer les fichiers de base de données et les fichiers journaux en fonction d’un ensemble de règles prédéfini.</span><span class="sxs-lookup"><span data-stu-id="b7928-159">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="b7928-160">Sur n’importe quel ordinateur, connectez-vous avec des informations d’identification d’administrateur pour créer les bases de données sur le serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7928-160">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="b7928-161">Voir la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b7928-161">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b7928-162">Pour être en mesure de configurer les bases de données SQL Server, assurez-vous que le compte d’administrateur SQL Server utilisé pour exécuter les étapes décrites ci-après est également membre du groupe sysadmins (ou équivalent) sur le serveur exécutant SQL Server et disposant de la gestion centrale Rôle du serveur.</span><span class="sxs-lookup"><span data-stu-id="b7928-162">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="b7928-163">C’est particulièrement important de rechercher d’autres pools de serveurs Lync qui nécessitent l’installation ou la configuration de la base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7928-163">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="b7928-164">Par exemple, si vous déployez un deuxième pool (pool02), mais que le rôle serveur central de gestion est maintenu par pool01.</span><span class="sxs-lookup"><span data-stu-id="b7928-164">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="b7928-165">Le groupe SQL Server sysadmin (ou équivalent) doit avoir des autorisations sur les bases de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7928-165">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="b7928-166">Ouvrez Lync Server Management Shell, s’il n’est pas déjà ouvert.</span><span class="sxs-lookup"><span data-stu-id="b7928-166">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="b7928-167">Utilisez l’applet de passe **install-CsDatabase** avec le paramètre DatabasePathMap et une table de hachage PowerShell pour installer les bases de données configurées du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b7928-167">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="b7928-168">Dans l’exemple de code, les chemins d’accès définis pour les bases de données peuvent être déterminés de façon granulaire en utilisant le paramètre – DatabasePathMap et une table de hachage définie comme suit (l’exemple\\utilise «c: CSData» pour tous les fichiers de base de données (\\ . mdf) et «c: CSLogFiles "pour tous les fichiers journaux (. ldf).</span><span class="sxs-lookup"><span data-stu-id="b7928-168">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="b7928-169">Le dossier sera créé selon les besoins par l’installation-CsDatabase):</span><span class="sxs-lookup"><span data-stu-id="b7928-169">Folder will be created as needed by Install-CsDatabase):</span></span>
    
        $pathmap = @{
        "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
        "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
        "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
        "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
        }
        Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap

6.  <span data-ttu-id="b7928-170">Dans la mesure où les fichiers de base de données et les fichiers journaux sont explicitement nommés avec leur emplacement sur le serveur de base de données de destination, vous pouvez définir des emplacements spécifiques pour la base de données et l’emplacement du journal de chaque type de service.</span><span class="sxs-lookup"><span data-stu-id="b7928-170">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="b7928-171">L’exemple ci-dessous place les bases de données pour chaque type de service spécifique sur des disques distincts et les fichiers journaux associés sur un autre.</span><span class="sxs-lookup"><span data-stu-id="b7928-171">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="b7928-172">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b7928-172">For example:</span></span>
    
      - <span data-ttu-id="b7928-173">Toutes les bases de données RTC en «\\D: RTCDatabase»</span><span class="sxs-lookup"><span data-stu-id="b7928-173">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="b7928-174">Tous les fichiers journaux RTC comme suit:\\«E: RTCLogs»</span><span class="sxs-lookup"><span data-stu-id="b7928-174">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="b7928-175">Toutes les bases de données du Windows Store en\\"F: CPSDatabases"</span><span class="sxs-lookup"><span data-stu-id="b7928-175">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="b7928-176">Toutes les journaux de l’application Store sur\\«G: CPSLogs»</span><span class="sxs-lookup"><span data-stu-id="b7928-176">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="b7928-177">Toutes les bases de données du magasin de Response Group\\en «H: RGSDatabases»</span><span class="sxs-lookup"><span data-stu-id="b7928-177">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="b7928-178">Tous les journaux du magasin de réponse à «\\I: RGSLogs»</span><span class="sxs-lookup"><span data-stu-id="b7928-178">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="b7928-179">Toutes les bases de données du magasin d’adresses en\\«J: ABSDatabases»</span><span class="sxs-lookup"><span data-stu-id="b7928-179">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="b7928-180">Tous les fichiers journaux du magasin d’adresses en «\\K: ABSLogs»</span><span class="sxs-lookup"><span data-stu-id="b7928-180">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="b7928-181">Toutes les bases de données de l’archivage du\\magasin sur «L: ArchivingDatabases»</span><span class="sxs-lookup"><span data-stu-id="b7928-181">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="b7928-182">Tous les journaux d’archivage de la boutique\\sur «M: ArchivingLogs»</span><span class="sxs-lookup"><span data-stu-id="b7928-182">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="b7928-183">Toutes les bases de données de magasin de l'\\analyse sur «N: MonitoringDatabases»</span><span class="sxs-lookup"><span data-stu-id="b7928-183">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="b7928-184">Toutes les analyses des fichiers journaux du magasin dans\\«O: MonitoringLogfiles»</span><span class="sxs-lookup"><span data-stu-id="b7928-184">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ``` 
    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    <span data-ttu-id="b7928-185">À l’aide du paramètre-DatabasePathMap, vous pouvez définir toute combinaison de mappage de lettre de lecteur logique qui fournit la solution la plus adaptée à vos besoins en matière de performances et de placement SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7928-185">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="b7928-186">Si vous configurez les fichiers de données et les fichiers journaux de votre base de données à l’aide de la méthode **DatabasePathMap** , vous devrez apporter une légère modification à votre processus normal lors de l’utilisation du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b7928-186">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="b7928-187">En règle générale, vous devez définir vos choix de topologie, publier la topologie et choisir de déployer les sélections de la base de données.</span><span class="sxs-lookup"><span data-stu-id="b7928-187">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="b7928-188">Si vous avez déjà utilisé **DatabasePathMap** , vous avez déjà effectué la troisième partie du processus du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b7928-188">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="b7928-189">Dans le cas où il est nécessaire de disposer d’un serveur de base de données complètement configuré avant d’exécuter le générateur de topologie, vous devez toujours définir tous les rôles et options de votre serveur, mais désélectionner l’option de création des bases de données.</span><span class="sxs-lookup"><span data-stu-id="b7928-189">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

