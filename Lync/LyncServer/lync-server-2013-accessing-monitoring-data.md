---
title: Accès aux données de surveillance dans Lync Server 2013
TOCTitle: Accès aux données de surveillance dans Lync Server 2013
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49891423
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Accès aux données de surveillance dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-05_

Les données de surveillance sont stockées dans deux bases de données SQL Server: LcsCdr pour les données d’enregistrement de détails des appels et QoEMetrics pour les données de qualité de l’expérience. Ces deux bases de données n’ont rien de particulier, les données qu’elles contiennent sont accessibles avec les outils que vous utilisez habituellement pour accéder à et analyser des données SQL Server.

Pour accéder à et analyser les données de surveillance, l’outil Rapports de surveillance de Lync Server est très utile. Ces rapports de surveillance sont un ensemble de rapports standard publiés par Microsoft SQL Server Reporting Service. Ces rapports, accessibles avec un navigateur web, fournissent des informations d’utilisation, de diagnostic d’appel et de qualité du média basées sur les enregistrements CDR (Enregistrement des détails des appels) et les enregistrements QoE (qualité de l’expérience) qui sont stockés dans les bases de données CDR et QoE. Les rapports de surveillance sont intégrés à Lync Server 2013 et peuvent être installés à partir de l’Assistant Déploiement de Lync Server une fois Lync Server installé et la surveillance configurée.

Comme cela a été indiqué, les rapports de surveillance nécessitent l’utilisation de SQL Server Reporting Service. SQL Server Reporting Service peut être installé en même temps que SQL Server ou ultérieurement.

Pour plus d’informations, voir [Installation des rapports de surveillance Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) dans le guide de déploiement de Lync Server 2013.

