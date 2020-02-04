---
title: 'Lync Server 2013 : M :N Trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4485380d6de5d247511b863761fcf7c75d38a29b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mn-trunk-in-lync-server-2013"></a>M :N Trunk dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Lync Server 2013 prend en charge une plus grande souplesse dans la définition d’un Trunk pour le routage des appels à partir des versions précédentes. Un Trunk est une association logique entre un serveur de médiation et un numéro de port d’écoute avec une passerelle et un numéro de port d’écoute. Cela implique plusieurs facteurs : un serveur de médiation peut avoir plusieurs Trunks vers la même passerelle ; un serveur de médiation peut avoir plusieurs Trunks pour différentes passerelles. à l’inverse, une passerelle peut avoir plusieurs Trunks pour différents serveurs de médiation.

Un Trunk racine est toujours requis pour être créé lors de l’ajout d’une passerelle à la topologie Lync à l’aide du générateur de topologie. Le nombre de passerelles qu’un serveur de médiation peut gérer dépend de la capacité de traitement du serveur pendant les heures de pointe. Si vous déployez un serveur de médiation sur du matériel qui dépasse la configuration minimale requise pour Lync Server 2013, comme décrit dans la section [matériel pris en charge pour Lync server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge, l’estimation du nombre d’appels de non-contournement actifs qu’un serveur de médiation autonome peut gérer est approximativement 1000 appels. Lorsqu’il est déployé sur du matériel et répondez à ces spécifications, le serveur de médiation doit procéder au transcodage, mais continuer à acheminer les appels pour plusieurs passerelles, même si les passerelles ne prennent pas en charge la dérivation multimédia.

Lors de la définition d’un itinéraire d’appel, vous spécifiez les Trunks associés à cet itinéraire, mais vous ne spécifiez pas les serveurs de médiation associés à cet itinéraire. À la place, vous utilisez le générateur de topologie pour associer des Trunks aux serveurs de médiation. En d’autres termes, le routage détermine le Trunk à utiliser pour un appel et, par la suite, le serveur de médiation associé à cette ligne envoie le signalement pour cet appel.

Le serveur de médiation peut être déployé en tant que pool. ce pool peut être colocalisé avec un pool frontal ou déployé en tant que pool autonome. Lorsqu’un serveur de médiation est colocalisé avec un pool frontal, la taille du pool peut être 12 (la limite de la taille du pool d’inscriptions). Grâce à ces nouvelles fonctionnalités, la flexibilité et la souplesse de déploiement pour les serveurs de médiation peuvent être associées, mais ils nécessitent des fonctionnalités associées dans les entités homologues suivantes :

  - **Passerelle RTC.** Une passerelle éligible de Lync Server 2013 doit implémenter l’équilibrage de charge DNS, ce qui permet à une passerelle RTC (réseau téléphonique commuté) qualifiée d’un équilibreur de charge d’un pool de serveurs de médiation, et donc de répartir les appels sur le pool.

  - **Contrôleur de bordure de session.** Dans le cas d’un Trunk SIP, l’entité homologue est un contrôleur de bordure de session (SBC) sur un fournisseur de services de téléphonie Internet. Dans la direction du pool de serveurs de médiation vers SBC, l’SBC peut recevoir des connexions à partir d’un serveur de médiation du pool. Dans la direction de l’SBC vers le pool, le trafic peut être envoyé à un serveur de médiation du pool. Il est possible d’effectuer cette opération par le biais de l’équilibrage de charge DNS, le cas échéant par le fournisseur de services et SBC. Une autre solution consiste à fournir à l’opérateur de service les adresses IP de tous les serveurs de médiation du pool, et le prestataire de services les mettra en service dans leur SBC en tant que serveur SIP distinct pour chaque serveur de médiation. Le prestataire de services doit alors gérer l’équilibrage de charge de ses propres serveurs. Tous les fournisseurs de services ou SBCs ne prennent pas en charge ces fonctionnalités. Par ailleurs, le prestataire de services pourra facturer des frais supplémentaires pour cette fonctionnalité. En règle générale, chaque ligne SIP de l’SBC entraîne des frais mensuels.

  - **PBX IP.** Dans la direction du pool de serveurs de médiation vers arrêt SIP IP-PBX, le PBX IP peut recevoir des connexions à partir de n’importe quel serveur de médiation du pool. Dans la direction du système PBX IP vers le pool, le trafic peut être envoyé à un serveur de médiation du pool. Étant donné que la plupart des PBX IP ne prennent pas en charge l’équilibrage de charge DNS, il est recommandé de définir des connexions SIP directes individuelles entre le PBX IP et chaque serveur de médiation du pool. Le PBX IP doit alors gérer son propre équilibrage de charge en répartissant le trafic via le groupe de lignes. L’hypothèse est que le groupe Trunk dispose d’un ensemble cohérent de règles de routage au PBX IP. Si un PBX IP particulier prend en charge ce concept de groupe de lignes et comment il s’intersecte avec la redondance et l’architecture de regroupement du PBX IP, vous devez déterminer si un cluster de serveurs de médiation peut interagir correctement avec un PBX IP.

Un pool de serveurs de médiation doit avoir une vue uniforme de la passerelle homologue avec laquelle il interagit. Cela signifie que tous les membres du pool accèdent à la même définition de passerelle homologue à partir du magasin de configurations et qu’ils ont tous autant de chances d’interagir avec elle pour les appels sortants. Par conséquent, il n’existe aucun moyen de segmenter le pool de façon à ce que certains serveurs de médiation communiquent uniquement avec certains homologues de passerelle pour les appels sortants. Si une telle segmentation est nécessaire, il est nécessaire d’utiliser une réserve distincte de serveurs de médiation. Ce serait le cas, par exemple, si les fonctionnalités associées dans les passerelles RTC, jonctions SIP ou systèmes IP-PBX pour interagir avec un pool n’étaient pas présentes (voir plus haut dans cette rubrique).

Une passerelle RTC, un PBX IP ou un homologue de réseau SIP en particulier peuvent être routés vers plusieurs serveurs ou Trunks de médiation. Le nombre de passerelles qu’un pool particulier de serveurs de médiation peut contrôler dépend du nombre d’appels utilisant une dérivation multimédia. Si un grand nombre d’appels utilise le contournement du contenu multimédia, un serveur de médiation du pool peut gérer de nombreux appels, car seul le traitement de la couche de signalisation est nécessaire.

</div>

<span> </span>

</div>

</div>

</div>

