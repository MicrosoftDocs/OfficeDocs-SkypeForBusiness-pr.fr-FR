---
title: Modifications de schéma dans Lync Server 2013
TOCTitle: Modifications de schéma dans Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398944(v=OCS.15)
ms:contentKeyID: 49298998
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifications de schéma dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Avant de déployer et d’utiliser Lync Server 2013, vous devez préparer les services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Lync Server 2013.

Lync Server 2013 requiert plusieurs nouvelles classes et nouveaux attributs, et en modifie certains. En outre, la plupart des informations de configuration pour Lync Server 2013 sont enregistrées dans le magasin central de gestion, et non plus dans AD DS comme dans les versions précédentes. Les informations suivantes sont toujours stockées dans AD DS dans Lync Server 2013 :

  - **Extensions de schéma** :
    
      - Extensions de l’objet utilisateur
    
      - Extensions pour les classes Office Communications Server 2007 et Office Communications Server 2007 R2 pour assurer la compatibilité descendante avec les versions antérieures prises en charge.

<!-- end list -->

  - **Données** (enregistrées dans le schéma étendu Lync Server et dans les classes de schéma existantes) :
    
      - URI (Uniform Resource Identifier) SIP de l’utilisateur et autres paramètres utilisateur
    
      - Objets contact pour des applications telles que le service Response Group et l’Intendant Conférence
    
      - Un pointeur vers le magasin central de gestion
    
      - Compte d’authentification Kerberos (un objet ordinateur facultatif)

Cette rubrique décrit les modifications de schéma Active Directory requises par Lync Server 2013. Elle n’aborde pas les modifications de schéma qui ont été introduites par des versions antérieures d’Office Communications Server. Pour obtenir une liste des classes et leurs descriptions, voir [Classes et descriptions de schéma dans Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Pour obtenir une liste des attributs et leurs descriptions, voir [Attributs et descriptions de schéma dans Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Pour obtenir une liste des classes avec les attributs qu’elles peuvent contenir, voir [Attributs de schéma par classe dans Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

Le préfixe msRTCSIP identifie les classes et les attributs spécifiques à Lync Server.

## Nouveaux attributs Active Directory

Le tableau suivant décrit les attributs Active Directory qui sont ajoutés par Lync Server 2013.

### Attributs ajoutés par Lync Server 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Cet attribut gérant plusieurs valeurs contient les identificateurs pour les stratégies d’attente s’appliquant à l’utilisateur. Les stratégies d’attente conservent les éléments de boîte au lettres de l’utilisateur durant l’attente. Cet attribut est partagé avec Exchange 2013.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Il s’agit de l’ID de groupe de groupe de routage SIP. Les utilisateurs du même groupe seront inscrits au même serveur frontal.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Cet attribut est utilisé pour stocker le serveur SQL Server principal mis en miroir utilisé par le pool de serveurs frontaux.</p></td>
</tr>
</tbody>
</table>


## Classes Active Directory modifiées

Le tableau suivant décrit les classes Active Directory modifiées par Lync Server 2013.

### Classes modifiées par Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Classe</th>
<th>Modification</th>
<th>Classe ou attribut</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>User</p></td>
<td><p>ajouté : mayContain</p>
<p>ajouté : mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Contact</p></td>
<td><p>ajouté : mayContain</p>
<p>ajouté : mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>ajouté : mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>ajouté : mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>

