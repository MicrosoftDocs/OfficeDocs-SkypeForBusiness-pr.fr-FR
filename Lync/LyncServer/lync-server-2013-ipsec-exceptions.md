---
title: Exceptions IPsec Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee06e4b7f3cabc606a612cd0f332aed47b46823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514151"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a>Exceptions IPsec dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-27_

Dans les réseaux d’entreprise où la sécurité du protocole Internet (IPsec, Internet Protocol security) a été déployée (voir les RFC 4301-4309 de l’IETF), IPsec doit être désactivée sur la plage de ports utilisée pour la transmission des données audio/vidéo et des panoramas vidéo. Cette recommandation s’explique par la nécessité d’éviter tout retard dans l’affectation des ports multimédias lors de la négociation IPsec.

Le tableau suivant présente les paramètres recommandés pour les exceptions IPsec.

### <a name="recommended-ipsec-exceptions"></a>Exceptions recommandées pour IPsec

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de la règle</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Protocole</th>
<th>Port source</th>
<th>Port de destination</th>
<th>Besoin d’authentification</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Edge A/V, ports internes/entrants</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Serveur Edge A/V - interne</p></td>
<td><p>UDP et TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Serveur Edge A/V, ports externes/entrants</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Serveur Edge A/V - externe</p></td>
<td><p>UDP et TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Serveur Edge A/V, ports internes/sortants</p></td>
<td><p>Serveur Edge A/V - interne</p></td>
<td><p>N’importe lequel</p></td>
<td><p>&amp;TCP UDP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Serveur Edge A/V, ports externes/sortants</p></td>
<td><p>Serveur Edge A/V - externe</p></td>
<td><p>N’importe lequel</p></td>
<td><p>UDP et TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Serveur de médiation, ports entrants</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Élaboration</p>
<p>Serveur (s)</p></td>
<td><p>UDP et TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Serveur de médiation, ports sortants</p></td>
<td><p>Élaboration</p>
<p>Serveur (s)</p></td>
<td><p>N’importe lequel</p></td>
<td><p>UDP et TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Intendant Conférence entrant</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Serveur frontal exécutant l’Intendant Conférence</p></td>
<td><p>UDP et TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Intendant Conférence sortant</p></td>
<td><p>Serveur frontal exécutant l’Intendant Conférence</p></td>
<td><p>N’importe lequel</p></td>
<td><p>UDP et TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Serveur de conférence A/V, ports entrants</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Serveurs frontaux</p></td>
<td><p>UDP et TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Conférence A/V, ports sortants</p></td>
<td><p>Serveurs frontaux</p></td>
<td><p>N’importe lequel</p></td>
<td><p>UDP et TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Exchange, ports entrants</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Messagerie unifiée Exchange</p></td>
<td><p>UDP et TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Serveurs de partage d’application, ports entrants</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Serveurs de partage d’application</p></td>
<td><p>TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Serveur de partage d’application, ports sortants</p></td>
<td><p>Serveurs de partage d’application</p></td>
<td><p>N’importe lequel</p></td>
<td><p>TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="even">
<td><p>Exchange, ports sortants</p></td>
<td><p>Messagerie unifiée Exchange</p></td>
<td><p>N’importe lequel</p></td>
<td><p>UDP et TCP</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
<tr class="odd">
<td><p>Clients</p></td>
<td><p>N’importe lequel</p></td>
<td><p>N’importe lequel</p></td>
<td><p>DATAGRAMME</p></td>
<td><p>Plage de ports multimédias définie</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Ne pas authentifier</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

