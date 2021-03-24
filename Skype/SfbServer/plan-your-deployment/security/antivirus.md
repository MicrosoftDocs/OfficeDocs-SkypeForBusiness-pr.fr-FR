---
title: Exclusions de l’analyse antivirus pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Vue d’ensemble de l’interopérabilité du scanneur antivirus avec Skype Entreprise Server.
ms.openlocfilehash: 64646304b98de075fd9af0a82096da8c0bff2f12
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104240"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Exclusions de l’analyse antivirus pour Skype Entreprise Server

Vue d’ensemble de l’interopérabilité du scanneur antivirus avec Skype Entreprise Server.

Pour vous assurer que le scanneur antivirus n’interfère pas avec le fonctionnement de Skype Entreprise Server, vous devez exclure des processus et des répertoires spécifiques pour chaque serveur ou rôle serveur Skype Entreprise Server sur lequel vous exécutez un scanneur antivirus. Les répertoires et processus suivants doivent être exclus :

> [!NOTE]
> Les emplacements de dossiers et de fichiers répertoriés ci-dessous sont les emplacements par défaut pour Skype Entreprise Server. Pour tout emplacement pour lequel vous n’avez pas utilisé le paramètre par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut mentionnés dans cette rubrique.

> [!IMPORTANT]
> Notez que certains programmes antivirus peuvent avoir besoin de chemins absolus, et non relatifs, pour leur liste d’exclusions.

- Processus Skype Entreprise Server :

  - ABServer.exe

  - ASMCUSvc.exe

  - AVMCUSvc.exe

  - ChannelService.exe

  - ClsAgent.exe

  - ComplianceService.exe

  - DataMCUSvc.exe

  - DataProxy.exe

  - FileTransferAgent.exe

  - HealthAgent.exe

  - IMMCUSvc.exe
  
  - LyncBackupService.exe

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

- Processus du service hôte Windows Fabric :

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- Processus IIS :

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-End processus :

    > [!NOTE]
    > Notez que ces chemins d’accès sont spécifiques SQL Server version.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End processus :

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Instance RTC d’installation Standard Edition

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Répertoires et fichiers :

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Notez que ces chemins d’accès sont spécifiques à la version de Skype Entreprise Server.

  - %programfiles%\Skype Entreprise Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype Entreprise Online

  - %SystemDrive%\RtcReplicaRoot

  - Magasin de partages de fichiers (spécifié dans le Générateur de topologies). Les magasins de fichiers sont spécifiés dans le Générateur de topologies.

  - Données et fichiers journaux de SQL server, y compris ceux de la base de données principale, magasin utilisateur, magasin d’archivage, magasin de surveillance et magasin d’applications. Les fichiers journaux et de base de données peuvent être spécifiés dans le Générateur de topologies. Pour plus de détails sur les données et fichiers journaux pour chaque base de données, y compris les noms par défaut, voir [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) dans la documentation de déploiement.

  - SQL Server données et fichiers journaux, y compris ceux de la base de données frontale, du magasin Skype Entreprise et du magasin RtcDatabase. Ils sont normalement sous %localdrive%\CSData.