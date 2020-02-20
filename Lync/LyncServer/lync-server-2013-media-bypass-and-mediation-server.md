---
title: 'Lync Server 2013 : contournement de média et serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a33ed2c9b3494e9c67e8ac4a658b6aee75ff7649
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Contournement de média et serveur de médiation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

La déviation du trafic multimédia est une fonctionnalité Lync Server qui permet à un administrateur de configurer le routage des appels pour qu’il circule directement entre le point de terminaison de l’utilisateur et la passerelle PSTN sans traverser le serveur de médiation. La déviation du trafic multimédia améliore la qualité des appels en réduisant la latence, la traduction inutile, la perte de paquets possible et le nombre de points de défaillance potentiels. Lorsqu’un site distant dépourvu de serveur de médiation est connecté à un site central par une ou plusieurs liaisons de réseau étendu avec bande passante limitée, le contournement de média diminue la bande passante requise en permettant à un client situé sur un site distant de circuler directement vers sa passerelle locale sans Il faut d’abord circuler sur la liaison de réseau étendu vers un serveur de médiation sur le site central et inversement. Cette réduction du traitement multimédia complète également la capacité du serveur de médiation à contrôler plusieurs passerelles.

Le contournement de média et le contrôle d’admission des appels s’excluent mutuellement. Si le contournement de média est utilisé pour un appel, le contrôle d’admission des appels n’est pas effectué pour cet appel. L’hypothèse repose sur le fait qu’aucun lien avec bande passante restreinte n’est impliqué dans l’appel.

<div>

## <a name="see-also"></a>Voir aussi


[Contrôle d’admission des appels et serveur de médiation dans Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

