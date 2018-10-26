---
title: Modifications apportées par Grant-CsOUPermission dans Lync Server 2013
TOCTitle: Modifications apportées par Grant-CsOUPermission dans Lync Server 2013
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205310(v=OCS.15)
ms:contentKeyID: 49298995
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifications apportées par Grant-CsOUPermission dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour déléguer l’administration de Lync Server 2013, vous pouvez ajouter des autorisations aux unités d’organisation définies pour que les membres des groupes universels RTC créés par la préparation de la forêt puissent accéder aux unités d’organisation définies sans appartenir au groupe Administrateurs du domaine.

La cmdlet **Grant-CsOuPermission** des autorisations à des objets dans des unités d’organisation définies, comme indiqué dans les tableaux suivants.

## Octroi d’une autorisation pour les objets utilisateur

Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets utilisateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.

### Autorisations octroyées pours les objets utilisateur

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe</th>
<th>Autorisation</th>
<th>S’applique à :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Réplication des modifications du répertoire</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Lister le contenu</p>
<p>Lire toutes les propriétés</p>
<p>Lire les autorisations</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lister le contenu</p>
<p>Lire toutes les propriétés</p>
<p>Lire les autorisations</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lire RTCUserSearchPropertySet</p>
<p>Lire RTCUserProvisioningPropertySet</p>
<p>Lire RTCPropertySet</p>
<p>Lire les informations publiques</p>
<p>Lire les informations générales</p>
<p>Lire les restrictions de compte utilisateur</p></td>
<td><p>Objets d’utilisateur descendant</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Écrire RTCUserSearchPropertySet</p>
<p>Écrire msExchUCVoiceMailSettings</p>
<p>Écrire RTCUserProvisioningPropertySet</p>
<p>Écrire RTCPropertySet</p>
<p>Écrire proxyAddresses</p></td>
<td><p>Objets d’utilisateur descendant</p></td>
</tr>
</tbody>
</table>


## Octroi d’une autorisation pour les objets utilisateur

Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets ordinateur ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.

### Autorisations octroyées pour les objets ordinateur

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe</th>
<th>Autorisation</th>
<th>S’applique à :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Réplication des modifications du répertoire</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Lister le contenu</p>
<p>Lire toutes les propriétés</p>
<p>Lire les autorisations</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lister le contenu</p>
<p>Lire toutes les propriétés</p>
<p>Lire les autorisations</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lire les informations publiques</p>
<p>Lire le nom d’hôte DNS validé</p></td>
<td><p>Objets de l’ordinateur descendant</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Lire les informations publiques</p>
<p>Lire le nom d’hôte DNS validé</p></td>
<td><p>Objets de l’ordinateur descendant</p></td>
</tr>
</tbody>
</table>


## Octroi d’autorisation pour les objets contact ou AppContact

Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets contact ou AppContact sur une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.

### Autorisations octroyées pour les objets contact ou AppContact

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe</th>
<th>Autorisation</th>
<th>S’applique à :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Réplication des modifications du répertoire</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Lister le contenu</p>
<p>Lire toutes les propriétés</p>
<p>Lire les autorisations</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lister le contenu</p>
<p>Lire toutes les propriétés</p>
<p>Lire les autorisations</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lire RTCUserSearchPropertySet</p>
<p>Lire RTCUserProvisioningPropertySet</p>
<p>Lire RTCPropertySet</p>
<p>Lire les informations publiques</p>
<p>Lire les informations générales</p>
<p>Lire les informations publiques</p>
<p>Lire les restrictions de compte utilisateur</p></td>
<td><p>Objets du contact descendant</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Écrire RTCUserSearchPropertySet</p>
<p>Écrire otherIpPhone</p>
<p>Écrire displayName</p>
<p>Écrire la description</p>
<p>Écrire telephoneNumber</p>
<p>Écrire msExchUCVoiceMailSettings</p>
<p>Écrire RTCUserProvisioningPropertySet</p>
<p>Écrire RTCPropertySet</p>
<p>Écrire proxyAddresses</p></td>
<td><p>Objets du contact descendant</p></td>
</tr>
</tbody>
</table>


## Octroi d’une autorisation pour les objets périphérique

Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets périphérique ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.

### Autorisations octroyées pours les objets périphérique

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe</th>
<th>Autorisation</th>
<th>S’applique à :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Réplication des modifications du répertoire</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Lister le contenu</p>
<p>Lire toutes les propriétés</p>
<p>Lire les autorisations</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lister le contenu</p>
<p>Lire toutes les propriétés</p>
<p>Lire les autorisations</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lire RTCUserSearchPropertySet</p>
<p>Lire RTCUserProvisioningPropertySet</p>
<p>Lire RTCPropertySet</p>
<p>Lire les informations publiques</p>
<p>Lire les informations publiques</p>
<p>Lire les informations générales</p>
<p>Lire les restrictions de compte utilisateur</p></td>
<td><p>Objets du contact descendant</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Créer un enfant</p>
<p>Supprimer un enfant</p>
<p>Supprimer l’arborescence</p></td>
<td><p>Contact</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Écrire displayName</p>
<p>Écrire la description</p>
<p>Écrire telephoneNumber</p></td>
<td><p>Objets d’utilisateur descendant</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Écrire RTCUserSearchPropertySet</p>
<p>Écrire otherIpPhone</p>
<p>Écrire displayName</p>
<p>Écrire la description</p>
<p>Écrire telephoneNumber</p>
<p>Écrire msExchUCVoiceMailSettings</p>
<p>Écrire RTCUserProvisioningPropertySet</p>
<p>Écrire RTCPropertySet</p>
<p>Écrire proxyAddresses</p></td>
<td><p>Objets du contact descendant</p></td>
</tr>
</tbody>
</table>


## Octroi d’une autorisation pour les objets InetOrgPerson

Lorsque vous exécutez la cmdlet **Grant-CsOuPermission** pour les objets InetOrgPerson ou une unité d’organisation, les groupes se voient octroyer des autorisations, comme indiqué dans les tableaux suivants.

### Autorisations octroyées pour les objets InetOrgPerson

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Groupe</th>
<th>Autorisation</th>
<th>S’applique à :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Réplication des modifications du répertoire</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Lister le contenu</p>
<p>Lire toutes les propriétés</p>
<p>Lire les autorisations</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lister le contenu</p>
<p>Lire toutes les propriétés</p>
<p>Lire les autorisations</p></td>
<td><p>Cet objet uniquement</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Lire RTCUserSearchPropertySet</p>
<p>Lire RTCUserProvisioningPropertySet</p>
<p>Lire RTCPropertySet</p>
<p>Lire les informations publiques</p>
<p>Lire les informations publiques</p>
<p>Lire les informations générales</p>
<p>Lire les restrictions de compte utilisateur</p></td>
<td><p>Objets du InetOrgPerson descendant</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Écrire RTCUserSearchPropertySet</p>
<p>Écrire RTCUserProvisioningPropertySet</p>
<p>Écrire RTCPropertySet</p>
<p>Écrire proxyAddresses</p></td>
<td><p>Objets du InetOrgPerson descendant</p></td>
</tr>
</tbody>
</table>

