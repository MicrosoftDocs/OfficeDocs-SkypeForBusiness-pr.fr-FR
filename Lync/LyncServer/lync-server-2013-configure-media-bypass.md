---
title: 'Lync Server 2013 : Configuration de la déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 465a949ca1581933f96f18cfe2977d400fa7a152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a>Configuration de la déviation du trafic multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-24_

Cette section part du principe que vous avez déjà publié et configuré au moins un ou plusieurs serveurs de médiation (comme décrit dans [définir un serveur de médiation dans le générateur de topologie de Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) et [publier la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md)ou dans [Définissez et configurez un pool frontal ou un serveur Standard Edition dans Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) et [publiez la topologie dans Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivement, dans la documentation de déploiement).

Dans cette section, vous devez également définir au moins un homologue de passerelle pour fournir une connectivité PSTN, comme décrit dans [la section définir une passerelle dans le générateur de topologie de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md). Si l’homologue auquel vous vous connectez est le contrôleur SBC (Session Border Controller) d’un fournisseur de jonctions SIP (Session Initiation Protocol), assurez-vous qu’il s’agit d’un fournisseur qualifié et qu’il prend en charge la déviation du trafic multimédia. Par exemple, de nombreux fournisseurs de jonctions SIP autoriseront uniquement leurs contrôleurs SBC à recevoir du trafic du serveur de médiation. Dans ce cas, la déviation du trafic doit être activée pour la jonction en question. De même, vous ne pouvez pas activer la déviation du trafic multimédia sauf si l’organisation communique les adresses IP de son réseau interne au fournisseur de jonctions SIP.

<div>


> [!NOTE]  
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et contrôleur SBC. Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco. La dérivation de média est uniquement prise en charge avec les produits et les versions indiqués sur le programme d’interopérabilité d’ouverture de communications unifiées-Lync Server à <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.



</div>

Cette section décrit comment activer la dérivation multimédia pour réduire le traitement requis par le serveur de médiation. Avant d’activer la dérivation multimédia, assurez-vous que votre environnement répond aux conditions nécessaires à la prise en charge du contournement multimédia, comme décrit dans la section [planification de la dérivation multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la documentation de planification. Assurez-vous également d’avoir utilisé les informations fournies dans la section [planification de la dérivation multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) pour décider si vous voulez activer les paramètres globaux de contournement du contenu multimédia pour ignorer toujours le serveur de médiation ou utiliser les informations sur le site et la région lorsque vous déterminez s’il doit contournement du serveur de médiation.

Si vous avez déjà configuré le contrôle d’admission des appels, une autre fonction avancée de Voix Entreprise, notez que la réservation de bande passante effectuée par le contrôle d’admission des appels ne s’applique à aucun appel pour lequel la déviation du trafic multimédia est employée. La vérification de l’emploi de la déviation du trafic multimédia est effectuée en premier, et si elle est employée, le contrôle d’admission des appels n’est pas utilisé pour l’appel. Ce n’est qu’en cas d’échec de la déviation du trafic multimédia que le contrôle d’admission des appels est vérifié. Ces deux fonctions sont, par conséquent, mutuellement exclusives pour tout appel particulier acheminé sur le RTC. Il s’agit du comportement logique, car la déviation du trafic multimédia suppose qu’il n’y a pas de restrictions de bande passante entre les points de terminaison multimédia sur un appel. La déviation du trafic multimédia est impossible sur les liaisons avec bande passante restreinte. Une des deux situations suivantes s’appliquera donc à un appel RTC : a) le trafic multimédia contourne le serveur de médiation, et le contrôle d’admission des appels ne réserve pas de bande passante pour l’appel ; ou b) le contrôle d’admission des appels réserve de la bande passante pour l’appel, et le trafic multimédia est traité par le serveur de médiation impliqué dans l’appel.

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a>Étapes suivantes: activer la dérivation multimédia sur la connexion Trunk

Après avoir configuré les paramètres initiaux pour la connectivité PSTN (plans de numérotation, stratégies vocales, enregistrements d’utilisation RTC, itinéraires d’appels sortants et règles de traduction), commencez le processus d’activation de la contournement de média en suivant les étapes décrites dans la rubrique [configurer un Trunk avec le contournement multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[Options de contournement global de médias dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

