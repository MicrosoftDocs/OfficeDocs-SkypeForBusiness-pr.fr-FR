---
title: 'Lync Server 2013 : Table Users'
TOCTitle: Table Users
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412791(v=OCS.15)
ms:contentKeyID: 49298480
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Users dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Users est une table de prise en charge. Chaque enregistrement dans la table contient des informations sur un utilisateur impliqué dans des appels ou des sessions possédant des enregistrements dans la base de données.


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>DateHeure</p></td>
<td><p></p></td>
<td><p>Horodatage pour utilisation interne.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant cet utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p> </p></td>
<td><p>URI de l’utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID de locataire de cet utilisateur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Type d’URI de cet utilisateur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

