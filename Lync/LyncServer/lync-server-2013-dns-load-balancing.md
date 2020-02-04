---
title: 'Lync Server 2013 : équilibrage de charge DNS'
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
ms.openlocfilehash: 30d3b88ac66ad7dc6dd3216d941f4a99fc2feedd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Équilibrage de charge DNS dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-15_

Lync Server active l’équilibrage de charge DNS, une solution logicielle permettant de réduire considérablement la surcharge d’administration pour l’équilibrage de charge sur votre réseau. L’équilibrage de charge DNS équilibre le trafic réseau unique vers Lync Server, comme le trafic SIP et le trafic multimédia.

Si vous déployez l’équilibrage de charge DNS, la surcharge d’administration de votre organisation pour les équilibreurs de charge matérielle est réduite. Par ailleurs, le dépannage complexe des problèmes liés à la configuration incompatibilité des équilibreurs de charge pour le trafic SIP sera éliminé. Vous pouvez également empêcher les connexions au serveur pour pouvoir mettre en ligne des serveurs. L’équilibrage de charge DNS vérifie également que les problèmes liés à l’équilibrage de charge matérielle n’affectent pas les éléments du trafic SIP tels que le routage des appels de base.

Si vous utilisez l’équilibrage de charge DNS, vous pouvez également être en mesure d’acheter des équilibreurs de charge matérielle économiques que si vous utilisiez les équilibreurs de charge matérielle pour tous les types de trafic. Vous devez utiliser des équilibreurs de charge qui ont passé des tests de compétences d’interopérabilité avec Lync Server. Pour plus d’informations sur le test de l’interopérabilité de l’équilibrage de charge, voir « partenaires de [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)l’équilibrage de charge Lync Server 2010 » à l’adresse.

Le service d’équilibrage de la charge DNS est pris en charge pour les pools front-end, les pools de serveurs Edge, les pools de directeurs et les pools de serveurs de médiation autonome

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Équilibrage de charge DNS pour les pools front-end et les pools de directeurs

Vous pouvez utiliser l’équilibrage de charge DNS pour le trafic SIP sur les listes frontales et les pools de Director. Après le déploiement de l’équilibrage de charge DNS, vous devez également utiliser des équilibreurs de charge matérielle pour ces pools, mais uniquement pour le trafic HTTPs de client à serveur. L’équilibrage de charge matérielle est utilisé pour le trafic HTTPs des clients sur les ports 443 et 80.

Même si vous avez encore besoin d’équilibreurs de charge matérielle pour ces pools, leur configuration et leur administration s’adresseront essentiellement au trafic HTTPs, que les administrateurs des équilibreurs de charge matérielle sont habitués.

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Équilibrage de charge DNS et prise en charge de clients et de serveurs plus anciens

L’équilibrage de charge DNS prend en charge le basculement automatique uniquement pour les serveurs exécutant Lync Server 2013 ou Lync Server 2010 ainsi que les clients Lync 2013 et Lync 2010. Les versions antérieures de clients et d’Office Communications Server peuvent toujours se connecter aux pools exécutant l’équilibrage de charge DNS, mais, si elles ne peuvent pas établir une connexion au premier serveur auquel l’équilibrage de charge DNS fait référence, elles ne peuvent pas basculer sur un autre serveur du pool. .

Par ailleurs, si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum de Exchange 2010 SP1 pour obtenir une prise en charge de l’équilibrage de charge DNS de Lync Server. Si vous utilisez une version antérieure d’Exchange, vos utilisateurs ne disposent pas des fonctionnalités de basculement pour ces scénarios de messagerie unifiée Exchange :

  - Lecture de la messagerie vocale de votre entreprise sur son téléphone

  - Transfert d’appels à partir d’un standard automatique de messagerie unifiée Exchange

Tous les autres scénarios Exchange UM fonctionnent correctement.

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Déploiement de l’équilibrage de charge DNS pour les pools front-end et les pools de directeurs

Le déploiement de l’équilibrage de charge DNS pour les pools principaux et les pools de directeurs nécessite que vous effectuiez quelques étapes supplémentaires avec les noms de domaine complets et les enregistrements DNS.

  - Un pool qui utilise l’équilibrage de charge DNS doit avoir deux noms de domaine complets (FQDN) du pool standard utilisés par l’équilibrage de charge DNS (par exemple, pool01.contoso.com), et est résolu sur l’IPs physique des serveurs du pool et un autre nom de domaine complet pour les services Web du pool (par exemple, web01.contoso.com), qui est résolue en adresse IP virtuelle du pool.
    
    Dans le générateur de topologie, si vous voulez déployer l’équilibrage de charge DNS pour un pool, pour créer ce nom de domaine complet supplémentaire pour les services Web du pool, vous devez activer la case à cocher **ignorer le nom de domaine complet du pool de services Web internes** , puis taper le nom de domaine complet (FQDN) dans la page **spécifier les URL des services Web pour ce pool** .

  - Pour prendre en charge le FQDN utilisé par l’équilibrage de charge DNS, vous devez configurer le système DNS pour résoudre le nom de domaine complet (par exemple, pool01.contoso.com) pour les adresses IP de tous les serveurs du pool (par exemple, 192.168.1.1, 192.168.1.2, etc.). Vous ne devez inclure que les adresses IP des serveurs actuellement déployés.
    
    <div>
    

    > [!WARNING]  
    > Si vous avez plusieurs pools front-end ou serveur frontal, le nom de domaine complet des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour n’importe quel directeur ou pool de réalisateur doit être unique à partir d’un autre directeur ou pool de directeurs, ainsi que sur n’importe quel pool frontal ou serveur frontal. Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de réalisateur.

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>Équilibrage de charge DNS sur les pools de serveurs Edge

Vous pouvez déployer l’équilibrage de charge DNS sur les pools de serveurs de périphérie. Dans le cas contraire, vous devez tenir compte de certaines considérations.

L’utilisation de l’équilibrage de charge DNS sur votre serveur Edge entraîne une perte de fonctionnalité de basculement dans les cas suivants :

  - Fédération avec des organisations qui utilisent des versions d’Office Communications Server précédées d’une version antérieure à Lync Server 2010.

  - Échangez des messages instantanés avec des utilisateurs de services de messagerie instantanée publique\!AOLand Yahoo, en plus des fournisseurs et des serveurs utilisant la fonction de messagerie vocale, tels que Google Talk.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Pour le moment, Google Talk est le seul partenaire XMPP pris en charge.</P>
    > <LI>
    > <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo ! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P></LI></UL>

    
    </div>

Ces scénarios fonctionneront tant que tous les serveurs Edge du pool seront opérationnels, mais si un serveur Edge n’est pas disponible, toutes les demandes de ces scénarios qui y sont envoyés échoueront au lieu d’être routés vers un autre serveur Edge.

Si vous utilisez la messagerie unifiée Exchange, vous devez utiliser un minimum d’Exchange 2013 pour obtenir une prise en charge de l’équilibrage de charge DNS de Lync Server sur Edge. Si vous utilisez une version antérieure d’Exchange, vos utilisateurs distants ne disposent pas des fonctionnalités de basculement pour ces scénarios de messagerie unifiée Exchange :

  - Lecture de la messagerie vocale de votre entreprise sur son téléphone

  - Transfert d’appels à partir d’un standard automatique de messagerie unifiée Exchange

Tous les autres scénarios Exchange UM fonctionnent correctement.

L’interface Edge interne et l’interface Edge externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface Edge et l’équilibrage de la charge matérielle sur l’autre interface Edge.

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Déploiement de l’équilibrage de charge DNS sur les pools de serveurs de périphérie

Pour déployer l’équilibrage de charge DNS sur l’interface externe de votre pool de serveurs Edge, vous avez besoin des entrées DNS suivantes :

  - Pour le service Edge d’accès, vous avez besoin d’une entrée pour chaque serveur du pool. Chaque entrée doit résoudre le nom de domaine complet du service Edge d’accès (par exemple, sip.contoso.com) en adresse IP du service Edge d’accès sur l’un des serveurs Edge du pool.

  - Pour le service Edge de conférence Web, vous avez besoin d’une entrée pour chaque serveur du pool. Chaque entrée doit résoudre le nom de domaine complet (par exemple, webconf.contoso.com) de l’adresse IP du service Edge de conférence Web sur l’un des serveurs Edge du pool.

  - Pour le service Edge audio/vidéo, vous avez besoin d’une entrée pour chaque serveur dans le pool. Chaque entrée doit résoudre le nom de domaine complet (par exemple, av.contoso.com) de l’adresse IP du service Edge A/V sur l’un des serveurs Edge du pool.

Pour déployer l’équilibrage de charge DNS sur l’interface interne de votre pool de serveurs Edge, vous devez ajouter un enregistrement DNS A, qui résout le nom de domaine complet (FQDN) du pool de serveurs Edge, à l’adresse IP de chaque serveur du pool.

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Utilisation de l’équilibrage de charge DNS sur les pools de serveurs de médiation

Vous pouvez utiliser l’équilibrage de charge DNS sur les pools de serveurs de médiation autonomes. Le trafic SIP et de média est équilibré par l’équilibrage de charge DNS.

Pour déployer l’équilibrage de charge DNS sur un pool de serveurs de médiation, vous devez configurer le DNS pour résoudre le nom de domaine complet (par exemple, mediationpool1.contoso.com) pour les adresses IP de tous les serveurs du pool (par exemple, 192.168.1.1, 192.168.1.2, etc.).

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blocage du trafic vers un serveur avec l’équilibrage de charge DNS

Si vous utilisez l’équilibrage de charge DNS et que vous voulez bloquer le trafic vers un ordinateur particulier, vous devez supprimer les adresses IP dans le nom de domaine complet du pool, mais également l’entrée DNS associée à l’ordinateur.

Notez que pour le trafic de serveur à serveur, Lync Server 2013 utilise l’équilibrage de charge prenant en charge la topologie. Les serveurs lisent la topologie publiée dans le magasin central de gestion pour obtenir les noms de domaine complets des serveurs dans la topologie et distribuent automatiquement le trafic entre les serveurs. Pour empêcher un serveur de recevoir du trafic de serveur à serveur, vous devez supprimer le serveur de la topologie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

