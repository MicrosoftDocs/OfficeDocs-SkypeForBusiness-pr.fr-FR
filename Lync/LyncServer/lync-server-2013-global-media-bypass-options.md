---
title: 'Lync Server 2013 : options globales de déviation du trafic multimédia'
description: 'Lync Server 2013 : options globales de déviation du trafic multimédia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e69a776c13171d74666a202108fa4b5c72e224d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554550"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a>Options globales de déviation du trafic multimédia dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

<div>


> [!NOTE]  
> Cette rubrique suppose que vous ayez déjà configuré la déviation du trafic multimédia pour toutes les jonctions à un homologue (une passerelle RTC (réseau téléphonique commuté), un système IP-PBX ou un contrôleur SBC (session Border Controller) sur un fournisseur de services de téléphonie Internet) pour un site ou un service spécifique pour lequel vous souhaitez que le support contourne le serveur de médiation.



</div>

En plus d’activer le contournement de média pour des connexions de jonction associées à un homologue, vous devez également configurer les paramètres globaux du contournement de média. Les paramètres globaux de déviation du trafic multimédia peuvent spécifier que la déviation du trafic multimédia pour les appels vers le RTC ou cette déviation du trafic multimédia est utilisée en utilisant le mappage des sous-réseaux aux sites réseau et aux régions réseau, de la même manière que le contrôle d’admission des appels, une autre fonctionnalité vocale avancée. Lorsque la déviation du trafic multimédia et le contrôle d’admission des appels sont tous les deux activés, les informations de région réseau, de site réseau et de sous-réseau spécifiées pour le contrôle d’admission des appels sont automatiquement utilisées pour déterminer s’il faut employer le contournement de média. Cela signifie que vous ne pouvez pas spécifier que la déviation du trafic multimédia est toujours tentée pour les appels au réseau téléphonique commuté lorsque le contrôle d’admission des appels est activé.

Cette rubrique décrit comment utiliser le panneau de configuration Lync Server et Lync Server Management Shell conjointement pour configurer les paramètres globaux de contournement de média.

<div>


> [!NOTE]  
> Pour configurer le contournement de média en suivant cette procédure, la connectivité entre les clients et l’homologue du serveur de médiation (par exemple, une passerelle PSTN, un PBX IP ou un contrôleur de frontière de session d’un fournisseur de jonction SIP) doit être bonne. Si des restrictions de bande passante sont appliquées sur la liaison, le contournement de média ne peut pas être appliqué aux appels. Le contournement de média ne va pas interagir avec chaque passerelle PSTN, chaque système IP-PBX et chaque SBC. Microsoft a testé un ensemble de passerelles PSTN et de contrôleurs SBC avec des partenaires agréés et a effectué quelques tests avec les systèmes IP-PBX de Cisco. La déviation du trafic multimédia n’est prise en charge qu’avec les produits et les versions mentionnés dans le programme d’interopérabilité ouvert pour les communications unifiées – Lync Server à <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>Étapes suivantes : choisir les paramètres globaux du contournement de média

Après avoir activé le contournement de média sur des connexions de jonction vers un homologue pour des sites ou des services spécifiques, utilisez le contenu suivant pour :

  - Activez toujours la déviation du trafic multimédia, comme indiqué dans [configure Media Bypass in Lync Server 2013 pour toujours contourner le serveur de médiation](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).

  - Ou configurez la déviation du trafic multimédia pour utiliser les informations de site et de région, comme indiqué dans [configure Media Bypass Global Settings in Lync Server 2013 pour utiliser les informations de site et de région](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[Configurer la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Contournement de média et serveur de médiation dans Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

