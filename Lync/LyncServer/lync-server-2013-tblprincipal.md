---
title: 'Lync Server 2013 : tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24f963b34ef6184675e724496d7d45ca1d40d27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>tblPrincipal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-12_

tblPrincipal contient l’ensemble des principaux, y compris des utilisateurs, des dossiers et des groupes.

### <a name="columns"></a>Celles

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
<td><p>ent, non null</p></td>
<td><p>ID du principal.</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID, pas null</p></td>
<td><p>GUID principal. Cette opération est globalement utilisée comme clé primaire alternative, car sa signification croise l’espace des services de domaine Active Directory. (Le GUID d’un principal mis en cache est égal au GUID d’objet Active Directory correspondant.)</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256), pas null</p></td>
<td><p>URI principal. Le schéma SIP est utilisé pour les utilisateurs et ma-GRP est utilisé pour presque tout le reste.</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom usuel. Utilisées uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>Nom d’affichage. Utilisées uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom de la société. Utilisées uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Messagerie. Utilisées uniquement par les types d’utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>Nom de domaine de l’objet Active Directory dont le principal est une version mise en cache. Il peut s’agir de valeurs NULL pour les types qui ne sont pas des objets Active Directory (par exemple, utilisateurs système).</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom d’utilisateur principal (UPN) de l’utilisateur. Utilisé uniquement par les types d’utilisateurs normaux.</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint, pas null</p></td>
<td><ul>
<li><p>0: le principal est actif.</p></li>
<li><p>1: le principal est désactivé car les fonctionnalités SIP de l’utilisateur sont désactivées.</p></li>
<li><p>2: le principal est supprimé, car l’objet publicitaire associé a été supprimé.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint, pas null</p></td>
<td><p>Type principal (issu de la table tblPrincipalType)</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Ent</p></td>
<td><p>Attribution du pool Lync au principal.</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Ent</p></td>
<td><p>Valeur de la stratégie de serveur de chat permanent pour l’utilisateur, si la stratégie de type balise est présente.</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>ID principal du créateur.</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint, pas null</p></td>
<td><p>Horodatage de l’heure de création.</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>ID de l’entité de confiance qui a mis à jour pour la dernière fois.</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint, pas null</p></td>
<td><p>Horodatage de la dernière mise à jour.</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>DATEHEURE, pas null</p></td>
<td><p>Date et heure de la dernière actualisation de la synchronisation Active Directory de l’utilisateur principal.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Permettent

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
<td><p>Clé étrangère avec recherche dans la table tblPrincipalType. ptypeID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

