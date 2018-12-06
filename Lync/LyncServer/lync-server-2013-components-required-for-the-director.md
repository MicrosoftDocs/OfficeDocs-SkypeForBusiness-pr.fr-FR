---
title: 'Lync Server 2013 : Composants requis pour le directeur'
TOCTitle: Composants requis pour le directeur
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398228(v=OCS.15)
ms:contentKeyID: 49296361
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants requis pour le directeur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Pour créer et configurer un directeur, vous devez déployer le rôle serveur directeur. Pour ce faire, utilisez le Générateur de topologie et définissez un pool d’ordinateur unique ou un pool de plusieurs ordinateurs dans le nœud pool de directeurs. Une fois que vous avez défini le directeur ou le pool de directeurs, exécutez l’Assistant Déploiement de Lync Server sur l’ordinateur qui sera directeur. Dans le cas d’un pool de directeurs, exécutez l’Assistant Déploiement de Lync Server sur chaque serveur destiné à faire partie du pool.

## Topologies

Vous pouvez implémenter un seul serveur directeur ou un pool de directeurs. Le directeur est toujours un serveur ou un pool distinct, il n’est pas colocalisé avec un autre rôle serveur dans Lync Server 2013.

> [!NOTE]  
> Si vous ne déployez pas les directeurs, les serveur frontal ou le pool de serveurs frontaux endosseront le rôle des directeur.

La charge du pool de directeurs doit être équilibrée. Vous pouvez effectuer l’une des opérations suivantes :

  - Créez une topologie qui utilise un équilibreur de la charge matérielle pour les services web et un équilibrage de la charge DNS (Domain Name System) pour les autres types de trafic.
    
    [Pool directeur mis à l’échelle - Équilibrage de charge DNS et équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Créez une topologie qui utilise un équilibreur de la charge matérielle pour l’équilibrage de la charge requise pour le pool de directeurs.
    
    [Pool directeur mis à l’échelle - Équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

