---
title: 'Lync Server 2013 : composant du serveur de médiation'
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
ms.openlocfilehash: 363b277003d7ca1581475ec7c1197bb0f60ccfaa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Composant serveur de médiation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Si vous déployez la charge de travail voix entreprise, vous devez déployer Lync Server 2013, serveur de médiation. Cette section décrit les fonctionnalités de base, les dépendances, les topologies de base et les recommandations en matière de planification.

Le serveur de médiation translate les signaux et, dans certaines configurations, les éléments multimédias entre votre serveur interne Lync Server 2013, l’infrastructure voix entreprise et une passerelle de réseau téléphonique commuté (PSTN) ou un Trunk SIP (Session Initiation Protocol). Sur le site Lync Server 2013, le serveur de médiation écoute une seule adresse de transport Mutual TLS (MTLS). Sur le côté passerelle, le serveur de médiation écoute tous les ports d’écoute associés associés à des lignes définies dans le document topologique. Toutes les passerelles qualifiées doivent prendre en charge le protocole TLS mais peuvent aussi activer le protocole TCP. Le protocole TCP est pris en charge pour les passerelles qui ne prennent pas en charge le protocole TLS.

Si vous avez également un échange de succursale publique (PBX) existant dans votre environnement, le serveur de médiation gère les appels entre les utilisateurs voix entreprise et le PBX. S’il s’agit d’un PBX IP, vous pouvez créer une connexion SIP directe entre le PBX et le serveur de médiation. S’il s’agit d’un système PBX (TDM) PBX, vous devez également déployer une passerelle RTC entre le serveur de médiation et le PBX.

Le serveur de médiation est colocalisé par défaut avec le serveur frontal. Le serveur de médiation peut également être déployé dans un pool autonome pour des raisons de performances, ou si vous déployez le trunking SIP, auquel cas le pool autonome est fortement recommandé.

Si vous déployez des connexions SIP directes vers une passerelle RTC qualifiée qui prend en charge le contournement du contenu multimédia et l’équilibrage de charge DNS, vous n’avez pas besoin d’un pool de serveurs de médiation autonome. Il n’est pas nécessaire de disposer d’un pool de serveurs de médiation autonomes, car les passerelles qualifiées sont en mesure d’équilibrer la charge DNS vers un pool de serveurs de médiation et ils peuvent recevoir le trafic de n’importe quel serveur de médiation dans un pool.

Nous vous recommandons également de collocate le serveur de médiation sur un pool frontal lorsque vous avez déployé des PBX IP ou de vous connecter à un contrôleur de bordure de session du fournisseur de téléphonie Internet (SBC), à condition que l’une des conditions suivantes soit remplie :

  - Le PBX IP ou le SBC est configuré pour recevoir le trafic de n’importe quel serveur de médiation dans le pool et peut acheminer le trafic uniformément vers tous les serveurs de médiation du pool.

  - Le PBX IP ne prend pas en charge la dérivation multimédia, mais le pool frontal qui héberge le serveur de médiation peut gérer le transcodage de la voix pour les appels pour lesquels aucune dérivation de média ne s’applique.

Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour déterminer si le pool frontal sur lequel vous souhaitez collocate le serveur de médiation peut gérer le chargement. Si votre environnement ne peut pas répondre à ces exigences, vous devez déployer un pool de serveurs de médiation autonome.

Les principales fonctions du serveur de médiation sont les suivantes :

  - Le chiffrement et le déchiffrement de SRTP du côté serveur Lync

  - Traduction SIP sur TCP (pour les passerelles qui ne prennent pas en charge TLS) pour SIP sur Mutual TLS

  - Traduction de flux multimédias entre Lync Server et l’homologue de passerelle du serveur de médiation

  - Connexion de clients se trouvant hors du réseau à des composants de glace internes, qui permettent le passage de contenus multimédias de tar et de pare-feu

  - Agissant en tant qu’intermédiaire pour les flux d’appels qui n’est pas pris en charge par une passerelle, comme les appels de travailleurs à distance sur un client voix entreprise

  - Dans les déploiements qui incluent le trunking SIP, en travaillant avec le fournisseur de service de trunking SIP pour fournir la prise en charge RTC, qui rend inutile le besoin d’une passerelle RTC

La figure suivante illustre les protocoles de signalisation et de média utilisés par le serveur de médiation pour communiquer avec une passerelle RTC de base et l’infrastructure voix entreprise.

**Protocoles de signalisation et de données multimédias utilisés par le serveur de médiation**

![Diagramme de protocoles de serveur de médiation](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Diagramme de protocoles de serveur de médiation")

<div>


> [!NOTE]  
> Si vous utilisez TCP ou RTP/RTCP (au lieu de SRTP ou SRTCP) sur le réseau entre la passerelle RTC et le serveur de médiation, nous vous conseillons de prendre des mesures pour garantir la sécurité et la confidentialité du réseau.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [M :N Trunk dans Lync Server 2013](lync-server-2013-m-n-trunk.md)

  - [Contrôle d’admission des appels et serveur de médiation dans Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Enhanced 9-1-1 (E9-1-1) et serveur de médiation dans Lync Server 2013](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Déviation du trafic multimédia et serveur de médiation dans Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Composants et topologies utilisés pour le serveur de médiation dans Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Recommandations en matière de déploiement pour le serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

