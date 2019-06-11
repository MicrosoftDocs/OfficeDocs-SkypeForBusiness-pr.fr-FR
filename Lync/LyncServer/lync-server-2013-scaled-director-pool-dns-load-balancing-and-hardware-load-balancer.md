---
title: Pool directeur mis à l’échelle - Équilibrage de charge DNS et équilibreur de charge matérielle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cd92304ca3a1147737958ad9d9fc94a49b2e5e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Pool directeur mis à l’échelle - Équilibrage de charge DNS et équilibreur de charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

Un pool de Directors mis à l’échelle, dans lequel plusieurs Director sont déployés pour gérer une capacité supplémentaire et de garantir une haute disponibilité, nécessitent un équilibrage de charge pour distribuer la communication du client et du serveur à tous les membres du pool. Un directeur héberge des services Web de la même façon qu’un pool frontal. Pour fournir l’équilibrage de charge, vous pouvez utiliser le service d’équilibrage de la charge matérielle ou d’équilibrage de la charge matérielle et l’équilibrage de charge matérielle. L’équilibrage de charge matérielle est requis pour les services Web et l’équilibrage de charge DNS seul ne fournit pas les fonctionnalités requises pour les services Web.

Les rubriques suivantes décrivent les considérations en matière de planification pour le déploiement d’un pool de directeurs à l’aide de l’équilibrage de charge DNS conjointement avec l’équilibrage de charge matérielle. Si vous envisagez d’utiliser l’équilibrage de charge matérielle, mais pas l’équilibrage de charge DNS pour le pool de directeurs, voir la rubrique mise à l’échelle de l’application du [pool de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) qui décrit les exigences de planification pour cette topologie.

![Pool de Directors mis] à l’échelle (images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Pool de Directors mis") à l’échelle

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé des certificats - Équilibrage de charge DNS et matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Résumé des ports - Équilibrage de charge DNS et matérielle dans Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Résumé des enregistrements DNS - Équilibrage de charge DNS et matérielle dans Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

