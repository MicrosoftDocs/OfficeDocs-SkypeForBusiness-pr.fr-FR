---
title: 'Lync Server 2013 : Vue d’ensemble du déploiement'
TOCTitle: Vue d’ensemble du déploiement
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205305(v=OCS.15)
ms:contentKeyID: 49299027
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble du déploiement pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-12_

La différence principale entre Lync Server 2013  Enterprise Edition et Lync Server 2013  Standard Edition réside dans le fait que Standard Edition ne prend pas en charge les fonctionnalités à haute disponibilité incluses dans Enterprise Edition. Pour la haute disponibilité, vous devez déployer plusieurs serveurs frontaux dans un pool, puis mettre en miroir le serveur exécutant SQL Server. Avec Enterprise Edition, vous pouvez choisir de colocaliser ou définir un serveur de médiation autonome. Le serveur de surveillance et le serveur d’archivage peuvent utiliser un serveur autonome exécutant SQL Server. Ils peuvent également avoir des instances SQL Server exécutées sur le serveur de base de données pour les serveurs frontaux et les pools.

Les serveurs exécutant Lync Server 2013Standard Edition sont conçus pour les petites organisations et les emplacements distants, supprimés géographiquement du déploiement principal de l’organisation. Deux serveurs serveur Standard Edition couplés pour le basculement en cas de récupération d’urgence peuvent prendre en charge jusqu’à 5 000 utilisateurs. Vous ne pouvez pas regrouper des serveurs Standard Edition dans un pool comme vous pouvez le faire avec des serveurs frontaux dans Enterprise Edition. De plus, la base de données SQL Server qu’utilise Standard Edition est un serveur colocalisé exécutant SQL Server Express, conçu pour gérer les charges de travail d’un serveur Standard Edition. Cela ne veut pas dire que tous les rôles doivent se trouver sur un serveur Standard Edition. Vous pouvez avoir des serveurs de médiation et des serveurs Edge autonomes. La base de données SQL Server pour le magasin central de gestion et le fonctionnement de Lync Server 2013 doit se trouver sur le serveur Standard Edition colocalisé avec le serveur exécutant SQL Server. Le serveur de surveillance et le serveur d’archivage utilisent un serveur autonome avec la base de données SQL Server.

