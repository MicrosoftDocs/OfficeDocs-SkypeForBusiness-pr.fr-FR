---
title: 'Lync Server 2013 : Planification du jumelage de pools frontaux'
TOCTitle: Planification du jumelage de pools frontaux
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205293(v=OCS.15)
ms:contentKeyID: 49298883
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification du jumelage de pools frontaux dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-28_

Pour obtenir les meilleures fonctionnalités de récupération d’urgence dans Lync Server 2013, déployez des paires de pools frontaux à travers deux sites géographiquement dispersés. Chaque site contient un pool frontal couplé à un pool frontal correspondant dans l’autre site. Les deux sites sont actifs, et le service de sauvegarde Lync Server assure la réplication des données en temps réel pour garder les pools synchronisés. Le service de sauvegarde est une nouvelle fonction dans Lync Server 2013, conçue pour prendre en charge la solution de récupération d’urgence. Il est installé sur un pool frontal lorsque vous couplez le pool avec un autre pool frontal.

Si le pool dans un site échoue, vous pouvez basculer les utilisateurs de ce pool vers le pool dans l’autre site, qui fournit alors les services à tous les utilisateurs dans les deux pools. À des fins de planification de capacité, chaque pool doit être conçu pour gérer les charges de travail de tous les utilisateurs dans les deux pools en cas de sinistre.

## Dans cette section

  - [Options de couplage de pools et meilleures pratiques prises en charge pour Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Relations des serveurs d’inscriptions de sauvegarde dans Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Temps de récupération nécessaire pour basculer et restaurer les pools dans Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Basculement du magasin central de gestion dans Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Sécurité des données d’appariement de pools frontaux dans Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

