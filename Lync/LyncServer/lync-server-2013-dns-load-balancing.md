---
title: 'Lync Server 2013 : équilibrage de la charge DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46d1efb960e6f60118364193dffdbedcefea94a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Équilibrage de la charge DNS dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-15_

Lync Server active l’équilibrage de charge DNS, une solution logicielle qui réduit considérablement la charge d’administration pour l’équilibrage de charge sur votre réseau. L’équilibrage de charge DNS équilibre le trafic réseau propre à Lync Server, tel que le trafic SIP et le trafic multimédia.

Si vous déployez l’équilibrage de la charge DNS, les frais d’administration de votre organisation pour les programmes d’équilibrage de la charge matérielle seront minimisés. De plus, le travail ardu de dépannage qu’imposent les problèmes découlant d’une mauvaise configuration des programmes d’équilibrage de la charge pour le trafic SIP sera évité. Vous pouvez aussi empêcher les connexions serveur afin de mettre les serveurs hors connexion. L’équilibrage de la charge DNS permet également d’éviter que des problèmes liés aux programmes d’équilibrage de la charge matérielle n’aient une incidence sur des éléments du trafic SIP, notamment le routage de base des appels.

En optant pour l’équilibrage de la charge DNS, vous pouvez aussi acheter des programmes d’équilibrage de la charge matérielle moins chers que ceux proposés pour tous les types de trafic. Vous devez utiliser des programmes d’équilibrage de charge qui ont passé des tests de compétences d’interopérabilité avec Lync Server. Pour plus d’informations sur les tests d’interopérabilité de l’équilibreur de charge, voir « partenaires d' [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)équilibrage de charge Lync Server 2010 » à l’adresse.

L’équilibrage de charge DNS est pris en charge pour les pools frontaux, les pools de serveurs Edge, les pools de directeurs et les pools de serveurs de médiation autonomes.

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Équilibrage de la charge DNS dans les pools frontaux et les pools directeurs

Vous pouvez désormais utiliser l’équilibrage de la charge DNS pour le trafic SIP dans les pools frontaux et les pools directeurs. Avec l’équilibrage de charge DNS déployé, vous devrez quand même toujours utiliser les programmes d’équilibrage de la charge matérielle pour ces pools, mais seulement pour le trafic HTTPS du client vers le serveur. Le programme d’équilibrage de la charge matérielle est utilisé pour le trafic HTTPS venant des clients sur les ports 443 et 80.

Bien que le recours à des programmes d’équilibrage de la charge matérielle soit toujours nécessaire pour ces pools, leur configuration et leur administration concernera avant tout le trafic HTTPS avec lequel les administrateurs des programmes d’équilibrage de la charge matérielle sont familiarisés.

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Équilibrage de charge DNS et prise en charge d’anciens clients et serveurs

L’équilibrage de charge DNS prend en charge le basculement automatique uniquement pour les serveurs exécutant Lync Server 2013 ou Lync Server 2010, ainsi que pour les clients Lync 2013 et Lync 2010. Les versions antérieures des clients et d’Office Communications Server peuvent toujours se connecter aux pools exécutant l’équilibrage de charge DNS, mais si elles ne peuvent pas établir une connexion avec le premier serveur auquel l’équilibrage de charge DNS les renvoie, ils ne peuvent pas basculer vers un autre serveur du pool. .

En outre, si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum de Exchange 2010 SP1 pour obtenir la prise en charge de l’équilibrage de charge DNS de Lync Server. Si vous utilisez une version antérieure d’Exchange, vos utilisateurs ne disposeront pas des fonctionnalités de basculement pour ces scénarios de messagerie unifiée Exchange :

  - Lecture de leur messagerie vocale Voix Entreprise sur leur téléphone

  - Transfert d’appels à partir d’un standard automatique de la messagerie unifiée Exchange

Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Déploiement de l’équilibrage de la charge DNS dans les pools frontaux et les pools directeurs

Le déploiement de l’équilibrage de la charge DNS dans les pools frontaux et les pools directeurs vous oblige à effectuer quelques étapes supplémentaires avec les enregistrements de noms de domaine complets et les enregistrements DNS.

  - Un pool qui utilise l’équilibrage de la charge DNS doit avoir deux noms de domaine complets : le nom de domaine complet standard du pool qui est utilisé par l’équilibrage de la charge DNS (par exemple, pool01.contoso.com) et qui est résolu en adresse IP pour chaque serveur dans le pool et un autre nom de domaine complet pour les services web du pool (par exemple, web01.contoso.com) qui est résolu en adresse IP virtuelle de ce dernier.
    
    Dans le générateur de topologies, si vous voulez déployer l’équilibrage de charge DNS pour un pool, vous devez activer la case à cocher Remplacer le nom de domaine complet du **pool des services Web internes** et taper le nom de domaine complet (FQDN) dans la page **spécifier les URL des services Web pour ce pool** .

  - Pour prendre en charge le nom de domaine complet utilisé par l’équilibrage de la charge DNS, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, pool01.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.). Veillez à inclure uniquement les adresses IP des serveurs en cours de déploiement.
    
    <div>
    

    > [!WARNING]  
    > Si vous avez plusieurs pools frontaux ou serveurs frontaux, le nom de domaine complet (FQDN) des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour tout directeur ou pool directeur doit être unique à partir d’un autre directeur ou pool Directeur, ainsi que d’un pool frontal ou d’un serveur frontal. Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>Équilibrage de charge DNS dans les pools de serveurs Edge

Vous pouvez déployer l’équilibrage de charge DNS dans les pools de serveurs Edge. Dans ce cas, vous devez tenir compte de certaines considérations.

L’utilisation de l’équilibrage de charge DNS sur vos serveurs Edge entraîne une perte des capacités de basculement dans les scénarios suivants :

  - Fédération avec les organisations qui exécutent des versions d’Office Communications Server antérieures à Lync Server 2010.

  - Échange de messages instantanés avec des utilisateurs de services de messagerie instantanée (IM\!) publics AOLand Yahoo, en plus des fournisseurs et des serveurs basés sur XMPP, tels que Google Talk.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google Talk est actuellement le seul partenaire XMPP pris en charge.</P>
    > <LI>
    > <P>À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</P></LI></UL>

    
    </div>

Ces scénarios fonctionneront tant que tous les serveurs Edge dans le pool sont opérationnels, mais si un serveur Edge est indisponible, toutes les demandes envoyées à ces scénarios échoueront au lieu d’être routées vers un autre serveur Edge.

Si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum d’Exchange 2013 pour obtenir la prise en charge de l’équilibrage de charge DNS Lync Server sur Edge. Si vous utilisez une version antérieure d’Exchange, vos utilisateurs distants ne disposeront pas des fonctionnalités de basculement pour ces scénarios de messagerie unifiée Exchange :

  - Lecture de leur messagerie vocale Voix Entreprise sur leur téléphone

  - Transfert d’appels à partir d’un standard automatique de la messagerie unifiée Exchange

Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.

Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Déploiement de l’équilibrage de charge DNS dans les pools de serveurs Edge

Pour déployer l’équilibrage de charge DNS sur l’interface externe de votre pool de serveurs Edge, vous avez besoin des entrées DNS suivantes :

  - Pour le service Edge d’accès, vous avez besoin d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge d’accès (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès sur l’un des serveurs Edge du pool.

  - Pour le service Edge de conférence Web, vous avez besoin d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge de conférence Web (par exemple, webconf.contoso.com) en adresse IP du service Edge de conférence Web sur l’un des serveurs Edge du pool.

  - Pour le service Edge audio/vidéo, vous avez besoin d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet (FQDN) du service Edge audio/vidéo (par exemple, av.contoso.com) en adresse IP du service Edge A/V sur l’un des serveurs Edge du pool.

Pour déployer l’équilibrage de la charge DNS sur l’interface interne de votre pool de serveurs Edge, vous devez ajouter un enregistrement DNS A qui résout le nom de domaine complet interne du pool de serveurs Edge en adresse IP pour chaque serveur dans le pool.

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Utilisation de l’équilibrage de charge DNS dans les pools de serveurs de médiation

Vous pouvez utiliser l’équilibrage de charge DNS sur des pools de serveurs de médiation autonomes. Tout le trafic SIP et multimédia est équilibré par l’équilibrage de charge DNS.

Pour déployer l’équilibrage de la charge DNS sur un pool de serveurs de médiation, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, mediationpool1.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.).

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blocage du trafic vers un serveur avec équilibrage de la charge DNS

Si vous utilisez l’équilibrage de la charge DNS et que vous avez besoin de bloquer le trafic sur un ordinateur spécifique, il ne suffit pas de supprimer les entrées d’adresses IP du nom de domaine complet du pool. Vous devez également supprimer l’entrée DNS pour l’ordinateur.

Notez que pour le trafic de serveur à serveur, Lync Server 2013 utilise un équilibrage de charge prenant en charge la topologie. Les serveurs lisent la topologie publiée dans le magasin central de gestion pour obtenir les noms de domaine complets des serveurs dans la topologie et distribuent automatiquement le trafic entre les serveurs. Pour empêcher un serveur de recevoir du trafic de serveur à serveur, vous devez supprimer le serveur de la topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

