---
title: 'Lync Server 2013 : tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cee7c67421ae12d08e52bee1b013dfa6280472f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>tblNode dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

tblNode contient l’arborescence d’objets (avec les nœuds de catégorie ou de salle de conversation) telle qu’elle est gérée dans le panneau de configuration et les cmdlets administratives Lync Server 2013.

### <a name="columns"></a>Columns

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
<td><p>nodeID</p></td>
<td><p>int, non null</p></td>
<td><p>ID de nœud (numéro unique).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, non null</p></td>
<td><p>GUID de nœud.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>ID de nœud du parent. Le nœud racine (avec l’ID 1) s’inclut lui-même comme parent.</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit, non null</p></td>
<td><p>True si le nœud est une catégorie.</p>
<p>False si le nœud est une salle de conversation.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Nom du nœud.</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), non null</p></td>
<td><p>Description du nœud.</p></td>
</tr>
<tr class="odd">
<td><p>invite</p></td>
<td><p>légèrement</p></td>
<td><p>Pour les catégories :</p>
<ul>
<li><p>True si les invitations sont activées.</p></li>
<li><p>False si les invitations sont désactivées.</p></li>
</ul>
<p>Pour les salles :</p>
<ul>
<li><p>False si les invitations sont désactivées (remplace la catégorie parente).</p></li>
<li><p>Null si le paramètre d’invitation est hérité de la catégorie parente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>connecté</p></td>
<td><p>légèrement</p></td>
<td><p>Pour les catégories :</p>
<ul>
<li><p>True si l’historique des conversations est activé.</p></li>
<li><p>False si l’historique des conversations est désactivé.</p></li>
</ul>
<p>Pour les salles :</p>
<ul>
<li><p>Valeurs.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>légèrement</p></td>
<td><p>Pour les catégories :</p>
<ul>
<li><p>True si les téléchargements de fichiers sont autorisés.</p></li>
<li><p>False si les téléchargements de fichiers sont interdits.</p></li>
</ul>
<p>Pour les salles :</p>
<ul>
<li><p>Valeurs.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>activation</p></td>
<td><p>bit, non null</p></td>
<td><p>True si la salle de conversation est désactivée. S’applique uniquement aux salles de conversation. (False pour les catégories.)</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>connaissance</p></td>
<td><p>smallint, non null</p></td>
<td><p>Comportement (tiré de la table EnumValue) :</p>
<ul>
<li><p>4 : normal (salles de conversation normales).</p></li>
<li><p>5 : auditorium (salles de conversation de type auditorium, seuls les présentateurs peuvent contribuer).</p></li>
</ul>
<p>S’applique uniquement aux salles de conversation.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>smallint, non null</p></td>
<td><p>Visibilité (tirée de la table EnumValue) :</p>
<ul>
<li><p>2 : privée</p></li>
<li><p>3 : limitée par une étendue</p></li>
<li><p>6 : ouvert</p></li>
</ul>
<p>S’applique uniquement aux salles de conversation.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>GUID de complément si un complément est associé à cette salle de conversation. (Les catégories n’ont pas de complément.)</p>
<p>Les informations relatives aux compléments sont recherchées dans la table SiopWhiteList.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, non null</p></td>
<td><p>ID du principal ayant créé ce nœud.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, non null</p></td>
<td><p>Horodatage de la création de nœud.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, non null</p></td>
<td><p>ID du principal ayant effectué la dernière mise à jour de ce nœud.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, non null</p></td>
<td><p>Horodatage de la dernière mise à jour de ce nœud.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de la dernière opération de vidage (suppression des étendues de la table tblScopedPrincipal et des rôles de la table tblPrincipalRole) ayant affecté ce nœud. Utilisé uniquement par le mécanisme de mise à jour du cache interne du service de conversation.</p></td>
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
<td><p>nodeID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>connaissance</p></td>
<td><p>Clé étrangère avec recherche dans la table tblEnumValue.valueID.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>Clé étrangère avec recherche dans la table tblEnumValue.valueID.</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblNode.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblSiopWhiteList.siopId.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

