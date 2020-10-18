---
title: 'Lync Server 2013 : tblPrincipalMeta'
description: 'Lync Server 2013 : tblPrincipalMeta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573640"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a>tblPrincipalMeta dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

tblPrincipalMeta contient les principaux qui doivent être actualisés à partir des services de domaine Active Directory.

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
<td><p>prinAffiliationsDirty</p></td>
<td><p>bit, non null</p></td>
<td><p>True si les affiliations de principaux doivent être actualisées.</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesDirty</p></td>
<td><p>bit, non null</p></td>
<td><p>True si les attributs de principaux doivent être actualisés.</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit, non null</p></td>
<td><p>True si le principal doit être supprimé.</p></td>
</tr>
<tr class="odd">
<td><p>tryCount</p></td>
<td><p>int</p></td>
<td><p>Nombre de tentatives d’actualisation à partir des services AD DS ayant eu lieu jusqu’à maintenant.</p></td>
</tr>
<tr class="even">
<td><p>lastTry</p></td>
<td><p>DateHeure</p></td>
<td><p>Horodatage de la dernière tentative d’actualisation du principal. Peut être null si aucune actualisation n’a encore été tentée.</p></td>
</tr>
<tr class="odd">
<td><p>nextTry</p></td>
<td><p>DateHeure</p></td>
<td><p>Horodatage de la prochaine actualisation planifiée. Peut être null si aucune actualisation supplémentaire n’a été planifiée.</p></td>
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
<td><p>prinID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

