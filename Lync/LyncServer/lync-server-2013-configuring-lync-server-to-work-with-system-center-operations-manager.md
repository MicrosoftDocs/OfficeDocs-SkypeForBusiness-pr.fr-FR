---
title: "Conf. de Lync Server pour le fonct. avec System Center Operations Manager"
TOCtitle: "Conf. de Lync Server pour le fonct. avec System Center Operations Manager"
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205188(v=OCS.15)
ms:contentKeyID: 49298591
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de Lync Server pour le fonctionnement avec System Center Operations Manager

 

_**Dernière rubrique modifiée :** 2012-10-22_

Pour configurer votre infrastructure Microsoft Lync Server 2013 afin qu’elle fonctionne avec System Center Operations Manager, vous devez effectuer trois opérations :

  - Identifiez et configurez votre serveur de gestion System Center Operations Manager principal. La configuration du serveur de gestion inclut l’installation de System Center Operations Manager 2012 ou de System Center Operations Manager 2007 R2, ainsi que la configuration d’une base de données principale à l’aide de SQL Server. La version actuelle de SQL Server que vous devez utiliser dépend de la version de System Center Operations Manager que vous utilisez. Pour plus d’informations, voir [Configuration du serveur d’administration principal](lync-server-2013-configuring-the-primary-management-server.md).

  - Identifiez et configurez les ordinateurs Lync Server que vous voulez surveiller. Pour surveiller un ordinateur Lync Server à l’aide de System Center Operations Manager, vous devez installer les fichiers d’agents System Center Operations Manager, et configurer chaque serveur pour qu’il agisse en tant que proxy.

  - Identifiez et configurez les ordinateurs qui doivent agir en tant que *nœuds observateurs*Lync Server. Les nœuds observateurs sont des ordinateurs qui exécutent régulièrement des transactions synthétiques Lync Server, lesquelles sont des applets de commande Windows PowerShell qui vérifient que les composants Lync Server clés, tels que la capacité à se connecter au système ou la capacité à échanger des messages instantanés, fonctionnent comme prévu.

Les rubriques de cette section contiennent des instructions pour l’exécution de chacune de ces tâches.

## Dans cette section

  - [Configuration du serveur d’administration principal](lync-server-2013-configuring-the-primary-management-server.md)

  - [Installation des packs d’administration Lync Server 2013](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Configuration des ordinateurs Lync Server qui seront surveillés](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Installation et configuration de nœuds observateurs](lync-server-2013-installing-and-configuring-watcher-nodes.md)

