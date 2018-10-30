---
title: "Lync Server 2013 : Inst. base de données avec Lync Server Management Shell"
TOCTitle: Installation de la base de données avec Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398832(v=OCS.15)
ms:contentKeyID: 49298843
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation de la base de données avec Lync Server Management Shell dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

La séparation des rôles et des responsabilités entre les administrateurs de serveur et les administrateurs SQL Server peut entraîner des retards d’implémentation. Lync Server 2013 utilise le contrôle d’accès basé sur un rôle (RBAC) pour remédier à ces difficultés. Dans certains cas, l’administrateur SQL Server doit gérer l’installation des bases de données sur le serveur SQL Server externe au contrôle d’accès basé sur un rôle. Lync Server 2013 Management Shell permet à l’administrateur SQL Server d’exécuter des applets de commande Windows PowerShell conçues pour configurer les bases de données avec les fichiers de données et fichiers journaux appropriés. Pour plus d’informations, reportez-vous à [Autorisations de déploiement de SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

> [!IMPORTANT]  
> La procédure suivante suppose que OCSCore.msi de Lync Server 2013, SQL Server Native Client (sqlncli.msi), Microsoft SQL Server 2012 Management Objects, les types CLR pour Microsoft SQL Server 2012 et Microsoft SQL Server 2012 ADOMD.NET sont installés. Le fichier OCSCore.msi se trouve sur le support d’installation dans le répertoire \Setup\AMD64\Setup. Les autres composants sont situés dans \Setup\amd64. En outre, la préparation d’Active Directory pour Lync Server 2013 doit avoir été exécutée avec succès.

**Install-CsDatabase** est l’applet de commande Windows PowerShell qui permet d’installer les bases de données. L’applet de commande **Install-CsDatabase** inclut de nombreux paramètres dont quelques-uns seulement sont décrits ici. Pour plus d’informations sur ces paramètres, reportez-vous à la documentation de Lync Server 2013 Management Shell.

> [!WARNING]  
> Pour éviter la survenue de problèmes de performances ou de délais, n’oubliez pas d’utiliser des noms de domaine complets lorsque vous désignez des serveurs SQL Server. Évitez d’utiliser uniquement des noms d’hôte. Par exemple, utilisez sqlbe01.contoso.net plutôt que SQLBE01.

Pour installer les bases de données, **Install-CsDatabase** fait appel à trois méthodes principales pour placer les bases de données sur le serveur SQL Server préparé :

  - Exécutez **Install-CsDatabase** sans DatabasePaths ou UseDefaultSqlPath. Cette applet de commande utilise un algorithme intégré pour déterminer le meilleur emplacement des fichiers de données et des fichiers journaux. L’algorithme ne fonctionne qu’avec des implémentations SQL Server autonomes.

  - Exécutez **Install-CsDatabase** sans le paramètre DatabasePaths. L’algorithme intégré pour optimiser les emplacements des fichiers de données et des fichiers journaux n’est pas employé si le paramètre DatabasePaths est défini. Ce paramètre vous permet de définir les emplacements où seront déployés les fichiers de données et les fichiers journaux.

  - Exécutez **Install-CsDatabase** avec UseDefaultSqlPaths. Cette option ne fait pas appel à l’algorithme intégré pour optimiser les emplacements des fichiers de données et des fichiers journaux. Ceux-ci sont déployés conformément aux paramètres par défaut définis par l’administrateur SQL Server. Ces chemins d’accès sont généralement définis pour permettre la gestion automatique anticipée des fichiers de données et des fichiers journaux sur SQL Server ; ils ne sont pas associés à l’installation de Lync Server 2013.

  - Le paramètre DatabasePathMap permet également de spécifier de manière explicite un emplacement pour chaque base de données et son fichier journal respectif.

## Pour utiliser des applets de commande Windows PowerShell pour configurer le magasin central de gestion SQL Server

1.  Ouvrez une session d’administration sur un ordinateur pour créer les bases de données sur le serveur SQL Server. Pour plus d’informations, reportez-vous à [Autorisations de déploiement de SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Ouvrez Lync Server 2013 Management Shell. Si vous n’avez pas modifié la stratégie d’exécution pour Windows PowerShell, faites-le pour autoriser l’exécution des scripts Windows PowerShell. Pour plus d’informations, reportez-vous à « Examen de la stratégie d’exécution » à la page <http://go.microsoft.com/fwlink/?linkid=203093>.

3.  Utilisez l’applet de commande **Install-CsDatabase** pour installer le magasin central de gestion.
    
    ```
    Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
    -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
    -Report <path to report file>
    ```
    ```
    Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
    ```

    > [!TIP]  
    > Le paramètre Report est facultatif, mais peut être utile si vous documentez le processus d’installation.

4.  **Install-CsDatabase –DatabasePaths** peut utiliser jusqu’à six paramètres de chemin d’accès, chacun définissant les chemins d’accès aux lecteurs tels que définis dans l’emplacement des fichiers de données et fichiers journaux SQL Server. Conformément aux règles logiques de la configuration des bases de données de Lync Server 2013, les lecteurs sont analysés dans des compartiments de deux, quatre ou six. Selon votre configuration SQL Server et le nombre de compartiments, vous indiquerez deux, quatre ou six chemins d’accès.
    
    Si vous disposez de trois lecteurs, le journal devient prioritaire et les fichiers de données sont distribués après. Voici un exemple pour un serveur SQL Server configuré avec six lecteurs :
    
        Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"

5.  Lorsque la base de données est installée, vous pouvez fermer Lync Server 2013 Management Shell ou lancer l’installation des bases de données configurées de Lync Server 2013 définies dans le Générateur de topologie.

## Pour utiliser les applets de commande Windows PowerShell et configurer les bases de données configurées de la topologie SQL Server

1.  Pour installer les bases de données configurées du Générateur de topologie pour Lync Server 2013, l’administrateur Lync Server 2013 doit publier la topologie. Pour plus d’informations, reportez-vous à [Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md) dans la documentation de déploiement.

2.  Ouvrez une session d’administration sur un ordinateur pour créer les bases de données sur le serveur SQL Server. Reportez-vous à la rubrique [Autorisations de déploiement de SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    > [!IMPORTANT]  
    > Pour pouvoir configurer les bases de données SQL Server, assurez-vous que le compte d’administrateur SQL Server utilisé pour exécuter les étapes décrites ici est également membre du groupe sysadmins (ou équivalent) sur le serveur exécutant SQL Server et détenant le rôle de serveur de gestion centralisée. Cela est particulièrement important pour vérifier la présence de pools Lync Server 2013 supplémentaires qui nécessiteraient l’installation ou la configuration d’une base de données SQL Server. Par exemple, si vous déployez un deuxième pool (pool02) mais que le rôle de serveur de gestion centralisée est détenu par pool01, le groupe sysadmins SQL Server (ou équivalent) doit bénéficier d’autorisations sur les deux bases de données SQL Server.

3.  Ouvrez Lync Server 2013 Management Shell, si vous ne l’avez pas encore fait.

4.  Utilisez l’applet de commande **Install-CsDatabase** pour installer les bases de données configurées avec le Générateur de topologie.
    
    ```
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
     -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
    ```
    ```
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
    -Report "C:\Logs\InstallDatabases.html"
    ```
    
    > [!TIP]  
    > Le paramètre Report est facultatif, mais peut être utile si vous documentez le processus d’installation.

5.  Lorsque la base de données est installée, fermez Lync Server 2013 Management Shell.

## Pour utiliser les applets de commande Windows PowerShell et configurer la topologie SQL Server à l’aide du paramètre DatabasePathMap

1.  Pour installer les bases de données pour Lync Server 2013, l’administrateur Lync Server doit créer les chemins d’accès et déployer les fichiers de base de données et les fichiers journaux selon un ensemble prédéfini de règles.

2.  Ouvrez une session d’administration sur un ordinateur pour créer les bases de données sur le serveur SQL Server. Reportez-vous à la rubrique [Autorisations de déploiement de SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    > [!IMPORTANT]  
    > Pour pouvoir configurer les bases de données SQL Server, assurez-vous que le compte d’administrateur SQL Server utilisé pour exécuter les étapes décrites ici est également membre du groupe sysadmins (ou équivalent) sur le serveur exécutant SQL Server et détenant le rôle de serveur de gestion centralisée. Cela est particulièrement important pour vérifier la présence de pools Lync Server supplémentaires qui nécessiteraient l’installation ou la configuration d’une base de données SQL Server. Par exemple, si vous déployez un deuxième pool (pool02) mais que le rôle de serveur de gestion centralisée est détenu par pool01, le groupe sysadmins SQL Server (ou équivalent) doit bénéficier d’autorisations sur les deux bases de données SQL Server.

3.  Le cas échéant, ouvrez Lync Server Management Shell.

4.  Utilisez l’applet de commande **Install-CsDatabase** avec le paramètre DatabasePathMap et une table de hachage PowerShell pour installer les bases de données configurées par le Générateur de topologie.

5.  Dans l’exemple de code, les chemins d’accès définis pour les bases de données peuvent être déterminés de manière granulaire à l’aide du paramètre –DatabasePathsMap et d’une table de hachage définie comme suit (l’exemple utilise « C:\\CSData » pour les fichiers de base de données (.mdf), et « C:\\CSLogFiles » pour les fichiers journaux (.ldf). Le dossier sera éventuellement créé par Install-CsDatabase) :
    
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
        Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathsMap $pathmap

6.  Comme les fichiers de base de données et les fichiers journaux sont nommés de manière explicite avec leur emplacement sur le serveur de base de données de destination, vous pouvez définir des emplacements spécifiques pour la base de données réelle de chaque type de service et l’emplacement des fichiers journaux. L’exemple suivant place les bases de données pour chaque type de service spécifique sur des disques distincts, et les fichiers journaux associés sur un autre. Par exemple :
    
      - toutes les bases de données RTC dans « D:\\RTCDatabase » ;
    
      - tous les fichiers journaux RTC dans « E:\\RTCLogs » ;
    
      - toutes les bases de données de magasin d’application dans « F:\\CPSDatabases » ;
    
      - tous les fichiers journaux de magasin d’application dans « G:\\CPSLogs » ;
    
      - toutes les bases de données de magasin Response Group dans « H:\\RGSDatabases » ;
    
      - tous les fichiers journaux de magasin Response Group dans « I:\\RGSLogs » ;
    
      - toutes les bases de données de magasin de carnet d’adresses dans « J:\\ABSDatabases » ;
    
      - tous les fichiers journaux de magasin de carnet d’adresses dans « K:\\ABSLogs » ;
    
      - toutes les bases de données de magasin d’archivage dans « L:\\ArchivingDatabases » ;
    
      - tous les fichiers journaux de magasin d’archivage dans « M:\\ArchivingLogs » ;
    
      - toutes les bases de données de magasin de surveillance dans « N:\\MonitoringDatabases » ;
    
      - tous les fichiers journaux de magasin de surveillance dans « O:\\MonitoringLogfiles ».
    
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
    
    Le paramètre –DatabasePathMap vous permet de définir une combinaison de mappage de lettres de disque logique adaptée à vos besoins de performance et de positionnement SQL Server.

Si vous configurez vos fichiers de base de données et fichiers journaux à l’aide de la méthode **DatabasePathMap**, vous devez apporter une légère modification à votre processus normal lors de l’utilisation du Générateur de topologie. Vous devez définir vos choix de topologie, publier la topologie et choisir de déployer les sélections de base de données.

Si vous avez utilisé **DatabasePathMap**, vous avez déjà accompli la troisième partie du processus du Générateur de topologie. Si vous avez un serveur de base de données complètement configuré avant l’exécution du Générateur de topologie, vous devez toujours définir vos rôles et options de serveur, mais désactiver l’option de création des bases de données.

