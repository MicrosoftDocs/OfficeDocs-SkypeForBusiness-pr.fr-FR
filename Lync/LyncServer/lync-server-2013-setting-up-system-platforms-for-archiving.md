---
title: Configuration des plateformes système pour l’archivage
TOCTitle: Configuration des plateformes système pour l’archivage
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204768(v=OCS.15)
ms:contentKeyID: 49296735
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des plateformes système pour l’archivage

 

_**Dernière rubrique modifiée :** 2012-10-09_

Avant de commencer à déployer l’archivage, vous devez installer le système d’exploitation requis et tout autre logiciel prérequis sur du matériel conforme à la configuration requise :

  - **Plateforme Lync Server 2013** : les déploiements Lync Server 2013 ne comprennent pas de serveurs d’archivage, mais des Agents de collecte de données unifiées qui s’exécutent sur des serveurs frontaux et des serveurs Standard Edition pour capturer des données à archiver. Aucune plateforme système séparée n’est donc nécessaire pour héberger l’archivage.

  - **Plateforme de stockage de données** : dans Lync Server 2013, vous pouvez stocker des données à l’aide des deux méthodes suivantes :
    
      - **Intégration de Microsoft Exchange** : si vous voulez stocker des données d’archivage Lync Server 2013 à l’aide de votre déploiement Exchange 2013, en remplacement ou en plus de la configuration d’une base de données séparée pour le stockage des données d’archivage, votre déploiement Exchange doit exécuter Exchange 2013. Pour plus d’informations sur la configuration des plateformes système pour Exchange 2013, voir la documentation d’Exchange.
    
      - **SQL Server** : si vous voulez utiliser une base de données SQL Server séparée pour le stockage des données d’archivage, en remplacement ou en plus de l’utilisation de l’intégration de Microsoft Exchange, vous devez configurer la plateforme système pour la base de données avant de déployer l’archivage. La configuration requise d’une plateforme système spécifique dépend de l’utilisation de Microsoft SQL Server 2008 R2 ou Microsoft SQL Server 2012 pour la base de données d’archivage. Pour plus d’informations sur la configuration des plateformes système pour ces bases de données, voir la documentation de Microsoft SQL Server 2008 R2 et Microsoft SQL Server 2012.

  - **Plateforme des serveurs de fichiers** : Lync Server 2013 stocke les fichiers d’archivage Lync Server à l’emplacement que vous avez défini pour le stockage de fichiers lors de la configuration de vos serveurs frontaux ou Standard Edition. Vous ne pouvez pas spécifier d’emplacement séparé pour le stockage des fichiers d’archivage, aucune plateforme système séparée n’est donc nécessaire. Si vous utilisez l’intégration de Microsoft Exchange, Exchange 2013, les fichiers des communications Lync archivées sont stockés sur des serveurs Exchange 2013 pour les utilisateurs hébergés sur ces serveurs Exchange.

