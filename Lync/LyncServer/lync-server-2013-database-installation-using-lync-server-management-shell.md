---
title: 'Lync Server 2013 : Installation de la base de données avec Lync Server Management Shell'
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
ms.openlocfilehash: 8c617d323eb00476b53677b670c8cc6db0b8d05c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Installation de la base de données avec Lync Server Management Shell dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-06-16_

La séparation des rôles et des responsabilités entre les administrateurs du serveur et les administrateurs SQL Server peut entraîner des retards de l’implémentation. Lync Server 2013 utilise le contrôle de contrôle d’accès basé sur les rôles (RBAC) pour limiter ces difficultés. Dans certains cas, l’administrateur SQL Server doit gérer l’installation de bases de données sur le serveur SQL Server en dehors de RBAC. Lync Server 2013 Management Shell permet à l’administrateur SQL Server d’exécuter des cmdlets Windows PowerShell conçues pour configurer les bases de données avec les données et les fichiers journaux appropriés. Pour plus d’informations, reportez-vous à la section [autorisations de déploiement pour SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

<div class=" ">


> [!IMPORTANT]  
> La procédure suivante suppose que, au minimum, 2013 le client SQL Server Native Client (sqlncli. msi) Microsoft SQL Server 2012 Management objets, les types CLR pour Microsoft SQL Server 2012 et Microsoft SQL Server 2012 ADOMD.NET sont installés. OCSCore. msi se trouve sur le média d’installation dans le répertoire \Setup\AMD64\Setup. Les composants restants se trouvent dans \Setup\amd64. Par ailleurs, la préparation d’Active Directory pour Lync Server 2013 a été effectuée avec succès.



</div>

**Install-CsDatabase** est l’applet de la cmdlet Windows PowerShell que vous utilisez pour installer les bases de données. L’applet de l’applet de **CsDatabase installation-** a un grand nombre de paramètres, dont seuls quelques sont décrits ici. Pour plus d’informations sur les paramètres possibles, voir la documentation Lync Server 2013 Management Shell.

<div class=" ">


> [!WARNING]  
> Pour éviter les problèmes de performances et de délais éventuels, utilisez toujours des noms de domaine complets lorsque vous faites référence à des serveurs SQL Server. Évitez d’utiliser des références de nom d’hôte uniquement. Par exemple, utilisez sqlbe01.contoso.net, mais évitez d’utiliser SQLBE01.



</div>

Pour l’installation de bases de données, **install-CsDatabase** utilise trois méthodes principales de placement des bases de données sur le serveur SQL Server préparé :

  - Exécutez **install-CsDatabase** sans DatabasePaths ou UseDefaultSqlPath. L’applet de connexion utilise un algorithme intégré pour déterminer le meilleur emplacement pour les fichiers journaux et les fichiers de données. L’algorithme fonctionne uniquement pour les implémentations SQL Server autonomes.

  - Exécutez **install-CsDatabase** avec le paramètre DatabasePaths. L’algorithme intégré pour optimiser les emplacements des fichiers journaux et des fichiers de données n’est pas utilisé si le paramètre DatabasePaths est défini. Ce paramètre vous permet de définir les emplacements dans lesquels les fichiers de données et de journaux seront déployés.

  - Exécutez **install-CsDatabase** avec UseDefaultSqlPaths. Cette option n’utilise pas l’algorithme intégré pour optimiser les emplacements du journal et des fichiers de données. Le fichier journal et les fichiers de données sont déployés conformément aux paramètres par défaut définis par l’administrateur SQL Server. Ces chemins d’accès sont généralement définis pour l’utilisation de l’administration automatique de fichiers de journaux et de données sur le serveur SQL Server à l’avance, et ne sont pas associés à l’installation de Lync Server 2013.

  - Le paramètre DatabasePathMap peut également être utilisé pour spécifier explicitement un emplacement pour chaque base de données et son fichier journal respectif.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Pour utiliser des cmdlets Windows PowerShell pour configurer le magasin de gestion SQL Server central

1.  Sur n’importe quel ordinateur, connectez-vous avec des informations d’identification d’administrateur pour créer les bases de données sur le serveur SQL Server. Pour plus d’informations, reportez-vous à la section [autorisations de déploiement pour SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Ouvrez Lync Server 2013 Management Shell. Si vous n’avez pas ajusté la stratégie d’exécution pour Windows PowerShell, vous devez ajuster la stratégie pour autoriser l’exécution des scripts Windows PowerShell. Pour plus d’informations, consultez la section « examen de [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)la stratégie d’exécution ».

3.  Utilisez l’applet de passe **install-CsDatabase** pour installer le centre de gestion central.
    
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
    > Le paramètre de rapport est facultatif, mais il est utile si vous documentez le processus d’installation.

    
    </div>

4.  **Install-CsDatabase – DatabasePaths** peut utiliser jusqu’à six paramètres de chemin d’accès, chacun définissant les chemins d’accès pour les lecteurs tels qu’ils sont définis dans les données SQL Server et l’emplacement des fichiers journaux. Conformément aux règles logiques de la configuration de la base de données dans Lync Server 2013, les lecteurs sont analysés en compartiments de deux, quatre ou six. En fonction de votre configuration SQL Server et du nombre de compartiments, vous fournissez deux chemins d’accès, quatre chemins d’accès ou six chemins.
    
    Si vous avez trois lecteurs, le journal est prioritaire et les fichiers de données sont distribués après. Exemple pour un serveur SQL Server configuré sur six lecteurs :
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  À l’issue de l’installation de la base de données, vous pouvez fermer Lync Server 2013 Management Shell ou procéder à l’installation des bases de données configurées Lync Server 2013 définies dans le générateur de topologie.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Pour utiliser des cmdlets Windows PowerShell pour configurer la base de données configurée de topologie SQL Server

1.  Pour installer les bases de données configurées du générateur de topologie pour Lync Server 2013, l’administrateur 2013 du serveur Lync doit publier la topologie. Pour plus d’informations, reportez-vous à la rubrique [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation de déploiement.

2.  Sur n’importe quel ordinateur, connectez-vous avec des informations d’identification d’administrateur pour créer les bases de données sur le serveur SQL Server. Voir la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Pour être en mesure de configurer les bases de données SQL Server, assurez-vous que le compte d’administrateur SQL Server utilisé pour exécuter les étapes décrites ci-après est également membre du groupe sysadmins (ou équivalent) sur le serveur exécutant SQL Server et disposant de la gestion centrale Rôle du serveur. C’est particulièrement important de rechercher d’autres pools Lync Server 2013 qui nécessitent une installation ou une configuration de la base de données SQL Server. Par exemple, si vous déployez un deuxième pool (pool02), mais que le rôle serveur central de gestion est maintenu par pool01. Le groupe SQL Server sysadmin (ou équivalent) doit avoir des autorisations sur les bases de données SQL Server.

    
    </div>

3.  Ouvrez Lync Server 2013 Management Shell, s’il n’est pas déjà ouvert.

4.  Utilisez l’applet de cmdlet **install-CsDatabase** pour installer les bases de données configurées du générateur de topologie.
    
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
    > Le paramètre de rapport est facultatif, mais il est utile si vous documentez le processus d’installation.

    
    </div>

5.  À la fin de l’installation de la base de données, fermez Lync Server 2013 Management Shell.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Pour utiliser des cmdlets Windows PowerShell pour configurer la topologie SQL Server à l’aide du paramètre DatabasePathMap

1.  Pour installer des bases de données pour Lync Server 2013, l’administrateur du serveur Lync doit créer les chemins d’accès et déployer les fichiers de base de données et les fichiers journaux en fonction d’un ensemble de règles prédéfini.

2.  Sur n’importe quel ordinateur, connectez-vous avec des informations d’identification d’administrateur pour créer les bases de données sur le serveur SQL Server. Voir la rubrique [autorisations de déploiement pour SQL Server dans Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Pour être en mesure de configurer les bases de données SQL Server, assurez-vous que le compte d’administrateur SQL Server utilisé pour exécuter les étapes décrites ci-après est également membre du groupe sysadmins (ou équivalent) sur le serveur exécutant SQL Server et disposant de la gestion centrale Rôle du serveur. C’est particulièrement important de rechercher d’autres pools de serveurs Lync qui nécessitent l’installation ou la configuration de la base de données SQL Server. Par exemple, si vous déployez un deuxième pool (pool02), mais que le rôle serveur central de gestion est maintenu par pool01. Le groupe SQL Server sysadmin (ou équivalent) doit avoir des autorisations sur les bases de données SQL Server.

    
    </div>

3.  Ouvrez Lync Server Management Shell, s’il n’est pas déjà ouvert.

4.  Utilisez l’applet de passe **install-CsDatabase** avec le paramètre DatabasePathMap et une table de hachage PowerShell pour installer les bases de données configurées du générateur de topologie.

5.  Dans l’exemple de code, les chemins d’accès définis pour les bases de données peuvent être déterminés de façon granulaire en utilisant le paramètre – DatabasePathMap et une table de hachage définie comme suit (l’exemple\\utilise « c : CSData » pour tous les fichiers de base de données (\\. mdf) et « c : CSLogFiles » pour tous les fichiers du journal (. ldf). Le dossier sera créé selon les besoins par l’installation-CsDatabase) :
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
6.  Dans la mesure où les fichiers de base de données et les fichiers journaux sont explicitement nommés avec leur emplacement sur le serveur de base de données de destination, vous pouvez définir des emplacements spécifiques pour la base de données et l’emplacement du journal de chaque type de service. L’exemple ci-dessous place les bases de données pour chaque type de service spécifique sur des disques distincts et les fichiers journaux associés sur un autre. Par exemple :
    
      - Toutes les bases de données RTC en «\\D : RTCDatabase »
    
      - Tous les fichiers journaux RTC comme suit :\\« E : RTCLogs »
    
      - Toutes les bases de données du Windows Store en\\"F : CPSDatabases"
    
      - Toutes les journaux de l’application Store sur\\« G : CPSLogs »
    
      - Toutes les bases de données du magasin de Response Group\\en « H : RGSDatabases »
    
      - Tous les journaux du magasin de réponse à «\\I : RGSLogs »
    
      - Toutes les bases de données du magasin d’adresses en\\« J : ABSDatabases »
    
      - Tous les fichiers journaux du magasin d’adresses en «\\K : ABSLogs »
    
      - Toutes les bases de données de l’archivage du\\magasin sur « L : ArchivingDatabases »
    
      - Tous les journaux d’archivage de la boutique\\sur « M : ArchivingLogs »
    
      - Toutes les bases de données de magasin de l'\\analyse sur « N : MonitoringDatabases »
    
      - Toutes les analyses des fichiers journaux du magasin dans\\« O : MonitoringLogfiles »
    
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
    
    À l’aide du paramètre-DatabasePathMap, vous pouvez définir toute combinaison de mappage de lettre de lecteur logique qui fournit la solution la plus adaptée à vos besoins en matière de performances et de placement SQL Server.

Si vous configurez les fichiers de données et les fichiers journaux de votre base de données à l’aide de la méthode **DatabasePathMap** , vous devrez apporter une légère modification à votre processus normal lors de l’utilisation du générateur de topologie. En règle générale, vous devez définir vos choix de topologie, publier la topologie et choisir de déployer les sélections de la base de données.

Si vous avez déjà utilisé **DatabasePathMap** , vous avez déjà effectué la troisième partie du processus du générateur de topologie. Dans le cas où il est nécessaire de disposer d’un serveur de base de données complètement configuré avant d’exécuter le générateur de topologie, vous devez toujours définir tous les rôles et options de votre serveur, mais désélectionner l’option de création des bases de données.

</div>

</div>

<span> </span>

</div>

</div>

</div>

