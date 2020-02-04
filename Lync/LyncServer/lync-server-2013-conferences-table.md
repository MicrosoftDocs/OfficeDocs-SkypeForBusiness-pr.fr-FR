---
title: 'Lync Server 2013 : Table Conferences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c5464d3161a52a31fddb1322c82181d6e7a97fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Table Conferences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Chaque enregistrement de cette table contient les détails des appels sur une conférence.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Clé/Index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Principal</p></td>
<td><p>Temps d’acquisition de la demande de conférence par l’agent CDR. Utilisé uniquement comme clé primaire pour identifier de manière unique une instance de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>IDENTIFIant de la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une instance de conférence. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>URI de conférence. Pour plus d’informations, voir la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>identificateur</p></td>
<td><p> </p></td>
<td><p>Utile pour les conférences récurrentes ; chaque instance d’une conférence périodique a le même <strong>ConferenceUri</strong>, mais aura un autre <strong>ConfInstance</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p> </p></td>
<td><p>Heure de début de la Conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p> </p></td>
<td><p>Heure de début de la Conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Numéro d’identification identifiant le regroupement dans lequel la Conférence a été capturée. Pour plus d’informations, voir la <a href="lync-server-2013-pools-table.md">table pools dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Ent</p></td>
<td><p>Externes</p></td>
<td><p>Numéro d’identification identifiant l’URI organisateur de la Conférence. Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Indication</strong></p></td>
<td><p>type</p></td>
<td></td>
<td><p>Masque binaire qui contient les attributs de la Conférence. Valeurs possibles :</p>
<ul>
<li><p>0X01</p></li>
<li><p>Synthetic</p></li>
<li><p>Transaction</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Formé</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Champ interne utilisé par le service de surveillance.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1. S’il s’agit d’une session à partir de la même heure, le SessionIdSeq d’une personne sera 1, et pour l’autre, sera égale à 2, et ainsi de suite.

</div>

<span> </span>

</div>

</div>

</div>

