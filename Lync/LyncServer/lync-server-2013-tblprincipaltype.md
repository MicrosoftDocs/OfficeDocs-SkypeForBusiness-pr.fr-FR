---
title: 'Lync Server 2013 : tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60fa841f7f88e0da2c428ae68c5007fb79e6c69d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536321"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a>tblPrincipalType dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

La table tblPrincipalType contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal.

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
<td><p>ptypeID</p></td>
<td><p>smallint, non null</p></td>
<td><p>ID de type Principal.</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Description du type.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit, non null</p></td>
<td><p>Vrai si le type correspond aux principaux qui sont utilisés pour des fonctions internes.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit, non null</p></td>
<td><p>Vrai si le type est un type utilisateur.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Clé

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
<td><p>ptypeID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a>Valeurs principales

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Role</th>
<th>Description</th>
<th>Utilisateur</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0,1</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Principal générique sans type connu. Inutilisé dans la table tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>n°2</p></td>
<td><p>AnyUser</p></td>
<td><p>Principal générique de type utilisateur. Inutilisé dans table tblPrincipal.</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>Principal générique avec sémantique de groupe. Inutilisé dans table tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>SystemUser</p></td>
<td><p>Principal utilisé en interne par le serveur de conversation permanente.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5 </p></td>
<td><p>Utilisateur</p></td>
<td><p>Utilisateur régulier.</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>DC</p></td>
<td><p>Contrôleur de domaine des services de domaine Active Directory.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>Groupe</p></td>
<td><p>Groupe de sécurité Active Directory.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>Folder</p></td>
<td><p>Conteneur ou unité d’organisation Active Directory.</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Voir aussi


[tblPrincipal dans Lync Server 2013](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

