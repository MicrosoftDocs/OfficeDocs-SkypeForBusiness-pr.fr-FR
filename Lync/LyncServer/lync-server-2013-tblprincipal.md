---
title: 'Lync Server 2013 : tblPrincipal'
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558667(v=OCS.15)
ms:contentKeyID: 49297813
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblPrincipal dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblPrincipal contient tous les principaux, dont les utilisateurs, les dossiers et les groupes.

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
<td><p>prinID</p></td>
<td><p>int, non null</p></td>
<td><p>ID du principal.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID, non null</p></td>
<td><p>ID de principal. Utilisé comme autre clé primaire car sa signification englobe l’espace des services de domaine Active Directory. (Le GUID d’un principal mis en cache est égal au GUID d’objet Active Directory correspondant.)</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>ID de principal. Le modèle SIP est utilisé pour les utilisateurs et ma-grp est utilisé pour presque tout le reste.</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom commun. Utilisé uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar(256)</p></td>
<td><p>Nom complet. Utilisé uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de société. Utilisé uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Adresse de messagerie. Utilisée uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar(384)</p></td>
<td><p>Nom de domaine de l’objet Active Directory dont le principal est une version mise en cache. Peut être Null pour les types qui ne sont pas des objets Active Directory (tels que les utilisateurs système).</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom d’utilisateur principal (UPN) de l’utilisateur. Utilisé uniquement par les types d’utilisateurs réguliers.</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint, non null</p></td>
<td><ul>
<li><p>0 : le principal est actif.</p></li>
<li><p>1 : le principal est désactivé car les fonctionnalités SIP de l’utilisateur sont désactivées.</p></li>
<li><p>2 : le principal est supprimé car l’objet AD associé a été supprimé.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint, non null</p></td>
<td><p>Type de principal (tiré de la table tblPrincipalType).</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>int</p></td>
<td><p>Affectation de pool Lync du principal.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>int</p></td>
<td><p>Valeur de la stratégie du serveur de conversations permanentes pour l’utilisateur, si la stratégie de type de balise est présente.</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>ID de principal du créateur.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint, non null</p></td>
<td><p>Horodatage de la création.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>ID du principal ayant effectué la dernière mise à jour.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint, non null</p></td>
<td><p>Horodatage de la dernière mise à jour.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>datetime, non null</p></td>
<td><p>Date et heure de la dernière actualisation de synchronisation Active Directory pour le principal.</p></td>
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
<th>Colonne</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblPrincipalType.ptypeID.</p></td>
</tr>
</tbody>
</table>

