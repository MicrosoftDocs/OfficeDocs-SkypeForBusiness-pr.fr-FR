---
title: "LS 2013 : Gest. de la réc. d’urg., de la haute dispo. et du serv. de sauv."
TOCTitle: Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server 2013
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49891614
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-12_

Cette section contient des procédures destinées aux opérations de récupération d’urgence, ainsi que pour la maintenance du service de sauvegarde qui synchronise les données des pools frontaux couplés.

Les procédures de récupération d’urgence, qu’il s’agisse du basculement ou de la restauration automatique, sont manuelles. En cas d’urgence, l’administrateur doit appeler manuellement les procédures de basculement. Il en est de même pour la restauration automatique, après la réparation du pool.

Les procédures de récupération d’urgence présentées dans le reste de la section supposent les éléments suivants :

  - Votre déploiement doit comprendre des pools frontaux couplés, situés dans différents sites, comme décrit dans [Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Le service de sauvegarde a été exécuté sur ces pools couplés pour maintenir leur synchronisation.

  - Si le magasin central de gestion est hébergé sur un autre pool, il est installé et exécuté sur les deux pools couplés, et un de ces pools héberge le Réplicateur principal actif tandis que l’autre héberge celui de secours.

> [!IMPORTANT]  
> Dans les procédures suivantes, le paramètre <em>PoolFQDN</em> se réfère au nom de domaine complet (FQDN) du pool affecté par la situation d’urgence et non pas le pool depuis lequel les utilisateurs affectés sont redirigés. Dans le cas d’un ensemble d’utilisateurs identique, le paramètre se réfère au même pool, dans les applets de commande de basculement et de récupération automatique (c’est-à-dire, le pool ayant hébergé les utilisateurs avant le basculement).<br />
Par exemple, supposons que tous les utilisateurs hébergés sur un pool P1 ont été basculés sur le pool de sauvegarde, P2. Si l’administrateur veut déplacer tous les utilisateurs actuellement traités par les services de P2 pour qu’ils soient traités par les services de P1, l’administrateur doit procéder comme ceci :
> <ol>
> <li><p>Il doit restaurer automatiquement tous les utilisateurs hébergés à l’origine sur P1 de P2 à P1 en utilisant l’applet de commande de restauration automatique. Dans ce cas, le <em>PoolFQDN</em> est le nom de domaine complet (FQDN) de P1.</p></li>
> <li><p>Il doit ensuite basculer tous les utilisateurs hébergés à l’origine sur P2 vers P1 en utilisant l’applet de commande de basculement. Dans ce cas, le <em>PoolFQDN</em> est le nom de domaine complet (FQDN) de P2.</p></li>
> <li><p>Si l’administrateur souhaite ultérieurement restaurer automatiquement les utilisateurs de P2 vers P2, le <em>PoolFQDN</em> est le nom de domaine complet FQDN de P2.</p></li></ol>
> Remarquez que l’étape 1 ci-dessus doit être effectuée avant l’étape 2 pour préserver l’intégrité du pool. Si vous essayez l’étape 2 avant l’étape 1, l’applet de commande de l’étape 2 ne fonctionnera pas.


## Dans cette section

  - [Configuration et surveillance du service de sauvegarde dans Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Basculement vers un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Basculement vers un pool dans Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Basculement vers une base de données en miroir dans Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Basculement vers le pool Edge utilisé pour la fédération Lync Server dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Restauration du pool Edge utilisé pour la fédération XMPP ou Lync Server dans Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Modification du pool de serveurs Edge associé à un pool de serveurs frontaux dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Restauration du contenu d’une conférence avec le service de sauvegarde dans Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

## Voir aussi

#### Concepts

[Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

