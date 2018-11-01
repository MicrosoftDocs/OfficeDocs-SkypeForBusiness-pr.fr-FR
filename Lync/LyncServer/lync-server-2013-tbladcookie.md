---
title: 'Lync Server 2013 : tblADCookie'
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558610(v=OCS.15)
ms:contentKeyID: 49296199
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblADCookie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblADCookie contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs.

### Colonnes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>GUID, non null</p></td>
<td><p>GUID principal du domaine en cours de surveillance.</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar(255)</p></td>
<td><p>Nom de domaine complet (FQDN) du serveur utilisé pour le contrôleur de domaine actuel pour la synchronisation des services de domaine Active Directory. Présente une valeur informative.</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>image (binaire)</p></td>
<td><p>Cookie de synchronisation Active Directory.</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>datetime</p></td>
<td><p>Horodatage avec l’heure de mise à jour de ligne.</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>datetime</p></td>
<td><p>Heure jusqu’à laquelle la ligne est verrouillée pour modification. Il s’agit d’une partie d’un mécanisme de verrouillage logiciel qui garantit la réalisation de la synchronisation Active Directory par un seul des services de conversation à la fois.</p></td>
</tr>
</tbody>
</table>


### Clés

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne(s)</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>Clé étrangère avec recherche dans la table Principal.prinGuid.</p></td>
</tr>
</tbody>
</table>

