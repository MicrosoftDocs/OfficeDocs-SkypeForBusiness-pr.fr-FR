---
title: "Lync Server 2013 : Ressources req. pour le serveur de conversation permanente"
TOCTitle: Ressources requises
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205211(v=OCS.15)
ms:contentKeyID: 49298664
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ressources requises pour le serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-02-05_

La haute disponibilité et la récupération d’urgence pour les serveur de conversations permanentes nécessite des ressources supplémentaires dépassant ce qui est généralement nécessaire pour une exploitation complète. Avant la configuration des serveur de conversations permanentes pour la haute disponibilité et la récupération d’urgence, vérifiez que vous avez bien les ressources suivantes en plus de ce qui est obligatoire pour un fonctionnement standard des serveur de conversations permanentes. Pour plus d’informations sur la configuration, reportez-vous à [Configuration du serveur de conversation permanente dans Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Une instance dédiée de la base de données, située au même centre de données physique dans lequel le serveur de conversations permanentes frontal d’accueil du service se trouve. Cette base de données sert de miroir SQL Server pour la base de données de conversation permanente principale. Désignez au besoin une base de données SQL Server en plus comme témoin de mise en miroir si vous voulez que le basculement automatisé se fasse sur la base de données miroir.

  - Une instance dédiée de la base de données, située dans l’autre centre de données physique. Elle doit servir de base de données SQL Server secondaire de copie des journaux de transaction pour la base de données qui se trouve dans le centre de données principal.

  - Une instance dédiée de la base de données servant de miroir SQL Server pour la base de données secondaire. Désignez au besoin une SQL Server en plus comme témoin de mise en miroir. Elles doivent toutes deux se situer dans le même centre de données physique que la base de données secondaire.

  - Si la conformité du serveur de conversations permanentes est activée, trois autres instances dédiées de base de données sont obligatoires. Leur distribution est identique à celle déjà indiquée pour la base de données de conversation permanente. S’il est possible que la base de données de conformité partage la même instance SQL Server que la base de données de conversation permanente, nous vous recommandons de créer des instances autonomes pour la haute disponibilité et la récupération d’urgence.

  - Vous devez aussi créer et désigner un partage de fichiers pour les journaux des transactions de copie des journaux de transaction SQL Server. Tous les serveurs SQL Server des deux centres de données qui exécutent des bases de données conversation permanente doivent disposer d’un accès en lecture/écriture à ce partage de fichiers. Celui-ci n’est pas défini avec un rôle FileStore.

  - Un partage de fichiers sur le serveur de base de données secondaire servant de dossier de destination pour les journaux de transaction SQL Server copiés depuis le partage de fichiers du serveur principal.

Les données suivantes fournissent des exemples de configuration du pool de serveurs de conversations permanentes complet dans les deux topologies de pool étirées :

  - pool de serveurs de conversations permanentes étiré quand les centres de données sont localisés géographiquement et font état d’une bande passante élevée/faible latence.

  - pool de serveurs de conversations permanentes étiré quand les centres de données sont localisés géographiquement et font état d’une bande passante réduite/latence élevée.

Les données suivantes montrent une topologie de pool de serveurs de conversations permanentes étirée où les centres de données sont localisés géographiquement avec une bande passante élevée/faible latence.

**Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement et font état d’une bande passante élevée/faible latence.**

![Examen de configuration HBW du pool de serveurs de conversations persistantes](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Examen de configuration HBW du pool de serveurs de conversations persistantes")

Les données suivantes montrent une topologie de pool de serveurs de conversations permanentes étirée où les centres de données sont localisés géographiquement avec une bande passante réduite/latence élevée.

**Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement avec une bande passante réduite/latence élevée.**

![Examen de configuration LBW du pool de serveurs de conversations persistantes](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Examen de configuration LBW du pool de serveurs de conversations persistantes")

