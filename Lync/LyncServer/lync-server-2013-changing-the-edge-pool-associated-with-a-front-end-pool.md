---
title: 'Lync Server 2013 : Modification du pool de serveurs Edge associé à un pool de serveurs frontaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>Modification du pool de serveurs Edge associé à un pool de serveurs frontaux dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Si un pool de bords est en panne alors que le pool frontal sur le même site est toujours en cours d’exécution, vous devez définir le pool frontal pour qu’il utilise un pool de bords sur un autre site jusqu’à ce que le pool de frontière en panne soit restauré.

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>Modification de la liste de serveurs Edge associée à un pool frontal

1.  Dans le générateur de topologie, accédez au nom de la réserve frontale que vous devez modifier.

2.  Cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.

3.  Dans la section **associations** , sous **associer le pool de bords (pour les composants multimédias)**, utilisez la zone de liste déroulante pour sélectionner le pool de bords avec lequel vous voulez associer ce pool frontal.

4.  Cliquez sur **OK**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Récupération d’urgence de serveur Edge dans Lync Server 2013](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

