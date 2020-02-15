---
title: 'Lync Server 2013 : configuration technique requise pour la déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b962905870287ef6765ecb6e7ee9b3e321ac6a8e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Pour chaque appel au RTC, le serveur de médiation détermine si les médias du point de terminaison Lync peuvent être envoyés directement à un homologue de serveur de médiation sans traverser le serveur de médiation. L’homologue peut être une passerelle PSTN, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP) associé à la jonction entre le serveur de médiation où l’appel est routé.

Le contournement de média peut être utilisé lorsque les conditions suivantes sont remplies :

  - Un homologue de serveur de médiation doit prendre en charge les fonctionnalités nécessaires à la déviation du trafic multimédia, la plus importante étant la possibilité de gérer plusieurs réponses branches (appelées « boîtes de dialogue précoces »). Contactez le fabricant de votre passerelle ou système PBX, ou votre fournisseur ITSP, pour obtenir la valeur du nombre maximal de boîtes de dialogue préliminaires que la passerelle, PBX ou SBC peut accepter.

  - L’homologue du serveur de médiation doit accepter le trafic multimédia directement à partir des points de terminaison Lync. De nombreux ITSPs autorisent leur SBC à recevoir du trafic uniquement à partir du serveur de médiation. Contactez votre téléphonie Internet pour déterminer si sa SBC accepte le trafic multimédia directement depuis les points de terminaison Lync.

  - Les clients Lync et un homologue de serveur de médiation doivent être bien connectés, ce qui signifie qu’ils sont situés dans la même région réseau ou sur des sites réseau qui se connectent à la région sur des liaisons de réseau étendu qui n’ont pas de contraintes de bande passante.

<div>

## <a name="see-also"></a>Voir aussi


[Modes de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

