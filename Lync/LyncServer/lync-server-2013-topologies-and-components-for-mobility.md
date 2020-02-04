---
title: 'Lync Server 2013 : Topologies et composants pour la mobilité'
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
ms.openlocfilehash: 739deecf47e25e57ca0175c29a2721e509f8dbe2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Topologies et composants pour la mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Pour prendre en charge les applications mobiles Lync sur les appareils mobiles, Lync Server 2013 fournit trois services : Lync Server 2013 MCX Mobility service, Lync Server 2013 de découverte automatique et service de notification Poussée Lync Server 2013. Les mises à jour cumulatives de Lync Server 2013 : février 2013 ajoute un service gratuit, mais avancé, pour les clients mobiles Lync 2013 : prise en charge de la mobilité par le biais de l’utilisation de l’API Web de communications unifiées, ou UCWA. Cette section décrit brièvement ces composants et identifie les topologies Lync Server 2013 qui prennent en charge la mobilité.

<div>


> [!NOTE]  
> Les services de mobilité sont également disponibles dans les déploiements hybrides. Vous n’êtes pas tenu de déployer des services pour la mobilité si vos utilisateurs sont hébergés en ligne. Pour permettre aux utilisateurs mobiles de rechercher leur identité en ligne, vous devez définir un paramètre pour le service de découverte automatique.



</div>

<div>


> [!IMPORTANT]  
> Si vous planifiez une connectivité utilisateur externe (par exemple, une Fédération, un accès utilisateur externe ou des fonctionnalités de mobilité), vous devez utiliser les serveurs Edge avec Standard Edition Server, le serveur frontal ou le pool frontal. Le serveur Standard Edition et le serveur frontal ou le pool frontal ne disposent pas des composants nécessaires pour permettre aux utilisateurs externes d’accéder à votre déploiement interne ou pour le déploiement interne de communiquer avec les utilisateurs externes. Dans tous les cas où les utilisateurs externes collaborent ou communiquent avec des utilisateurs internes, y compris la mobilité, vous devez déployer au moins un serveur Edge et un proxy inverse.<BR>La <EM>notification de transmission</EM> utilise un type de Fédération pour les services Lync Online, qui héberge le centre de suppression des notifications de transmission (PNCH). La notification push fait référence aux alertes sonores, aux alertes à l’écran (texte) et aux badges envoyés par les applications sur l’Apple iPhone, iPad et Windows Phone, lorsque l’appareil mobile n’est pas actif. PNCH reçoit les notifications de transmission de Lync Server. Lorsque PNCH reçoit une notification de message, PNCH envoie une notification aux clients mobiles par le biais du service de notifications d’applets d’Apple ou du service de notifications de transmission de Lync Server 2013, en fonction du client mobile pour lequel le message est destiné. PNCH est un service requis pour ces clients mobiles. Pour fédérer sur Lync Online, PNCH utilise des serveurs de périphérie et des certificats pour garantir la confidentialité et l’authentification, les politiques et les enregistrements DNS (Domain Name System) correctement configurés. Les clients mobiles Lync Symbian et Android n’utilisent pas PNCH. Pour plus d’informations sur la planification et le déploiement de serveurs Edge, voir <A href="lync-server-2013-planning-for-external-user-access.md">planification d’un accès utilisateur externe dans Lync server 2013</A> et déploiement d’un <A href="lync-server-2013-deploying-external-user-access.md">accès utilisateur externe dans Lync Server 2013</A>.<BR>Les clients mobiles Lync 2013 pour les appareils Apple introduits avec les mises à jour cumulatives de Lync Server 2013 : février 2013 n’utilise plus la notification d’émission ou la chambre d’échanges de notifications de transmission (PNCH). Les clients mobiles Lync 2013 sur Windows Phone utilisent toujours les notifications de transmission et le (PNCH).



</div>

<div>

## <a name="mobility-components"></a>Composants de mobilité

Les services qui prennent en charge la mobilité sont les suivants :

  - **L’API Web de communications unifiées (UCWA)**   Lync Server 2013 fournit des services pour communiquer en temps réel avec des clients mobiles et Web dans Lync Server 2013. Lorsque vous déployez les mises à jour cumulatives pour Lync Server 2013 : février 2013 sur le serveur frontal et le directeur, l’installation crée un répertoire virtuel dans les services Web internes et externes (Ucwa). Un composant WebPart qui fait partie du répertoire virtuel Ucwa accepte les appels de clients UCWA. Les applications clientes communiquent par le biais d’une interface REST pour la présence, les contacts, la messagerie instantanée, les appels VoIP, les conférences vidéo et la collaboration. UCWA utilise un canal basé sur P pour envoyer des événements, tels qu’un appel entrant, un message instantané entrant ou un message à l’application cliente.
    
    <div>
    

    > [!NOTE]  
    > Le transfert d’état <EM>Rest</EM> ou de présentation est un style architectural logiciel pour les systèmes distribués qui ont été largement adoptés dans de nombreuses formes et qui sont bien adaptés aux exigences des services Web en général.

    
    </div>

  - **Service de mobilité Lync Server 2013 (MCX)**   ce service prend en charge les fonctionnalités de Lync, telles que la messagerie instantanée, la présence et les contacts, sur les appareils mobiles. Le service de mobilité est installé sur chaque serveur frontal de chaque pool prenant en charge la fonctionnalité Lync sur les appareils mobiles. Lorsque vous installez Lync Server 2013, un nouveau répertoire virtuel (MCX) est créé sous le site Web interne et le site Web externe sur votre serveur frontal.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 avec les mises à jour cumulatives de Lync Server 2013:2013 février prend en charge à la fois le service de mobilité présenté dans la mise à jour cumulative de Lync Server 2010 : de 2011 novembre, connu sous le nom de MCX et du composant WebPart UCWA. La combinaison de ces deux services de mobilité fournit une interopérabilité et une utilisation par les utilisateurs des clients de Lync 2010 mobile et de Lync 2013 mobile sur Lync Server 2013.

    
    </div>

  - **Service de découverte automatique Lync Server 2013**   ce service identifie l’emplacement de l’utilisateur et permet aux appareils mobiles et aux autres clients Lync de rechercher des ressources (par exemple, les URL internes et externes pour les services Web de Lync Server 2013) et l’URL du MCX ou UCWA, quel que soit l’emplacement réseau. La découverte automatique utilise des noms d’hôtes encodés (lyncdiscoverinternal pour les utilisateurs à l’intérieur du réseau ; lyncdiscover pour les utilisateurs en dehors du réseau) et le domaine SIP de l’utilisateur. Elle prend en charge les connexions clientes qui utilisent le protocole HTTP ou HTTPS.
    
    Le service de découverte automatique est installé sur chaque serveur frontal et sur tous les directeurs de chaque liste qui prend en charge la fonctionnalité Lync sur les appareils mobiles. Lorsque vous installez le service de découverte automatique, un nouveau répertoire virtuel (découverte automatique) est créé sous le site Web interne et le site Web externe, sur les serveurs et les directeurs du serveur principal.
    
    <div>
    

    > [!NOTE]  
    > Le service de découverte automatique est répertorié ici, car il reste un composant essentiel lors de la fourniture de services pour les clients mobiles. Le rôle de découverte automatique dans Lync Server 2013 a été développé de manière à fournir des services à tous les clients. Pour plus d’informations sur la planification du service de découverte automatique, voir <A href="lync-server-2013-planning-for-autodiscover.md">planification de la découverte automatique dans Lync Server 2013</A>.

    
    </div>

  - **Service de notifications de transmission**   ce service est un service basé sur le Cloud qui se trouve dans le centre de données Lync Online. Lorsque l’application mobile Lync sur un appareil iOS Apple ou Windows Phone pris en charge est désactivée, elle ne peut pas répondre aux nouveaux événements, tels qu’une nouvelle invitation à une messagerie instantanée, un message instantané manqué, un appel manqué ou une messagerie vocale, car ces appareils ne sont pas pris en charge. applications mobiles s’exécutant en arrière-plan. Dans ces cas, une notification du nouvel événement (appelé notification de *transmission*) est envoyée à l’appareil mobile. Le service de mobilité envoie la notification au service de notifications de transmission Cloud, qui envoie ensuite la notification au service de notifications de transmission d’Apple (APNS) (pour les appareils iOS iOS pris en charge) ou au service de notifications Microsoft émission (MPNS ) (pour Windows Phone), qui l’envoie ensuite à l’appareil mobile. L’utilisateur peut alors répondre à la notification sur l’appareil mobile pour activer l’application.
    
    Le mobile Lync 2010 sur les appareils Apple et Windows Phone utilisent les notifications de transmission. Le client mobile 2013 Lync pour les appareils Apple introduits avec les mises à jour cumulatives pour Lync Server 2013:2013 février n’utilise plus la notification d’émission ou la chambre d’échanges de notifications de transmission (PNCH).

Le diagramme suivant illustre le fonctionnement du service de notifications d’émission au sein d’une topologie Lync Server 2013 qui utilise les clients mobiles UCWA et Lync 2013.

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Introduction dans la mise à jour cumulative pour Lync Server 2010:2011 novembre, le service MCX fournit des services aux clients mobiles Lync 2010. Le diagramme suivant illustre le service de notifications d’émission tel qu’il s’applique à une topologie utilisant des clients mobiles MCX et Lync 2010.

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>Topologies prises en charge

L’application des mises à jour cumulatives pour Lync Server 2013 : février 2013 ajoute les composants Web UCWA pour la prise en charge de la mobilité pour les fonctionnalités du client mobile Lync 2013 dans les topologies suivantes :

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

Le serveur Edge peut être un serveur Edge Lync Server 2010.

Un déploiement de Lync Server 2013 sans les mises à jour cumulatives de Lync Server 2013:2013 février utilise le service de mobilité MCX et peut fournir des services uniquement pour Lync 2010 mobile.

<div>


> [!IMPORTANT]  
> Le service de mobilité est pris en charge sur les serveurs front-end possédant le rôle serveur de médiation avec deux interfaces réseau, mais vous devez prendre les mesures appropriées pour configurer les interfaces. Vous devez affecter les adresses IP à l’interface spécifique qui communiquera en tant que serveur de médiation et l’adresse IP de l’interface réseau qui communiquera en tant que serveur frontal. Pour cela, vous pouvez sélectionner l’adresse IP correcte pour chaque service au lieu d’utiliser la valeur par défaut <STRONG>utiliser toutes les adresses IP configurées</STRONG>.



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

