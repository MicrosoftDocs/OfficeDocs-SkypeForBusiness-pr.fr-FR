---
title: 'Lync Server 2013 : Table Dialogs'
TOCTitle: Table Dialogs
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425954(v=OCS.15)
ms:contentKeyID: 49297095
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Dialogs dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Dialogs est une table de prise en charge qui stocke les informations relatives aux DialogID des sessions P2P.


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
<td><p>Heure de la demande de session ; utilisée en conjonction avec SessionIDSeq pour identifier de manière unique une session.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro d’identification de la session. Utilisé conjointement avec SessionIDTime pour identifier de manière unique une session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalChecksum</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Somme de contrôle de ExternalID. Ce champ est utilisé pour accélérer les recherches dans les bases de données.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExternalId</strong></p></td>
<td><p>varbinary(775)</p></td>
<td><p> </p></td>
<td><p>ID de dialogue SIP, stocké comme une valeur binaire. Le format de la valeur binaire est :</p>
<p>dialog;from-tag;to-tag</p>
<p>Ces données peuvent être converties au format texte à l’aide de cette syntaxe :</p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

