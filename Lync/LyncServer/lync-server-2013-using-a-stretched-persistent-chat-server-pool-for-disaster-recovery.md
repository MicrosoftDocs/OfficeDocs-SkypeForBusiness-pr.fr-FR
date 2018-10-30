---
title: "Lync Server 2013 : Ut. d’un pool de serv. de conv. perm. élargi pr réc d’urg."
TOCTitle: Utilisation d’un pool de serveurs de conversation permanente élargi pour la récupération d’urgence
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205007(v=OCS.15)
ms:contentKeyID: 49297740
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation d’un pool de serveurs de conversation permanente élargi pour la récupération d’urgence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

La solution de récupération d’urgence pour le serveur de conversations permanentes repose sur un pool de serveurs de conversations permanentes étiré, ce qui s’apparente à la résistance de site métropolitain dans Lync Server 2010 ; en revanche, aucun réseau local virtuel (VLAN) étiré n’est requis. En étirant le pool de serveurs de conversations permanentes, vous configurez en fait un seul pool dans la topologie de manière logique, mais vous placez physiquement les serveurs dans le pool dans deux centres de données différents. Configurez la mise en miroir SQL Server pour la base de données de la même manière, puis déployez la base de données et le miroir dans le même centre de données. Vous devez configurer une base de données de sauvegarde dans le second centre de données (avec un miroir éventuel pour assurer la haute disponibilité pendant la récupération d’urgence). Il s’agit de la base de données de sauvegarde utilisée pour le basculement pendant la récupération d’urgence.

Pour plus d’informations sur la manière de configurer la mise en miroir SQL Server pour la haute disponibilité, reportez-vous à [Mise en miroir SQL Server dans Lync Server 2013](lync-server-2013-sql-server-mirroring.md). Pour plus d’informations sur le basculement de la base de données pour la récupération d’urgence, reportez-vous à [Configuration de la copie des journaux de transaction SQL Server dans Lync Server 2013 pour la base de données principale du serveur de conversation permanente](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) et à [Définition de la copie des journaux de transaction SQL Server entre la base de données miroir principale et la base de données secondaire de copie des journaux de transaction dans Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md).

