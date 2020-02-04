---
title: 'Lync Server 2013 : tblNode'
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
ms.openlocfilehash: 24ba45d9ba650a9de4359d64e3281fb488b6a279
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a>tblNode dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

tblNode contient l’arborescence d’objets (avec des nœuds de catégorie ou de salle de conversation) qui est gérée dans le panneau de configuration et les applets de commande d’administration de Lync Server 2013.

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
<td><p>ID</p></td>
<td><p>ent, non null</p></td>
<td><p>ID de nœud (numéro unique).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, pas null</p></td>
<td><p>GUID du nœud.</p></td>
</tr>
<tr class="odd">
<td><p>Parent</p></td>
<td><p>int</p></td>
<td><p>ID de nœud du parent. Le nœud racine (avec l’ID 1) s’intègre également en tant que parent.</p></td>
</tr>
<tr class="even">
<td><p>nodeType</p></td>
<td><p>bit, pas null</p></td>
<td><p>True si le nœud est une catégorie.</p>
<p>Faux si le nœud est une salle de conversation.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), pas null</p></td>
<td><p>Nom du nœud.</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), pas null</p></td>
<td><p>Description du nœud.</p></td>
</tr>
<tr class="odd">
<td><p>inviter</p></td>
<td><p>bit</p></td>
<td><p>Pour les catégories :</p>
<ul>
<li><p>True si les invitations sont activées.</p></li>
<li><p>Faux si les invitations sont désdésactivées.</p></li>
</ul>
<p>Pour les salles :</p>
<ul>
<li><p>Faux si les invitations sont désactivées (ignore la catégorie parent).</p></li>
<li><p>NULL si le paramètre d’invitations est hérité de la catégorie parent.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>utilisé</p></td>
<td><p>bit</p></td>
<td><p>Pour les catégories :</p>
<ul>
<li><p>True si l’historique des conversations est activé.</p></li>
<li><p>Faux si l’historique des conversations est désactivé.</p></li>
</ul>
<p>Pour les salles :</p>
<ul>
<li><p>Valeur.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>bit</p></td>
<td><p>Pour les catégories :</p>
<ul>
<li><p>True si les téléchargements de fichiers sont autorisés.</p></li>
<li><p>False si les téléchargements de fichiers ne le sont pas.</p></li>
</ul>
<p>Pour les salles :</p>
<ul>
<li><p>Valeur.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>désactivé</p></td>
<td><p>bit, pas null</p></td>
<td><p>True si la salle de conversation est désactivée. S’applique uniquement aux salles de conversation. (Faux pour les catégories.)</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>fonctionnement</p></td>
<td><p>smallint, pas null</p></td>
<td><p>Comportement (recherché dans la table EnumValue) :</p>
<ul>
<li><p>4 : normal (salles de conversation normales).</p></li>
<li><p>5 : Auditorium (salles de conversation d’Auditorium ; seuls les présentateurs peuvent collaborer).</p></li>
</ul>
<p>S’applique uniquement aux salles de conversation.</p></td>
</tr>
<tr class="odd">
<td><p>notoriété</p></td>
<td><p>smallint, pas null</p></td>
<td><p>Visibility (recherché sur la table EnumValue) :</p>
<ul>
<li><p>2 : privé</p></li>
<li><p>3 : étendue</p></li>
<li><p>6 : ouvrir</p></li>
</ul>
<p>S’applique uniquement aux salles de conversation.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>GUID du complément si un complément est associé à cette salle de conversation. (Les catégories n’ont pas de compléments.)</p>
<p>Les informations de complément sont recherchées dans la table SiopWhiteList.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>ent, non null</p></td>
<td><p>ID de l’élément principal qui a créé ce nœud.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, pas null</p></td>
<td><p>Horodatage de la création du nœud.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>ent, non null</p></td>
<td><p>ID de l’entité de l’utilisateur qui a effectué la dernière mise à jour de ce nœud.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, pas null</p></td>
<td><p>Horodatage de la dernière mise à jour de ce nœud.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de la dernière opération de purge (la suppression des étendues de la table tblScopedPrincipal et des rôles de la table tblPrincipalRole) qui ont affecté ce nœud. Ce mode est utilisé par le mécanisme de mise à jour du cache interne du service de conversation.</p></td>
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
<td><p>ID</p></td>
<td><p>Clé primaire.</p></td>
</tr>
<tr class="even">
<td><p>fonctionnement</p></td>
<td><p>Clé étrangère avec recherche dans la table tblEnumValue. valueID.</p></td>
</tr>
<tr class="odd">
<td><p>notoriété</p></td>
<td><p>Clé étrangère avec recherche dans la table tblEnumValue. valueID.</p></td>
</tr>
<tr class="even">
<td><p>Parent</p></td>
<td><p>Clé étrangère avec recherche dans la table tblNode. nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Clé étrangère avec recherche dans la table tblSiopWhiteList. siopId.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

