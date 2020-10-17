---
title: 'Lync Server 2013 : exclusions d’analyse antivirus'
description: 'Lync Server 2013 : exclusions de l’analyse antivirus.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561910"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Exclusions d’analyse antivirus pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-11-02_

Pour vous assurer que le scanneur antivirus n’interfère pas avec le fonctionnement de Lync Server 2013, vous devez exclure des processus et des répertoires spécifiques pour chaque rôle serveur ou serveur Lync Server 2013 sur lequel vous exécutez un scanneur antivirus. Les répertoires et processus suivants doivent être exclus :

<div>


> [!NOTE]  
> Emplacements de fichiers et de dossiers répertoriés ci-dessous sont les emplacements par défaut pour Lync Server 2013. Pour tout emplacement pour lequel vous n’avez pas utilisé le paramètre par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut mentionnés dans cette rubrique.



</div>

<div>


> [!IMPORTANT]  
> Notez que certains programmes antivirus peuvent nécessiter des chemins d’accès absolus, non relatifs, pour leur liste d’exclusion.



</div>

  - Processus Lync Server 2013 :
    
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

  - Processus du service d’hôte de fabric Windows :
    
      - Fabric.exe
    
      - FabricDCA.exe
    
      - FabricHost.exe

  - Processus IIS :
    
      - % systemroot% \\ system32 \\ inetsrv \\w3wp.exe
    
      - % systemroot% \\ SysWOW64 \\ inetsrv \\w3wp.exe

  - Processus de Back-End SQL Server :
    
      - % ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11.SQLServr.exe de MSSQLSERVER \\ MSSQL \\ \\
    
      - % ProgramFiles% \\ Microsoft SQL Server \\ MSRS11.ReportingServicesService.exe bin de l’outil MSSQLSERVER \\ Reporting Services \\ \\ \\
    
      - % ProgramFiles% \\ Microsoft SQL Server \\ MSAS11.MSMDSrv.exe de la \\ Corbeille OLAP de MSSQLSERVER \\ \\

  - Processus de Front-End SQL Server :
    
      - % ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. \\SQLServr.exe MSSQL \\ Binn \\ LYNCLOCAL
    
      - % ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. \\SQLServr.exe MSSQL \\ Binn \\ RTCLOCAL

  - Répertoires et fichiers :
    
      - % systemroot% \\ system32 \\ LogFiles
    
      - % systemroot% \\ SysWOW64 \\ LogFiles
    
      - % systemroot% \\ Microsoft.NET \\ \\ GAC GAC \_
    
      - % ProgramFiles% \\ Microsoft Lync Server 2013
    
      - % ProgramFiles% de \\ fichiers communs le \\ \\ nœud observateur Microsoft Lync Server 2013
    
      - \\fichiers communs% ProgramFiles% \\ Microsoft Lync Server 2013
    
      - % SystemDrive% \\ RtcReplicaRoot
    
      - Magasin de partages de fichiers (spécifié dans le Générateur de topologies). Les magasins de fichiers sont spécifiés dans le Générateur de topologies.
    
      - Données et fichiers journaux de SQL server, y compris ceux de la base de données principale, magasin utilisateur, magasin d’archivage, magasin de surveillance et magasin d’applications. Les fichiers journaux et de base de données peuvent être spécifiés dans le Générateur de topologies. Pour plus d’informations sur les données et les fichiers journaux de chaque base de données, y compris les noms par défaut, voir [SQL Server Data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) dans la documentation de déploiement.
    
      - Les fichiers de données et les fichiers journaux SQL Server, y compris ceux de la base de données frontale, Lync Store et RtcDatabase Store. Ils sont normalement sous% Lecteur_Local% \\ CSData.

</div>

<span> </span>

</div>

</div>

</div>

