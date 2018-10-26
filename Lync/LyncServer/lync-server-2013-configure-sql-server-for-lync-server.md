---
title: 'Lync Server 2013 : Configuration de SQL Server pour Lync Server'
TOCTitle: Configuration de SQL Server pour Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425848(v=OCS.15)
ms:contentKeyID: 49296863
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de SQL Server pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-08-12_

Les rubriques de cette section abordent le déploiement et la configuration de SQL Server de sorte qu’il utilise un déploiement Enterprise de Lync Server. Les serveurs Standard Edition utilisent une version SQL Server Express colocalisée de SQL Server, parfaitement adaptée aux charges de travail d’un serveur Standard Edition.

Le magasin central de gestion de Lync Server 2013 détient les données utilisateur de tous les serveurs Enterprise Edition d’un pool. Il est conçu pour se trouver sur un serveur principal SQL Server. Comme il s’agit d’un espace de stockage centralisé, le magasin central de gestion ne peut pas être installé sur le même ordinateur que tout autre rôle Lync Server 2013. Le magasin central de gestion ne peut pas se trouver sur un serveur Enterprise Edition du pool. Le magasin central de gestion est automatiquement créé lorsque vous publiez la topologie pour la première fois et choisissez de créer les bases de données. L’ordinateur que vous désignez comme serveur principal doit exécuter le logiciel de base de données SQL Server pour que l’installation se déroule correctement.

## Dans cette section

  - [Emplacement des fichiers journaux et des données SQL Server pour Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Configuration de SQL Server dans Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Autorisations de déploiement de SQL Server dans Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Installation de la base de données avec Lync Server Management Shell dans Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Description des exigences de pare-feu pour SQL Server avec Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Configurer le clustering SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

