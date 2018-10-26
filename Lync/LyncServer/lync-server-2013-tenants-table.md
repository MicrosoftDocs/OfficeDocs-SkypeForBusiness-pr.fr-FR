---
title: 'Lync Server 2013 : Table Tenants'
TOCTitle: Table Tenants
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412950(v=OCS.15)
ms:contentKeyID: 49298757
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Tenants dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La table Tenants est une table de prise en charge qui stocke une liste des différents clients. Chaque enregistrement de la table représente un client.

> [!NOTE]  
> Dans les déploiement sur site, CDR utilise l’ID de client intégré pour indiquer différents types d’authentification, tels que la connectivité de messagerie instantanée publique, l’authentification fédérée et l’authentification anonyme.


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
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro unique identifiant cet ID de client.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Valeurs autorisées :</p><ul><li><p>00000000-0000-0000-0000-000000000000 (entreprise)</p></li><li><p>00000000-0000-0000-0000-000000000001 (fédéré)</p></li><li><p>00000000-0000-0000-0000-000000000002 (anonyme)</p></li><li><p>00000000-0000-0000-0000-000000000003 (connectivité PIC)</p></li></ul></td>
</tr>
</tbody>
</table>

