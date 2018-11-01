---
title: Vue Media
TOCTitle: Vue Media
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49891250
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue Media

 

_**Dernière rubrique modifiée :** 2015-03-09_

La vue Media stocke des informations sur un type de média utilisé au cours d’une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés. Cette vue est une nouveauté de Microsoft Lync Server 2013.

> [!NOTE]  
> La vue Media ne doit pas être utilisée pour calculer la durée du média lors d’une session. Cette vue contient les détails de signalisation de l’échange multimédia lors d’une session. L’échange multimédia est effectué par la requête INVITE et StartTime indique l’heure à laquelle la requête INVITE a été envoyée. L’heure d’invitation ne signifie pas nécessairement l’heure de début du média, car le média démarre seulement une fois la session acceptée.

La vue Media contient toutes les colonnes de [Vue SessionDetails](lync-server-2013-sessiondetails-view.md) en plus de celles répertoriées ci-dessous.


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
<td><p><strong>Média</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type de média. Pour plus d’informations, voir la <a href="lync-server-2013-medialist-table.md">Table MediaList dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>Date/heure</p></td>
<td><p>Heure d’envoi d’une demande multimédia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>Date/heure</p></td>
<td><p>Heure de fin de la session.</p></td>
</tr>
</tbody>
</table>

