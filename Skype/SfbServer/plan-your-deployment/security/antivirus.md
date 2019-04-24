---
title: Antivirus exclusions d’analyse pour Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Vue d’ensemble de l’interopérabilité de scanneur antivirus avec Skype pour Business Server.
ms.openlocfilehash: 377c9e8fb9de71187978fe541a23f43cc2282749
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213668"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Antivirus exclusions d’analyse pour Skype pour Business Server

Vue d’ensemble de l’interopérabilité de scanneur antivirus avec Skype pour Business Server.

Cet article contient des recommandations qui peuvent aider à un administrateur de déterminer la cause de l’instabilité potentielle sur un ordinateur qui exécute une version prise en charge de Microsoft Windows lorsqu’il est utilisé avec un logiciel antivirus dans un domaine Active Directory environnement ou dans un environnement professionnel géré.

Nous vous recommandons d’appliquer temporairement ces procédures pour évaluer un système. Si vos performances du système ou la stabilité est améliorée par les recommandations effectuées dans cet article, contactez votre fournisseur d’antivirus pour obtenir des instructions ou une version mise à jour du logiciel antiviru.

Cet article contient des informations indiquant comment les paramètres de sécurité inférieur ou désactiver temporairement les fonctionnalités de sécurité sur un ordinateur. Vous pouvez apporter ces modifications pour comprendre la nature d’un problème spécifique. Avant d’apporter ces modifications, nous vous recommandons d’évaluer les risques qui sont associés à l’implémentation de cette solution de contournement dans votre environnement. Si vous implémentez cette solution de contournement, prendre toutes les mesures appropriées pour protéger les fichiers qui ne sont plus en cours d’analyse par un logiciel antivirus sur l’ordinateur.

Pour vous assurer que le scanneur antivirus n’interfère pas avec l’opération de Skype pour Business Server, vous devez exclure des répertoires et les processus spécifiques pour chaque Skype pour serveur Business Server ou rôle de serveur sur lequel vous exécutez un logiciel antivirus. Vous devez exclure les processus et les répertoires suivants :

> [!NOTE]
> Les emplacements de fichiers et de dossier répertoriées ci-dessous sont les emplacements par défaut pour Skype pour Business Server. Pour les emplacements pour lesquels vous n’avez pas utilisé la valeur par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut spécifiés dans cette rubrique.

> [!IMPORTANT]
> Notez que certains programmes antivirus peuvent avoir besoin de chemins d’accès absolus, non relatifs, pour leur liste d’exclusions.

- Skype pour les processus Business Server :

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

- Processus du service d’hôte Windows Fabric :

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- Processus d’IIS :

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

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

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Notez que ces chemins d’accès sont spécifiques à Skype pour la version du serveur d’entreprise.

  - %programfiles%\Skype Entreprise Server 2015

  - %programfiles%\Common Files\Skype Entreprise Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype Entreprise Server 2015

  - %programfiles%\Common Files\Skype Entreprise Online

  - %SystemDrive%\RtcReplicaRoot

  - Magasin de partage de fichiers (spécifié dans le générateur de topologies). Les magasins de fichiers sont spécifiés dans le générateur de topologies.

  - Fichiers journaux et de données SQL Server, dont ceux pour la base de données principale, le magasin d’utilisateurs, le magasin d’archivage, le magasin de surveillance et le magasin d’applications. Les fichiers journaux et de base de données peuvent être spécifiés dans le générateur de topologies. Pour plus d’informations sur les fichiers journaux et de données pour chaque base de données, dont les noms par défaut, reportez-vous à la rubrique [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation relative au déploiement.

  - SQL Server données et fichiers journaux, y compris ceux de la base de données frontal Skype pour le magasin Business et magasin RtcDatabase. Ils se trouvent normalement sous %localdrive%\CSData.


