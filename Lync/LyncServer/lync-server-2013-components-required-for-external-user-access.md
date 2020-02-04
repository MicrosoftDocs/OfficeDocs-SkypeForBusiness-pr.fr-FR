---
title: 'Lync Server 2013 : Composants requis pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 550eb864ff7cc26eb0bfeace37759bb15b9816f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Composants requis pour l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-29_

La plupart des composants Edge sont déployés sur un réseau de périmètre. Les composants suivants constituent la topologie latérale du réseau de périmètre. Sauf indication contraire, les composants font partie des [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) et se trouvent dans le réseau de périmètre. Ces composants Edge sont les suivants :

  - Edge Servers

  - Reverse proxies

  - Firewalls

  - Directeurs (facultatif et logiquement situé sur le réseau interne)

  - Équilibrage de la charge pour les topologies Edge mises à l’échelle (avec charge DNS équilibrée ou un équilibreur de la charge matérielle)
    
    <div>
    

    > [!IMPORTANT]  
    > L’utilisation de l’équilibrage de charge DNS sur une interface et de l’équilibrage de charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser l’équilibrage de charge matérielle ou l’équilibrage de charge DNS.

    
    </div>

<div>

## <a name="edge-servers"></a>serveurs Edge

Les serveurs Edge envoient et reçoivent le trafic réseau pour les services proposés par un déploiement interne par des utilisateurs externes. Le serveur Edge exécute les services suivants :

  - **Service Edge d'**   accès le service Edge d’accès fournit un point de connexion unique et approuvé pour le trafic SIP (Session Initiation Protocol) entrant et sortant.

  - **Service Edge de conférence Web**   ce service permet aux utilisateurs externes de rejoindre des réunions hébergées sur votre déploiement interne Lync Server 2013.

  - **Service Edge a/v**   le service Edge a/v effectue des appels audio, vidéo, de partage d’application et de transfert de fichiers aux utilisateurs externes. Vos utilisateurs peuvent ajouter de l’audio et de la vidéo à des réunions qui incluent des participants externes, et ils peuvent communiquer en utilisant directement l’audio et/ou la vidéo avec un utilisateur externe dans les sessions de point à point. Le service Edge A/V fournit également une prise en charge du partage de bureau et du transfert de fichiers.

  - **Service proxy XMPP**   le service proxy XMPP accepte les messages de la messagerie électronique et les protocoles de présence (XMPP) extensibles, ainsi que les partenaires fédérés fédérés configurés.

Les utilisateurs externes autorisés peuvent accéder aux serveurs de périphérie afin de se connecter à votre déploiement interne de Lync Server 2013, mais les serveurs de périphérie ne fournissent aucun moyen pour tout autre accès au réseau interne.

<div>


> [!NOTE]  
> Les serveurs Edge sont déployés de manière à fournir des connexions pour les clients Lync et les autres serveurs Microsoft Edge compatibles (comme dans les scénarios de Fédération). Elles ne sont pas conçues pour autoriser les connexions à partir d’un autre client ou type de serveur principal. Le serveur de passerelle XMPP peut être déployé pour autoriser les connexions avec les partenaires XMPP configurés. Le serveur de périphérie et la passerelle XMPP peuvent uniquement prendre en charge les connexions de point de terminaison de ces types de client et de Fédération.



</div>

</div>

<div>

## <a name="reverse-proxy"></a>Proxy inverse

Le proxy inverse est requis pour les éléments suivants :

  - Pour permettre aux utilisateurs de se connecter à des réunions ou des conférences rendez-vous à l’aide d’URL simples

  - Pour permettre aux utilisateurs externes de télécharger le contenu d’une réunion

  - Pour permettre aux utilisateurs externes d’étendre les groupes de distribution

  - Pour permettre à l’utilisateur d’obtenir un certificat basé sur l’utilisateur pour l’authentification par certificat client

  - Pour permettre aux utilisateurs distants de télécharger des fichiers à partir du serveur du carnet d’adresses ou d’adresser des requêtes au service de requête sur le carnet d’adresses

  - Pour permettre aux utilisateurs distants d’obtenir les mises à jour du logiciel client et de l’appareil

  - Pour permettre aux appareils mobiles de détecter automatiquement les serveurs frontaux proposant des services de mobilité

  - Pour activer les notifications de transmission vers des appareils mobiles à partir d’Office 365 ou d’Apple notifications services

Pour plus d’informations sur les proxys inversés et les configurations requises pour les proxys inverse, voir les détails de la [Configuration requise pour le proxy inverse dans Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).

<div>


> [!NOTE]  
> Les utilisateurs externes n’ont pas besoin d’une connexion de réseau privé virtuel (VPN) pour votre organisation afin de participer aux communications à l’aide de Lync Server 2013. Si vous avez implémenté la technologie VPN au sein de votre organisation et que vos utilisateurs utilisent le VPN pour Lync, le trafic multimédia (par exemple, les conférences vidéo) peut être affecté. Nous vous conseillons de fournir un moyen pour le trafic multimédia de se connecter directement au service Edge AV et de contourner le VPN. Pour plus d’informations, reportez-vous à l’article de blog NextHop intitulé « activation de médias <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>Lync pour ignorer un tunnel VPN ».



</div>

</div>

<div>

## <a name="firewall"></a>Pare-feu

Vous pouvez déployer votre topologie de périphérie avec un pare-feu externe uniquement ou les pare-feu internes et externes. Les architectures de scénario incluent deux pare-feu. L’utilisation de deux pare-feu est l’approche recommandée, car elle assure le routage strict d’un bord réseau vers l’autre et protège votre déploiement interne derrière deux niveaux de pare-feu.

</div>

<div>

## <a name="director"></a>directeur

Un directeur est un rôle de serveur distinct et facultatif dans Lync Server 2013 qui ne prend pas en charge les comptes d’utilisateurs personnels ou qui fournissent des services de présence et de conférence. Il sert de serveur interne de tronçons de tronçon sur lequel un serveur de périphérie route le trafic SIP entrant destiné aux serveurs internes. Le directeur authentifie les demandes entrantes et les redirige vers le serveur ou le groupe d’accueil de l’utilisateur. En effectuant une authentification au niveau du réalisateur, vous pouvez déplacer des requêtes de comptes d’utilisateur qui sont inconnus du déploiement.

Un directeur permet d’isoler les serveurs Standard Edition et les serveurs frontaux dans les listes frontales d’Enterprise Edition d’un trafic malveillant (par exemple, les attaques par déni de service (DoS)). Si le réseau est inondé de trafic externe non valide lors d’une telle attaque, le trafic se termine au directeur. Pour plus d’informations sur l’utilisation des directeurs, voir [scénarios pour le directeur dans Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration requise pour l’équilibreur de charge matérielle pour Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

