---
title: Vue ConferenceMessageCount
TOCTitle: Vue ConferenceMessageCount
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49891442
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue ConferenceMessageCount

 

_**Dernière rubrique modifiée :** 2015-03-09_

L’affichage ConferenceMessageCount stocke les informations relatives au nombre de messages envoyés par un utilisateur à une conférence. Cette vue est une nouveauté de Microsoft Lync Server 2013.

> [!NOTE]  
> L’affichage ConferenceMessageCount contient toutes les colonnes de l’<a href="lync-server-2013-conferencesessiondetails-view.md">Vue ConferenceSessionDetails</a> en plus des colonnes répertoriées ci-dessous.


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
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur qui a envoyé le message.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur qui a envoyé les messages. Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Locataire de l’utilisateur qui a envoyé les messages. Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserMessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p>Nombre de messages envoyés par l’utilisateur pendant la session de conférence.</p></td>
</tr>
</tbody>
</table>

