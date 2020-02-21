---
title: 'Lync Server 2013 : tableau conférences'
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
ms.openlocfilehash: d3dbaf1a721433cc04aa681dad56d753de8bc9a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Tableau conférences dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Chaque enregistrement de cette table contient les détails des appels d’une conférence.


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
<th>Clé/index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Primaire</p></td>
<td><p>Heure à laquelle la demande de conférence a été capturée par l’agent CDR. Utilisé uniquement comme clé primaire pour identifier une instance de conférence de manière unique.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Numéro d’ID identifiant la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une instance de conférence de manière unique. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>URI de la conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">table ConferenceUris dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>unique</p></td>
<td><p> </p></td>
<td><p>Utile pour les conférences périodiques ; chaque instance d’une conférence périodique a le même <strong>ConferenceUri</strong>, mais elle aura un <strong>ConfInstance</strong>différent.</p></td>
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
<td><p>Etranger</p></td>
<td><p>Numéro d’identification permettant d’identifier le pool dans lequel la Conférence a été capturée. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Etranger</p></td>
<td><p>Numéro d’identification permettant d’identifier l’URI de l’organisateur de la Conférence. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Indicateur</strong></p></td>
<td><p>type</p></td>
<td></td>
<td><p>Masque de bits qui contient les attributs de la Conférence. Les valeurs possibles sont les suivantes :</p>
<ul>
<li><p>0X01</p></li>
<li><p>Fibres</p></li>
<li><p>Transaction</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Traiter</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Champ interne utilisé par le service de surveillance.</p>
<p>Ce champ a été introduit dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1. Si deux sessions commencent exactement en même temps, le SessionIdSeq est égal à 1 et l’autre à 2, et ainsi de suite.

</div>

<span> </span>

</div>

</div>

</div>

