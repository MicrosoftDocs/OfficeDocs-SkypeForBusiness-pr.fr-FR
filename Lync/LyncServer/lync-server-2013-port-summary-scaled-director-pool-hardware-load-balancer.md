---
title: 'Lync Server 2013 : Résumé des ports - Pool directeur mis à l’échelle, équilibreur de charge matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9a78225f7cf523d5f120f291498007fcdfa0cd3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Résumé des ports - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-21_

La configuration requise pour les ports de pare-feu pour un pool de directeurs est composée des ports utilisés pour établir une communication avec le directeur à partir de l’interface interne du serveur Edge ou de l’interface interne du proxy inverse. Microsoft Lync Server 2013 par défaut s’attend à ce que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts du proxy inverse au directeur, ainsi qu’au pool frontal et au serveur frontal. Par ailleurs, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge au directeur et au serveur principal et au pool frontal. Le protocole SIP utilise SIP/MTLS/TCP 5061 du serveur Edge au pool frontal et au serveur frontal. Une règle qui autorise la communication SIP/MTLS/TCP 5061 à partir du réalisateur, du pool frontal et du serveur frontal vers l’interface interne du serveur Edge doit également être créée.

### <a name="director-ports-and-protocols-for-firewall-definitions"></a>Ports et protocoles de Director pour les définitions de pare-feu

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rôles/protocole/TCP ou UDP/Port</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interface interne du proxy inverse</p></td>
<td><p>Adresse VIP de l’équilibrage de charge matérielle Director</p></td>
<td><p>Initialement reçues par le côté extérieur du proxy inverse, la communication est envoyée aux services Internet de Director HLB VIP et aux services Web des serveurs frontaux.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interface interne du proxy inverse</p></td>
<td><p>Adresse VIP de l’équilibrage de charge matérielle Director</p></td>
<td><p>Initialement reçues par le côté extérieur du proxy inverse, la communication est envoyée aux services Internet de Director HLB VIP et aux services Web des serveurs frontaux.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>directeur</p></td>
<td><p>Serveur frontal ou liste de front-end</p></td>
<td><p>Communication entre serveur entre le directeur HLB VIP et les serveurs frontaux</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clients internes</p></td>
<td><p>Adresse VIP de l’équilibrage de charge matérielle Director</p></td>
<td><p>Le directeur fournit des services Web aux clients externes et internes.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clients internes</p></td>
<td><p>Adresse VIP de l’équilibrage de charge matérielle Director</p></td>
<td><p>Le directeur fournit des services Web aux clients externes et internes.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Adresse VIP de l’équilibrage de charge matérielle Director</p></td>
<td><p>Communication SIP du serveur Edge au directeur et aux serveurs frontaux.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Indifférente</p></td>
<td><p>directeur</p></td>
<td><p>Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClsAgent. exe) et collection de journaux</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Indifférente</p></td>
<td><p>directeur</p></td>
<td><p>Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClsAgent. exe) et collection de journaux</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Indifférente</p></td>
<td><p>directeur</p></td>
<td><p>Commandes de service de journalisation centralisées (ClsController. exe) ou d’agent (ClsAgent. exe) et collection de journaux</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

