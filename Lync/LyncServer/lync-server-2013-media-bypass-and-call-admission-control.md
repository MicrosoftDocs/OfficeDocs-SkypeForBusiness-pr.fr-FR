---
title: 'Lync Server 2013 : déviation du trafic multimédia et contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0a2df9eee6ee9cf0ca387c9098623d574292a27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a>Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-05_

La déviation du trafic multimédia et le contrôle d’admission des appels (CAC) permettent de gérer le contrôle de la bande passante des appels. La déviation du trafic multimédia facilite le flux de médias sur les liens bien connectés ; CAC gère le trafic sur les liens avec des contraintes de bande passante. Étant donné que la déviation du trafic multimédia et le contrôle d’admission des médias s’excluent mutuellement, vous devez être attentif à un lors de la planification de l’autre. Les combinaisons suivantes sont prises en charge :

  - Le contrôle d’admission des médias et la déviation du trafic multimédia sont activés. La déviation du trafic multimédia doit être configurée pour **utiliser les informations de site et de région**. Ces informations sur les sites et les régions sont les mêmes que celles utilisées pour le contrôle d’admission des messages.
    
    Si vous activez le contrôle d’admission des droits, vous ne pouvez pas sélectionner **toujours Bypass**, et inversement, car les deux configurations s’excluent mutuellement. Autrement dit, seule l’une des deux s’applique à un appel RTC donné. Tout d’abord, une vérification est effectuée afin de déterminer si la déviation du trafic multimédia s’applique à l’appel. Si c’est le cas, CAC n’est pas utilisé. Cela est logique, car si un appel est éligible pour contournement, il est par définition à l’aide d’une connexion où CAC n’est pas nécessaire. Si la contourner ne peut pas être appliquée à l’appel (autrement dit, si les ID de contournement du client et de la passerelle ne correspondent pas), le contrôle d’admission des appels est appliqué à l’appel.

  - CAC non activé et contournement de média défini sur **toujours Bypass**.
    
    Dans cette configuration, les sous-réseaux de client et de jonction sont mappés à un seul ID de contournement, qui est calculé par le système.

  - CAC non activé et contournement de média défini pour **utiliser les informations de site et de région**.
    
    Lorsque les **informations de site et de région** sont activées, la détermination de contournement fonctionne de la même manière, que CAC soit activé ou non. Autrement dit, pour tout appel RTC donné, le sous-réseau du client est mappé à un site particulier, et l’ID de contournement pour ce sous-réseau est extrait. De même, le sous-réseau de la passerelle est mappé à un site particulier, et l’ID de contournement pour ce sous-réseau est extrait. Uniquement si les deux ID de contournement sont identiques, le contournement se produit pour l’appel. Si elles ne sont pas identiques, la déviation du trafic multimédia ne se produira pas.
    
    Même si le contrôle d’admission des appel est désactivé globalement, la stratégie de bande passante doit être définie pour chaque site et lien si vous voulez utiliser la configuration de site et de région pour contrôler la décision de contournement. La valeur réelle de la contrainte de bande passante ou sa modalité n’a pas d’importance. Le but ultime est de faire en sorte que le système calcule automatiquement différents ID de contournement à associer à différents paramètres régionaux qui ne sont pas bien connectés. La définition d’une contrainte de bande passante par définition signifie qu’un lien n’est pas bien connecté.

  - Le contrôle d’admission des médias est activé et la déviation du trafic multimédia n’est pas activée. Cela ne s’applique que si toutes les passerelles et tous les PBX IP ne sont pas bien connectés ou ne répondent pas à d’autres exigences pour la déviation du trafic multimédia. Pour plus d’informations sur les conditions requises pour la déviation du trafic multimédia, voir [Technical Requirements for Media Bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).

<div>

## <a name="see-also"></a>Voir aussi


[Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Modes de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

