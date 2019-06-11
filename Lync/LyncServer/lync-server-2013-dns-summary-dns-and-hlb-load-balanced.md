---
title: 'Lync Server 2013 : Résumé des enregistrements DNS - Équilibrage de charge DNS et matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceccb52a8ef9fae810821ffe6b52b763dd8904c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Résumé des enregistrements DNS - Équilibrage de charge DNS et matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-20_

Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge le système de répartition de charge DNS et le directeur équilibré de charge matérielle. Le rôle du directeur nécessite des enregistrements DNS similaires comme serveur frontal. Le nombre d’enregistrements nécessaires est reflété dans les autres noms d’objet requis sur le certificat de réalisateur. Différent du serveur frontal, le pool de directeurs n’héberge pas les comptes d’utilisateurs ou n’héberge pas les services de mobilité.

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a>Enregistrements DNS requis pour le pool de directeurs à l’aide de l’équilibrage de charge DNS et de l’équilibrage de charge matérielle

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement/TYPE/port</th>
<th>Nom de domaine complet/enregistrement DNS</th>
<th>IP address/FQDN</th>
<th>Cartes sur/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>directeur</p></td>
<td><p>Enregistrement hôte de Director utilisé pour la réplication et le serveur vers serveur</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>pool de directeurs</p></td>
<td><p>Enregistrement hôte du pool de directeurs d’équilibrage de charge DNS pour serveur à serveur</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>pool de directeurs</p></td>
<td><p>Protocole SIP (Session Initiation Protocol) à partir de l’interface interne du serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>HLB VIP du pool de réalisateurs</p></td>
<td><p>Équilibrage de charge matérielle publié services Web de numérotation à partir du proxy inverse</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>HLB VIP du pool de réalisateurs</p></td>
<td><p>Équilibrage de charge matérielle publié avec les services Web à partir du proxy inverse</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>HLB VIP du pool de réalisateurs</p></td>
<td><p>Équilibrage de la charge matérielle publié et définie par les services Web externes du ticket de proxy inverse pour le pool de réalisateurs</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

