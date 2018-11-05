---
title: 'Lync Server 2013 : tblFileToken'
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558646(v=OCS.15)
ms:contentKeyID: 49297113
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblFileToken dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

tblFileToken contient des jetons temporaires pour le transfert de fichiers.

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
<td><p>fileToken</p></td>
<td><p>nvarchar (50), non null</p></td>
<td><p>Jeton unique (un GUID).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenUserID</p></td>
<td><p>entier, non null</p></td>
<td><p>ID du principal qui transfère le fichier.</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenChannelID</p></td>
<td><p>GUID, non null</p></td>
<td><p>GUID du nœud de salles de conversation.</p></td>
</tr>
<tr class="even">
<td><p>fileTokenExpireDate</p></td>
<td><p>datetime, non null</p></td>
<td><p>Heure d’expiration. Les jetons expirent après 30 minutes sauf s’ils sont épinglés (reportez-vous aux descriptions suivantes dans cette colonne).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceFileUrl</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URL du fichier transféré (pour l’utilisation du service de conformité).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceThumbnailUrl</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>URL de la miniature du fichier transféré (pour l’utilisation du service de conformité).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceTime</p></td>
<td><p>datetime2</p></td>
<td><p>Horodatage de l’opération effective de transfert de fichier (pour l’utilisation du service de conformité).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceIsUpload</p></td>
<td><p>bit</p></td>
<td><p>True en cas de téléchargement sortant ; False en cas de téléchargement entrant (pour l’utilisation du service de conformité).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenCompliancePinned</p></td>
<td><p>bit, non null</p></td>
<td><p>True si le jeton est épinglé. Cela permet de garder le jeton dans la table jusqu’à ce que le service de conformité puisse y récupérer les champs appropriés.</p></td>
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
<td><p>fileToken</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>fileTokenChannelID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblNode.nodeGuid.</p></td>
</tr>
</tbody>
</table>

