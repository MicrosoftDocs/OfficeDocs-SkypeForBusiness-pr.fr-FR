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
ms.openlocfilehash: 8ec13a23daf0f3dae47ae0ce0dc630e64c596e7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529411"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Modifications apportées par Grant-CsSetupPermission dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-20_

Pour déléguer le programme d’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique, permettant ainsi aux membres du groupe RTCUniversalServerAdmins de cette unité d’organisation d’installer Lync Server 2013 dans le domaine spécifié sans être membres du groupe administrateurs du domaine.

L’applet de commande **Grant-CsSetupPermission** accorde des autorisations de groupe RTCUniversalServerAdmins sur une unité d’organisation, comme indiqué dans le tableau suivant :

### <a name="permissions-granted-to-objects-in-the-ou"></a>Autorisations accordées aux objets dans l’unité d’organisation

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Les autorisations s’appliquent à :</th>
<th>Les autorisations accordées sont :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Accès particulier :</p>
<ul>
<li><p>Lecture servicePrincipalName</p></li>
<li><p>Écriture servicePrincipalName</p></li>
<li><p>Suppression de l’arborescence</p></li>
<li><p>Réplication des modifications d’annuaire</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objets serviceConnectionPoint descendants</p></td>
<td><p>Accès particulier :</p>
<ul>
<li><p>Autorisations en lecture</p></li>
<li><p>Autorisations en écriture</p></li>
<li><p>Création de l’enfant</p></li>
<li><p>Suppression de l’enfant</p></li>
<li><p>Affichage du contenu</p></li>
<li><p>Écriture de propriété</p></li>
<li><p>Lecture de propriété</p></li>
<li><p>Suppression de l’arborescence</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objets msRTCSIP-Server descendants</p></td>
<td><p>Accès particulier :</p>
<ul>
<li><p>Écriture de propriété</p></li>
<li><p>Lecture de propriété</p></li>
<li><p>Suppression de l’arborescence</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objets msRTCSIP-WebComponents descendants</p></td>
<td><p>Accès particulier :</p>
<ul>
<li><p>Écriture de propriété</p></li>
<li><p>Lecture de propriété</p></li>
<li><p>Suppression de l’arborescence</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objets msRTCSIP-MCU descendants</p></td>
<td><p>Accès particulier :</p>
<ul>
<li><p>Écriture de propriété</p></li>
<li><p>Lecture de propriété</p></li>
<li><p>Suppression de l’arborescence</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objets msRTCSIP-MediationServer descendants</p></td>
<td><p>Accès particulier :</p>
<ul>
<li><p>Écriture de propriété</p></li>
<li><p>Lecture de propriété</p></li>
<li><p>Suppression de l’arborescence</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objets msRTCSIP-ApplicationServer descendants</p></td>
<td><p>Accès particulier :</p>
<ul>
<li><p>Écriture de propriété</p></li>
<li><p>Lecture de propriété</p></li>
<li><p>Suppression de l’arborescence</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Objets msRTCSIP-ConnectionPoint descendants</p></td>
<td><p>Accès particulier :</p>
<ul>
<li><p>Écriture de propriété</p></li>
<li><p>Lecture de propriété</p></li>
<li><p>Suppression de l’arborescence</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Objets Computer descendants</p></td>
<td><p>Accès particulier pour serviceConnectionPoint :</p>
<ul>
<li><p>Création d’objets enfants</p></li>
<li><p>Suppression d’objets enfants</p></li>
<li><p>Suppression de l’arborescence</p></li>
</ul>
<p>Accès particulier pour les informations publiques :</p>
<ul>
<li><p>Lecture de propriété</p></li>
</ul>
<p>Accès particulier pour le nom d’hôte DNS :</p>
<ul>
<li><p>Lecture de propriété</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

