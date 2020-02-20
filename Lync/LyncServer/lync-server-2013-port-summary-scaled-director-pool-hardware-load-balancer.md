---
title: 'Lync Server 2013 : Résumé des ports-pool directeur mis à l’ampleur, équilibreur de charge matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72d059cc32015409377ab0b12bbe8c3ebc7da7d3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Résumé des ports-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Les exigences de port de pare-feu pour un pool directeur consistent en des ports utilisés pour établir la communication avec le directeur à partir de l’interface interne du serveur Edge ou de l’interface interne du proxy inverse. Microsoft Lync Server 2013 attend par défaut que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts depuis le proxy inverse vers le directeur, ainsi que le pool frontal et le serveur frontal. En outre, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge vers le directeur et vers le pool frontal et le serveur frontal. Le protocole SIP utilise SIP/MTLS/TCP 5061 à partir du serveur Edge vers le pool frontal et le serveur frontal. Une règle qui autorise la communication SIP/MTLS/TCP 5061 depuis le directeur, le pool frontal et le serveur frontal vers l’interface interne du serveur Edge doit également être créée.

### <a name="director-ports-and-protocols-for-firewall-definitions"></a>Ports et protocoles de directeur pour les définitions de pare-feu

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rôle/Protocole/TCP ou UDP/Port</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP 8080</p></td>
<td><p>Interface interne de proxy inverse</p></td>
<td><p>Adresse IP du programme d’équilibrage de la charge matérielle directeur</p></td>
<td><p>Initialement reçue par le côté externe du proxy inverse, la communication est envoyée aux services Web du directeur charge matérielle VIP et serveurs frontaux.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interface interne de proxy inverse</p></td>
<td><p>Adresse IP du programme d’équilibrage de la charge matérielle directeur</p></td>
<td><p>Initialement reçue par le côté externe du proxy inverse, la communication est envoyée aux services Web du directeur charge matérielle VIP et serveurs frontaux.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>48000b</p></td>
<td><p>Serveur frontal ou pool frontal</p></td>
<td><p>Communication entre le directeur charge matérielle VIP et les serveurs frontaux</p></td>
</tr>
<tr class="even">
<td><p>HTTP/TCP 80</p></td>
<td><p>Clients internes</p></td>
<td><p>Adresse IP du programme d’équilibrage de la charge matérielle directeur</p></td>
<td><p>Le directeur fournit des services Web aux clients internes et externes.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 443</p></td>
<td><p>Clients internes</p></td>
<td><p>Adresse IP du programme d’équilibrage de la charge matérielle directeur</p></td>
<td><p>Le directeur fournit des services Web aux clients internes et externes.</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP 5061</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Adresse IP du programme d’équilibrage de la charge matérielle directeur</p></td>
<td><p>Communication SIP du serveur Edge vers le directeur et les serveurs frontaux.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>N'importe lequel</p></td>
<td><p>48000b</p></td>
<td><p>Commandes et collection de journaux du service de journalisation centralisée (ClsController. exe) ou de l’agent (ClsAgent. exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>N'importe lequel</p></td>
<td><p>48000b</p></td>
<td><p>Commandes et collection de journaux du service de journalisation centralisée (ClsController. exe) ou de l’agent (ClsAgent. exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>N'importe lequel</p></td>
<td><p>48000b</p></td>
<td><p>Commandes et collection de journaux du service de journalisation centralisée (ClsController. exe) ou de l’agent (ClsAgent. exe)</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

