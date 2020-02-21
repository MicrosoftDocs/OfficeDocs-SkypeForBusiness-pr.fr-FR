---
title: 'Lync Server 2013 : composant de serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c068e284e871caf5848ba9616f8bf7afa380b49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Composant de serveur de médiation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Vous devez déployer Lync Server 2013, serveur de médiation si vous déployez la charge de travail voix entreprise. Cette section décrit les fonctionnalités et topologies de base, les dépendances et les directives de planification.

Le serveur de médiation traduit la signalisation et, dans certaines configurations, les médias entre votre infrastructure interne de Lync Server 2013, votre infrastructure voix entreprise et une passerelle PSTN ou une jonction SIP (Session Initiation Protocol). Sur le côté Lync Server 2013, le serveur de médiation écoute sur une seule adresse de transport Mutual TLS (MTLS). Du côté de la passerelle, le serveur de médiation est à l’écoute sur tous les ports d’écoute associés aux jonctions définies dans le document de topologie. Toutes les passerelles qualifiées doivent prendre en charge le protocole TLS mais peuvent aussi activer le protocole TCP. Le protocole TCP est pris en charge pour les passerelles qui ne prennent pas en charge le protocole TLS.

Si vous disposez également d’un autocommutateur public (PBX) dans votre environnement, le serveur de médiation gère les appels entre les utilisateurs voix entreprise et le PBX. Si votre PBX est un PBX IP, vous pouvez créer une connexion SIP directe entre le PBX et le serveur de médiation. Si votre PBX est un PBX de multiplexage temporel, vous devez également déployer une passerelle PSTN entre le serveur de médiation et le PBX.

Par défaut, le serveur de médiation est colocalisé avec le serveur frontal. Le serveur de médiation peut également être déployé dans un pool autonome pour des raisons de performances, ou si vous déployez la jonction SIP, auquel cas le pool autonome est fortement recommandé.

Si vous déployez des connexions SIP directes vers une passerelle PSTN qualifiée qui prend en charge la déviation du trafic multimédia et l’équilibrage de la charge DNS, un pool de serveurs de médiation autonomes n’est pas nécessaire. Si vous déployez des connexions Direct SIP sur une passerelle multimédia PSTN qualifiée prenant en charge le contournement du média et l‘équilibrage de charge DNS, un pool de serveurs de médiation autonome n‘est pas nécessaire, car les passerelles qualifiées sont capables d‘effectuer l‘équilibrage de charge DNS sur un pool de serveurs de médiation et recevoir du trafic provenant d‘un des serveurs du pool.

Il est également recommandé de colocaliser le serveur de médiation sur un pool frontal lorsque vous avez déployé des systèmes IP-PBX ou que vous vous êtes connecté(e) au contrôleur SBC (Session Border Controller) d‘un fournisseur ITSP (Internet Telephony Server Provider), à condition de respecter les indications suivantes :

  - Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

  - Le système IP-PBX ne prend pas en charge la déviation du trafic multimédia, mais le pool frontal qui héberge le serveur de médiation peut gérer le transcodage des communications vocales pour les appels auxquels la déviation du trafic multimédia ne s’applique pas.

Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour évaluer si le pool frontal où vous souhaitez colocaliser le serveur de médiation peut gérer la charge. Si votre environnement ne remplit pas les conditions requises, vous devez alors déployer un pool de serveurs de médiation autonome.

Les principales fonctions du serveur de médiation sont les suivantes :

  - Chiffrement et déchiffrement des SRTP sur le côté Lync Server

  - Traduction SIP sur TCP (pour les passerelles non compatibles TLS) vers SIP sur mutual TLS

  - Conversion de flux multimédia entre Lync Server et l’homologue de passerelle du serveur de médiation

  - Connexion des clients situés hors du réseau aux composants ICE internes, ce qui permet aux données multimédias de traverser les traducteurs d’adresses réseau (NAT) et les pare-feu

  - Agir en tant qu’intermédiaire pour les flux d’appels non pris en charge par une passerelle, tels que les appels de travailleurs distants sur un client voix entreprise

  - Dans les déploiements qui incluent la jonction SIP, collaboration avec le fournisseur de services de jonction SIP pour fournir la prise en charge PSTN, de sorte qu’il ne soit plus nécessaire de disposer d’une passerelle PSTN

La figure suivante illustre les protocoles de signalisation et de média utilisés par le serveur de médiation lors de la communication avec une passerelle PSTN de base et l’infrastructure voix entreprise.

**Protocoles de signalisation et de données multimédias utilisés par le serveur de médiation**

![Diagramme des protocoles de serveur de médiation](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagramme des protocoles de serveur de médiation")

<div>


> [!NOTE]  
> Si vous utilisez TCP ou RTP/RTCP (au lieu de SRTP ou SRTCP) sur le réseau entre la passerelle PSTN et le serveur de médiation, nous vous recommandons de prendre des mesures pour garantir la sécurité et la confidentialité du réseau.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Jonction M :N dans Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Contrôle d’admission des appels et serveur de médiation dans Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Enhanced 9-1-1 (E9-1-1) et serveur de médiation dans Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Contournement de média et serveur de médiation dans Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Composants et topologies pour le serveur de médiation dans Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Instructions de déploiement pour le serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

