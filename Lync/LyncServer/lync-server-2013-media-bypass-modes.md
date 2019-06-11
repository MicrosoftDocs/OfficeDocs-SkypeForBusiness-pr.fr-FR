---
title: 'Lync Server 2013 : Modes de déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a08ec3ae6d985c18e20964a857a74ad40bc7668d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a>Modes de déviation du trafic multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-05_

Vous devez configurer la déviation du trafic multimédia à la fois au niveau global et au niveau de chaque jonction PSTN. Lorsque vous activez la déviation du trafic multimédia au niveau global, vous avez le choix entre deux options : **Toujours ignorer** et **Utiliser la configuration des sites et des régions**.

As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.

L’option **Utiliser la configuration des sites et des régions** associe l’ID de contournement à la configuration de site ou de région chargée de prendre la décision relative au contournement. Cette configuration présente l’avantage d’apporter la flexibilité de configurer le contournement pour la plupart des topologies courantes. Elle permet de contrôler de manière précise quand le contournement doit se produire et prend en charge les interactions avec le contrôle d’admission des appels (CAC). Le système tente de vous faciliter la tâche en affectant automatiquement des ID de contournement comme indiqué ci-dessous.

  - Le système affecte automatiquement un ID de contournement unique à chaque région.

  - Tout site connecté à une région via une liaison de réseau étendu (WAN) non soumise à des contraintes de bande passante hérite du même ID de contournement que la région.

  - Un site connecté à une région via une liaison de réseau étendu à bande passante restreinte se voit affecter un ID de contournement différent de celui de la région.

  - Les sous-réseaux associés à chaque site héritent de l’ID de contournement de ce site.

<div>

## <a name="see-also"></a>Voir aussi


[Présentation de l’exclusion de médias dans Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

