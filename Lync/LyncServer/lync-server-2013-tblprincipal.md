---
title: 'Lync Server 2013 : tblPrincipal'
description: 'Lync Server 2013 : tblPrincipal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f07b37ac4c8ceed5c044b5c263eeee6370adfdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547490"
---
# <a name="tblprincipal-in-lync-server-2013"></a>tblPrincipal dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

tblPrincipal contient tous les principaux, y compris les utilisateurs, les dossiers et les groupes.

### <a name="columns"></a>Colonnes

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
<td><p>ID de principal.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID, non null</p></td>
<td><p>ID de principal. Elle est largement utilisée comme clé primaire de remplacement car sa signification passe à l’espace des services de domaine Active Directory. (Le GUID d’un principal mis en cache est égal au GUID d’objet Active Directory correspondant.)</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>ID de principal. Le modèle SIP est utilisé pour les utilisateurs et ma-grp est utilisé pour presque tout le reste.</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom commun. Utilisé uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar(256)</p></td>
<td><p>Nom complet. Utilisé uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom de société. Utilisé uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Adresse de messagerie. Utilisée uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar(384)</p></td>
<td><p>Nom de domaine de l’objet Active Directory dont le principal est une version mise en cache. Peut être Null pour les types qui ne sont pas des objets Active Directory (tels que les utilisateurs système).</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar (256)</p></td>
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
<td><p>Int</p></td>
<td><p>Assignation de pool Lync pour le principal.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>Valeur de stratégie de serveur de conversation permanente pour l’utilisateur, si la stratégie de type de balise est présente.</p></td>
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


### <a name="keys"></a>Keys

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


</div>

<span> </span>

</div>

</div>

</div>

