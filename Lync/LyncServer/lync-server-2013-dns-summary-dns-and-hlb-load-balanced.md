---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-équilibrage de charge DNS et charge matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6a3dc04856e1727c3982864995494cee751f457
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532151"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Résumé des enregistrements DNS-charge DNS et charge matérielle équilibrée dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge le directeur de charge DNS et le directeur équilibré par la charge matérielle. Le rôle du directeur requiert des enregistrements DNS similaires comme serveur frontal. Le nombre d’enregistrements nécessaires est reflété dans les autres noms du sujet requis sur le certificat directeur. Différent du serveur frontal, le pool directeur n’héberge pas les comptes d’utilisateur ou n’héberge pas les services de mobilité.

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a>Enregistrements DNS nécessaires pour le pool de directeurs en utilisant l’équilibrage de la charge DNS et le programme d’équilibrage de la charge matérielle

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
<th>Adresse IP/Nom de domaine complet</th>
<th>Mappe vers/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Directeur</p></td>
<td><p>Enregistrement d’hôte directeur utilisé pour la réplication et le serveur vers le serveur</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>pool directeur</p></td>
<td><p>Enregistrement d’hôte pour le pool directeur à charge DNS équilibrée pour le serveur à serveur</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>pool directeur</p></td>
<td><p>Protocole SIP (Session Initiation Protocol) entrant à partir de l’interface interne du serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Pool directeur charge matérielle VIP</p></td>
<td><p>Services web de numérotation publiés avec charge matérielle équilibrée à partir d’un proxy inverse</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Pool directeur charge matérielle VIP</p></td>
<td><p>Services web de conférence publiés avec charge matérielle équilibrée à partir d’un proxy inverse</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Pool directeur charge matérielle VIP</p></td>
<td><p>Services web externes de tickets web publiés et définis par le proxy inverse avec charge matérielle équilibrée pour le pool de directeurs</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

