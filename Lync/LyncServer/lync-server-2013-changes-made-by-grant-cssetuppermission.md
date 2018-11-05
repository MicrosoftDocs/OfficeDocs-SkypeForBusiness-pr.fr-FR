---
title: Modifications apportées par Grant-CsSetupPermission dans Lync Server 2013
TOCTitle: Modifications apportées par Grant-CsSetupPermission dans Lync Server 2013
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205250(v=OCS.15)
ms:contentKeyID: 49298806
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifications apportées par Grant-CsSetupPermission dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour déléguer l’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique afin que les membres du groupe et de l’unité d’organisation puissent installer Lync Server 2013 dans le domaine spécifié sans avoir à être membres du groupe Administrateurs d’entreprise.

L’applet de commande **Grant-CsSetupPermission** accorde des autorisations de groupe RTCUniversalServerAdmins sur une unité d’organisation, comme indiqué dans le tableau suivant :

### Autorisations accordées aux objets dans l’unité d’organisation

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

