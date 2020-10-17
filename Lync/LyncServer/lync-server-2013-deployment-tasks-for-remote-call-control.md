---
title: 'Lync Server 2013 : tâches de déploiement pour le contrôle d’appel distant'
description: 'Lync Server 2013 : tâches de déploiement pour le contrôle d’appel distant.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61d0d57489bd93d7e6ce0209c605f05a2417bded
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553580"
---
# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Tâches de déploiement pour le contrôle d’appel distant dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Cette rubrique décrit les tâches de déploiement que vous devez effectuer pour activer le contrôle d’appel distant pour les utilisateurs dans votre environnement Lync Server.

<div>


> [!NOTE]  
> Si vous migrez des utilisateurs précédemment activés pour le contrôle d’appel distant dans Microsoft Office Communicator 2007 R2, vous devez effectuer une tâche de déploiement supplémentaire avant de commencer à exécuter les tâches de déploiement du contrôle d’appel distant décrites dans cette rubrique. Lors du processus de migration vers Lync Server, les entrées d’applications approuvées (précédemment appelées <EM>entrées d’hôte autorisé</EM>) doivent être supprimées à l’aide des outils d’administration Office Communications Server 2007 R2, selon le cas.<BR>Pour plus d’informations sur la suppression des hôtes autorisés, voir <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a Legacy Authorized Host in Lync Server 2013 (optional)</A>.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>Étape 1 : Installer la passerelle SIP/CSTA et la configurer de sorte qu’elle communique avec le PBX

Vous devez installer au moins une passerelle SIP/CSTA qui peut se connecter à Lync Server et au PBX (Private Branch Exchange) existant dans votre environnement afin de fournir des fonctionnalités de contrôle d’appel distant à vos utilisateurs. Une passerelle SIP/CSTA est une passerelle entre un serveur SIP et une application CSTA (Computer-Supported Telecommunications Application). Quel que soit le nombre de passerelles que vous installez, chaque utilisateur ne peut être configuré qu’avec une seule passerelle ou un seul PBX. Si votre PBX existant ne dispose pas d’une interface SIP/CSTA, déployez une passerelle SIP/CSTA pouvant prendre en charge le PBX, ainsi que les protocoles de signalisation propriétaires propres au fournisseur du PBX. Pour plus d’informations sur ce que les passerelles prennent en charge, renseignez-vous directement auprès du fournisseur.

Lorsque vous êtes prêt à déployer une passerelle SIP/CSTA qui peut s’intégrer à Lync Server pour le contrôle d’appel distant, consultez également votre fournisseur de passerelle ou la documentation de passerelle du fournisseur concernant la syntaxe requise par la passerelle pour obtenir les informations suivantes :

  - URI du serveur de ligne de la passerelle

  - URI de ligne pour les utilisateurs qui seront affectés à la passerelle

Vous devez fournir les valeurs des paramètres précédents au cours de la configuration des utilisateurs, car la passerelle en a besoin pour se connecter correctement au PBX et lui transmettre le trafic.

Vous pouvez vous reporter à la rubrique fournisseurs sur le site Web du programme d’interopérabilité Microsoft Unified Communications à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) .

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>Étape 2 : configurer Lync Server pour acheminer les demandes CSTA vers la passerelle SIP/CSTA

Vous devez créer des itinéraires statiques sur les pools de serveurs Lync Server vers l’adresse de destination (URI du serveur) de toutes les passerelles SIP/CSTA de votre déploiement vers lequel vous envisagez d’acheminer les demandes de contrôle d’appel distant. Vous devez également créer une entrée d’application approuvée qui correspond à chaque adresse de destination. Lorsque vous désignez la passerelle en tant qu’application approuvée, elle reçoit un État approuvé à exécuter dans le cadre de l’environnement Lync Server même si elle est développée par un tiers (et exécute ce qui est appelé *service externe* , car il s’agit d’un service qui n’est pas intégré au produit). Enfin, si Lync Server se connecte à la passerelle SIP/CSTA à l’aide d’une connexion TCP (Transmission Control Protocol) au lieu d’une connexion TLS (Transport Layer Security), vous devez également définir l’adresse IP de la passerelle à l’aide du générateur de topologie.

Pour plus d’informations sur la configuration des itinéraires statiques, voir [configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Pour plus d’informations sur la configuration des entrées d’applications approuvées, voir [Configure a Trusted application Entry for Remote Call Control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Pour plus d’informations sur la définition d’une adresse IP de passerelle SIP/CSTA dans le générateur de topologies, voir [define a SIP/CSTA Gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>Étape 3 : configuration des utilisateurs Lync pour le contrôle d’appel distant

Une fois que les utilisateurs ont été activés pour Lync Server, vous pouvez utiliser le panneau de configuration Lync Server ou Lync Server Management Shell pour les activer pour le contrôle d’appel distant. C’est également au cours de cette étape que vous devez affecter à chaque utilisateur un URI de serveur de ligne et un URI de ligne. L’URI de serveur de ligne est l’URI SIP de la passerelle SIP/CSTA que vous envisagez d’affecter à l’utilisateur. L’URI de ligne est le numéro de téléphone unique affecté à l’utilisateur.

Pour plus d’informations sur la configuration des utilisateurs pour le contrôle d’appel distant, reportez-vous à la rubrique [activation des utilisateurs Lync pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>Étape 4 : Définir les règles de normalisation des numéros de téléphone Lync Server

Dans les scénarios de contrôle d’appel distant, Lync Server utilise les règles de normalisation des numéros de téléphone pour convertir les numéros de téléphone qu’il reçoit de la passerelle SIP/CSTA au format E. 164. Les numéros de téléphone doivent être dans ce format standard pour que certaines fonctionnalités de contrôle d’appel distant fonctionnent correctement. Le contrôle d’appel distant utilise les mêmes règles de normalisation des numéros de téléphone que celles que vous configurez pour la normalisation des numéros de téléphone du Service de carnet d’adresses, qui sont différentes des règles de normalisation utilisées pour Voix Entreprise.

Pour plus d’informations sur la façon dont le contrôle d’appel distant utilise les règles de normalisation des numéros de téléphone, consultez la rubrique [contrôle d’appel distant et normalisation des numéros de téléphone dans Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Pour plus d’informations sur les règles de normalisation des numéros de téléphone pour le service de carnet d’adresses, voir [administration de la rubrique Service de carnet d’adresses dans Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) dans la documentation des opérations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

