---
title: 'Lync Server 2013 : composants et topologies pour le serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ac46c8aba06bdfedaafa7846142d5a584c703c3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502561"
---
# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Composants et topologies pour le serveur de médiation dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Cette rubrique décrit les composants dont dépend le serveur de médiation et les topologies dans lesquelles le serveur de médiation peut être déployé.

<div>

## <a name="dependencies"></a>Dépendances

Le serveur de médiation présente les dépendances suivantes :

  - **Inscriptions.** Obligatoire. Le serveur d’inscriptions est le tronçon suivant pour la signalisation dans les interactions du serveur de médiation avec le réseau Lync Server 2013. Notez que le serveur de médiation peut être colocalisé sur un serveur frontal avec le serveur d’inscriptions, en plus d’être installé dans un pool autonome constitué uniquement de serveurs de médiation. Le serveur d’inscriptions est colocalisé avec un serveur de médiation et une passerelle PSTN sur un Survivable Branch appliance.

  - **Serveur de surveillance.** Facultatif mais fortement recommandé. Le serveur de surveillance permet au serveur de médiation d’enregistrer les mesures de qualité associées à ses sessions multimédia.

  - **Serveur Edge.** Obligatoire pour la prise en charge des utilisateurs externes. Le serveur Edge permet au serveur de médiation d’interagir avec les utilisateurs situés derrière un NAT ou un pare-feu.

</div>

<div>

## <a name="topologies"></a>Topologies

Le serveur de médiation Lync Server 2013 est colocalisé par défaut avec une instance du serveur d’inscriptions sur un serveur Standard Edition, un pool frontal ou un Survivable Branch appliance. Tous les serveurs de médiation d’un pool frontal doivent être configurés de manière identique.

Lorsque les performances sont problématiques, il peut être préférable de déployer un ou plusieurs serveurs de médiation dans un pool autonome dédié. Ou, si vous déployez une jonction SIP, nous vous recommandons de déployer un pool de serveurs de médiation autonome.

Si vous déployez des connexions SIP directes vers une passerelle PSTN qualifiée qui prend en charge la déviation du trafic multimédia et l’équilibrage de la charge DNS, un pool de serveurs de médiation autonomes n’est pas nécessaire. Si vous déployez des connexions Direct SIP sur une passerelle multimédia PSTN qualifiée prenant en charge le contournement du média et l‘équilibrage de charge DNS, un pool de serveurs de médiation autonome n‘est pas nécessaire, car les passerelles qualifiées sont capables d‘effectuer l‘équilibrage de charge DNS sur un pool de serveurs de médiation et recevoir du trafic provenant d‘un des serveurs du pool.

Il est également recommandé de colocaliser le serveur de médiation sur un pool frontal lorsque vous avez déployé des systèmes IP-PBX ou que vous vous êtes connecté(e) au contrôleur SBC (Session Border Controller) d‘un fournisseur ITSP (Internet Telephony Server Provider), à condition de respecter les indications suivantes :

  - Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

  - Le système IP-PBX ne prend pas en charge la déviation du trafic multimédia, mais le pool frontal qui héberge le serveur de médiation peut gérer le transcodage des communications vocales pour les appels auxquels la déviation du trafic multimédia ne s’applique pas.

Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour évaluer si le pool frontal où vous souhaitez colocaliser le serveur de médiation peut gérer la charge. Si votre environnement ne remplit pas les conditions requises, vous devez alors déployer un pool de serveurs de médiation autonome.

Pour plus d’informations sur la topologie à déployer, voir [instructions de déploiement pour le serveur de médiation dans Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

La figure suivante montre une topologie simple constituée de deux sites connectés par une liaison WAN. Le serveur de médiation est colocalisé avec le serveur d’inscriptions sur un pool frontal sur le site 1. Les serveurs de médiation du site 1 contrôlent à la fois la passerelle PSTN sur le site 1 et la passerelle sur le site 2. Dans cette topologie, le contournement de média est activé globalement afin d’utiliser les informations de site et de région, et le contournement est activé sur les jonctions vers chaque passerelle PSTN (GW1 et GW2).

**Exemple de sites connectés par une liaison WAN avec un serveur de médiation sur Site 1 et une passerelle PSTN sur Site 2**

![Topologie vocale avec passerelle WAN de serveur de médiation](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Topologie vocale avec passerelle WAN de serveur de médiation")

La figure suivante montre une topologie simple dans laquelle le serveur de médiation est colocalisé avec le serveur d’inscriptions sur le pool frontal sur le site 1 et dispose d’une connexion SIP directe vers le PBX IP sur le site 1. Dans cette illustration, le serveur de médiation contrôle également une passerelle RTC sur le site 2. Supposons que des utilisateurs Lync existent sur les sites 1 et 2. Supposons également que le système IP-PBX possède un processeur multimédia associé qui doit être traversé par tous les médias provenant de points de terminaison Lync avant d’être envoyés aux points de terminaison multimédias contrôlés par le système IP-PBX. Dans cette topologie, le contournement de média est activé globalement pour utiliser les informations de site et de région, et il est activé pour les jonctions vers la passerelle PBX et PSTN.

**Exemple de sites connectés par une liaison WAN avec un serveur de médiation sur Site 1 et un PBX sur Site 2**

![Serveur de médiation de topologie vocale-PBX WAN](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Serveur de médiation de topologie vocale-PBX WAN")

Pour plus d’informations sur la planification des topologies PBX, voir [Deployment Guidelines for Mediation Server in Lync server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) et [direct SIP Deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).

La dernière figure de cette rubrique montre une topologie à laquelle le serveur de médiation est connecté à l’SBC d’un fournisseur de services de téléphonie Internet. Pour plus d’informations sur les topologies de jonction SIP, voir [SIP Trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

