---
title: 'Lync Server 2013: modifications apportées par Grant-CsOUPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Modifications apportées par Grant-CsOUPermission dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-20_

Pour déléguer l’administration de Lync Server 2013, vous pouvez ajouter des autorisations aux unités d’organisation (UO) spécifiées de sorte que les membres des groupes universels RTC créés par la préparation de la forêt puissent accéder aux UO sans être membres du groupe administrateurs de domaine.

L’applet **de commande Grant-CsOuPermission** accorde des autorisations aux objets de l’unité d’organisation spécifiée, comme indiqué dans les tableaux suivants.

<div>

## <a name="granting-permission-for-user-objects"></a>Octroi d’autorisations pour les objets utilisateur

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets utilisateur sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.

### <a name="permissions-granted-for-user-objects"></a>Autorisations accordées pour les objets utilisateur

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe</th>
<th>Permission</th>
<th>S’applique à</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Répliquer les modifications de l’annuaire</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenu de la liste</p>
<p>Lire toutes les propriétés</p>
<p>Autorisations de lecture</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenu de la liste</p>
<p>Lire toutes les propriétés</p>
<p>Autorisations de lecture</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lecture de RTCUserSearchPropertySet</p>
<p>Lecture de RTCUserProvisioningPropertySet</p>
<p>Lecture de RTCPropertySet</p>
<p>Lecture publique-informations</p>
<p>Lecture générale-informations</p>
<p>Lire le compte d’utilisateur-restrictions</p></td>
<td><p>Objets utilisateur descendants</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Écrire RTCUserSearchPropertySet</p>
<p>Écrire msExchUCVoiceMailSettings</p>
<p>Écrire RTCUserProvisioningPropertySet</p>
<p>Écrire RTCPropertySet</p>
<p>Écrire proxyAddresses</p></td>
<td><p>Objets utilisateur descendants</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>Octroi d’autorisations pour les objets ordinateur

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets ordinateur sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.

### <a name="permissions-granted-for-computer-objects"></a>Autorisations accordées pour les objets ordinateur

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe</th>
<th>Permission</th>
<th>S’applique à</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Répliquer les modifications de l’annuaire</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenu de la liste</p>
<p>Lire toutes les propriétés</p>
<p>Autorisations de lecture</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenu de la liste</p>
<p>Lire toutes les propriétés</p>
<p>Autorisations de lecture</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lecture publique-informations</p>
<p>Lecture validée de DNS-nom d’hôte-nom</p></td>
<td><p>Objets ordinateur descendants</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Lecture publique-informations</p>
<p>Lecture validée de DNS-nom d’hôte-nom</p></td>
<td><p>Objets ordinateur descendants</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Octroi d’autorisations de contact ou d’objets AppContact

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets de contact ou les objets AppContact sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>Autorisations accordées pour les objets contact ou AppContact

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe</th>
<th>Permission</th>
<th>S’applique à</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Répliquer les modifications de l’annuaire</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenu de la liste</p>
<p>Lire toutes les propriétés</p>
<p>Autorisations de lecture</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenu de la liste</p>
<p>Lire toutes les propriétés</p>
<p>Autorisations de lecture</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lecture de RTCUserSearchPropertySet</p>
<p>Lecture de RTCUserProvisioningPropertySet</p>
<p>Lecture de RTCPropertySet</p>
<p>Lecture publique-informations</p>
<p>Lecture générale-informations</p>
<p>Lire les informations personnelles</p>
<p>Lire le compte d’utilisateur-restrictions</p></td>
<td><p>Objets contact descendants</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Écrire RTCUserSearchPropertySet</p>
<p>Écrire otherIpPhone</p>
<p>Écrire displayName</p>
<p>Entrer une description</p>
<p>Écrire telephoneNumber</p>
<p>Écrire msExchUCVoiceMailSettings</p>
<p>Écrire RTCUserProvisioningPropertySet</p>
<p>Écrire RTCPropertySet</p>
<p>Écrire proxyAddresses</p></td>
<td><p>Objets contact descendants</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>Octroi d’autorisations pour les objets appareil

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets d’appareil sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.

### <a name="permissions-granted-for-device-objects"></a>Autorisations accordées pour les objets appareil

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe</th>
<th>Permission</th>
<th>S’applique à</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Répliquer les modifications de l’annuaire</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenu de la liste</p>
<p>Lire toutes les propriétés</p>
<p>Autorisations de lecture</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenu de la liste</p>
<p>Lire toutes les propriétés</p>
<p>Autorisations de lecture</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lecture de RTCUserSearchPropertySet</p>
<p>Lecture de RTCUserProvisioningPropertySet</p>
<p>Lecture de RTCPropertySet</p>
<p>Lecture publique-informations</p>
<p>Lire les informations personnelles</p>
<p>Lecture générale-informations</p>
<p>Lire le compte d’utilisateur-restrictions</p></td>
<td><p>Objets contact descendants</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Créer un enfant</p>
<p>Supprimer un enfant</p>
<p>Supprimer l’arborescence</p></td>
<td><p>Locuteur</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Écrire displayName</p>
<p>Entrer une description</p>
<p>Écrire telephoneNumber</p></td>
<td><p>Objets utilisateur descendants</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Écrire RTCUserSearchPropertySet</p>
<p>Écrire otherIpPhone</p>
<p>Écrire displayName</p>
<p>Entrer une description</p>
<p>Écrire telephoneNumber</p>
<p>Écrire msExchUCVoiceMailSettings</p>
<p>Écrire RTCUserProvisioningPropertySet</p>
<p>Écrire RTCPropertySet</p>
<p>Écrire proxyAddresses</p></td>
<td><p>Objets contact descendants</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>Octroi d’autorisations pour les objets InetOrgPerson

Lorsque vous exécutez l’applet de commande **Grant-CsOuPermission** pour les objets InetOrgPerson sur une unité d’organisation, les autorisations de groupe sont accordées, comme indiqué dans le tableau suivant.

### <a name="permissions-granted-for-inetorgperson-objects"></a>Autorisations accordées pour les objets InetOrgPerson

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe</th>
<th>Permission</th>
<th>S’applique à</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Répliquer les modifications de l’annuaire</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Contenu de la liste</p>
<p>Lire toutes les propriétés</p>
<p>Autorisations de lecture</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Contenu de la liste</p>
<p>Lire toutes les propriétés</p>
<p>Autorisations de lecture</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lecture de RTCUserSearchPropertySet</p>
<p>Lecture de RTCUserProvisioningPropertySet</p>
<p>Lecture de RTCPropertySet</p>
<p>Lire les informations personnelles</p>
<p>Lecture publique-informations</p>
<p>Lecture générale-informations</p>
<p>Lire le compte d’utilisateur-restrictions</p></td>
<td><p>Objets inetOrgPerson descendants</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Écrire RTCUserSearchPropertySet</p>
<p>Écrire RTCUserProvisioningPropertySet</p>
<p>Écrire RTCPropertySet</p>
<p>Écrire proxyAddresses</p></td>
<td><p>Objets inetOrgPerson descendants</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

