---
title: 'Lync Server 2013 : Table ErrorDef'
TOCTitle: 'Table ErrorDef '
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398503(v=OCS.15)
ms:contentKeyID: 49297516
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table ErrorDef dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table ErrorDef stocke les informations relatives à chaque type d’erreur susceptible de se produire. Chaque enregistrement représente un type d’erreur.


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
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro d’ID unique identifiant ce type d’erreur.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Code de réponse SIP standard associé à cette erreur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ID de diagnostic Microsoft.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Type de l’appel. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-calltype-table.md">Table CallType dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varbinary(33)</p></td>
<td><p> </p></td>
<td><p>Type de la demande ayant échoué.</p>
<p>Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varbinary(257)</p></td>
<td><p> </p></td>
<td><p>Type de contenu de la demande ayant échoué.</p>
<p>Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

