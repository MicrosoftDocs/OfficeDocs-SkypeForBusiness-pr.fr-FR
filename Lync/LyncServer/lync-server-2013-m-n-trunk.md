---
title: 'Lync Server 2013 : jonction M :N'
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
ms.openlocfilehash: 15e18bff7fa6031101f73ba4b5ce11f5a0d3c015
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mn-trunk-in-lync-server-2013"></a>Jonction M :N dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Lync Server 2013 prend en charge une plus grande flexibilité dans la définition d’une jonction à des fins de routage des appels à partir des versions précédentes. Une jonction est une association logique entre un serveur de médiation et un numéro de port d’écoute avec une passerelle et un numéro de port d’écoute. Cela implique plusieurs éléments : un serveur de médiation peut avoir plusieurs jonctions à la même passerelle ; un serveur de médiation peut avoir plusieurs tronçons vers différentes passerelles ; Inversement une passerelle peut avoir plusieurs jonctions à différents serveurs de médiation.

Une jonction racine doit encore être créée lorsqu’une passerelle est ajoutée à la topologie Lync à l’aide du générateur de topologie. Le nombre de passerelles qu’un serveur de médiation donné peut gérer dépend de la capacité de traitement du serveur pendant les heures de pointe. Si vous déployez un serveur de médiation sur un matériel dépassant la configuration matérielle minimale requise pour Lync Server 2013, comme décrit dans Hardware Supported [for Lync server 2013](lync-server-2013-supported-hardware.md) dans la documentation de prise en charge, l’estimation du nombre d’appels de non-contournement actifs pouvant être gérés par un serveur de médiation autonome est d’environ 1000 appels. Lorsqu’il est déployé sur le matériel répondant à ces spécifications, le serveur de médiation est supposé effectuer le transcodage, mais continuer à acheminer les appels pour plusieurs passerelles, même si les passerelles ne prennent pas en charge la déviation du trafic multimédia.

Lors de la définition d’un itinéraire d’appel, vous spécifiez les jonctions associées à cet itinéraire, mais vous ne spécifiez pas les serveurs de médiation associés à cet itinéraire. Au lieu de cela, vous utilisez le générateur de topologie pour associer des jonctions aux serveurs de médiation. En d’autres termes, le routage détermine quelle jonction utiliser pour un appel et, par la suite, le serveur de médiation associé à cette jonction reçoit la signalisation pour cet appel.

Le serveur de médiation peut être déployé en tant que pool ; ce pool peut être colocalisé avec un pool frontal ou déployé en tant que pool autonome. Lorsqu’un serveur de médiation est colocalisé avec un pool frontal, la taille du pool peut être de 12 (la limite de la taille du pool de serveurs d’inscriptions). Ensemble, ces nouvelles fonctionnalités augmentent la fiabilité et la flexibilité de déploiement pour les serveurs de médiation, mais elles nécessitent des fonctionnalités associées dans les entités homologues suivantes :

  - **Passerelle PSTN.** Une passerelle qualifiée Lync Server 2013 doit implémenter l’équilibrage de charge DNS, ce qui permet à une passerelle de réseau téléphonique commuté (PSTN) qualifiée de se comporter comme un équilibreur de charge pour un pool de serveurs de médiation, et donc de équilibrer la charge des appels dans le pool.

  - **Contrôleur de frontière de session.** Pour une jonction SIP, l’entité homologue est un contrôleur de frontière de session (SBC) sur un fournisseur de services de téléphonie Internet. Dans le sens du pool de serveurs de médiation vers l’SBC, l’SBC peut recevoir des connexions à partir de n’importe quel serveur de médiation du pool. Dans le sens de la SBC vers le pool, le trafic peut être envoyé à n’importe quel serveur de médiation du pool. L’équilibrage de charge DNS, s’il est pris en charge par le fournisseur de services et SBC, est une méthode permettant d’atteindre ce objectif. Une autre solution consiste à donner aux fournisseurs de services les adresses IP de tous les serveurs de médiation du pool, et le fournisseur de services les configure dans leur SBC en tant que jonction SIP distincte pour chaque serveur de médiation. Le fournisseur de services gère alors l’équilibrage de charge pour ses propres serveurs. Tous les fournisseurs de services ou les contrôleurs SBC ne peuvent pas prendre en charge ces fonctionnalités. Par ailleurs, le fournisseur de services peut facturer des frais supplémentaires pour cette fonctionnalité. En règle générale, chaque jonction SIP vers la SBC entraîne une redevance mensuelle.

  - **IP-PBX.** Dans le sens du pool de serveurs de médiation vers l’arrêt SIP IP-PBX, le système IP-PBX peut recevoir des connexions à partir de n’importe quel serveur de médiation du pool. Dans le sens entre le système PBX IP et le pool, le trafic peut être envoyé à n’importe quel serveur de médiation du pool. Étant donné que la plupart des IP-PBX ne prennent pas en charge l’équilibrage de charge DNS, nous vous recommandons de définir des connexions SIP directes individuelles à partir du système IP-PBX vers chaque serveur de médiation du pool. Le système IP-PBX gère ensuite son propre équilibrage de charge en répartissant le trafic dans le groupe de jonctions. Le groupe de jonctions est supposé avoir un ensemble cohérent de règles de routage sur le système IP-PBX. Si un système IP-PBX particulier prend en charge ce concept de groupe de jonction et comment il croise la redondance et l’architecture de cluster de l’IP-PBX, il doit être déterminé avant de décider si un cluster de serveurs de médiation peut interagir correctement avec un système IP-PBX.

Un pool de serveurs de médiation doit avoir une vue uniforme de la passerelle homologue avec laquelle il interagit. Cela signifie que tous les membres du pool accèdent à la même définition de passerelle homologue à partir du magasin de configurations et qu’ils ont tous autant de chances d’interagir avec elle pour les appels sortants. Par conséquent, il n’est pas possible de segmenter le pool pour que certains serveurs de médiation communiquent avec certains homologues de passerelle pour les appels sortants. Si une telle segmentation est nécessaire, un pool de serveurs de médiation distinct doit être utilisé. Ce serait le cas, par exemple, si les fonctionnalités associées dans les passerelles PSTN, jonctions SIP ou systèmes IP-PBX pour interagir avec un pool n’étaient pas présentes (voir plus haut dans cette rubrique).

Une passerelle PSTN particulière, un système IP-PBX ou un homologue de jonction SIP peut acheminer vers plusieurs serveurs de médiation ou jonctions. Le nombre de passerelles qu’un pool particulier de serveurs de médiation peut contrôler dépend du nombre d’appels qui utilisent la déviation du trafic multimédia. Si un grand nombre d’appels utilise la déviation du trafic multimédia, un serveur de médiation du pool peut gérer un plus grand nombre d’appels, car seul le traitement de la couche de signalisation est nécessaire.

</div>

<span> </span>

</div>

</div>

</div>

