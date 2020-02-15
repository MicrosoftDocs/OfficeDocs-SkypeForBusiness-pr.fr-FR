---
title: Pool directeur mis à l’ampleur-équilibrage de charge DNS et équilibreur de charge matérielle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af050cbef7c75bb7b403dc4ef74c4750a9e8b3c3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Pool directeur mis à l’ampleur-équilibrage de charge DNS et équilibreur de charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Un pool directeur mis à l’ampleur, dans lequel plusieurs directeurs sont déployés pour gérer les capacités supplémentaires et pour fournir une haute disponibilité, nécessite un équilibrage de charge pour distribuer la communication client et serveur à tous les membres du pool. Un directeur héberge des services Web de la même manière qu’un pool frontal. Vous pouvez utiliser soit l’équilibrage de la charge matérielle, soit l’équilibrage de la charge DNS (Domain Name System) et l’équilibrage de la charge matérielle. L’équilibrage de la charge matérielle est nécessaire pour les services web et l’équilibrage de la charge DNS seul ne procure pas les fonctionnalités requises pour les services web.

Les rubriques suivantes décrivent les considérations relatives à la planification du déploiement d’un pool directeur à l’aide de l’équilibrage de charge DNS en association avec l’équilibrage de charge matérielle. Si vous envisagez d’utiliser l’équilibrage de charge matérielle, mais pas l’équilibrage de charge DNS pour le pool Directeur, reportez-vous à la rubrique [pool directord directord-équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) qui décrit les exigences de planification pour cette topologie.

![Pool directeur mis à l’échelle](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Pool directeur mis à l’échelle")

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Résumé des certificats-charge DNS et charge matérielle équilibrée dans Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Résumé des ports-équilibrage de charge DNS et charge matérielle dans Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Résumé des enregistrements DNS-charge DNS et charge matérielle équilibrée dans Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

