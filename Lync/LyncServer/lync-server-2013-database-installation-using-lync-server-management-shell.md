---
title: 'Lync Server 2013 : installation de la base de données à l’aide de Lync Server Management Shell'
description: 'Lync Server 2013 : installation de la base de données à l’aide de Lync Server Management Shell.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d572984c94d280723b12c5343a92ddfaa12d4f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558180"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="5b8e1-103">Installation de la base de données à l’aide de Lync Server Management Shell dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8e1-103">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b8e1-104">_**Dernière modification de la rubrique :** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="5b8e1-104">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="5b8e1-105">La séparation des rôles et des responsabilités entre les administrateurs de serveurs et les administrateurs SQL Server peut entraîner des retards d’implémentation.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-105">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="5b8e1-106">Lync Server 2013 utilise le contrôle d’accès basé sur un rôle (RBAC) pour atténuer ces difficultés.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-106">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="5b8e1-107">Dans certains cas, l’administrateur SQL Server doit gérer l’installation des bases de données sur le serveur SQL Server externe au contrôle d’accès basé sur un rôle.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-107">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="5b8e1-108">Lync Server 2013 Management Shell permet à l’administrateur SQL Server d’exécuter des applets de commande Windows PowerShell conçues pour configurer les bases de données avec les fichiers de données et journaux appropriés.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-108">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="5b8e1-109">Pour plus d’informations, reportez-vous à la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5b8e1-109">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="5b8e1-110">La procédure suivante suppose que, au minimum, le OCSCore.msi Lync Server 2013, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, les types CLR pour Microsoft SQL Server 2012 et Microsoft SQL Server 2012 ADOMD.NET sont installés.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-110">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="5b8e1-111">Le fichier OCSCore.msi se trouve sur le média d’installation dans le répertoire \Setup\AMD64\Setup.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-111">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="5b8e1-112">Les composants restants se trouvent dans \Setup\amd64.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-112">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="5b8e1-113">En outre, la préparation d’Active Directory pour Lync Server 2013 a réussi.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-113">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="5b8e1-114">**Install-applet csdatabase** est l’applet de commande Windows PowerShell que vous utilisez pour installer les bases de données.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-114">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="5b8e1-115">L’applet de commande **Install-CsDatabase** dispose de nombreux paramètres dont quelques-uns seulement sont décrits ici.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-115">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="5b8e1-116">Pour plus d’informations sur les paramètres possibles, voir la documentation de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-116">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="5b8e1-117">Pour éviter la survenue de problèmes de performances ou de délais, n’oubliez pas d’utiliser des noms de domaines complets lorsque vous désignez des serveurs SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-117">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="5b8e1-118">Évitez d’utiliser uniquement des noms d’hôtes.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-118">Avoid using host name-only references.</span></span> <span data-ttu-id="5b8e1-119">Par exemple, utilisez sqlbe01.contoso.net, mais évitez d’utiliser SQLBE01.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-119">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="5b8e1-120">Pour l’installation des bases de données, **install-applet csdatabase** utilise trois méthodes principales pour placer les bases de données sur le serveur SQL Server préparé :</span><span class="sxs-lookup"><span data-stu-id="5b8e1-120">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="5b8e1-121">Exécutez **Install-CsDatabase** sans DatabasePaths ou UseDefaultSqlPath.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-121">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="5b8e1-122">Cette applet de commande utilise un algorithme intégré pour déterminer le meilleur emplacement des fichiers de données et des fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-122">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="5b8e1-123">L’algorithme fonctionne uniquement pour les implémentations SQL Server autonomes.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-123">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="5b8e1-124">Exécutez **Install-CsDatabase** sans le paramètre DatabasePaths.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-124">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="5b8e1-125">L’algorithme intégré pour optimiser les emplacements des fichiers de données et des fichiers journaux n’est pas employé si le paramètre DatabasePaths est défini.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-125">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="5b8e1-126">Ce paramètre vous permet de définir les emplacements où seront déployés les fichiers de données et les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-126">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="5b8e1-127">Exécutez **Install-CsDatabase** avec UseDefaultSqlPaths.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-127">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="5b8e1-128">Cette option ne fait pas appel à l’algorithme intégré pour optimiser les emplacements des fichiers de données et des fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-128">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="5b8e1-129">Ceux-ci sont déployés conformément aux paramètres par défaut définis par l’administrateur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-129">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="5b8e1-130">Ces chemins d’accès sont généralement définis pour l’utilisation de l’administration automatique des fichiers journaux et de données sur le serveur SQL à l’avance, et ne sont pas associés à la configuration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-130">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="5b8e1-131">Le paramètre DatabasePathMap peut également être utilisé pour spécifier explicitement un emplacement pour chaque base de données et son fichier journal respectif.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-131">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="5b8e1-132">Pour utiliser les applets de commande Windows PowerShell et configurer le magasin central de gestion SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b8e1-132">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="5b8e1-133">Ouvrez une session d’administration sur un ordinateur pour créer les bases de données sur le serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-133">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="5b8e1-134">Pour plus d’informations, reportez-vous à la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5b8e1-134">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="5b8e1-135">Ouvrez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-135">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="5b8e1-136">Si vous n’avez pas ajusté la stratégie d’exécution pour Windows PowerShell, vous devez ajuster la stratégie pour autoriser l’exécution des scripts Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-136">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="5b8e1-137">Pour plus d’informations, consultez la rubrique « examen de la stratégie d’exécution » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) .</span><span class="sxs-lookup"><span data-stu-id="5b8e1-137">For details, see “Examining the Execution Policy” at [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="5b8e1-138">Utilisez la cmdlet **install-applet csdatabase** pour installer le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-138">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="5b8e1-139">Le paramètre Report est facultatif, mais peut être utile si vous documentez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-139">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="5b8e1-140">**Install-applet csdatabase : DatabasePaths** peut utiliser jusqu’à six paramètres de chemin d’accès, chacun définissant les chemins d’accès pour les lecteurs, comme défini dans SQL Server Data and log file placement.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-140">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="5b8e1-141">Par les règles logiques de configuration de base de données dans Lync Server 2013, les lecteurs sont analysés en compartiments de deux, quatre ou six.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-141">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="5b8e1-142">En fonction de votre configuration de SQL Server et du nombre de compartiments, vous fournirez deux chemins d’accès, quatre chemins d’accès ou six chemins d’accès.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-142">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="5b8e1-143">Si vous disposez de trois lecteurs, le journal devient prioritaire et les fichiers de données sont distribués après.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-143">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="5b8e1-144">Exemple de serveur basé sur SQL Server configuré avec six lecteurs :</span><span class="sxs-lookup"><span data-stu-id="5b8e1-144">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="5b8e1-145">Une fois l’installation de la base de données terminée, vous pouvez fermer Lync Server 2013 Management Shell ou procéder à l’installation des bases de données configurées Lync Server 2013 définies dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-145">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="5b8e1-146">Pour utiliser les applets de commande Windows PowerShell et configurer les bases de données configurées de la topologie SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b8e1-146">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="5b8e1-147">Pour installer les bases de données configurées du générateur de topologies pour Lync Server 2013, l’administrateur de Lync Server 2013 doit publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-147">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="5b8e1-148">Pour plus d’informations, reportez-vous à [la rubrique publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-148">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="5b8e1-149">Ouvrez une session d’administration sur un ordinateur pour créer les bases de données sur le serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-149">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="5b8e1-150">Reportez-vous à la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5b8e1-150">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5b8e1-151">Pour pouvoir configurer les bases de données basées sur SQL Server, assurez-vous que le compte d’administrateur SQL Server utilisé pour exécuter les étapes décrites ici est également membre du groupe administrateurs système (ou équivalent) sur le serveur exécutant SQL Server et hébergeant le rôle serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-151">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="5b8e1-152">Ceci est particulièrement important pour vérifier les pools Lync Server 2013 supplémentaires qui nécessitent une installation ou une configuration de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-152">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="5b8e1-153">Par exemple, si vous déployez un deuxième pool (pool02) mais que le rôle de serveur de gestion centralisée est conservé par pool01.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-153">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="5b8e1-154">Le groupe sysadmin SQL Server (ou équivalent) doit disposer d’autorisations sur les bases de données basées sur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-154">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="5b8e1-155">Ouvrez Lync Server 2013 Management Shell, s’il n’est pas déjà ouvert.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-155">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="5b8e1-156">Utilisez l’applet de commande **install-applet csdatabase** pour installer les bases de données configurées du générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-156">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="5b8e1-157">Le paramètre Report est facultatif, mais peut être utile si vous documentez le processus d’installation.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-157">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="5b8e1-158">Une fois l’installation de la base de données terminée, fermez Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-158">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="5b8e1-159">Pour utiliser les applets de commande Windows PowerShell pour configurer la topologie SQL Server à l’aide du paramètre DatabasePathMap</span><span class="sxs-lookup"><span data-stu-id="5b8e1-159">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="5b8e1-160">Pour installer les bases de données pour Lync Server 2013, l’administrateur Lync Server doit créer les chemins d’accès et déployer les fichiers de bases de données et les fichiers journaux en fonction d’un ensemble prédéfini de règles.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-160">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="5b8e1-161">Ouvrez une session d’administration sur un ordinateur pour créer les bases de données sur le serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-161">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="5b8e1-162">Reportez-vous à la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5b8e1-162">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5b8e1-163">Pour pouvoir configurer les bases de données basées sur SQL Server, assurez-vous que le compte d’administrateur SQL Server utilisé pour exécuter les étapes décrites ici est également membre du groupe administrateurs système (ou équivalent) sur le serveur exécutant SQL Server et hébergeant le rôle serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-163">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="5b8e1-164">Ceci est particulièrement important pour vérifier les pools Lync Server supplémentaires qui nécessitent l’installation ou la configuration de la base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-164">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="5b8e1-165">Par exemple, si vous déployez un deuxième pool (pool02) mais que le rôle de serveur de gestion centralisée est conservé par pool01.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-165">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="5b8e1-166">Le groupe sysadmin SQL Server (ou équivalent) doit disposer d’autorisations sur les bases de données basées sur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-166">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="5b8e1-167">Ouvrez Lync Server Management Shell, s’il n’est pas déjà ouvert.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-167">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="5b8e1-168">Utilisez la cmdlet **install-applet csdatabase** avec le paramètre DatabasePathMap et une table de hachage PowerShell pour installer les bases de données configurées du générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-168">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="5b8e1-169">Dans l’exemple de code, les chemins d’accès définis pour les bases de données peuvent être déterminés de manière granulaire en utilisant le paramètre – DatabasePathMap et une table de hachage définie comme suit (l’exemple utilise « C : \\ CSData » pour tous les fichiers de base de données (. mdf) et « c : \\ CSLogFiles » pour tous les fichiers journaux (. ldf).</span><span class="sxs-lookup"><span data-stu-id="5b8e1-169">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="5b8e1-170">Le dossier sera créé si nécessaire par install-applet csdatabase) :</span><span class="sxs-lookup"><span data-stu-id="5b8e1-170">Folder will be created as needed by Install-CsDatabase):</span></span>
    ```powershell
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
    ```
6.  <span data-ttu-id="5b8e1-171">Étant donné que la base de données et les fichiers journaux sont explicitement nommés avec leur emplacement sur le serveur de base de données de destination, vous pouvez définir des emplacements spécifiques pour la base de données et l’emplacement de journal de chaque type de service.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-171">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="5b8e1-172">L’exemple suivant place les bases de données pour chaque type de service spécifique sur des disques distincts et les fichiers journaux associés sur un autre.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-172">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="5b8e1-173">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="5b8e1-173">For example:</span></span>
    
      - <span data-ttu-id="5b8e1-174">Toutes les bases de données RTC sur « D : \\ RTCDatabase »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-174">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="5b8e1-175">Tous les fichiers journaux RTC sur « E : \\ RTCLogs »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-175">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="5b8e1-176">Toutes les bases de données de magasin d’applications vers « F : \\ CPSDatabases »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-176">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="5b8e1-177">Tous les journaux du magasin d’applications sur « G : \\ CPSLogs »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-177">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="5b8e1-178">Toutes les bases de données de magasin Response Group sur « H : \\ RGSDatabases »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-178">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="5b8e1-179">Tous les journaux de magasin Response Group sur « I : \\ RGSLogs »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-179">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="5b8e1-180">Toutes les bases de données de magasin de carnet d’adresses vers « J : \\ ABSDatabases »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-180">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="5b8e1-181">Tous les fichiers journaux du magasin d’adresses en « K : \\ ABSLogs »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-181">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="5b8e1-182">Toutes les bases de données de magasin d’archivage vers « L : \\ ArchivingDatabases »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-182">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="5b8e1-183">Tous les journaux de magasin d’archivage sur « M : \\ ArchivingLogs »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-183">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="5b8e1-184">Toutes les bases de données de magasin de surveillance vers « N : \\ MonitoringDatabases »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-184">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="5b8e1-185">Tous les fichiers journaux du magasin de surveillance sur « O : \\ MonitoringLogfiles »</span><span class="sxs-lookup"><span data-stu-id="5b8e1-185">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ```powershell    
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
    
    <span data-ttu-id="5b8e1-186">À l’aide du paramètre – DatabasePathMap, vous pouvez définir toute combinaison de mappage de lettre de lecteur logique qui offre la meilleure solution pour vos besoins en matière de performances et de positionnement de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-186">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="5b8e1-187">Si vous configurez vos fichiers de données et fichiers journaux de base de données à l’aide de la méthode **DatabasePathMap** , vous devrez modifier légèrement votre processus normal lors de l’utilisation du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-187">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="5b8e1-188">En règle générale, vous devez définir vos choix de topologie, publier la topologie et choisir de déployer les sélections de base de données.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-188">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="5b8e1-189">Si vous avez utilisé **DatabasePathMap** , vous avez déjà effectué la troisième partie du processus du générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-189">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="5b8e1-190">Si vous disposez d’un serveur de base de données entièrement configuré avant d’exécuter le générateur de topologie, vous devez toujours définir tous vos rôles serveur et toutes les options, mais désélectionnez l’option de création des bases de données.</span><span class="sxs-lookup"><span data-stu-id="5b8e1-190">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

