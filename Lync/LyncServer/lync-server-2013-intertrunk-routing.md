---
title: 'Lync Server 2013 : routage interjonction'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce206c0f20dc00c6abc1304db8c1f933cbefdbca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Routage interjonctions dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Lync Server 2013 peut interconnecter un PBX IP à une passerelle de réseau téléphonique commuté (PSTN) de sorte que les appels provenant d’un téléphone PBX puissent être acheminés vers le RTC et que les appels RTC entrants puissent être acheminés vers un téléphone PBX (Private Branch Exchange). De même, Lync Server 2013 peut interconnecter deux systèmes IP-PBX ou plus afin que les appels puissent être passés et reçus entre les téléphones PBX à partir des différents systèmes IP-PBX.

Cette fonctionnalité de routage interjonction peut être configurée à l’aide de la cmdlet Lync Server Management Shell, **Set-applet cstrunkconfiguration**, avec le nouveau paramètre PstnUsages. Ce paramètre spécifie l’ensemble d’enregistrements d’utilisation PSTN à utiliser. Une jonction fait appel à cette utilisation PSTN pour déterminer un itinéraire et pour acheminer tous les appels entrants en conséquence.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

Le diagramme suivant illustre Lync Server 2013 fournissant une interconnexion entre une passerelle PSTN et un IP-PBX.

**Routage d’inter-jonctions entre la passerelle et le système IP-PBX**

![Diagramme de passerelle RTC/IP-PBX de connexion Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Diagramme de passerelle RTC/IP-PBX de connexion Lync Server")

Le diagramme suivant illustre Lync Server 2013 interconnectant deux systèmes IP-PBX.

**Routage d’inter-jonctions entre deux systèmes IP-PBXs**

![Diagramme de systèmes IP-PAX d’interconnexion de Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramme de systèmes IP-PAX d’interconnexion de Lync Server")

</div>

<span> </span>

</div>

</div>

</div>

