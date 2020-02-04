---
title: 'Lync Server 2013 : Nouvelle fonctionnalité de jonction'
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
ms.openlocfilehash: 962da42567ffcc1c0d541b74266ac5bb1b4653c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="a66ac-102">Nouvelle fonctionnalité de jonction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a66ac-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a66ac-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a66ac-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a66ac-104">Dans Microsoft Lync Server 2013, plusieurs ISL entre un serveur de médiation et une passerelle peuvent être définies.</span><span class="sxs-lookup"><span data-stu-id="a66ac-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="a66ac-105">Microsoft Lync Server 2010 uniquement autorisé pour une ISL unique entre un serveur de médiation et une passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="a66ac-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="a66ac-106">Cette fonctionnalité permet de définir davantage de Trunks.</span><span class="sxs-lookup"><span data-stu-id="a66ac-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="a66ac-107">Un Trunk est une association logique entre un nom de domaine complet du serveur de médiation et un port d’écoute et un nom de domaine complet et un port d’écoute de la passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="a66ac-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="a66ac-108">Cette nouvelle fonctionnalité permet une définition de Trunk simple pour la résilience (qui permet d’utiliser plusieurs serveurs de médiation pour acheminer les appels vers la même passerelle RTC), en fonction de l’interopérabilité de PBX, dans laquelle plusieurs lignes associées à différentes stratégies associées peuvent être utilisées entre et Par le biais d’un PBX IP et d’un serveur de médiation, et pour les configurations SIP Trunk pour lesquelles des serveurs de médiation sur différents sites disposent de lignes SIP sur l’opérateur de nom de domaine complet du transporteur.</span><span class="sxs-lookup"><span data-stu-id="a66ac-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a66ac-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a66ac-109">See Also</span></span>


[<span data-ttu-id="a66ac-110">Nouvelles fonctionnalités Voix Entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a66ac-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

