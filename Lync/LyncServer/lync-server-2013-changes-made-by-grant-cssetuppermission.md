---
title: 'Lync Server 2013 : modifications apportées par Grant-CsSetupPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d82b896f1d6d1da1184bfa61d7352c9b4803a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Modifications apportées par Grant-CsSetupPermission dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-20_

Pour déléguer le programme d’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique (UO), ce qui permet aux membres du groupe RTCUniversalServerAdmins dans cette UO d’installer Lync Server 2013 dans le dossier spécifié. domaine sans être membre du groupe administrateurs de domaine.

L’applet de commande **Grant-CsSetupPermission** accorde aux autorisations de groupe RTCUniversalServerAdmins sur une unité d’organisation, comme indiqué dans le tableau suivant :

### <a name="permissions-granted-to-objects-in-the-ou"></a>Autorisations accordées aux objets dans l’unité d’organisation

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Les autorisations s’appliquent à :</th>
<th>Les autorisations accordées sont les suivantes :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Accès spécial :</p>
<ul>
<li><p>Lire servicePrincipalName</p></li>
<li><p>Écrire le servicePrincipalName</p></li>
<li><p>Supprimer l’arborescence</p></li>
<li><p>Répliquer les modifications de l’annuaire</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objets serviceConnectionPoint descendants</p></td>
<td><p>Accès spécial :</p>
<ul>
<li><p>Autorisations de lecture</p></li>
<li><p>Autorisations d’écriture</p></li>
<li><p>Créer un enfant</p></li>
<li><p>Supprimer un enfant</p></li>
<li><p>Contenu de la liste</p></li>
<li><p>Propriété Write</p></li>
<li><p>Propriété de lecture</p></li>
<li><p>Supprimer l’arborescence</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objets enfants msRTCSIP-Server</p></td>
<td><p>Accès spécial :</p>
<ul>
<li><p>Propriété Write</p></li>
<li><p>Propriété de lecture</p></li>
<li><p>Supprimer l’arborescence</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objets enfants msRTCSIP-webcomposants</p></td>
<td><p>Accès spécial :</p>
<ul>
<li><p>Propriété Write</p></li>
<li><p>Propriété de lecture</p></li>
<li><p>Supprimer l’arborescence</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objets descendants msRTCSIP-MCU</p></td>
<td><p>Accès spécial :</p>
<ul>
<li><p>Propriété Write</p></li>
<li><p>Propriété de lecture</p></li>
<li><p>Supprimer l’arborescence</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objets MediationServer en descendant</p></td>
<td><p>Accès spécial :</p>
<ul>
<li><p>Propriété Write</p></li>
<li><p>Propriété de lecture</p></li>
<li><p>Supprimer l’arborescence</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objets ApplicationServer en descendant</p></td>
<td><p>Accès spécial :</p>
<ul>
<li><p>Propriété Write</p></li>
<li><p>Propriété de lecture</p></li>
<li><p>Supprimer l’arborescence</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objets descendants de msRTCSIP-ConnectionPoint</p></td>
<td><p>Accès spécial :</p>
<ul>
<li><p>Propriété Write</p></li>
<li><p>Propriété de lecture</p></li>
<li><p>Supprimer l’arborescence</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objets ordinateur descendants</p></td>
<td><p>Accès spécial pour serviceConnectionPoint :</p>
<ul>
<li><p>Créer des objets enfants</p></li>
<li><p>Supprimer des objets enfants</p></li>
<li><p>Supprimer l’arborescence</p></li>
</ul>
<p>Accès spécial pour les informations publiques :</p>
<ul>
<li><p>Propriété de lecture</p></li>
</ul>
<p>Accès spécial pour le nom d’hôte DNS :</p>
<ul>
<li><p>Propriété de lecture</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

