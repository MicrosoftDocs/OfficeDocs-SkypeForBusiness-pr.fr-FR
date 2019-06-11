---
title: 'Lync Server 2013 : exclusions de l’analyse antivirus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Exclusions de l’analyse antivirus pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-11-02_

Pour vous assurer que le scanner antivirus n’interagit pas avec le fonctionnement de Lync Server 2013, vous devez exclure les processus et répertoires spécifiques pour chaque serveur Lync Server 2013 Server ou le rôle serveur sur lequel vous exécutez un scanneur antivirus. Vous devez exclure les processus et les répertoires suivants :

<div>


> [!NOTE]  
> Emplacement des dossiers et fichiers indiqués ci-dessous sont les emplacements par défaut de Lync Server 2013. Pour les emplacements pour lesquels vous n’avez pas utilisé la valeur par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut spécifiés dans cette rubrique.



</div>

<div>


> [!IMPORTANT]  
> Notez que certains programmes antivirus peuvent avoir besoin de chemins d’accès absolus, non relatifs, pour leur liste d’exclusions.



</div>

  - Processus Lync Server 2013:
    
      - ABServer.exe
    
      - AcpMcuSvc. exe
    
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

  - Processus du service d’hôte Windows Fabric :
    
      - Fabric.exe
    
      - FabricDCA.exe
    
      - FabricHost.exe

  - Processus d’IIS :
    
      - % systemroot%\\system32\\inetsrv\\w3wp. exe
    
      - % systemroot%\\SysWOW64\\inetsrv\\w3wp. exe

  - Processus du serveur dorsal SQL Server :
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\Reporting\\services\\\\ReportServer bin ReportingServicesService. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11. Emplacement\\\\OLAP\\de MSSQLSERVER MSMDSrv. exe

  - Processus du serveur SQL Server frontal :
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\sqlservr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr. exe

  - Répertoires et fichiers :
    
      - % systemroot%\\system32\\LogFiles
    
      - % systemroot%\\SysWOW64\\LogFiles
    
      - code global du\\GAC\\\_de\\l’assembly% systemroot% Microsoft.net
    
      - % ProgramFiles%\\Microsoft Lync Server 2013
    
      - % ProgramFiles%\\fichiers\\communs Microsoft Lync Server 2013\\FileSystemWatcher
    
      - Fichiers\\communs%\\ProgramFiles% Microsoft Lync Server 2013
    
      - % SystemDrive%\\RtcReplicaRoot
    
      - Magasin de partage de fichiers (spécifié dans le générateur de topologies). Les magasins de fichiers sont spécifiés dans le générateur de topologies.
    
      - Fichiers journaux et de données SQL Server, dont ceux pour la base de données principale, le magasin d’utilisateurs, le magasin d’archivage, le magasin de surveillance et le magasin d’applications. Les fichiers journaux et de base de données peuvent être spécifiés dans le générateur de topologies. Pour plus d’informations sur les données et les fichiers journaux pour chaque base de données, y compris les noms par défaut, voir [données SQL Server et emplacement des fichiers journaux pour Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) dans la documentation de déploiement.
    
      - Les fichiers de données et les fichiers journaux de SQL Server, y compris ceux de la base de données frontale, du magasin Lync et du magasin RtcDatabase. Ils sont généralement sous% Lecteur_Local%\\CSData.

</div>

<span> </span>

</div>

</div>

</div>

