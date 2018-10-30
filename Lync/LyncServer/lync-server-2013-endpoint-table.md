---
title: 'Lync Server 2013 : Table Endpoint'
TOCTitle: Table Endpoint
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398327(v=OCS.15)
ms:contentKeyID: 49297188
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Endpoint dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Endpoint est une table de prise en charge qui stocke des informations relatives aux points de terminaison ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un point de terminaison.


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
<td><p><strong>EndpointKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant ce point de terminaison.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nom</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>Nom du point de terminaison.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OS</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p> </p></td>
<td><p>Système d’exploitation (OS) du point de terminaison.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p></p></td>
<td><p>Nom de l’UC du point de terminaison.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Nombre de cœurs de l’UC du point de terminaison.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUProcessorSpeed</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Vitesse du processeur d’UC du point de terminaison.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Indicateur binaire indiquant si le système est exécuté dans un environnement virtualisé :</p>
<ul>
<li><p>0x0000 – Aucun</p></li>
<li><p>0x0001 – HyperV</p></li>
<li><p>0x0002 – VMWare</p></li>
<li><p>0x0004 – PC virtuel</p></li>
<li><p>0x0008 – PC Xen</p></li>
</ul></td>
</tr>
</tbody>
</table>

