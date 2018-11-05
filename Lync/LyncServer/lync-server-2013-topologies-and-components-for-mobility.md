---
title: 'Lync Server 2013 : Topologies et composants pour la mobilité'
TOCTitle: Topologies et composants pour la mobilité
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690037(v=OCS.15)
ms:contentKeyID: 49298687
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologies et composants pour la mobilité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Pour prendre en charge les applications mobiles Lync sur des appareils mobiles, Lync Server 2013 fournit trois services : Lync Server 2013 le service de mobilité Mcx, Lync Server 2013 le service de découverte automatique et Lync Server 2013 le service de notification push. Les Mises à jour cumulatives pour Lync Server 2013 de février 2013 ajoutent un service complémentaire, mais avancé pour les clients Lync 2013 Mobile : la prise en charge de la mobilité grâce à l’utilisation de l’API Web de communications unifiées, ou UCWA. Cette section décrit brièvement ces composants et identifie les topologies Lync Server 2013 qui prennent en charge la mobilité.

> [!NOTE]  
> Les services de mobilité sont aussi disponibles dans des déploiements hybrides. Vous n’êtes pas obligé de déployer des services pour prendre en charge la mobilité si vos utilisateurs sont hébergés en ligne. Vous devez par contre définir un paramètre pour le service de découverte automatique pour permettre aux utilisateurs mobiles d’accéder à leur identité en ligne.

> [!IMPORTANT]  
> Si vous envisagez un mécanisme quelconque de connectivité externe des utilisateurs (par exemple, par la fédération, l’accès externe des utilisateurs ou des fonctionnalités de mobilité), vous devez passer par des serveurs Edge avec un serveur Standard Edition et le serveur frontal ou pool de serveurs frontaux. Le serveur Standard Edition et le serveur frontal ou pool de serveurs frontaux n’ont pas les composants nécessaires qui permettent aux utilisateurs externes d’accéder à votre déploiement interne, ou au déploiement interne de communiquer avec vos utilisateurs externes. Pour tous les scénarios incluant des utilisateurs externes collaborant ou communiquant avec des utilisateurs internes, y compris dans les cas de mobilité, vous devez déployer au moins un serveur Edge et un proxy inverse.<br />
La <em>notification push</em> fait appel à un type de fédération des services Lync Online et héberge le centre d’échanges de notification push (PNCH, Push Notification Clearing House). La notification push fait référence aux alertes sonores, aux alertes à l’écran (sous forme de texte) et aux badges que les applications émettent vers les appareils Apple iPhone, iPad et Windows Phone quand l’appareil est inactif. Le PNCH reçoit les notifications push en provenance de Lync Server. Quand il reçoit la notification d’un message, il transfert une notification aux clients mobiles soit par le biais des services de notification Push d’Apple, soit par le biais du Service de notification Push de Lync Server 2013, en fonction du client mobile auquel le message est destiné. Le PNCH est un service obligatoire pour ces clients mobiles. Pour fédérer vers Lync Online, le PNCH utilise des serveurs Edge et des certificats pour s’assurer de la confidentialité et de l’authentification, des stratégies et des enregistrements DNS (Domain Name System, système de nom de domaine) correctement configurés. Les clients Lync Mobile Nokia Symbian et Android n’utilisent pas le PNCH. Pour plus d’informations sur la planification et le déploiement des serveurs Edge, reportez-vous à <a href="lync-server-2013-planning-for-external-user-access.md">Planification de l’accès des utilisateurs externes dans Lync Server 2013</a> et <a href="lync-server-2013-deploying-external-user-access.md">Déploiement de l’accès des utilisateurs externes dans Lync Server 2013</a>.<br />
Les clients Lync 2013 pour appareils Apple introduits dans le cadre des Mises à jour cumulatives pour Lync Server 2013 de février 2013 n’utilisent plus les notifications push ou le centre d’échange de notifications push (PNCH). Les clients Lync 2013 sur Windows Phone utilisent encore les notifications push et le PNCH.

## Composants de mobilité

Les services qui prennent en charge la mobilité sont les suivants :

  - **API Web de communications unifiées (UCWA) de Lync Server 2013**   Fournit des services pour les communications en temps réel avec des clients mobiles et web dans Lync Server 2013. Lorsque vous déployez les Mises à jour cumulatives pour Lync Server 2013 de février 2013 sur le serveur frontal et le directeur, l’installation crée un répertoire virtuel dans les services web internes et externes (UCWA). Un composant web qui fait partie du répertoire virtuel UCWA accepte les appels en provenance des clients activés pour UCWA. Les applications clientes communiquent par le biais d’une interface REST pour la présence, les contacts, la messagerie instantanée, VoIP, la conférence vidéo et la collaboration. UCWA utilise un canal basé sur P-GET pour envoyer des événements tels qu’un appel entrant, un message instantané entrant ou un message à l’application cliente.
    
    > [!NOTE]  
    > <em>REST</em> (Representational State Transfer) est un style d’architecture logicielle pour les systèmes distribués qui a été largement adopté dans de nombreux formats et convient parfaitement aux exigences des services web en général.

  - **Lync Server 2013 Service de mobilité (Mcx)**   Ce service prend en charge les fonctionnalités Lync, telles que la messagerie instantanée, la présence et les contacts sur les appareils mobiles. Le service de mobilité est installé sur chaque serveur frontal dans chaque pool qui doit prendre en charge les fonctionnalités Lync sur ces appareils. Lorsque vous installez Lync Server 2013, un nouveau répertoire virtuel (Mcx) est créé sous les sites web interne et externe sur vos serveurs frontaux.
    
    > [!IMPORTANT]  
    > Lync Server 2013 avec les Mises à jour cumulatives pour Lync Server 2013 de février 2013 prend en charge le service de mobilité introduit dans la Mise à jour cumulative pour Lync Server 2010 de novembre 2011, couramment appelé Mcx, ainsi que le composant web UCWA. La combinaison de ces deux services de mobilité procure une interopérabilité et une utilisation par les utilisateurs disposant de clients Lync 2010 Mobile et Lync 2013 Mobile sur Lync Server 2013.

  - **Service de découverte automatique de Lync Server 2013**   Ce service identifie l’emplacement de l’utilisateur et permet aux appareils mobiles et autres clients Lync de rechercher les ressources, telles que les URL internes et externes des services web Lync Server 2013 et l’URL de Mcx ou UCWA, quel que soit l’emplacement réseau. La découverte automatique utilise des noms d’hôtes codés en dur (lyncdiscoverinternal pour les utilisateurs qui se trouvent sur le réseau et lyncdiscover pour les utilisateurs en dehors du réseau) et le domaine SIP de l’utilisateur. Elle prend en charge les connexions clientes qui utilisent le protocole HTTP ou HTTPS.
    
    Le service de découverte automatique est installé sur chaque serveur frontal et sur chaque directeur dans chaque pool qui doit prendre en charge les fonctionnalités Lync sur les appareils mobiles. Lorsque vous installez le service de découverte automatique, un nouveau répertoire virtuel (Autodiscover) est créé sous le site web interne et sous le site web externe sur les serveurs frontaux et les directeurs.
    
    > [!NOTE]  
    > Le service de découverte automatique est répertorié ici car il demeure un composant essentiel lors de la fourniture de services aux clients mobiles. Le rôle de ce service dans Lync Server 2013 a été étendu de manière à fournir des services à tous les clients. Pour plus d’informations sur la planification du service de découverte automatique, reportez-vous à <a href="lync-server-2013-planning-for-autodiscover.md">Planification de la découverte automatique</a>.

  - **Service de notification push**   Il s’agit d’un service nuage qui se trouve dans le centre de données Lync Online. Lorsque l’application mobile Lync d’un appareil Apple iOS ou Windows pris en charge est inactive, elle ne peut pas répondre aux nouveaux événements (tels que les nouvelles invitations de messagerie instantanée, les messages instantanés manqués, les appels manqués ou les messages vocaux), car ces appareils ne prennent pas en charge l’exécution en arrière-plan des applications mobiles. Dans ces cas-là, une notification concernant le nouvel événement, appelée *notification push*, est envoyée à l’appareil mobile. Le service de mobilité envoie la notification au service de notification push dans le nuage, qui envoie ensuite la notification au service de notification Push d’Apple (APNS) (pour les appareils Apple iOS pris en charge) ou au système de notification de transmission de Microsoft (MPNS) (pour Windows Phone), qui l’envoie ensuite à l’appareil mobile. Après, l’utilisateur peut appuyer sur la notification sur l’appareil mobile pour activer l’application.
    
    Lync 2010 Mobile sur les appareils Apple et Windows Phone utilise les notifications push. Le client Lync 2013 Mobile pour appareils Apple introduit dans le cadre des Mises à jour cumulatives pour Lync Server 2013 de février 2013 n’utilise plus les notifications push ou le centre d’échanges de notifications push (PNCH).

Le diagramme suivant illustre l’intégration du service de notification push dans une topologie Lync Server 2013 qui utilise UCWA et des clients Lync 2013 Mobile.

![Services UCWA de notification Push](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "Services UCWA de notification Push")

Introduit dans le cadre de la Mise à jour cumulative pour Lync Server 2010 de novembre 2011, le service Mcx fournit des services aux clients Lync 2010 Mobile. Le diagramme suivant illustre le service de notification push tel qu’il s’applique à une topologie utilisant le service Mcx et des clients Lync 2010 Mobile.

![Services MCX de services de notification Push](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "Services MCX de services de notification Push")

## Topologies prises en charge

L’application des Mises à jour cumulatives pour Lync Server 2013 de février 2013 ajoute les composants web UCWA afin de prendre en charge la mobilité pour les fonctionnalités des clients Lync 2013 Mobile dans les topologies suivantes :

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

Le serveur Edge peut être un Lync Server 2010 serveur Edge.

Un déploiement de Lync Server 2013 sans les Mises à jour cumulatives pour Lync Server 2013 de février 2013 utilise le service de mobilité Mcx et peut fournir des services uniquement pour Lync 2010 Mobile.

> [!IMPORTANT]  
> Le service de mobilité est pris en charge sur serveurs frontaux colocalisé avec le rôle serveur de médiation avec deux interfaces réseau, mais vous devez effectuer les étapes nécessaires pour configurer les interfaces. Vous devez affecter les adresses IP à l’interface spécifique qui communiquera en tant que serveur de médiation et l’adresse IP de l’interface réseau qui communiquera en tant que serveur frontal. Vous pouvez effectuer ces opérations à l’aide de l’Générateur de topologie en sélectionnant l’adresse IP correcte pour chaque service, au lieu d’utiliser l’option par défaut <strong>Utiliser toutes les adresses IP configurées</strong>.

## Voir aussi

#### Autres ressources

[Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Planification de la découverte automatique](lync-server-2013-planning-for-autodiscover.md)

