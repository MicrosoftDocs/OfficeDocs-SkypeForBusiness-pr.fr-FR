---
title: Équilibrage de charge DNS dans Lync Server 2013
TOCTitle: Équilibrage de charge DNS dans Lync Server 2013
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398634(v=OCS.15)
ms:contentKeyID: 49297873
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Équilibrage de charge DNS dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

La fonctionnalité d’équilibrage de la charge DNS est une nouvelle solution logicielle de Lync Server qui réduit considérablement la charge administrative inhérente à l’équilibrage de charge sur votre réseau. L’équilibrage de charge DNS permet d’équilibrer le trafic réseau propre à Lync Server, notamment le trafic SIP et le trafic multimédia.

En déployant la solution d’équilibrage de la charge DNS, vous réduirez de manière drastique la charge administrative des programmes d’équilibrage de la charge matérielle déployés au sein de votre organisation. De plus, le travail ardu de dépannage qu’imposent les problèmes découlant d’une mauvaise configuration des programmes d’équilibrage de la charge pour le trafic SIP sera évité. Vous pouvez aussi empêcher les connexions serveur afin de mettre les serveurs hors connexion. L’équilibrage de la charge DNS permet également d’éviter que des problèmes liés aux programmes d’équilibrage de la charge matérielle n’aient une incidence sur des éléments du trafic SIP, notamment le routage de base des appels.

En optant pour l’équilibrage de la charge DNS, vous pouvez aussi acheter des programmes d’équilibrage de la charge matérielle moins chers que ceux proposés pour tous les types de trafic. Vous devez utiliser des programmes d’équilibrage de la charge dont l’interopérabilité avec Lync Server a été testée et approuvée. Pour plus d’informations sur les tests d’interopérabilité auxquels sont soumis les programmes d’équilibrage de la charge, voir « Programmes partenaires d’équilibrage de la charge Lync Server 2010 » à l’adresse <http://go.microsoft.com/fwlink/?linkid=202452>.

L’équilibrage de charge DNS est pris en charge pour les pools frontaux, les pools de serveurs Edge, les pools directeurs et les pools de serveurs de médiation autonomes.

## Équilibrage de la charge DNS dans les pools frontaux et les pools directeurs

Vous pouvez désormais utiliser l’équilibrage de la charge DNS pour le trafic SIP dans les pools frontaux et les pools directeurs. Avec l’équilibrage de charge DNS déployé, vous devrez quand même toujours utiliser les programmes d’équilibrage de la charge matérielle pour ces pools, mais seulement pour le trafic HTTPS du client vers le serveur. Le programme d’équilibrage de la charge matérielle est utilisé pour le trafic HTTPS venant des clients sur les ports 443 et 80.

Bien que le recours à des programmes d’équilibrage de la charge matérielle soit toujours nécessaire pour ces pools, leur configuration et leur administration concernera avant tout le trafic HTTPS avec lequel les administrateurs des programmes d’équilibrage de la charge matérielle sont familiarisés.

## Équilibrage de charge DNS et prise en charge d’anciens clients et serveurs

L’équilibrage de charge DNS prend en charge le basculement automatique uniquement sur les serveurs exécutant Lync Server 2013 ou Lync Server 2010, et les clients Lync 2013 et Lync 2010. Les versions précédentes des clients et d’Office Communications Server peuvent toujours se connecter aux pools exécutant l’équilibrage de charge DNS, mais si elles ne parviennent pas à établir une connexion sur le premier serveur auquel l’équilibrage de charge DNS fait référence, elles sont incapables de basculer sur un autre serveur du pool.

De plus, si vous utilisez la messagerie unifiée Exchange, vous devez utiliser au minimum Exchange 2010 SP1 pour la prise en charge intégrée pour l’équilibrage de la charge DNS de Lync Server. Si vous utilisez une version précédente d’Exchange, vos utilisateurs ne disposeront pas des fonctionnalités de basculement pour les scénarios de messagerie unifiée Exchange suivants :

  - Lecture de leur messagerie vocale Voix Entreprise sur leur téléphone

  - Transfert d’appels à partir d’un standard automatique de la messagerie unifiée Exchange

Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.

## Déploiement de l’équilibrage de la charge DNS dans les pools frontaux et les pools directeurs

Le déploiement de l’équilibrage de la charge DNS dans les pools frontaux et les pools directeurs vous oblige à effectuer quelques étapes supplémentaires avec les enregistrements de noms de domaine complets et les enregistrements DNS.

  - Un pool qui utilise l’équilibrage de la charge DNS doit avoir deux noms de domaine complets : le nom de domaine complet standard du pool qui est utilisé par l’équilibrage de la charge DNS (par exemple, pool01.contoso.com) et qui est résolu en adresse IP pour chaque serveur dans le pool et un autre nom de domaine complet pour les services web du pool (par exemple, web01.contoso.com) qui est résolu en adresse IP virtuelle de ce dernier.
    
    Dans le Générateur de topologie, si vous voulez déployer l’équilibrage de charge DNS dans un pool, vous devez, pour créer le nom de domaine complet supplémentaire pour les services web du pool, activer la case à cocher **Remplacer le nom de domaine complet du pool des services web internes** et taper le nom de domaine complet dans la page **Spécifier les URL des services web pour ce pool**.

  - Pour prendre en charge le nom de domaine complet utilisé par l’équilibrage de la charge DNS, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, pool01.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.). Veillez à inclure uniquement les adresses IP des serveurs en cours de déploiement.
    
    > [!WARNING]  
    > Si vous installez plus d’un pool de serveurs frontaux ou serveur frontal, le nom de domaine complet (FQDN) des services web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services web externes d’un serveur frontal en tant que <strong>pool01.contoso.com</strong>, vous ne pouvez pas utiliser ce nom <strong>pool01.contoso.com</strong> pour un autre pool de serveurs frontaux ou serveur frontal. Si vous déployez aussi des directeurs, le nom de domaine complet des services web externes défini pour un directeur ou un pool de directeurs doit être différent de tout autre directeur ou pool de directeurs et de tout pool de serveurs frontaux ou serveur frontal existant. Si vous choisissez de remplacer le nom des services web internes par un nom de domaine complet personnalisé, chaque nom de domaine complet doit être distinct des autres noms de pool de serveurs frontaux, directeur ou pool de directeurs.

## Équilibrage de charge DNS dans les pools de serveurs Edge

Vous pouvez déployer l’équilibrage de charge DNS dans les pools de serveurs Edge. Dans ce cas, vous devez tenir compte de certaines considérations.

L’utilisation de l’équilibrage de charge DNS sur vos serveurs Edge entraîne une perte des capacités de basculement dans les scénarios suivants :

  - Fédération avec des organisations qui exécutent des versions d’Office Communications Server antérieures à Lync Server 2010.

  - Échange de messages instantanés avec les utilisateurs de services de messagerie instantanée publique, tels que AOL et Yahoo\!, ainsi que les serveurs et fournisseurs basés sur XMPP, tels que Google Talk.
    
    > [!IMPORTANT]  
    > <ul>    
    > <li><p>Google Talk est à l’heure actuelle le seul partenaire XMPP pris en charge.</p></li>    
    > <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, voir <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>
    > </ul>


Ces scénarios fonctionneront tant que tous les serveurs Edge dans le pool sont opérationnels, mais si un serveur Edge est indisponible, toutes les demandes envoyées à ces scénarios échoueront au lieu d’être routées vers un autre serveur Edge.

Si vous utilisez la messagerie unifiée Exchange, vous devez utiliser au minimum Exchange 2013 pour la prise en charge de l’équilibrage de la charge DNS de Lync Server sur Edge. Si vous utilisez une version précédente d’Exchange, vos utilisateurs distants ne disposeront pas des fonctionnalités de basculement pour les scénarios de messagerie unifiée Exchange suivants :

  - Lecture de leur messagerie vocale Voix Entreprise sur leur téléphone

  - Transfert d’appels à partir d’un standard automatique de la messagerie unifiée Exchange

Tous les autres scénarios de messagerie unifiée Exchange fonctionneront normalement.

Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.

## Déploiement de l’équilibrage de charge DNS dans les pools de serveurs Edge

Pour déployer l’équilibrage de charge DNS sur l’interface externe de votre pool de serveurs Edge, vous avez besoin des entrées DNS suivantes :

  - Pour le service Edge d’accès, vous avez besoin d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet du service Edge d’accès (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès sur l’un des serveurs Edge dans le pool.

  - Pour le service Edge de conférence web, vous avez besoin d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet du service Edge de conférence web (par exemple, webconf.contoso.com) en adresse IP du service Edge de conférence web sur l’un des serveurs Edge dans le pool.

  - Pour le service Edge audio/vidéo, vous avez besoin d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet du service Edge audio/vidéo (par exemple, av.contoso.com) en adresse IP du service Edge audio/vidéo sur l’un des serveurs Edge dans le pool.

Pour déployer l’équilibrage de la charge DNS sur l’interface interne de votre pool de serveurs Edge, vous devez ajouter un enregistrement DNS A qui résout le nom de domaine complet interne du pool de serveurs Edge en adresse IP pour chaque serveur dans le pool.

## Utilisation de l’équilibrage de charge DNS dans les pools de serveurs de médiation

Vous pouvez utiliser l’équilibrage de charge DNS sur des pools de serveurs de médiation autonomes. Tout le trafic SIP et multimédia est équilibré par l’équilibrage de charge DNS.

Pour déployer l’équilibrage de la charge DNS sur un pool de serveurs de médiation, vous devez mettre en service DNS pour résoudre le nom de domaine complet du pool (par exemple, mediationpool1.contoso.com) en adresse IP pour chaque serveur dans le pool (par exemple, 192.168.1.1, 192.168.1.2, etc.).

## Blocage du trafic vers un serveur avec équilibrage de charge DNS

Si vous utilisez l’équilibrage de la charge DNS et que vous voulez bloquer le trafic vers un ordinateur particulier, vous devez supprimer les adresses IP dans le nom de domaine complet du pool, mais également supprimer l’entrée DNS associée à l’ordinateur.

Notez que pour le trafic serveur à serveur, Lync Server 2013 utilise un équilibrage de charge de topologie. Les serveurs lisent la topologie publiée dans le magasin central de gestion afin d’obtenir les noms de domaine complets des serveurs dans la topologie et distribuent automatiquement le trafic entre les serveurs. Pour bloquer la réception du trafic serveur à serveur pour un serveur, vous devez supprimer le serveur de la topologie.

