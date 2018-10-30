---
title: 'Lync Server 2013 : Tâches de déploiement du contrôle d’appel distant'
TOCTitle: Tâches de déploiement du contrôle d’appel distant
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558624(v=OCS.15)
ms:contentKeyID: 49296479
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tâches de déploiement du contrôle d’appel distant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette rubrique décrit les tâches de déploiement que vous devez effectuer pour activer le contrôle d’appel distant à l’intention des utilisateurs dans votre environnement Lync Server.

> [!NOTE]  
> Si vous transférez les utilisateurs activés pour le contrôle d’accès distant dans Microsoft Office Communicator 2007 R2, vous devez effectuer une tâche de déploiement supplémentaire avant de procéder aux tâches de déploiement du contrôle d’appel distant décrites dans cette rubrique. Au cours du processus de transfert vers Lync Server, les entrées d’applications approuvées (auparavant appelées <em>entrées d’hôtes autorisés</em> ) doivent être supprimées à l’aide des outils d’administration Office Communications Server 2007 R2 de façon appropriée.<br />
Pour plus d’informations sur la suppression d’hôtes autorisés, reportez-vous à <a href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Suppression d’un hôte autorisé hérité dans Lync Server 2013 (facultatif)</a>.

## Étape 1 : Installer la passerelle SIP/CSTA et la configurer de sorte qu’elle communique avec le PBX

Vous devez installer au moins une passerelle SIP/CSTA capable de se connecter à Lync Server et à l’autocommutateur privé (PBX) de votre environnement afin que les utilisateurs puissent accéder aux fonctionnalités de contrôle d’accès distant. Une passerelle SIP/CSTA est une passerelle entre un serveur SIP et une application CSTA (Computer-Supported Telecommunications Application). Quel que soit le nombre de passerelles que vous installez, chaque utilisateur ne peut être configuré qu’avec une seule passerelle ou un seul PBX. Si votre PBX existant ne dispose pas d’une interface SIP/CSTA, déployez une passerelle SIP/CSTA pouvant prendre en charge le PBX, ainsi que les protocoles de signalisation propriétaires propres au fournisseur du PBX. Pour plus d’informations sur ce que les passerelles prennent en charge, renseignez-vous directement auprès du fournisseur.

Quand vous êtes sur le point de déployer une passerelle SIP/CSTA pouvant être intégrée à Lync Server pour le contrôle d’appel distant, renseignez-vous auprès du fournisseur de la passerelle ou consultez la documentation de celle-ci pour connaître la syntaxe requise par la passerelle concernant les informations suivantes :

  - URI du serveur de ligne de la passerelle

  - URI de ligne pour les utilisateurs qui seront affectés à la passerelle

Vous devez fournir les valeurs des paramètres précédents au cours de la configuration des utilisateurs, car la passerelle en a besoin pour se connecter correctement au PBX et lui transmettre le trafic.

Vous pouvez consulter la liste des fournisseurs sur le site web du programme Microsoft Communications unifiées Open Interoperability à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).

## Étape 2 : Configurer Lync Server pour acheminer les requêtes CSTA vers la passerelle SIP/CSTA

Vous devez créer des itinéraires statiques sur les pools Lync Server vers l’adresse de destination (URI du serveur) de toutes les passerelles SIP/CSTA de votre déploiement, vers lesquelles vous envisagez d’acheminer les requêtes de contrôle d’appel distant. Vous devez également créer une entrée d’application approuvée qui correspond à chaque adresse de destination. Lorsque vous désignez la passerelle en tant qu’application approuvée, elle est autorisée à fonctionner dans l’environnement Lync Server, même si elle a été développée par un fournisseur tiers (elle fonctionnera en tant que *service externe* , car il s’agit d’un service qui n’est pas intégré au produit). Enfin, si Lync Server se connectera à la passerelle SIP/CSTA via une connexion TCP (Transmission Control Protocol) au lieu d’une connexion TLS (Transport Layer Security), vous devez également définir l’adresse IP de la passerelle à l’aide du Générateur de topologie.

Pour plus d’informations sur les itinéraires statiques, reportez-vous à [Configuration d’un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Pour plus d’informations sur la configuration des entrées d’applications approuvées, reportez-vous à [Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Pour plus d’informations sur la définition de l’adresse IP d’une passerelle SIP/CSTA dans le Générateur de topologie, reportez-vous à [Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

## Étape 3 : Configurer les utilisateurs Lync pour le contrôle d’appel distant

Une fois que les utilisateurs ont été activés pour Lync Server, vous pouvez les activer pour le contrôle d’accès distant avec le Panneau de configuration Lync Server ou Lync Server Management Shell. C’est également au cours de cette étape que vous devez affecter à chaque utilisateur un URI de serveur de ligne et un URI de ligne. L’URI de serveur de ligne est l’URI SIP de la passerelle SIP/CSTA que vous envisagez d’affecter à l’utilisateur. L’URI de ligne est le numéro de téléphone unique affecté à l’utilisateur.

Pour plus d’informations sur la configuration des utilisateurs pour le contrôle d’appel distant, reportez-vous à [Activation des utilisateurs Lync pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

## Étape 4 : Définir les règles de normalisation des numéros de téléphone Lync Server

Dans les scénarios de contrôle d’accès distant, Lync Server utilise des règles de normalisation des numéros de téléphone pour convertir les numéros de téléphone qu’il reçoit de la passerelle SIP/CSTA au format E.164. Les numéros de téléphone doivent être dans ce format standard pour que certaines fonctionnalités de contrôle d’appel distant fonctionnent correctement. Le contrôle d’appel distant utilise les mêmes règles de normalisation des numéros de téléphone que celles que vous configurez pour la normalisation des numéros de téléphone du Service de carnet d’adresses, qui sont différentes des règles de normalisation utilisées pour Voix Entreprise.

Pour plus d’informations sur l’utilisation des règles de normalisation des numéros de téléphone par le contrôle d’accès distant, reportez-vous à [Contrôle d’appel distant et normalisation des numéros de téléphone dans Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Pour plus d’informations sur les règles de normalisation des numéros de téléphone pour le Service de carnet d’adresses, reportez-vous à la rubrique [Administration du service de carnet d’adresses dans Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) dans la documentation des opérations.

