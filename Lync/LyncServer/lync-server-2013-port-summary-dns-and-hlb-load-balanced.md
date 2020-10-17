---
title: 'Lync Server 2013 : Résumé des ports-équilibrage de charge DNS et charge matérielle'
description: 'Lync Server 2013 : Résumé des ports-équilibrage de charge DNS et charge matérielle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be2e8204e792fd9c4718cb9171e90784af2d0104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543130"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Résumé des ports-équilibrage de charge DNS et charge matérielle dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Les exigences de port de pare-feu pour un seul directeur consistent en des ports utilisés pour établir la communication avec le directeur depuis l’interface interne ou le réseau interne du proxy inverse. Microsoft Lync Server 2013 attend par défaut que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts depuis le proxy inverse vers le directeur, ainsi que le pool frontal et le serveur frontal. En outre, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge vers le directeur et vers le pool frontal et le serveur frontal. Le protocole SIP utilise SIP/MTLS/TCP 5061 à partir du serveur Edge vers le pool frontal et le serveur frontal. Une règle qui autorise la communication SIP/MTLS/TCP 5061 depuis le directeur, le pool frontal et le serveur frontal vers l’interface interne du serveur Edge doit également être créée.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>Ports et protocoles de directeur unique pour les définitions de pare-feu

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
<td><p>Initialement reçue par le côté externe du proxy inverse, la communication est envoyée aux services Web de l’adresse IP virtuelle et du serveur frontal charge matérielle directeur.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interface interne de proxy inverse</p></td>
<td><p>Adresse IP du programme d’équilibrage de la charge matérielle directeur</p></td>
<td><p>Initialement reçue par le côté externe du proxy inverse, la communication est envoyée aux services Web de l’adresse IP virtuelle et du serveur frontal charge matérielle directeur.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>Directeur</p></td>
<td><p>Pool frontal ou serveur frontal</p></td>
<td><p>Communication entre le directeur charge matérielle VIP et le serveur frontal ou les serveurs frontaux.</p></td>
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
<td><p>Directeur</p></td>
<td><p>Communication SIP entre le serveur Edge et le directeur, ainsi que les serveurs frontaux.</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Directeur</p></td>
<td><p>Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClsAgent.exe) et collection de journaux</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Directeur</p></td>
<td><p>Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClsAgent.exe) et collection de journaux</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Directeur</p></td>
<td><p>Commandes de contrôleur de service de journalisation centralisée (ClsController.exe) ou agent (ClsAgent.exe) et collection de journaux</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

