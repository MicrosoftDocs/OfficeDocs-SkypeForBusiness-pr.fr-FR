---
title: 'Lync Server 2013 : configuration de la déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bf2fb06f25ccf1871393cf4d80ffa3c33a42fc5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a>Configurer la déviation du trafic multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

Cette section suppose que vous ayez déjà publié et configuré au moins un ou plusieurs serveurs de médiation (comme décrit dans [define a Mediation Server in Topology Builder in Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) et [publish the Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), ou dans [définir et configurer un pool frontal ou un serveur Standard Edition dans Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) et [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivement, tout dans la documentation de déploiement).

Cette section suppose également que vous ayez défini au moins un homologue de passerelle pour fournir la connectivité PSTN, comme décrit dans [define a Gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md). Si l’homologue auquel vous vous connectez est l’SBC d’un fournisseur de jonction SIP, assurez-vous que le fournisseur est un fournisseur qualifié et que le fournisseur prend en charge la déviation du trafic multimédia. Par exemple, de nombreux fournisseurs de jonction SIP autoriseront uniquement leurs SBC à recevoir du trafic du serveur de médiation. Dans ce cas, le contournement doit être activé pour la jonction en question. De même, vous ne pouvez pas activer le contournement de média, à moins que l’organisation ne révèle les adresses IP de son réseau interne au fournisseur de jonctions SIP.

<div>


> [!NOTE]  
> Le contournement de média ne fonctionnera pas avec chaque passerelle PSTN, système IP-PBX et SBC. Microsoft a testé un ensemble de passerelles PSTN et de contrôleurs SBC avec des partenaires agréés et a effectué quelques tests avec les systèmes IP-PBX de Cisco. La déviation du trafic multimédia n’est prise en charge qu’avec les produits et les versions mentionnés dans le <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>programme d’interopérabilité ouvert pour les communications unifiées – Lync Server à.



</div>

Cette rubrique explique comment activer le contournement de média en vue de réduire le traitement nécessaire du serveur de médiation. Avant d’activer la déviation du trafic multimédia, assurez-vous que votre environnement répond aux conditions requises pour prendre en charge la déviation du trafic multimédia, comme décrit dans la rubrique [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la documentation de planification. Assurez-vous également que vous avez utilisé les informations de planification de la déviation du trafic [multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) pour décider s’il faut activer les paramètres globaux de déviation du trafic multimédia pour toujours contourner le serveur de médiation ou utiliser les informations de site et de région lorsque vous déterminez s’il faut contourner le serveur de médiation.

Si vous avez déjà configuré le contrôle d’admission des appels (CAC), une autre fonction avancée de Voix Entreprise, notez que la réservation de bande passante effectuée par le contrôle d’admission des appels ne s’applique à aucun appel pour lequel le contournement de média est employé. La vérification de l’emploi du contournement de media est effectuée en premier, et s’il est employé, le contrôle d’admission des appels n’est pas utilisé pour l’appel ; ce n’est qu’en cas d’échec du contournement de média que le contrôle d’admission des appels est vérifié. Ces deux fonctions sont par conséquent mutuellement exclusives pour tout appel particulier qui est acheminé sur le PSTN. Il s’agit du comportement logique car le contournement de média suppose que les restrictions de bande passante n’existent pas entre systèmes d’extrémité de média sur un appel ; le contournement de média est impossible sur les liaisons avec bande passante restreinte. Une des deux situations suivantes s’appliquera donc à un appel PSTN : a) le média contourne le serveur de médiation, et le contrôle d’admission des appels ne réserve pas de bande passante pour l’appel ; ou b) le contrôle d’admission des appels réserve de la bande passante pour l’appel, et le media est traité par le serveur de médiation impliqué dans l’appel.

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>Étapes suivantes : Activer le contournement de média sur la connexion des jonctions

Après avoir configuré les paramètres initiaux pour la connectivité PSTN (plans de numérotation, stratégies de voix, enregistrements d’utilisation RTC, itinéraires d’appels sortants et règles de traduction), commencez le processus d’activation de la déviation du trafic multimédia en suivant les étapes décrites dans [Configure a trunk with Media Bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configuration de la déviation du trafic multimédia dans Lync Server 2013 pour toujours contourner le serveur de médiation](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Configurer les paramètres globaux de déviation du trafic multimédia dans Lync Server 2013 pour utiliser les informations de site et de région](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Options globales de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

