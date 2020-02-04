---
title: 'Lync Server 2013 : considérations d’interopérabilité pour les conférences vidéo'
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
ms.openlocfilehash: b8cdfa88cf6d6f58478ff3c6b44210545e24a765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Considérations en matière d’interopérabilité pour les conférences vidéo dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Cette section décrit l’utilisation de l’application par l’utilisateur lors de la phase de coexistence de la migration, en cas d’interopérabilité entre les clients hérités et un pool Lync Server 2013 ou un serveur Lync Server 2013.

<div>

## <a name="lync-server-2013-pools"></a>Pools Lync Server 2013

Les utilisateurs peuvent observer le comportement suivant lorsqu’un client hérité est utilisé dans un pool Lync Server 2013 :

  - Pour les appels à deux participants, la résolution vidéo est identique à celle du pool hérité.

  - Dans le cadre de conférences multiparties, les fonctionnalités de résolution vidéo et de visioconférence sont les mêmes que dans le pool hérité. Le mode Galerie et la haute résolution ne sont pas disponibles.

</div>

<div>

## <a name="legacy-pools"></a>Pools hérités

Les utilisateurs peuvent découvrir le comportement suivant lorsqu’un client Lync Server 2013 est utilisé dans un pool hérité :

  - Pour les appels à deux parties, les clients Lync Server 2013 peuvent utiliser les nouvelles fonctionnalités comme suit :
    
      - H. 264 est disponible si les deux participants utilisent les clients Lync Server 2013.
    
      - Le client Lync Server 2013 utilise la valeur par défaut pour TotalReceiveVideoBitRateKb, car le serveur hérité n’envoie pas ces informations avec la mise en service intrabande.

  - Dans le cadre de conférences multipièces, les fonctionnalités de résolution vidéo et de visioconférence sont les mêmes que celles d’un client hérité dans le pool hérité.

<div>


> [!NOTE]  
> Lorsqu’un serveur hérité héberge un client Lync Server 2013, il est possible de configurer une bande passante de conférence vidéo de sorte que tous les utilisateurs du pool reçoivent uniquement de la vidéo basse résolution, mais qu’ils envoient une vidéo haute résolution. C’est le cas, par exemple, lorsque MaxVideoRateAllowed est défini sur CAF-250K dans la configuration multimédia et VideoBitRateKb est défini sur 2000 KB/s dans la stratégie de conférence. Dans cette situation, l’effet net n’est pas possible pour les utilisateurs du pool.<BR>Étant donné que MaxVideoRateAllowed n’est plus utilisé pour les clients Lync Server 2013, il n’est pas possible d’empêcher les clients Lync Server 2013 de demander une vidéo haute résolution. Au lieu de cela, définissez VideoBitRateKb dans la stratégie de conférence pour que tous les utilisateurs du pool aient la même valeur que MaxVideoRateAllowed (c’est-à-dire que la valeur CAF est définie sur 250 kb/s, 600 ou la valeur HD est définie sur 1500 kb/s).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

