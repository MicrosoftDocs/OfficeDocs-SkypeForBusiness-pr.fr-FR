---
title: 'Lync Server 2013 : Routage interjonctions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1b66ea04ed72bab6d33114f52fa9fe96364b48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Routage interjonctions dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-20_

Lync Server 2013 peut interconnecter un PBX IP à une passerelle RTC (réseau téléphonique commuté) pour que les appels d’un téléphone PBX puissent être routés vers le RTC et que les appels RTC entrants puissent être routés vers un téléphone PBX (Private Branch Exchange). De la même façon, Lync Server 2013 peut interconnecter au moins deux systèmes IP-PBX pour que les appels puissent être placés et reçus entre les téléphones PBX des différents systèmes IP PBX.

Cette fonctionnalité de routage intertrunk peut être configurée à l’aide de la cmdlet Lync Server Management Shell, **Set-CsTrunkConfiguration**, avec le nouveau paramètre PstnUsages. Ce paramètre spécifie l’ensemble d’enregistrements d’utilisation RTC à utiliser. Un Trunk utilise cette utilisation PSTN pour déterminer un itinéraire et acheminer tous les appels entrants en conséquence.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

Le diagramme suivant illustre Lync Server 2013 permettant une interconnexion entre une passerelle RTC et un PBX IP.

**Routage intertrunk entre passerelle et PBX IP**

![Lync Server Connection RTC passerelle/PBX IP] (images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server Connection RTC passerelle/PBX IP")

Le diagramme suivant illustre Lync Server 2013 qui interconnecte deux systèmes PBX IP.

**Routage intertrunk entre deux PBX IP**

![Diagramme de systèmes IP-Pax d’interconnexion de Lync Server] (images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramme de systèmes IP-Pax d’interconnexion de Lync Server")

</div>

<span> </span>

</div>

</div>

</div>

