---
title: "Suppression des instances et des BD SQL Server sur le serveur principal"
TOCtitle: "Suppression des instances et des BD SQL Server sur le serveur principal"
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49891300
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression des instances et des bases de données SQL Server sur le serveur principal

 

_**Dernière rubrique modifiée :** 2012-10-19_

Vous supprimez les bases de données et instances de Microsoft SQL Server après avoir supprimé les serveurs exécutant Lync Server 2010 qui en dépendent, ou après avoir reconfiguré les serveurs exécutant Lync Server 2010 afin qu’ils utilisent une autre base de données. Vous devez appliquer la procédure indiquée dans cette rubrique quand vous mettez hors service le serveur SQL Server actuel ou que vous reconfigurez le serveur actuel exécutant Lync Server 2010 de sorte que la base de données devienne obsolète ou indisponible.

Pour supprimer les bases de données du serveur d’archivage ou du serveur de surveillance, vous devez d’abord supprimer le rôle serveur. De la même façon, pour supprimer les instances et les bases de données du pool de serveurs frontaux, vous devez d’abord supprimer ou reconfigurer le rôle serveur qui en dépend. Ces procédures ne font pas de distinction entre les bases de données colocalisées et les instances distinctes des serveurs. Elles ne sont pas affectées par la colocalisation des bases de données.

## Dans cette section

  - [Suppression de la base de données SQL Server pour un pool frontal](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Suppression de la base de données SQL Server pour un serveur de surveillance](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Suppression de la base de données SQL Server pour un serveur d’archivage](remove-the-sql-server-database-for-an-archiving-server.md)

