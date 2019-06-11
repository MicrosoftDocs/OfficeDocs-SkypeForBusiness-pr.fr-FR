---
title: 'Lync Server 2013 : tblPrincipalInvites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1081dbec8575eac0cc2aca7fc434b5801668f447
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a>tblPrincipalInvites dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-25_

tblPrincipalInvites contient des invitations pour tous les utilisateurs approvisionnés pour tous les nœuds avec l’invitation automatique activé.

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
<td><p>invID</p></td>
<td><p>ent, non null</p></td>
<td><p>Numéro séquentiel unique (par ID principal) généré à partir de la table tblLastInviteId.</p></td>
</tr>
<tr class="odd">
<td><p>ID</p></td>
<td><p>ent, non null</p></td>
<td><p>ID de nœud (salle de conversation uniquement).</p></td>
</tr>
<tr class="even">
<td><p>Created</p></td>
<td><p>DATEHEURE, pas null</p></td>
<td><p>Heure de création</p></td>
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
<td><p>&lt;prinID, nodeID&gt;</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblPrincipal. prinID.</p></td>
</tr>
<tr class="odd">
<td><p>ID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblNode. nodeID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

