---
title: 'Lync Server 2013 : Configuration technique requise pour l’archivage'
TOCTitle: Configuration technique requise pour l’archivage
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205059(v=OCS.15)
ms:contentKeyID: 49297984
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration technique requise pour l’archivage dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

La configuration technique de Lync Server 2013 comprend les éléments suivants :

  - Conditions requises pour l’infrastructure.

  - Logiciels prérequis à installer pour l’archivage.

  - Configuration requise pour le stockage des données pour l’archivage.

  - Conditions requises et éléments à prendre en compte concernant la mise à l’échelle pour le déploiement de l’archivage.

  - Conditions requises et éléments à prendre en compte concernant les performances pour les bases de données d’archivage.

> [!NOTE]  
> Les informations relatives à la mise à l’échelle et aux performances ne sont pas disponibles dans ces versions de Lync Server 2013.

## Conditions requises pour l’infrastructure

Les conditions requises en matière d’infrastructure de l’archivage Lync Server 2013 sont identiques à celles du déploiement de Lync Server 2013. Pour plus d’informations, reportez-vous à [Définition de la configuration requise pour l’infrastructure pour Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) dans la documentation de planification.

## Conditions requises pour l’archivage

Lync Server 2013 simplifie les conditions requises pour l’archivage, en raison des éléments suivants :

  - Le serveur d’archivage n’est plus un rôle serveur. À la place, les agents de collecte de données unifiées s’exécutent sur les serveurs frontaux dans un pool et les serveurs Standard Edition pour capturer les données pour l’archivage afin de ne pas avoir à configurer des plateformes système distinctes pour l’archivage.

  - L’archivage utilise le stockage de fichiers Lync Server 2013 pour le stockage temporaire des fichiers de contenu de réunion, vous n’avez donc pas besoin de configurer un magasin de fichiers distinct pour l’archivage.

  - Dans Lync Server 2013, Message Queuing n’est pas requis.

## Configuration requise pour le stockage des données pour l’archivage

Vous devez en plus configurer l’infrastructure pour le stockage de l’archivage. Cela comprend le ou les éléments suivants :

  - **Stockage Microsoft Exchange**. Les fichiers de contenu de réunion, par exemple, les présentations PowerPoint, sont archivés sous forme de pièces jointes. Pour utiliser l’intégration Microsoft Exchange afin de stocker les données d’archives Lync avec les données de conformité Exchange, vous devez employer Exchange 2013 pour votre déploiement Exchange et veiller à ce que la taille maximale de stockage prenne en charge le stockage des fichiers de contenu de réunion. Si vous déployez l’archivage à l’aide de l’option d’intégration Microsoft Exchange, les données d’archives Lync sont stockées avec les données de conformité Exchange 2013 uniquement pour les utilisateurs hébergés sur vos serveurs Exchange 2013. Vou devez déployer Exchange 2013 avant de déployer et d’activer l’archivage avec l’option d’intégration Microsoft Exchange. Si vous choisissez d’utiliser le stockage Exchange 2013, vous n’avez pas besoin de déployer des bases de données SQL Server distinctes pour l’archivage, sauf si des utilisateurs Lync ne sont pas hébergés sur vos serveurs Exchange 2013.

  - Stockage de base de données **SQL Server pour l’archivage**. Pour prendre en charge les utilisateurs qui ne sont pas hébergés sur des serveurs Exchange 2013 ou si vous ne voulez pas utiliser l’option d’intégration Microsoft Exchange, vous devez déployer le stockage de l’archivage à l’aide d’une base de données SQL Server. Lync Server 2013 prend en charge les versions 64 bits suivantes de SQL Server :
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    
    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express et Microsoft SQL Server 2012 Express ne sont pas pris en charge pour l’archivage. Les versions 32 bits de SQL Server ne sont pas prises en charge. Pour plus d’informations sur les exigences et les restrictions SQL Server, reportez-vous à <a href="lync-server-2013-database-software-support.md">Prise en charge du logiciel de base de données dans Lync Server 2013</a> dans la documentation de planification ou dans la documentation de prise en charge.
     
    Vous devez d’abord configurer les plateformes SQL Server avant de déployer et d’activer l’archivage. Si le compte à utiliser pour la publication de la topologie est doté des droits et autorisations d’administrateur appropriées, vous pouvez créer la base de données d’archivage (LcsLog) lorsque vous publiez votre topologie. Vous pouvez également créer la base de données plus tard, y compris dans le cadre de la procédure d’installation. Pour plus d’informations sur SQL Server, reportez-vous au site TechCenter SQL Server à l’adresse [http://go.microsoft.com/fwlink/?linkid=129045\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=129045%26clcid=0x40c).

