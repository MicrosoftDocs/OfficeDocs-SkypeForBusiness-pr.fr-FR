---
title: 'Lync Server 2013 : Composants et topologies utilisés pour le serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9c353dc65f5e943e082df9321a934ea8f14be1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Composants et topologies utilisés pour le serveur de médiation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Cette rubrique décrit les composants sur lesquels le serveur de médiation dépend et les topologies dans lesquelles il est possible de déployer le serveur de médiation.

<div>

## <a name="dependencies"></a>Dépendances

Le serveur de médiation a les dépendances suivantes:

  - **Autorités.** Requis. Le Bureau d’enregistrement est le tronçon suivant de signalisation dans les interactions du serveur de médiation avec le réseau Lync Server 2013. Notez que le serveur de médiation peut être localisé sur un serveur frontal conjointement au bureau d’enregistrement, en plus d’être installé dans un pool autonome composé uniquement de serveurs de médiation. Le Bureau d’enregistrement est colocalisé par un serveur de médiation et une passerelle RTC sur une unité de branchement Survivable.

  - **Serveur de surveillance.** Facultatif, mais fortement recommandé. Le serveur de surveillance permet au serveur de médiation d’enregistrer les mesures de qualité associées à ses sessions multimédias.

  - **Serveur Edge.** Requis pour la prise en charge des utilisateurs externes. Le serveur Edge permet au serveur de médiation d’interagir avec des utilisateurs situés derrière un NAT ou un pare-feu.

</div>

<div>

## <a name="topologies"></a>Topologies

Le serveur Lync Server 2013, médiation Server est par défaut colocalisé avec une instance du Bureau d’enregistrement sur un serveur Standard Edition Server, un pool frontal ou une unité de branchement Survivable. Tous les serveurs de médiation dans un pool frontal doivent être configurés de la même manière.

Lorsque la performance est un problème, il peut être préférable de déployer un ou plusieurs serveurs de médiation dans un pool autonome dédié. Par contre, si vous déployez le trunking SIP, nous vous recommandons de déployer un pool de serveurs de médiation autonome.

Si vous déployez des connexions SIP directes vers une passerelle RTC qualifiée qui prend en charge le contournement du contenu multimédia et l’équilibrage de charge DNS, vous n’avez pas besoin d’un pool de serveurs de médiation autonome. Il n’est pas nécessaire de disposer d’un pool de serveurs de médiation autonomes, car les passerelles qualifiées sont en mesure d’équilibrer la charge DNS vers un pool de serveurs de médiation et ils peuvent recevoir le trafic de n’importe quel serveur de médiation dans un pool.

Nous vous recommandons également de collocate le serveur de médiation sur un pool frontal lorsque vous avez déployé des PBX IP ou de vous connecter à un contrôleur de bordure de session du fournisseur de téléphonie Internet (SBC), à condition que l’une des conditions suivantes soit remplie:

  - Le PBX IP ou le SBC est configuré pour recevoir le trafic de n’importe quel serveur de médiation dans le pool et peut acheminer le trafic uniformément vers tous les serveurs de médiation du pool.

  - Le PBX IP ne prend pas en charge la dérivation multimédia, mais le pool frontal qui héberge le serveur de médiation peut gérer le transcodage de la voix pour les appels pour lesquels aucune dérivation de média ne s’applique.

Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour déterminer si le pool frontal sur lequel vous souhaitez collocate le serveur de médiation peut gérer le chargement. Si votre environnement ne peut pas répondre à ces exigences, vous devez déployer un pool de serveurs de médiation autonome.

Pour plus d’informations sur la topologie à déployer, voir [instructions de déploiement pour le serveur de médiation dans Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

La figure suivante montre une topologie simple constituée de deux sites connectés par une liaison de réseau étendu. Le serveur de médiation est colocalisé avec le Bureau d’enregistrement sur un pool frontal sur le site 1. Les serveurs de médiation du site 1 contrôlent à la fois la passerelle RTC sur le site 1 et la passerelle sur le site 2. Dans cette topologie, la déviation du trafic multimédia est activée globalement afin d’utiliser les informations de site et de région, et le contournement est activé sur les jonctions vers chaque passerelle RTC (GW1 et GW2).

**Exemple de sites connectés par une liaison de réseau étendu avec un serveur de médiation pour Site 1 et une passerelle RTC pour Site 2**

![Topologie vocale avec passerelle du réseau WAN du serveur de médiation] (images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topologie vocale avec passerelle du réseau WAN du serveur de médiation")

La figure suivante illustre une topologie simple dans laquelle le serveur de médiation est colocalisé avec le Bureau d’enregistrement de niveau frontal sur le site 1 et dispose d’une connexion SIP directe au PBX IP sur le site 1. Dans cette figure, le serveur de médiation contrôle également une passerelle RTC sur le site 2. Supposez que les utilisateurs de Lync existent sur les sites 1 et 2. Par ailleurs, supposez que le PBX IP possède un processeur de média associé qui doit être parcouru par tous les éléments multimédias provenant de points de terminaison Lync avant d’être envoyés aux points de terminaison multimédias contrôlés par le PBX IP. Dans cette topologie, la déviation du trafic multimédia est activée globalement pour utiliser les informations de site et de région, et il est activé pour les jonctions vers la passerelle PBX et RTC.

**Exemple de sites connectés par une liaison de réseau étendu avec un serveur de médiation pour Site 1 et un PBX pour Site 2**

![PBX WAN du serveur de médiation vocale] (images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "PBX WAN du serveur de médiation vocale")

Pour plus d’informations sur la planification des topologies PBX, voir [instructions de déploiement pour le serveur de médiation dans Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) et [options de déploiement SIP directes dans Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

La dernière figure de cette rubrique montre une topologie dans laquelle le serveur de médiation est connecté à l’SBC d’un fournisseur de services de téléphonie Internet. Pour plus d’informations sur les topologies du Trunk SIP, consultez l’une des [lignes SIP dans Lync Server 2013](lync-server-2013-sip-trunking.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

