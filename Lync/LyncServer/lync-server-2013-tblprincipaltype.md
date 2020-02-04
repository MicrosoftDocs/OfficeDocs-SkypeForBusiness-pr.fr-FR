---
title: 'Lync Server 2013 : tblPrincipalType'
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
ms.openlocfilehash: 6731d0bcda6e4e66b1b498a5f1bf91023627b1f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>tblPrincipalType dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

tblPrincipalType contient des types de principaux pour classer ce qui se trouve dans la table tblPrincipal.

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
<th>Description%</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ptypeID</p></td>
<td><p>smallint, pas null</p></td>
<td><p>ID de type principal.</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256), pas null</p></td>
<td><p>Description du type.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit, pas null</p></td>
<td><p>True si le type correspond aux éléments principaux utilisés à des fins internes.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit, pas null</p></td>
<td><p>True si le type est un type d’utilisateur.</p></td>
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
<th>Rôle</th>
<th>Description</th>
<th>Utilisateur</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Indifférente</p></td>
<td><p>Principal générique sans type connu. Non utilisé dans la table tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>deuxième</p></td>
<td><p>AnyUser</p></td>
<td><p>Principal générique de type d’utilisateur. Non utilisé dans la table tblPrincipal.</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>Principal générique avec la sémantique de groupe. Non utilisé dans la table tblPrincipal.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>SystemUser</p></td>
<td><p>Principal utilisé par le serveur de chat permanent.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>Utilisateur</p></td>
<td><p>Utilisateur ordinaire.</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="even">
<td><p>version8</p></td>
<td><p>CD</p></td>
<td><p>Contrôleur de domaine Active Directory Domain Services.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>09</p></td>
<td><p>Groupe</p></td>
<td><p>Groupe de sécurité Active Directory.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>0,10</p></td>
<td><p>Folder</p></td>
<td><p>Conteneur Active Directory ou unité d’organisation.</p></td>
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

