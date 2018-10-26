---
title: 'Lync Server 2013 : Table UserAgent'
TOCTitle: Table UserAgent
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398939(v=OCS.15)
ms:contentKeyID: 49298989
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table UserAgent dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table UserAgent est une table de prise en charge qui stocke la liste des différents agents utilisateur qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un agent utilisateur.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Colonne</strong></th>
<th><strong>Type de données</strong></th>
<th><strong>Clé/Index</strong></th>
<th><strong>Détails</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique qui identifie cet agent utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Chaîne d’agent utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1 correspond à un serveur de médiation.</p>
<p>2 correspond à un serveur de conférence A/V.</p>
<p>4 correspond à Lync.</p>
<p>8 correspond à un téléphone IP.</p>
<p>16 correspond à la console Live Meeting.</p>
<p>32 correspond à l’outil de validation de déploiement (DVT).</p>
<p>64 correspond à Lync sur les ordinateurs Macintosh.</p>
<p>128 correspond à Office Communications Server 2007 R2 Attendant.</p>
<p>256 correspond au service d’annonce de conférence.</p>
<p>512 correspond au standard automatique de conférence.</p>
<p>1024 correspond à l’application Response Group.</p>
<p>2048 correspond au contrôle vocal extérieur.</p></td>
</tr>
</tbody>
</table>

