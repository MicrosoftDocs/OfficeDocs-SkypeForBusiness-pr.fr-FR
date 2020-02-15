---
title: 'Lync Server 2013 : installation de la base de données à l’aide de Lync Server Management Shell'
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
ms.openlocfilehash: d46d3bc2ce881edc183e4996c0c71d6a90af4e6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Installation de la base de données à l’aide de Lync Server Management Shell dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-06-16_

La séparation des rôles et des responsabilités entre les administrateurs de serveurs et les administrateurs SQL Server peut entraîner des retards d’implémentation. Lync Server 2013 utilise le contrôle d’accès basé sur un rôle (RBAC) pour atténuer ces difficultés. Dans certains cas, l’administrateur SQL Server doit gérer l’installation des bases de données sur le serveur SQL Server externe au contrôle d’accès basé sur un rôle. Lync Server 2013 Management Shell permet à l’administrateur SQL Server d’exécuter des applets de commande Windows PowerShell conçues pour configurer les bases de données avec les fichiers de données et journaux appropriés. Pour plus d’informations, reportez-vous à la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

<div class=" ">


> [!IMPORTANT]  
> La procédure suivante suppose que, au minimum, les objets de gestion de Lync Server 2013 OCSCore. msi, SQL Server Native Client (sqlncli. msi) Microsoft SQL Server 2012, les types CLR pour Microsoft SQL Server 2012 et Microsoft SQL Server 2012 ADOMD.NET sont installés. Le fichier OCSCore.msi se trouve sur le média d’installation dans le répertoire \Setup\AMD64\Setup. Les composants restants se trouvent dans \Setup\amd64. En outre, la préparation d’Active Directory pour Lync Server 2013 a réussi.



</div>

**Install-applet csdatabase** est l’applet de commande Windows PowerShell que vous utilisez pour installer les bases de données. L’applet de commande **Install-CsDatabase** dispose de nombreux paramètres dont quelques-uns seulement sont décrits ici. Pour plus d’informations sur les paramètres possibles, voir la documentation de Lync Server 2013 Management Shell.

<div class=" ">


> [!WARNING]  
> Pour éviter la survenue de problèmes de performances ou de délais, n’oubliez pas d’utiliser des noms de domaines complets lorsque vous désignez des serveurs SQL Server. Évitez d’utiliser uniquement des noms d’hôtes. Par exemple, utilisez sqlbe01.contoso.net, mais évitez d’utiliser SQLBE01.



</div>

Pour l’installation des bases de données, **install-applet csdatabase** utilise trois méthodes principales pour placer les bases de données sur le serveur SQL Server préparé :

  - Exécutez **Install-CsDatabase** sans DatabasePaths ou UseDefaultSqlPath. Cette applet de commande utilise un algorithme intégré pour déterminer le meilleur emplacement des fichiers de données et des fichiers journaux. L’algorithme fonctionne uniquement pour les implémentations SQL Server autonomes.

  - Exécutez **Install-CsDatabase** sans le paramètre DatabasePaths. L’algorithme intégré pour optimiser les emplacements des fichiers de données et des fichiers journaux n’est pas employé si le paramètre DatabasePaths est défini. Ce paramètre vous permet de définir les emplacements où seront déployés les fichiers de données et les fichiers journaux.

  - Exécutez **Install-CsDatabase** avec UseDefaultSqlPaths. Cette option ne fait pas appel à l’algorithme intégré pour optimiser les emplacements des fichiers de données et des fichiers journaux. Ceux-ci sont déployés conformément aux paramètres par défaut définis par l’administrateur SQL Server. Ces chemins d’accès sont généralement définis pour l’utilisation de l’administration automatique des fichiers journaux et de données sur le serveur SQL à l’avance, et ne sont pas associés à la configuration de Lync Server 2013.

  - Le paramètre DatabasePathMap peut également être utilisé pour spécifier explicitement un emplacement pour chaque base de données et son fichier journal respectif.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Pour utiliser les applets de commande Windows PowerShell et configurer le magasin central de gestion SQL Server

1.  Ouvrez une session d’administration sur un ordinateur pour créer les bases de données sur le serveur SQL Server. Pour plus d’informations, reportez-vous à la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Ouvrez Lync Server 2013 Management Shell. Si vous n’avez pas ajusté la stratégie d’exécution pour Windows PowerShell, vous devez ajuster la stratégie pour autoriser l’exécution des scripts Windows PowerShell. Pour plus d’informations, consultez la rubrique « examen de [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)la stratégie d’exécution » à l’adresse.

3.  Utilisez la cmdlet **install-applet csdatabase** pour installer le magasin central de gestion.
    
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
    > Le paramètre Report est facultatif, mais peut être utile si vous documentez le processus d’installation.

    
    </div>

4.  **Install-applet csdatabase : DatabasePaths** peut utiliser jusqu’à six paramètres de chemin d’accès, chacun définissant les chemins d’accès pour les lecteurs, comme défini dans SQL Server Data and log file placement. Par les règles logiques de configuration de base de données dans Lync Server 2013, les lecteurs sont analysés en compartiments de deux, quatre ou six. En fonction de votre configuration de SQL Server et du nombre de compartiments, vous fournirez deux chemins d’accès, quatre chemins d’accès ou six chemins d’accès.
    
    Si vous disposez de trois lecteurs, le journal devient prioritaire et les fichiers de données sont distribués après. Exemple de serveur basé sur SQL Server configuré avec six lecteurs :
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  Une fois l’installation de la base de données terminée, vous pouvez fermer Lync Server 2013 Management Shell ou procéder à l’installation des bases de données configurées Lync Server 2013 définies dans le générateur de topologie.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Pour utiliser les applets de commande Windows PowerShell et configurer les bases de données configurées de la topologie SQL Server

1.  Pour installer les bases de données configurées du générateur de topologies pour Lync Server 2013, l’administrateur de Lync Server 2013 doit publier la topologie. Pour plus d’informations, reportez-vous à [la rubrique publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation de déploiement.

2.  Ouvrez une session d’administration sur un ordinateur pour créer les bases de données sur le serveur SQL Server. Reportez-vous à la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Pour pouvoir configurer les bases de données basées sur SQL Server, assurez-vous que le compte d’administrateur SQL Server utilisé pour exécuter les étapes décrites ici est également membre du groupe sysadmins (ou équivalent) sur le serveur exécutant SQL Server et en tenant compte de la direction centrale Rôle serveur. Ceci est particulièrement important pour vérifier les pools Lync Server 2013 supplémentaires qui nécessitent une installation ou une configuration de base de données SQL Server. Par exemple, si vous déployez un deuxième pool (pool02) mais que le rôle de serveur de gestion centralisée est conservé par pool01. Le groupe sysadmin SQL Server (ou équivalent) doit disposer d’autorisations sur les bases de données basées sur SQL Server.

    
    </div>

3.  Ouvrez Lync Server 2013 Management Shell, s’il n’est pas déjà ouvert.

4.  Utilisez l’applet de commande **install-applet csdatabase** pour installer les bases de données configurées du générateur de topologies.
    
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
    > Le paramètre Report est facultatif, mais peut être utile si vous documentez le processus d’installation.

    
    </div>

5.  Une fois l’installation de la base de données terminée, fermez Lync Server 2013 Management Shell.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Pour utiliser les applets de commande Windows PowerShell pour configurer la topologie SQL Server à l’aide du paramètre DatabasePathMap

1.  Pour installer les bases de données pour Lync Server 2013, l’administrateur Lync Server doit créer les chemins d’accès et déployer les fichiers de bases de données et les fichiers journaux en fonction d’un ensemble prédéfini de règles.

2.  Ouvrez une session d’administration sur un ordinateur pour créer les bases de données sur le serveur SQL Server. Reportez-vous à la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Pour pouvoir configurer les bases de données basées sur SQL Server, assurez-vous que le compte d’administrateur SQL Server utilisé pour exécuter les étapes décrites ici est également membre du groupe sysadmins (ou équivalent) sur le serveur exécutant SQL Server et en tenant compte de la direction centrale Rôle serveur. Ceci est particulièrement important pour vérifier les pools Lync Server supplémentaires qui nécessitent l’installation ou la configuration de la base de données SQL Server. Par exemple, si vous déployez un deuxième pool (pool02) mais que le rôle de serveur de gestion centralisée est conservé par pool01. Le groupe sysadmin SQL Server (ou équivalent) doit disposer d’autorisations sur les bases de données basées sur SQL Server.

    
    </div>

3.  Ouvrez Lync Server Management Shell, s’il n’est pas déjà ouvert.

4.  Utilisez la cmdlet **install-applet csdatabase** avec le paramètre DatabasePathMap et une table de hachage PowerShell pour installer les bases de données configurées du générateur de topologies.

5.  Dans l’exemple de code, les chemins d’accès définis pour les bases de données peuvent être déterminés de manière granulaire en utilisant le paramètre – DatabasePathMap et une table de hachage définie comme suit (l’exemple\\utilise « c : CSData » pour tous les fichiers de base de données (\\. mdf) et « c : CSLogFiles » pour tous les fichiers journaux (. ldf). Le dossier sera créé si nécessaire par install-applet csdatabase) :
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
6.  Étant donné que la base de données et les fichiers journaux sont explicitement nommés avec leur emplacement sur le serveur de base de données de destination, vous pouvez définir des emplacements spécifiques pour la base de données et l’emplacement de journal de chaque type de service. L’exemple suivant place les bases de données pour chaque type de service spécifique sur des disques distincts et les fichiers journaux associés sur un autre. Par exemple :
    
      - Toutes les bases de données RTC sur «\\D : RTCDatabase »
    
      - Tous les fichiers journaux RTC sur « E\\: RTCLogs »
    
      - Toutes les bases de données de magasin d’applications\\vers « F : CPSDatabases »
    
      - Tous les journaux du magasin d’applications sur\\« G : CPSLogs »
    
      - Toutes les bases de données de magasin Response Group sur\\« H : RGSDatabases »
    
      - Tous les journaux de magasin Response Group sur «\\I : RGSLogs »
    
      - Toutes les bases de données de magasin de carnet d'\\adresses vers « J : ABSDatabases »
    
      - Tous les fichiers journaux du magasin d’adresses en «\\K : ABSLogs »
    
      - Toutes les bases de données de magasin d’archivage\\vers « L : ArchivingDatabases »
    
      - Tous les journaux de magasin d’archivage sur\\« M : ArchivingLogs »
    
      - Toutes les bases de données de magasin de surveillance\\vers « N : MonitoringDatabases »
    
      - Tous les fichiers journaux du magasin de surveillance sur\\« O : MonitoringLogfiles »
    
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
    
    À l’aide du paramètre – DatabasePathMap, vous pouvez définir toute combinaison de mappage de lettre de lecteur logique qui offre la meilleure solution pour vos besoins en matière de performances et de positionnement de SQL Server.

Si vous configurez vos fichiers de données et fichiers journaux de base de données à l’aide de la méthode **DatabasePathMap** , vous devrez modifier légèrement votre processus normal lors de l’utilisation du générateur de topologie. En règle générale, vous devez définir vos choix de topologie, publier la topologie et choisir de déployer les sélections de base de données.

Si vous avez utilisé **DatabasePathMap** , vous avez déjà effectué la troisième partie du processus du générateur de topologies. Si vous disposez d’un serveur de base de données entièrement configuré avant d’exécuter le générateur de topologie, vous devez toujours définir tous vos rôles serveur et toutes les options, mais désélectionnez l’option de création des bases de données.

</div>

</div>

<span> </span>

</div>

</div>

</div>

