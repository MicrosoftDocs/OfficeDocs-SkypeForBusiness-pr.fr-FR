---
title: Compatibilité de Lync Server 2013 avec la résistance de site métropolitain de Lync Server 2010
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
ms.openlocfilehash: 04b3cca41b0ea7a7060e6349127dc7c7fb1732ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526051"
---
# <a name="lync-server-2010-metropolitan-site-resiliency"></a>Résilience de site métropolitain Lync Server 2010

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-19_

La solution de résistance de site métropolitain prise en charge pour Lync Server 2010 n’est pas prise en charge pour Lync Server 2013. Cette solution nécessitait qu’un seul pool frontal couvre deux centres de données au sein de la même zone métropolitaine.

La solution de résistance de site métropolitain a été conçue pour effectuer une récupération à partir de la perte d’un centre de déplacement complet. Lorsque vous englobez votre pool sur deux centres de ressources, vous placez généralement la moitié de vos serveurs frontaux dans un centre de de serveurs et l’autre moitié dans le deuxième centre de ressources. Si vous perdez l’intégralité d’un centre de données, vous avez perdu la moitié de vos serveurs frontaux. Cela peut entraîner des problèmes avec le nouveau modèle de système distribué pour les pools frontaux dans Lync Server 2013. Pour plus d’informations, voir [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

</div>

<span> </span>

</div>

</div>

</div>

