---
title: Configuration requise pour l’équilibrage de charge dans Lync Server 2013
TOCTitle: Configuration requise pour l’équilibrage de charge dans Lync Server 2013
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615011(v=OCS.15)
ms:contentKeyID: 49297939
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour l’équilibrage de charge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-05_

Si vous avez des pools de serveurs frontaux, des pools directeur ou des pools serveur Edge, vous devez déployer l’équilibrage de la charge pour ces pools. L’équilibrage de la charge distribue le trafic entre les serveurs dans un pool.

Lync Server 2013 prend en charge deux types de solutions d’équilibrage de la charge pour le trafic client à serveur : l’équilibrage de la charge DNS (Domain Name System) et l’équilibrage de la charge matérielle. L’équilibrage de la charge DNS offre plusieurs avantages, parmi lesquels une administration plus simple, un dépannage plus efficace et la possibilité d’isoler la plupart du trafic Lync Server des problèmes potentiels liés à l’équilibreur de la charge matérielle.

Déterminez la solution d’équilibrage de la charge adaptée à chaque pool de votre déploiement, en gardant à l’esprit les restrictions suivantes :

  - Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface et l’équilibrage de la charge matérielle sur l’autre.

  - Certains types de trafic nécessitent un équilibreur de la charge matérielle. Par exemple, le trafic HTTP requiert un équilibreur de la charge matérielle plutôt que l’équilibrage de la charge DNS. Celui-ci ne fonctionne pas avec le trafic web client-à-serveur.

Pour plus d’informations sur le choix d’une solution d’équilibreur de la charge matérielle, voir [Configuration requise pour l’équilibreur de charge matérielle pour Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).

Si vous décidez d’utiliser l’équilibrage de la charge DNS pour un pool mais que vous souhaitez quand même implémenter des équilibreurs de la charge matérielle pour certains types de trafics, tels que le trafic HTTP, l’administration des équilibreurs de la charge matérielle est grandement simplifiée. Par exemple, l’équilibreur de charge matérielle sera plus simple car il ne gérera que le trafic HTTP et HTTPS, alors que tous les autres protocoles seront gérés par l’équilibrage de charge DNS. Pour plus d’informations, voir [Équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md).

Pour le trafic serveur à serveur, Lync Server 2013 utilise l’équilibrage de charge de topologie. Les serveurs lisent la topologie publiée dans le magasin central de gestion afin d’obtenir les noms de domaine complets des serveurs dans la topologie et distribuent automatiquement le trafic entre les serveurs. Les administrateurs n’ont pas besoin de configurer ou de gérer ce type d’équilibrage de charge.

Si vous utilisez l’équilibrage de la charge DNS et que vous voulez bloquer le trafic vers un ordinateur particulier, vous devez supprimer les adresses IP dans le nom de domaine complet du pool, mais également supprimer l’entrée DNS associée à l’ordinateur.

