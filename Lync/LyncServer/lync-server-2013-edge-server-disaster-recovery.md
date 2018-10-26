---
title: 'Lync Server 2013 : Récupération d’urgence de serveur Edge'
TOCTitle: Récupération d’urgence de serveur Edge
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49891220
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Récupération d’urgence de serveur Edge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-03-12_

Comme avec les autres rôles serveur, le meilleur moyen d’offrir une haute disponibilité pour vos serveurs Edge consiste à déployer plusieurs serveurs Edge dans des pools pour chaque site. Si un serveur Edge ne fonctionne pas, les autres serveurs dans le pool continueront à assurer les services Edge.

Pour activer les procédures de récupération d’urgence, vous devez avoir déployé des pools de serveurs Edge distincts sur chaque site. Vous n’avez pas besoin d’associer par deux des pools Edge de façon explicite comme vous le feriez avec des pools frontaux, mais la disponibilité de plusieurs pools Edge permet de maintenir l’activité si un pool Edge entier le fonctionne pas. Les sections suivantes décrivent la récupération d’urgence pour les différentes fonctions des serveurs Edge.

## Accès à distance

Si vous disposez de plusieurs sites, chacun étant doté d’un pool de serveurs Edge, les services d’accès à distance continueront à fonctionner sans qu’aucune intervention de l’administrateur ne soit nécessaire si un pool Edge entier ne fonctionne pas. Lors de la création de pools Edge dans différents sites, vous ne pouvez pas utiliser le même nom de domaine complet. Chaque pool Edge doit avoir des noms de domaine complets et uniques (internes et externes). Les pools Edge n’utilisent pas les règles de publication proxy inverse pour converser avec les serveurs frontaux. Le basculement automatique se produit lorsque le client réinterroge les enregistrements de service DNS d’accès distant, et les utilisateurs distants sont routés vers les serveurs Edge d’un autre site. Le client essaie chaque nom de domaine complet Edge selon la priorité des enregistrements SRV de DNS.

> [!NOTE]  
> Pour que le basculement fonctionne correctement, veillez à ce que le pare-feu permette aux serveurs frontaux de chaque pool de communiquer avec tous les serveurs Edge.

## Fédération

Concernant les relations de fédération avec les autres organisations exécutant Lync Server, les demandes de fédération entrantes continueront à fonctionner du moment que vous avez configuré chaque pool Edge avec une priorité différente dans vos enregistrements SRV. Les demandes de fédération qui parviennent à un pool Edge en panne seront transférées vers un pool Edge en état de fonctionnement.

La fédération sortante est toujours configurée par le biais d’un pool ou d’un serveur Edge publié dans l’organisation. Si ce pool Edge est tombé en panne, vous devez utiliser le générateur de topologie pour changer l’itinéraire de la fédération sortante afin d’utiliser un pool Edge en état de fonctionnement. Pour plus d’informations, reportez-vous à [Basculement vers le pool Edge utilisé pour la fédération Lync Server dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

## Fédération XMPP

Concernant la fédération XMPP, le trafic entrant et sortant s’arrêtera si le pool Edge qui est désigné comme passerelle de fédération XMPP ne fonctionne pas. Pour que la fédération XMPP fonctionne de nouveau, vous devez configurer la fédération XMPP de sorte qu’elle utilise un autre pool Edge. Pour plus d’informations, reportez-vous à [Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

## Le pool Edge le fonctionne pas, mais le pool frontal fonctionne toujours

Si un pool Edge ne fonctionne pas sur un site, alors que le pool frontal de ce site fonctionne toujours, vous devez configurer le pool frontal pour qu’il utilise un autre pool Edge d’un autre site pendant que le premier pool Edge est en panne. Pour plus d’informations, reportez-vous à [Modification du pool de serveurs Edge associé à un pool de serveurs frontaux dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

