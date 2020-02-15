---
title: 'Lync Server 2013 : modification du pool de serveurs Edge associé à un pool frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7ad6ee6e40edb76d4ef5d7d53524f89e44a2aee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a>Modification du pool de serveurs Edge associé à un pool frontal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Si un pool de serveurs Edge est défaillant mais que le pool de serveurs frontaux du même site fonctionne encore, vous devrez définir le pool de serveurs frontaux pour qu’il utilise le pool de serveurs Edge d’un autre site jusqu’à ce que le pool de serveurs Edge défaillant soit restauré.

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a>Changement du pool de serveurs Edge associé à un pool de serveurs frontaux

1.  Dans le Générateur de topologie, accédez au nom du pool de serveurs frontaux que vous devez changer.

2.  Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.

3.  Dans la section **Associations**, sous **Associer le pool de serveurs Edge (pour les composants multimédias)**, utilisez la zone de liste déroulante pour sélectionner le pool de serveurs Edge que vous voulez associer à ce pool de serveurs frontaux.

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

