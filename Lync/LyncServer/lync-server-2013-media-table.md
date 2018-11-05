---
title: 'Lync Server 2013 : Table Media'
TOCTitle: Table Media
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398268(v=OCS.15)
ms:contentKeyID: 49296444
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Media dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement représente un type de média utilisé au cours d’une session P2P. Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés.

> [!NOTE]  
> La table Media ne doit pas être utilisée pour calculer la durée du média lors d’une session. Cette table contient les détails de signalisation de l’échange multimédia lors d’une session. L’échange multimédia est effectué par la requête INVITE et StartTime indique l’heure à laquelle la requête INVITE a été envoyée. L’heure d’invitation ne signifie pas nécessairement l’heure de début du média, car le média démarre seulement lorsque le destinataire de la session accepte la session. EndTime signifie généralement l’heure de fin de cette session.


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
<td><p>Primaire, étrangère</p></td>
<td><p>Heure de la demande de session. Utilisée de concert avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’ID identifiant la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro unique d’identification de ce type de média. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-medialist-table.md">Table MediaList dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Principal</p></td>
<td><p>Heure d’envoi de la demande multimédia et non heure réelle du début du média. <strong>StartTime</strong> inclut l’heure de configuration de la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p></p></td>
<td><p>Heure de fin de la session.</p></td>
</tr>
</tbody>
</table>

