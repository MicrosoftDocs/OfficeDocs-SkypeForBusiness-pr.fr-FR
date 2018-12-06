---
title: Vue Conferences
TOCTitle: Vue Conferences
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49891520
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue Conferences

 

_**Dernière rubrique modifiée :** 2015-03-09_

L’affichage des conférences fournit des informations relatives aux conférences. Cette vue est une nouveauté de Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Heure de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus d’informations, voir la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’identification de la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Pour plus d’informations, voir la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type de l’URI de la conférence. Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Utilisé pour les conférences périodiques. Chaque instance d’une conférence périodique a la même valeur ConferenceUri, mais une valeur ConfInstance différente.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Heure de début de la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Heure de fin de la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur qui a organisé la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OrganizerType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type de l’URI de l’utilisateur qui a organisé la conférence. Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Locataire de l’utilisateur qui a organisé la conférence. Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet du pool ayant hébergé la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Indicateur</strong></p></td>
<td><p>smallint</p></td>
<td><p>Masque de bits qui contient les attributs de la conférence. Les valeurs possibles sont les suivantes :</p>
<p>0X01 – Synthetic Transaction</p></td>
</tr>
</tbody>
</table>

