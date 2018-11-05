---
title: 'Lync Server 2013 : exclusions de l’analyse antivirus'
TOCTitle: Exclusions de l’analyse antivirus pour Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn440138(v=OCS.15)
ms:contentKeyID: 59602873
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exclusions de l’analyse antivirus pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-11-02_

Afin de vous assurer que le scanner antivirus n'interfère pas avec le fonctionnement de Lync Server 2013, vous devez exclure les processus et répertoires spécifiques de chaque serveur ou rôle serveur Lync Server 2013 sur lesquels vous exécutez le scanner antivirus. Les processus et répertoires suivants doivent être exclus :

> [!NOTE]  
> Les emplacements de dossiers et de fichiers répertoriés ci-dessous sont les emplacements par défaut pour Lync Server 2013. Pour les emplacements pour lesquels vous n'avez pas utilisé celui défini par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut indiqués dans cette rubrique.

  - Processus Lync Server 2013 :
    
      - ABServer.exe
    
      - AcpMcuSvc.exe
    
      - ASMCUSvc.exe
    
      - AVMCUSvc.exe
    
      - ChannelService.exe
    
      - ClsAgent.exe
    
      - ComplianceService.exe
    
      - DataMCUSvc.exe
    
      - DataProxy.exe
    
      - FileTransferAgent.exe
    
      - IMMCUSvc.exe
    
      - LysSvc.exe
    
      - MasterReplicatorAgent.exe
    
      - MediaRelaySvc.exe
    
      - MediationServerSvc.exe
    
      - MRASSvc.exe
    
      - OcsAppServerHost.exe
    
      - ReplicaReplicatorAgent.exe
    
      - ReplicationApp.exe
    
      - RtcHost.exe
    
      - RTCSrv.exe
    
      - XmppProxy.exe
    
      - XmppTGW.exe

  - Processus du service d'hôte Windows Fabric :
    
      - Fabric.exe
    
      - FabricDCA.exe
    
      - FabricHost.exe

  - Processus IIS :
    
      - %systemroot%\\system32\\inetsrv\\w3wp.exe
    
      - %systemroot%\\SysWOW64\\inetsrv\\w3wp.exe

  - Processus du serveur SQL Server principal :
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe

  - Processus du serveur SQL Server frontal :
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSMQL\\Binn\\SQLServr.exe
    
      - %ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSMQL\\Binn\\SQLServr.exe

  - Répertoires et fichiers :
    
      - %systemroot%\\System32\\LogFiles
    
      - %systemroot%\\SysWow64\\LogFiles
    
      - %systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL
    
      - %programfiles%\\Microsoft Lync Server 2013
    
      - %programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node
    
      - %programfiles%\\Common Files\\Microsoft Lync Server 2013
    
      - %SystemDrive%\\RtcReplicaRoot
    
      - Magasin de partage de fichiers (spécifié dans le générateur de topologies). Les magasins de fichiers sont indiqués dans le générateur de topologies.
    
      - Fichiers journaux et de données SQL Server, y compris ceux pour la base de données principale, le magasin d'utilisateurs, le magasin d'archivage, le magasin de surveillance et le magasin d'applications. Les fichiers journaux et de base de données peuvent être spécifiés dans le générateur de topologies. Pour plus d'informations sur les fichiers journaux et de données pour chaque base de données, y compris les noms par défaut, voir [Emplacement des fichiers journaux et des données SQL Server pour Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) dans la documentation relative au déploiement.
    
      - Fichiers journaux et de données SQL Server, y compris ceux pour la base de données frontale, le magasin Lync et le magasin RtcDatabase. Ils se trouvent normalement sous %localdrive%\\CSData.

