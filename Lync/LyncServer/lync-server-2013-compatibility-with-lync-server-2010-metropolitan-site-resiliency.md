---
title: Compatibilité de Lync Server 2013 avec la résistance de sites métropolitains Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395ec568ebafea5c7a06e19340ff5ad10158ffb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Résistance de sites métropolitains Lync Server 2010

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-19_

La solution de résilience de site métropolitaine prise en charge pour Lync Server 2010 n’est pas prise en charge pour Lync Server 2013. Cette solution impliquait le fractionnement d’un pool frontal unique entre deux centres de données dans la même zone métropolitaine.

La solution de résilience du site métropolitain a été conçue pour être récupérée suite à la perte d’un datacenter complet. Lorsque vous étendez votre réserve sur deux centres de serveurs, vous placez en général la moitié de vos extrémités au sein d’un centre de ressources et l’autre moitié dans le deuxième centre de ressources. Si vous perdez l’intégralité d’un centre de données, vous avez perdu la moitié de vos serveurs frontaux. Cela peut poser des problèmes avec le nouveau modèle de système distribué pour les pools front-end dans Lync Server 2013. Pour plus d’informations, reportez-vous à la rubrique [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

</div>

<span> </span>

</div>

</div>

</div>

