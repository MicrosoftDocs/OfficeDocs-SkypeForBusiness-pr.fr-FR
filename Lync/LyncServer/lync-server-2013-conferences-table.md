---
title: 'Lync Server 2013 : Table Conferences'
TOCTitle: Table Conferences
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412964(v=OCS.15)
ms:contentKeyID: 49298750
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Conferences dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement de cette table contient les détails des appels pour une conférence.


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
<td><p>datetime</p></td>
<td><p>Principal</p></td>
<td><p>Heure à laquelle la demande de conférence a été capturée par l’agent CDR. Sert uniquement de clé primaire afin d’identifier de manière unique une instance de conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro d’ID permettant d’identifier la session. Utilisé conjointement à <strong>SessionIdTime</strong> pour identifier une instance de conférence de manière unique. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>URI de la conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-conferenceuris-table.md">Table ConferenceUris dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p> </p></td>
<td><p>Utile pour les conférences périodique ; chaque instance d’une conférence périodique a le même <strong>ConferenceUri</strong> , mais une <strong>ConfInstance</strong> différente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Heure de fin de la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Heure de fin de la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Numéro d’identification du pool dans lequel la conférence a été capturée. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-pools-table.md">Table Pools dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Entier</p></td>
<td><p>Étrangère</p></td>
<td><p>Numéro d’identification de l’URI de l’organisateur de cette conférence. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Masque de bits qui contient les attributs de conférence. Les valeurs possibles sont les suivantes :</p>
<ul>
<li><p>0X01</p></li>
<li><p>Synthétique</p></li>
<li><p>Transaction</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Traité</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Champ interne utilisé par le service de surveillance.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\* Pour la plupart des sessions, SessionIdSeq a la valeur 1. Si deux sessions démarrent exactement en même temps, le SessionIdSeq sera 1 pour l’une et 2 pour l’autre.

