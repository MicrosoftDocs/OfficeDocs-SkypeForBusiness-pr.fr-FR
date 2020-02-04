---
title: 'Lync Server 2013 : Tâches de déploiement du contrôle d’appel distant'
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
ms.openlocfilehash: df80ebcdc879598677a037d60c9eeeee46ba5209
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Tâches de déploiement du contrôle d’appel distant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Cette rubrique décrit les tâches de déploiement que vous devez effectuer pour activer le contrôle d’appel distant pour les utilisateurs de votre environnement Lync Server.

<div>


> [!NOTE]  
> Si vous migrez des utilisateurs précédemment activés pour le contrôle d’appel distant dans Microsoft Office Communicator 2007 R2, vous devez effectuer une tâche de déploiement supplémentaire avant de commencer à effectuer les tâches de déploiement de contrôle d’appel distant décrites dans cette rubrique. Pendant le processus de migration vers Lync Server, les entrées d’applications approuvées (auparavant appelées « <EM>entrées d’hébergement d’hébergement</EM>») doivent être supprimées en utilisant les outils d’administration Office Communications Server 2007 R2, selon le cas.<BR>Pour plus d’informations sur la suppression d’hôtes autorisés, voir <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">supprimer un hôte autorisé hérité dans Lync Server 2013 (facultatif)</A>.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>Étape 1 : installer et configurer la passerelle SIP/CSTA pour communiquer avec votre système PBX

Vous devez installer au moins une passerelle SIP/CSTA qui peut se connecter à Lync Server et au PBX (PBX) existant dans votre environnement afin de fournir aux utilisateurs des fonctionnalités de contrôle d’appel distant. Une passerelle SIP/CSTA est une passerelle entre le SIP et une application de communication prenant en charge l’ordinateur (CSTA). Qu’il s’agisse d’installer plusieurs passerelles ou une seule, chaque utilisateur peut être configuré avec une seule passerelle ou PBX. Si votre système PBX existant ne dispose pas d’une interface SIP/CSTA, assurez-vous de déployer une passerelle SIP/CSTA qui peut prendre en charge le PBX, y compris la prise en charge de protocoles de signalisation spécifiques du fabricant PBX. Pour plus d’informations sur les fonctionnalités, consultez directement chaque fournisseur.

Lorsque vous êtes prêt à déployer une passerelle SIP/CSTA qui peut être intégrée à Lync Server pour le contrôle d’appel distant, contactez également le fournisseur de votre passerelle ou la documentation de la passerelle du fournisseur en ce qui concerne la syntaxe requise par la passerelle pour les informations suivantes :

  - URI de serveur ligne de la passerelle

  - URI de ligne pour les utilisateurs qui seront assignés à la passerelle

Les paramètres précédents sont requis lors de la configuration de l’utilisateur et doivent être spécifiés comme prévu par la passerelle pour le routage et la connexion au PBX correctement.

Vous pouvez consulter les fournisseurs sur le site Web Microsoft Unified Communications Open Interoperability du [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)programme à l’adresse.

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>Étape 2 : configurer Lync Server pour acheminer les demandes CSTA vers la passerelle SIP/CSTA

Vous devez créer des itinéraires statiques sur les pools de serveurs Lync vers l’adresse de destination (URI du serveur) de toutes les passerelles SIP/CSTA de votre déploiement pour lesquelles vous souhaitez acheminer les demandes de contrôle d’appel distant. Vous devez également créer une entrée d’application fiable qui correspond à chaque adresse de destination. Lorsque vous désignez la passerelle en tant qu’application approuvée, son état de confiance s’exécute dans le cadre de l’environnement Lync Server, même si elle est développée par une tierce partie (et exécute ce qu’il est désigné sous le terme de *service externe* , car il s’agit d’un service qui n’est pas intégré au produit). Enfin, si Lync Server se connecte à la passerelle SIP/CSTA par le biais d’une connexion TCP (Transmission Control Protocol) au lieu d’une connexion TLS (Transport Layer Security), vous devez également définir l’adresse IP de la passerelle à l’aide du générateur de topologie.

Pour plus d’informations sur la configuration des itinéraires statiques, voir [configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).

Pour plus d’informations sur la configuration d’entrées d’applications approuvées, voir [configurer une entrée d’application fiable pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).

Pour plus d’informations sur la définition d’une adresse IP de passerelle SIP/CSTA dans le générateur de topologie, voir [définir une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>Étape 3 : configurer les utilisateurs de Lync pour le contrôle d’appel distant

Une fois les utilisateurs activés pour Lync Server, vous pouvez utiliser le panneau de configuration de Lync Server ou Lync Server Management Shell pour les activer pour le contrôle d’appel distant. Au cours de cette étape de déploiement, vous affectez à chaque utilisateur un URI de ligne et un URI de ligne. L’URI de Line Server est l’URI SIP de la passerelle SIP/CSTA que vous envisagez d’affecter à l’utilisateur. L’URI de ligne correspond au numéro de téléphone unique attribué à l’utilisateur.

Pour plus d’informations sur la configuration des utilisateurs pour le contrôle d’appel distant, voir [activer les utilisateurs de Lync pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>Étape 4 : définir les règles de normalisation des numéros de téléphone de Lync Server

Dans les scénarios de contrôle d’appel distant, Lync Server utilise des règles de normalisation des numéros de téléphone pour convertir les numéros de téléphone reçus de la passerelle SIP/CSTA au format E. 164. Les numéros de téléphone doivent avoir le format standard pour que certaines fonctionnalités de contrôle d’appel distantes fonctionnent correctement. Le contrôle d’appel distant utilise les mêmes règles de normalisation des numéros de téléphone que celles configurées pour la normalisation des numéros de téléphone du service de carnet d’adresses, qui diffèrent des règles de normalisation des numéros de téléphone pour Enterprise Voice.

Pour plus d’informations sur la façon dont le contrôle d’appel distant utilise les règles de normalisation des numéros de téléphone, voir [contrôle d’appel distant et normalisation du numéro de téléphone dans Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md). Pour plus d’informations sur les règles de normalisation des numéros de téléphone pour le service de carnet d’adresses, voir [administration du service de carnet d’adresses dans Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) , rubrique documentation sur les opérations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

