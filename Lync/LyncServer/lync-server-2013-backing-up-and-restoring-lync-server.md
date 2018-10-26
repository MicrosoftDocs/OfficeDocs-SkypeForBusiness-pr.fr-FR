---
title: Sauvegarde et restauration de Lync Server 2013
TOCTitle: Sauvegarde et restauration de Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202160(v=OCS.15)
ms:contentKeyID: 53095352
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sauvegarde et restauration de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Cette section indique les meilleures pratiques pour la sauvegarde de vos données Lync Server 2013 et pour leur restauration en cas d’échec. Ces meilleures pratiques s’appliquent dans les circonstances suivantes :

  - un pool Lync Server entier de n’importe quel type (serveur frontal, serveur Edge, serveur de médiation, serveur de conversations permanentes ou directeur) ou un serveur individuel dans l’un de ces pools ;

  - le serveur de gestion centralisée ;

  - un serveur Standard Edition ;

  - un serveur principalEnterprise Edition ;

  - un magasin de fichiers ;

  - une base de données d’archivage, base de données de surveillance ou une base de données de conversation permanente.

Cette section n’inclut pas les informations permettant de restaurer tout un site ou de développer un site en veille. Pour plus d’informations sur le développement d’une solution de récupération d’urgence avec des pools frontaux appariés, voir [Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Il s’agit de la méthode recommandée pour planifier la récupération d’urgence.

Si vous avez déployé des pools frontaux appariés et que l’un de ces pools échoue et devient irrécupérable, vous pouvez le restaurer avec un nouveau nom de domaine complet à partir de son pool apparié. Pour plus d’informations sur les étapes de cette récupération, voir [Basculement vers un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md). En outre, si vous souhaitez par la suite recréer un pool défaillant et irrécupérable qui faisait partie d’une paire frontale, vous pouvez utiliser les étapes décrites dans [Exécution d’un basculement de pools frontaux ABC](lync-server-2013-performing-an-abc-front-end-pool-failover.md).

La méthodologie décrite dans ce document implique des considérations spécifiques lors de la phase de planification. Pour plus d’informations, voir [Établissement d’un plan de sauvegarde et de restauration](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

## Dans cette section

  - [Préparation de la sauvegarde et de la restauration de Lync Server](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Sauvegarde des données et des paramètres](lync-server-2013-backing-up-data-and-settings.md)

  - [Restauration des données et paramètres](lync-server-2013-restoring-data-and-settings.md)

  - [Feuilles de travail de sauvegarde et de restauration](lync-server-2013-backup-and-restoration-worksheets.md)

