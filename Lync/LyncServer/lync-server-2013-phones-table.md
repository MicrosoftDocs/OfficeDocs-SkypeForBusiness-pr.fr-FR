---
title: 'Lync Server 2013 : Table !Phones'
TOCTitle: Table !Phones
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425923(v=OCS.15)
ms:contentKeyID: 49297016
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table \!Phones dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Phones est une table de prise en charge. Chaque enregistrement de la table stocke des informations relatives à un numéro de téléphone utilisé dans les appels VoIP correspondant à des enregistrements dans la base de données.


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
<td><p><strong>PhoneId</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant ce téléphone.</p></td>
</tr>
<tr class="even">
<td><p><strong>PhoneUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p> </p></td>
<td><p>Numéro de téléphone</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>dateTime</p></td>
<td><p></p></td>
<td><p>Horodatage (pour utilisation interne uniquement).</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

