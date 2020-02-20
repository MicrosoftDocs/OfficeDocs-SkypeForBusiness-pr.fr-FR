---
title: 'Lync Server 2013 : nouvelle fonctionnalité de jonction'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 751d8cbbb4ab7a10ca468c0156e14a45c065fd25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="adead-102">Nouvelle fonctionnalité de jonction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adead-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adead-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="adead-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="adead-104">Dans Microsoft Lync Server 2013, plusieurs jonctions entre un serveur de médiation et une passerelle peuvent être définies.</span><span class="sxs-lookup"><span data-stu-id="adead-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="adead-105">Microsoft Lync Server 2010 uniquement autorisé pour une seule jonction entre un serveur de médiation et une passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="adead-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="adead-106">Cette fonctionnalité permet de définir des jonctions supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="adead-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="adead-107">Une jonction est une association logique entre le nom de domaine complet du serveur de médiation et le port d’écoute, ainsi qu’un nom de domaine complet et un port d’écoute de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="adead-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="adead-108">Cette nouvelle fonctionnalité permet une définition de jonction facile pour la résilience (où plusieurs serveurs de médiation peuvent être utilisés pour acheminer les appels vers la même passerelle RTC), pour l’interopérabilité des PBX, où plusieurs jonctions avec différentes stratégies associées peuvent être utilisées entre et IP-PBX et un serveur de médiation, et pour les configurations de jonction SIP où les serveurs de médiation sur différents sites ont des jonctions SIP vers l’opérateur référencées par le même nom de domaine complet du transporteur.</span><span class="sxs-lookup"><span data-stu-id="adead-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="adead-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="adead-109">See Also</span></span>


[<span data-ttu-id="adead-110">Nouvelles fonctionnalités voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adead-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

