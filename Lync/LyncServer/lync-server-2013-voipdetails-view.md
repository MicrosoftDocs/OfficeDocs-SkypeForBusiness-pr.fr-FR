---
title: Vue VoIPDetails
TOCTitle: Vue VoIPDetails
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49891239
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue VoIPDetails

 

_**Dernière rubrique modifiée :** 2015-03-09_

La vue VoIPDetails stocke des informations sur les sessions égal à égal, où au moins un utilisateur est un utilisateur VoIP. Cette vue est une nouveauté de Microsoft Lync Server 2013.

> [!NOTE]  
> La vue VoIPDetails contient toutes les colonnes de <a href="lync-server-2013-sessiondetails-view.md">Vue SessionDetails</a> en plus des colonnes répertoriées ci-dessous.


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
<td><p><strong>FromPhone</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI du téléphone de l’utilisateur qui a initié la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToPhone</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI du téléphone de l’utilisateur qui a rejoint la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur qui a déconnecté la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type de URI de l’utilisateur qui a déconnecté la session. Pour plus d’informations, voir <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Client de l’utilisateur qui a déconnecté la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI du téléphone de l’utilisateur qui a déconnecté la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Serveur de médiation utilisé par l’utilisateur qui a initié la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Serveur de médiation utilisé par l’utilisateur qui a rejoint la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Passerelle utilisée par l’utilisateur qui a initié la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Passerelle utilisée par l’utilisateur qui a rejoint la session.</p></td>
</tr>
</tbody>
</table>

