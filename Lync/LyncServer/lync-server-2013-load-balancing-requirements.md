---
title: Configuration requise pour l’équilibrage de charge de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83e5ebe92601b839f50604a93f10f7fc2f5d7deb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Exigences en matière d’équilibrage de charge pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Si vous disposez de pools frontaux, de pools directeurs ou de pools de serveurs Edge, vous devez déployer l’équilibrage de charge pour ces pools. L’équilibrage de la charge distribue le trafic entre les serveurs dans un pool.

Lync Server 2013 prend en charge deux types de solutions d’équilibrage de charge pour le trafic client à serveur : l’équilibrage de charge DNS (Domain Name System) et l’équilibrage de la charge matérielle. L’équilibrage de charge DNS offre plusieurs avantages, notamment l’administration simplifiée, une résolution des problèmes plus efficace et la possibilité d’isoler la plupart du trafic Lync Server des problèmes potentiels d’équilibreur de charge matériel.

Déterminez la solution d’équilibrage de la charge adaptée à chaque pool de votre déploiement, en gardant à l’esprit les restrictions suivantes :

  - Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de la charge. Vous ne pouvez pas utiliser l’équilibrage de la charge DNS sur une interface et l’équilibrage de la charge matérielle sur l’autre.

  - Certains types de trafic nécessitent un programme d’équilibrage de la charge matérielle. Par exemple, le trafic HTTP requiert un programme d’équilibrage de la charge matérielle plutôt que l’équilibrage de la charge DNS. Celui-ci ne fonctionne pas avec le trafic web client-à-serveur.

Pour plus d’informations sur le choix d’une solution d’équilibrage de la charge matérielle, voir [Configuration requise de l’équilibreur de charge matérielle pour Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).

Si vous décidez d’utiliser l’équilibrage de la charge DNS pour un pool mais que vous souhaitez quand même implémenter des programmes d’équilibrage de la charge matérielle pour certains types de trafics, tels que le trafic HTTP, l’administration des programmes d’équilibrage de la charge matérielle est grandement simplifiée. Par exemple, la configuration de l’équilibreur de la charge matérielle sera plus simple, car elle ne gérera que le trafic HTTP et HTTPs, tandis que tous les autres protocoles seront gérés par l’équilibrage de la charge DNS. Pour plus d’informations, reportez-vous à la rubrique [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).

Pour le trafic de serveur à serveur, Lync Server 2013 utilise un équilibrage de charge prenant en charge la topologie. Les serveurs lisent la topologie publiée dans le magasin central de gestion pour obtenir les noms de domaine complets des serveurs dans la topologie et distribuent automatiquement le trafic entre les serveurs. Les administrateurs n’ont pas besoin de configurer ou de gérer ce type d’équilibrage de charge.

Si vous utilisez l’équilibrage de la charge DNS et que vous avez besoin de bloquer le trafic sur un ordinateur spécifique, il ne suffit pas de supprimer les entrées d’adresses IP du nom de domaine complet du pool. Vous devez également supprimer l’entrée DNS pour l’ordinateur.

</div>

<span> </span>

</div>

</div>

</div>

