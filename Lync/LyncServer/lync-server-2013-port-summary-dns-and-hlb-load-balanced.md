---
title: 'Lync Server 2013 : Résumé des ports - Équilibrage de charge DNS et matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd2a276f9495d314d2a8d4588f027df08978b94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Résumé des ports - Équilibrage de charge DNS et matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

La configuration requise pour les ports de pare-feu pour un seul directeur consiste à utiliser les ports utilisés pour établir une communication avec le directeur à partir de l’interface interne ou du réseau interne du proxy inverse. Microsoft Lync Server 2013 par défaut s’attend à ce que les ports HTTP/TCP 8080 et HTTPs/TCP 4443 soient ouverts du proxy inverse au directeur, ainsi qu’au pool frontal et au serveur frontal. Par ailleurs, il doit y avoir une communication SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge au directeur et au serveur principal et au pool frontal. Le protocole SIP utilise SIP/MTLS/TCP 5061 du serveur Edge au pool frontal et au serveur frontal. Une règle qui autorise la communication SIP/MTLS/TCP 5061 à partir du réalisateur, du pool frontal et du serveur frontal vers l’interface interne du serveur Edge doit également être créée.

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a>Ports et protocoles de Director uniques pour les définitions de pare-feu

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
<td><p>Initialement reçues par le côté extérieur du proxy inverse, la communication est envoyée aux services d’adresse IP du directeur HLB et aux services Web du serveur frontal.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP 4443</p></td>
<td><p>Interface interne du proxy inverse</p></td>
<td><p>Adresse VIP de l’équilibrage de charge matérielle Director</p></td>
<td><p>Initialement reçues par le côté extérieur du proxy inverse, la communication est envoyée aux services d’adresse IP du directeur HLB et aux services Web du serveur frontal.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP 444</p></td>
<td><p>directeur</p></td>
<td><p>Pool frontal ou serveur frontal</p></td>
<td><p>Communications entre les serveurs entre le directeur HLB VIP et le serveur frontal ou les serveurs frontaux.</p></td>
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
<td><p>directeur</p></td>
<td><p>Communication SIP du serveur Edge au directeur ainsi qu’aux serveurs frontaux.</p></td>
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

