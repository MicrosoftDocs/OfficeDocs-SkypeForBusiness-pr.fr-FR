---
title: 'Lync Server 2013 : Composants et topologies pour la surveillance'
TOCTitle: Composants et topologies pour la surveillance
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412952(v=OCS.15)
ms:contentKeyID: 49891523
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants et topologies pour la surveillance dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-05_

Les agents de collecte de données unifiée étant automatiquement installés et activés sur chaque serveur frontal, vous n’avez pas besoin de configurer un serveur en tant que serveur de surveillance ; en effet, chaque serveur frontal fonctionne déjà comme un serveur de surveillance. En revanche, vous devez installer et configurer une base de données qui servira de magasin de données principal pour vos données d’analyse. Microsoft Lync Server 2013 prend en charge les bases de données suivantes comme magasin principal des données d’analyse :

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Notez que vous devez utiliser les versions 64 bits de ces bases de données, car les versions 32 bits de SQL Server ne sont pas prises en charge en tant que magasin principal des données d’analyse. De même, Lync Server 2013 ne prend pas en charge les versions Express Edition de SQL Server 2008 et de SQL Server 2012. Pour plus d’informations sur la configuration requise des bases de données pour Lync Server 2013, reportez-vous à la rubrique [Prise en charge du logiciel de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md) dans le guide de prise en charge de Lync Server 2013.

N’oubliez pas que SQL Server doit être installé et configuré avant de procéder au déploiement et à la configuration de la fonctionnalité d’analyse. Vous devez déployer SQL Server, mais vous n’avez pas besoin de configurer les bases de données d’analyse, car celles-ci seront automatiquement créées lorsque vous publierez votre topologie Lync Server.

Les données d’analyse peuvent utiliser la même instance SQL Server que d’autres types de données. Généralement, la base de données des enregistrements des détails des appels (LcsCdr) et la base de données de qualité de l’expérience (QoEMetrics) utilisent la même instance SQL ; par ailleurs, ces deux bases de données utilisent souvent la même instance SQL que la base de données d’archivage (LcsLog). La seule limitation réelle concernant les instances SQL Server est que chaque instance SQL Server est limitée à :

  - une seule instance de la base de données principale Lync Server 2013 (en règle générale, il est préférable de ne pas colocaliser votre base de données d’analyse dans la même instance SQL, ni sur le même ordinateur, que la base de données principale. Même si cela est techniquement possible, la base de données d’analyse risque d’utiliser de l’espace disque nécessaire à la base de données principale) ;

  - une seule instance de la base de données LcsCdr ;

  - une seule instance de la base de données QoEMetrics ;

  - une seule instance de la base de données d’archivage.

Autrement dit, vous ne pouvez pas avoir deux instances de la base de données LcsCdr dans la même instance SQL Server. Pour utiliser plusieurs instances de cette base de données, vous devez configurer plusieurs instances SQL Server.

## Voir aussi

#### Autres ressources

[Déploiement du serveur de surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md)

