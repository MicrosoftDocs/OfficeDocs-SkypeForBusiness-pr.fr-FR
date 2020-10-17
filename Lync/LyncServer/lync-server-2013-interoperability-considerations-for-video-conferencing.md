---
title: 'Lync Server 2013 : considérations relatives à l’interopérabilité pour la conférence vidéo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f71977dc1909fa6993bc21f7944e821276dd86d6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498391"
---
# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Considérations relatives à l’interopérabilité pour la conférence vidéo dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Cette section décrit l’expérience utilisateur pendant la phase de coexistence de la migration, lorsqu’il existe une interopérabilité entre les clients hérités et un pool Lync Server 2013 ou Lync Server 2013 et un pool hérité.

<div>

## <a name="lync-server-2013-pools"></a>Pools Lync Server 2013

Les utilisateurs subissent les comportements suivants lorsqu’un client hérité est utilisé dans un pool Lync Server 2013 :

  - Pour les appels à deux, la résolution vidéo est la même que dans le pool hérité.

  - Pour les conférences à plusieurs, la résolution vidéo et les fonctionnalités de vidéoconférence sont les mêmes que celles du pool hérité. La vue Galerie et la haute résolution ne sont pas disponibles.

</div>

<div>

## <a name="legacy-pools"></a>Pools hérités

Les utilisateurs subissent le comportement suivant lorsqu’un client Lync Server 2013 est utilisé dans un pool hérité :

  - Pour les appels à deux, les clients Lync Server 2013 peuvent utiliser les nouvelles fonctionnalités comme suit :
    
      - H. 264 est disponible si les deux participants utilisent les clients Lync Server 2013.
    
      - Le client Lync Server 2013 utilise la valeur par défaut pour TotalReceiveVideoBitRateKb, car le serveur hérité n’envoie pas ces informations avec la mise en service intrabande.

  - Pour les conférences à plusieurs, la résolution vidéo et les fonctionnalités de vidéoconférence sont les mêmes que celles d’un client hérité dans le pool hérité.

<div>


> [!NOTE]  
> Lorsqu’un serveur hérité héberge un client Lync Server 2013, il est possible de configurer la bande passante de la vidéoconférence de sorte que tous les utilisateurs du pool reçoivent uniquement la vidéo basse résolution, mais envoient une vidéo haute résolution. Par exemple, lorsque MaxVideoRateAllowed est défini sur CAF-250K dans la configuration des médias et que VideoBitRateKb est défini sur 2000 kbits/s dans la stratégie de conférence. Dans ce cas, l’effet net est que la résolution élevée n’est pas possible pour les utilisateurs du pool.<BR>Comme MaxVideoRateAllowed n’est plus utilisé pour les clients Lync Server 2013, il ne peut pas empêcher les clients Lync Server 2013 de demander une vidéo à haute résolution. En revanche, vous pouvez affecter pour tous les utilisateurs du pool la même valeur à VideoBitRateKb et à MaxVideoRateAllowed (c’est-à-dire, CIF est défini sur 250 Kbits/s ou VGA est défini sur 600 Kbits/s ou HD est défini sur 1 500 Kbits/s).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

