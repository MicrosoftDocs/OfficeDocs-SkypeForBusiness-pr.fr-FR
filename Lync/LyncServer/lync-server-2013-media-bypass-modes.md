---
title: 'Lync Server 2013 : modes de déviation du trafic multimédia'
description: 'Lync Server 2013 : modes de déviation du trafic multimédia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a7f1a71930df7ef92a29087f42bdb9382b3904c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577900"
---
# <a name="media-bypass-modes-in-lync-server-2013"></a>Modes de déviation du trafic multimédia dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

Vous devez configurer le contournement de média à la fois au niveau global et au niveau de chaque jonction PSTN. Lorsque vous activez le contournement de média au niveau global, vous avez le choix entre deux options : **Toujours ignorer** et **Utiliser la configuration des sites et des régions**.

L’option **Toujours ignorer** engendre une tentative de contournement pour tous les appels PSTN. **** Cette option s’applique aux déploiements au sein desquels il n’est pas nécessaire d’activer le contrôle d’admission des appels ou pour lesquels il n’est pas nécessaire de spécifier des informations de configuration détaillées sur les tentatives de contournement de média. De plus, **Toujours ignorer** est utilisée lorsque la connectivité entre les clients et les passerelles PSTN est satisfaisante. Dans cette configuration, les sous-réseaux sont mappés à un seul ID de contournement, qui est calculé par le système.

L’option **Utiliser la configuration des sites et des régions** associe l’ID de contournement à la configuration de site ou de région chargée de prendre la décision relative au contournement. Cette configuration présente l’avantage d’apporter la souplesse de configurer le contournement pour la plupart des topologies courantes. Elle permet de contrôler de manière précise quand le contournement doit se produire et prend en charge les interactions avec le contrôle d’admission des appels (CAC). Le système tente de vous faciliter la tâche en affectant automatiquement des ID de contournement comme indiqué ci-dessous.

  - Le système affecte automatiquement un ID de contournement unique à chaque région.

  - Tout site connecté à une région via une liaison de réseau étendu (WAN) non soumise à des contraintes de bande passante hérite du même ID de contournement que la région.

  - Un site connecté à une région via une liaison de réseau étendu à bande passante restreinte se voit affecter un ID de contournement différent de celui de la région.

  - Les sous-réseaux associés à chaque site héritent de l’ID de contournement de ce site.

<div>

## <a name="see-also"></a>Voir aussi


[Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

