---
title: Exclusions de l’analyse antivirus pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Vue d’ensemble de l’interopérabilité avec le scanner antivirus avec Skype entreprise Server.
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296972"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Exclusions de l’analyse antivirus pour Skype entreprise Server

Vue d’ensemble de l’interopérabilité avec le scanner antivirus avec Skype entreprise Server.

Cet article contient des recommandations susceptibles de permettre à un administrateur de déterminer la cause d’une instabilité éventuelle sur un ordinateur exécutant une version prise en charge de Microsoft Windows lorsqu’il est utilisé avec un logiciel antivirus dans un domaine Active Directory environnement ou dans un environnement d’entreprise géré.

Nous vous recommandons d’appliquer provisoirement ces procédures pour évaluer un système. Si les recommandations contenues dans cet article vous aideront à améliorer les performances ou la stabilité du système, contactez le fabricant de votre logiciel antivirus pour obtenir des instructions ou une version mise à jour du logiciel antivirus.

Cet article contient des informations pour vous aider à réduire les paramètres de sécurité ou pour désactiver temporairement les fonctionnalités de sécurité sur un ordinateur. Vous pouvez apporter ces modifications afin de comprendre la nature d’un problème spécifique. Avant de procéder à ces modifications, nous vous recommandons d’évaluer les risques associés à l’implémentation de cette solution de contournement dans votre environnement particulier. Si vous implémentez cette solution de contournement, prenez toutes les mesures supplémentaires appropriées pour protéger l’ordinateur des fichiers qui ne sont plus analysés par votre logiciel antivirus.

Pour vous assurer que le scanner antivirus n’interagit pas avec le fonctionnement de Skype entreprise Server, vous devez exclure des processus spécifiques et des annuaires pour chaque rôle serveur ou serveur Skype entreprise Server sur lequel vous exécutez un scanneur antivirus. Vous devez exclure les processus et les répertoires suivants :

> [!NOTE]
> Dossiers et emplacements de fichiers indiqués ci-dessous sont les emplacements par défaut de Skype entreprise Server. Pour les emplacements pour lesquels vous n’avez pas utilisé la valeur par défaut, excluez les emplacements spécifiés pour votre organisation au lieu des emplacements par défaut spécifiés dans cette rubrique.

> [!IMPORTANT]
> Notez que certains programmes antivirus peuvent avoir besoin de chemins d’accès absolus, non relatifs, pour leur liste d’exclusions.

- Processus du serveur Skype entreprise:

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
  
  - LyncBackupService. exe

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
    > Notez que ces chemins sont spécifiques à la version de Skype entreprise Server.

  - %programfiles%\Skype Entreprise Server 2015

  - %programfiles%\Common Files\Skype Entreprise Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype Entreprise Server 2015

  - %programfiles%\Common Files\Skype Entreprise Online

  - %SystemDrive%\RtcReplicaRoot

  - Magasin de partage de fichiers (spécifié dans le générateur de topologies). Les magasins de fichiers sont spécifiés dans le générateur de topologies.

  - Fichiers journaux et de données SQL Server, dont ceux pour la base de données principale, le magasin d’utilisateurs, le magasin d’archivage, le magasin de surveillance et le magasin d’applications. Les fichiers journaux et de base de données peuvent être spécifiés dans le générateur de topologies. Pour plus d’informations sur les fichiers journaux et de données pour chaque base de données, dont les noms par défaut, reportez-vous à la rubrique [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation relative au déploiement.

  - Les fichiers de données et les fichiers journaux de SQL Server, y compris ceux de la base de données frontale, Skype entreprise Store et RtcDatabase Store. Ils se trouvent normalement sous %localdrive%\CSData.


