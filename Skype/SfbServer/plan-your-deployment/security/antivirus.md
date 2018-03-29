---
title: Exclusions de l’analyse antivirus pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Vue d’ensemble de l’interopérabilité de moteur d’analyse antivirus avec Skype pour Business Server 2015.
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a>Exclusions de l’analyse antivirus pour Skype Entreprise Server 2015
 
Vue d’ensemble de l’interopérabilité de moteur d’analyse antivirus avec Skype pour Business Server 2015. 
  
Pour vous assurer que le moteur d’analyse antiviru n’interfère pas avec l’opération de Skype pour Business Server 2015, vous devez exclure les processus spécifiques et des répertoires pour chaque Skype pour Business Server 2015 serveur ou du rôle de serveur sur lequel vous exécutez un logiciel antivirus. Vous devez exclure les processus et les répertoires suivants :
  
> [!NOTE]
> Les emplacements de dossiers et de fichiers répertoriés ci-dessous sont les emplacements par défaut pour Skype pour Business Server 2015. Pour les emplacements pour lesquels vous n’avez pas utilisé la valeur par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut spécifiés dans cette rubrique. 
  
> [!IMPORTANT]
> Notez que certains programmes antivirus peuvent avoir besoin de chemins d’accès absolus, non relatifs, pour leur liste d’exclusions. 
  
- Skype pour les processus d’entreprise serveur 2015 :
    
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
    
  - %SystemRoot%\system32\inetsrv\w3wp.exe
    
  - %SystemRoot%\SysWOW64\inetsrv\w3wp.exe
    
- Processus du serveur dorsal SQL Server :
    
    > [!NOTE]
    > Notez que ces chemins d’accès sont spécifiques à la version de SQL Server. 
  
  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe
    
- Processus du serveur SQL Server frontal :
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - Instance RTC de l’installation de Standard Edition 
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe
    
- Répertoires et fichiers :
    
  - %systemroot%\System32\LogFiles
    
  - %SystemRoot%\SysWow64\LogFiles
    
  - %SystemRoot%\Microsoft.NET\assembly\GAC_MSIL
    
  - %programfiles%\Skype Entreprise Server 2015
    
  - %programfiles%\Common Files\Skype Entreprise Server 2015\Watcher Node
    
  - %programfiles%\Common Files\Skype Entreprise Server 2015
    
  - %programfiles%\Common Files\Skype Entreprise Online
    
  - %SystemDrive%\RtcReplicaRoot
    
  - Magasin de partage de fichiers (spécifié dans le générateur de topologies). Les magasins de fichiers sont spécifiés dans le générateur de topologies.
    
  - Fichiers journaux et de données SQL Server, dont ceux pour la base de données principale, le magasin d’utilisateurs, le magasin d’archivage, le magasin de surveillance et le magasin d’applications. Les fichiers journaux et de base de données peuvent être spécifiés dans le générateur de topologies. Pour plus d’informations sur les fichiers journaux et de données pour chaque base de données, y compris les noms par défaut, reportez-vous à la section [Placement des fichiers journaux et données de SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation de déploiement.
    
  - SQL Server données et fichiers journaux, y compris ceux de la base de données frontale, Skype pour entreprise banque et banque de RtcDatabase. Ils se trouvent normalement sous %localdrive%\CSData.
    

