---
title: Prise en charge du logiciel de base de données Lync Server 2013
TOCTitle: Prise en charge du logiciel de base de données
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398990(v=OCS.15)
ms:contentKeyID: 49299106
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge du logiciel de base de données dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server 2013 prend en charge les systèmes de gestion de base de données suivants :

  - **Base de données principale d’un pool frontal, base de données d’archivage, base de données de surveillance, base de données de conversation persistante, et base de données de conformité de la conversation persistante**
    
      - Logiciel de base de données Microsoft SQL Server 2008 R2 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.
    
      - Microsoft SQL Server 2008 R2 Standard (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.
    
      - Microsoft SQL Server 2012 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.
    
      - Microsoft SQL Server 2012 Standard (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.

  - **Base de données du serveur Standard Edition et bases de données serveur frontal**
    
      - Microsoft SQL Server 2012 Express (édition 64 bits). Il est également recommandé d’exécuter le dernier Service Pack.
        
        Nous prenons en charge l’application de correctifs et la mise à niveau de Microsoft SQL Server sur serveurs frontaux et serveurs Standard Edition. Toutefois, pour toute application de correctif ou mise à niveau sur serveurs frontaux, vous devez prendre en compte les exigences du quorum. Pour plus d’informations, voir [Mise à niveau ou mise à jour des serveurs frontaux dans Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) et [Topologies et composant utilisés pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (édition 64 bits) est automatiquement installé par Lync Server 2013sur chaque serveur Standard Edition et chaque serveur serveur frontal.

> [!IMPORTANT]  
> <ul>
> <li><p>Lync Server 2013 ne prend pas en charge l’édition 32 bits de SQL Server. Vous devez utiliser l’édition 64 bits.</p></li>
> <li><p>L’édition SQL Server pour le web et l’édition SQL Server pour les groupes de travail ne sont pas prises en charge. Vous ne pouvez pas les utiliser avec Lync Server 2013.</p></li>
> <li><p>Lync Server 2013 prend en charge la mise en miroir native des bases de données.</p></li>
> <li><p>Pour utiliser le rôle Serveur de surveillance, vous devriez installer SQL Server Reporting Services.</p></li></ul>


Dans un pool frontal, la base de données principale peut être un ordinateur SQL Server unique.

> [!IMPORTANT]  
> Si vous colocalisez des bases de données Lync Server avec d’autres bases de données, nous vous recommandons vivement d’évaluer tous les facteurs susceptibles d’affecter la disponibilité et les performances et de vous assurer qu’en cas de défaillance d’un nœud, le nœud restant puisse gérer la charge. Pour vérifier les capacités de basculement, nous vous recommandons de tester tous les scénarios de basculement.

## Utilisation de la mise en miroir SQL et du clustering SQL

Lync Server 2013 prend en charge l’utilisation de la mise en miroir SQL ou du clustering SQL pour chaque base de données Lync Server. Vous pouvez facilement configurer la mise en miroir SQL avec l’outil Générateur de topologie dans Lync Server 2013. Pour le clustering SQL avec basculement, vous devez utiliser SQL Server pour la configuration.

Lync Server 2013 prend en charge les topologies de clustering et de mise en miroir SQL pour tous les déploiements, dont les déploiements dans un environnement vierge et les organisations ayant effectué une mise à niveau à partir de versions précédentes de Lync Server.

La prise en charge du clustering SQL concerne les configurations active/passive. Pour des raisons de performance, le nœud passif ne doit pas être partagé par une autre instance SQL.

La prise en charge suivante est incluse :

  - Clustering de basculement à deux nœuds pour les configurations suivantes :
    
      - Microsoft SQL Server 2012 Standard (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.
    
      - Microsoft SQL Server 2008 R2 Standard (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.

  - Clustering de basculement à 16 nœuds maximum pour les configurations suivantes :
    
      - Microsoft SQL Server 2012 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.
    
      - Logiciel de base de données Microsoft SQL Server 2008 R2 Enterprise (édition 64 bits). Il également recommandé d’exécuter le dernier Service Pack.

Pour plus d’informations sur la mise en miroir SQL, reportez-vous à [Haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-back-end-server-high-availability.md). Pour plus d’informations sur le déploiement du clustering SQL, reportez-vous à [Configurer le clustering SQL Server pour Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).

Pour plus d’informations et consulter les pratiques recommandées relatives au clustering de basculement dans SQL Server 2012, reportez-vous à <http://technet.microsoft.com/fr-fr/library/hh231721.aspx>. Pour le clustering de basculement dans SQL Server 2008, reportez-vous à <http://technet.microsoft.com/fr-fr/library/ms189134(v=sql.105).aspx>.

