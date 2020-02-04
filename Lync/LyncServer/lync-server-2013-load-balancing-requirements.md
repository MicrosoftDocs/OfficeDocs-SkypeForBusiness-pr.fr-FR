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
ms.openlocfilehash: 8081ba60d826f0f765533abdb6c0f548045a7fa8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Exigences d’équilibrage de charge pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Si vous disposez de pools de serveurs frontaux, de pools de directeurs ou de serveurs de périphérie, vous devez déployer l’équilibrage de charge pour ces pools. Lʼéquilibrage de charge distribue le trafic entre les serveurs dans un pool.

Lync Server 2013 prend en charge deux types de solutions d’équilibrage de charge pour le trafic client à serveur : l’équilibrage de charge DNS (Domain Name System) et l’équilibrage de charge matérielle. Le service d’équilibrage de la charge DNS offre plusieurs avantages, notamment une administration plus simple, un dépannage plus efficace et la possibilité d’isoler une grande partie du trafic de votre serveur Lync de tout problème éventuel d’équilibrage de charge matériel.

Déterminez la solution d’équilibrage de charge adaptée à chaque pool de votre déploiement, en gardant à l’esprit les restrictions suivantes :

  - Les interfaces Edge interne et externe doivent utiliser le même type d’équilibrage de charge. Vous ne pouvez pas utiliser l’équilibrage de charge DNS sur une interface et l’équilibrage de charge matérielle sur l’autre.

  - Certains types de trafic nécessitent un programme dʼéquilibrage de charge matérielle. Par exemple, le trafic HTTP requiert un équilibrage de charge matérielle plutôt que l’équilibrage de charge DNS. Celui-ci ne fonctionne pas avec le trafic web client à serveur.

Pour plus d’informations sur le choix d’une solution d’équilibrage de charge matérielle, voir [Configuration requise pour l’équilibrage de charge matérielle pour Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).

Si vous décidez d’utiliser l’équilibrage de la charge DNS pour un pool mais que vous souhaitez quand même implémenter des équilibreurs de la charge matérielle pour certains types de trafics, tels que le trafic HTTP, l’administration des équilibreurs de la charge matérielle est grandement simplifiée. Par exemple, l’équilibreur de charge matérielle sera plus simple car il ne gérera que le trafic HTTP et HTTPS, alors que tous les autres protocoles seront gérés par l’équilibrage de charge DNS. Pour plus d’informations, voir [équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md).

Pour le trafic de serveur à serveur, Lync Server 2013 utilise l’équilibrage de charge prenant en charge la topologie. Les serveurs lisent la topologie publiée dans le magasin central de gestion pour obtenir les noms de domaine complets des serveurs dans la topologie et distribuent automatiquement le trafic entre les serveurs. Les administrateurs n’ont pas besoin de configurer ou de gérer ce type d’équilibrage de charge.

Si vous utilisez l’équilibrage de charge DNS et que vous voulez bloquer le trafic vers un ordinateur particulier, vous devez supprimer les adresses IP dans le nom de domaine complet du pool, mais également l’entrée DNS associée à l’ordinateur.

</div>

<span> </span>

</div>

</div>

</div>

