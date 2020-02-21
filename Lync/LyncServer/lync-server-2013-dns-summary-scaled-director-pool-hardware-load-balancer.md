---
title: 'Lync Server 2013 : Résumé DNS-pool directeur mis à l’ampleur, équilibreur de charge matérielle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10c742d8d58392b06bc563cd0a947d46243703d7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Résumé DNS-pool directeur mis à l’ampleur, équilibreur de charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge le directeur avec équilibrage de la charge matérielle. Le rôle du directeur requiert des enregistrements DNS similaires comme serveur frontal. Le nombre d’enregistrements nécessaires est reflété dans les autres noms du sujet requis sur le certificat directeur. Différent du serveur frontal, le pool directeur n’héberge pas les comptes d’utilisateur ou n’héberge pas les services de mobilité.

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>Enregistrements DNS requis pour le pool directeur à l’aide d’un programme d’équilibrage de la charge matérielle et de l’équilibrage de la charge DNS

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
<td><p>48000b</p></td>
<td><p>Enregistrement d’hôte directeur utilisé pour la communication de réplication et de serveur à serveur</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Pool directeur charge matérielle VIP</p></td>
<td><p>Enregistrement d’hôte pour le pool de directeurs à charge équilibrée DNS</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Pool directeur charge matérielle VIP</p></td>
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

