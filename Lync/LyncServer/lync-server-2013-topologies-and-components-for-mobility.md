---
title: 'Lync Server 2013 : topologies et composants pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ccce5823e997cafc5e8c8e7555df18bc67d1fe6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Topologies et composants pour la mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Pour prendre en charge les applications mobiles Lync sur des appareils mobiles, Lync Server 2013 fournit trois services : Lync Server 2013 MCX Mobility service, Lync Server 2013 Autodiscover Service et Lync Server 2013 service de notification poussé. Les mises à jour cumulatives pour Lync Server 2013 : février 2013 ajoutent un service gratuit, mais avancé, pour les clients mobiles Lync 2013 — prise en charge de la mobilité via l’utilisation de l’API Web Unified Communications, ou UCWA. Cette section décrit brièvement ces composants et identifie les topologies Lync Server 2013 qui prennent en charge la mobilité.

<div>


> [!NOTE]  
> Les services de mobilité sont aussi disponibles dans des déploiements hybrides. Vous n’êtes pas obligé de déployer des services pour prendre en charge la mobilité si vos utilisateurs sont hébergés en ligne. Vous devez définir un paramètre pour le service de découverte automatique pour permettre aux utilisateurs mobiles de trouver leur identité en ligne.



</div>

<div>


> [!IMPORTANT]  
> Si vous planifiez une connectivité utilisateur externe (par exemple, la Fédération, l’accès des utilisateurs externes ou les fonctionnalités de mobilité), vous devez utiliser des serveurs Edge avec le serveur Standard Edition et le serveur frontal ou le pool frontal. Le serveur Standard Edition et le serveur frontal ou le pool frontal ne disposent pas des composants nécessaires pour permettre aux utilisateurs externes d’accéder à votre déploiement interne ou au déploiement interne de communiquer avec vos utilisateurs externes. Pour tous les scénarios qui incluent les utilisateurs externes qui collaborent ou communiquent avec des utilisateurs internes, y compris la mobilité, vous devez déployer au moins un serveur Edge et un proxy inverse.<BR>La <EM>notification d’envoi</EM> utilise un type de Fédération pour Lync Online Services, qui héberge le centre d’échanges de notifications (échanges). Notifications push désigne les alertes sonores, les alertes à l’écran (texte) et les badges qui sont envoyés par les applications à Apple iPhone, iPad et Windows Phone, lorsque l’appareil mobile est inactif. ÉCHANGES reçoit des notifications de type transmission de Lync Server. Lorsque échanges reçoit une notification d’un message, échanges transfère une notification aux clients mobiles via le service Apple Notification Services ou le service de notification directe de Lync Server 2013, en fonction du client mobile auquel le message est destiné. Le PNCH est un service obligatoire pour ces clients mobiles. Pour se fédérer à Lync Online, échanges utilise des serveurs Edge et des certificats pour garantir la confidentialité et l’authentification, les stratégies et les enregistrements DNS (Domain Name System) correctement configurés. Les clients mobiles Lync Symbian Symbian et Android n’utilisent pas échanges. Pour plus d’informations sur la planification et le déploiement des serveurs Edge, consultez la rubrique <A href="lync-server-2013-planning-for-external-user-access.md">planification de l’accès des utilisateurs externes dans Lync server 2013</A> et <A href="lync-server-2013-deploying-external-user-access.md">déploiement de l’accès des utilisateurs externes dans Lync Server 2013</A>.<BR>Les clients mobiles Lync 2013 pour les périphériques Apple introduits avec les mises à jour cumulatives pour Lync Server 2013 : février 2013 n’utilisent plus la notification de transmission ou le centre d’échanges de notifications (échanges). Les clients mobiles Lync 2013 sur Windows Phone utilisent toujours la notification de transmission et le (échanges).



</div>

<div>

## <a name="mobility-components"></a>Composants de mobilité

Les services qui prennent en charge la mobilité sont les suivants :

  - **Lync Server 2013 Unified Communications Web API (UCWA)**   fournit des services pour les communications en temps réel avec les clients mobiles et Web dans Lync Server 2013. Lorsque vous déployez les mises à jour cumulatives pour Lync Server 2013 : février 2013 sur le serveur frontal et le directeur, l’installation crée un répertoire virtuel dans les services Web internes et externes (Ucwa). Un composant Web qui fait partie du répertoire virtuel Ucwa accepte les appels des clients à extension UCWA. Les applications clientes communiquent via une interface REST pour la présence, les contacts, la messagerie instantanée, la voix sur IP, la vidéoconférence et la collaboration. UCWA utilise un canal basé sur P-GET pour envoyer des événements, tels qu’un appel entrant, un message instantané entrant ou un message à l’application cliente.
    
    <div>
    

    > [!NOTE]  
    > <EM>Rest</EM> ou Representational State Transfer, est un style d’architecture logicielle pour les systèmes distribués qui a été largement adopté sous de nombreuses formes et qui est bien adapté aux exigences des services Web en général.

    
    </div>

  - **Service de mobilité Lync Server 2013 (MCX)**   ce service prend en charge les fonctionnalités Lync, telles que la messagerie instantanée, la présence et les contacts sur les appareils mobiles. Le service de mobilité est installé sur chaque serveur frontal dans chaque pool qui doit prendre en charge la fonctionnalité Lync sur les appareils mobiles. Lorsque vous installez Lync Server 2013, un nouveau répertoire virtuel (MCX) est créé sous le site Web interne et le site Web externe sur vos serveurs frontaux.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 avec les mises à jour cumulatives pour Lync Server 2013 : le 2013 février prend en charge le service de mobilité introduit dans la mise à jour cumulative de Lync Server 2010 : novembre 2011, communément appelée MCX, et le composant Web UCWA. L’Association de ces deux services de mobilité offre une interopérabilité et une utilisation par les utilisateurs avec les clients mobiles Lync 2010 mobile et Lync 2013 sur Lync Server 2013.

    
    </div>

  - **Service de découverte automatique Lync Server 2013**   ce service identifie l’emplacement de l’utilisateur et permet aux appareils mobiles et à d’autres clients Lync de localiser les ressources, telles que les URL internes et externes des services Web Lync Server 2013, ainsi que l’URL du MCX ou de UCWA, quel que soit l’emplacement réseau. La découverte automatique utilise des noms d’hôte codés en dur (lyncdiscoverinternal pour les utilisateurs au sein du réseau ; lyncdiscover pour les utilisateurs en dehors du réseau) et le domaine SIP de l’utilisateur. Il prend en charge les connexions client qui utilisent le protocole HTTP ou HTTPs.
    
    Le service de découverte automatique est installé sur chaque serveur frontal et sur chaque directeur de chaque pool qui prend en charge la fonctionnalité Lync sur les appareils mobiles. Lorsque vous installez le service de découverte automatique, un nouveau répertoire virtuel (découverte automatique) est créé sous le site Web interne et le site Web externe, sur les serveurs frontaux et les directeurs.
    
    <div>
    

    > [!NOTE]  
    > Le service de découverte automatique est répertorié ici, car il reste un composant essentiel lors de la fourniture de services client mobiles. Le rôle de découverte automatique dans Lync Server 2013 a été étendu pour fournir des services pour tous les clients. Pour plus d’informations sur la planification du service de découverte automatique, voir <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.

    
    </div>

  - **Service de notifications d’envoi**   ce service est un service en nuage qui se trouve dans le centre de données Lync Online. Lorsque l’application mobile Lync sur un périphérique ou un téléphone Apple iOS pris en charge est inactive, elle ne peut pas répondre à de nouveaux événements, tels qu’une nouvelle invitation de messagerie instantanée, un message instantané manqué, un appel en absence ou la messagerie vocale, car ces appareils ne prennent pas en charge applications mobiles s’exécutant en arrière-plan. Dans ce cas, une notification de nouvel événement, appelée notification de *transmission*, est envoyée à l’appareil mobile. Le service de mobilité envoie la notification au service de notifications d’envoi sur le Cloud, qui envoie ensuite la notification au service de notifications d’envoi de message Apple (APNS) (pour les appareils iOS d’Apple pris en charge) ou au service de notifications Microsoft (MPNS ) (pour Windows Phone), qui le transmet ensuite à l’appareil mobile. L’utilisateur peut ensuite répondre à la notification sur l’appareil mobile pour activer l’application.
    
    Les appareils Lync 2010 mobile sur Apple et Windows Phone utilisent des notifications de type transmission. Le client mobile Lync 2013 pour les périphériques Apple introduits avec les mises à jour cumulatives pour Lync Server 2013 : février 2013 n’utilise plus de notifications d’envoi ou le centre d’échanges de notifications (échanges).

Le diagramme suivant illustre comment le service de notifications d’envoi de notifications est adapté dans une topologie Lync Server 2013 qui utilise les clients mobiles UCWA et Lync 2013.

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Introduit dans la mise à jour cumulative pour Lync Server 2010 : novembre 2011, le service MCX fournit des services aux clients mobiles Lync 2010. Le diagramme suivant illustre le service de notifications d’envoi tel qu’il s’applique à une topologie à l’aide des clients mobiles MCX et Lync 2010.

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>Topologies prises en charge

Application des mises à jour cumulatives pour Lync Server 2013 : le 2013 février ajoute les composants Web UCWA pour prendre en charge la mobilité pour les fonctionnalités de client mobile Lync 2013 dans les topologies suivantes :

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

Le serveur Edge peut être un serveur Edge Lync Server 2010.

Un déploiement Lync Server 2013 sans les mises à jour cumulatives pour Lync Server 2013 : le 2013 février utilisera le service de mobilité MCX et ne pourra fournir des services que pour Lync 2010 mobile.

<div>


> [!IMPORTANT]  
> Le service de mobilité est pris en charge sur les serveurs frontaux colocalisés avec le rôle de serveur de médiation avec deux interfaces réseau, mais vous devez prendre les mesures nécessaires pour configurer les interfaces. Vous devez affecter les adresses IP à l’interface spécifique qui communiquera en tant que serveur de médiation, et l’adresse IP de l’interface réseau qui communiquera en tant que serveur frontal. Vous pouvez effectuer cette opération dans le générateur de topologie en sélectionnant l’adresse IP correcte pour chaque service, au lieu d’utiliser la valeur par défaut <STRONG>utiliser toutes les adresses IP configurées</STRONG>.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Planification de la découverte automatique dans Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

