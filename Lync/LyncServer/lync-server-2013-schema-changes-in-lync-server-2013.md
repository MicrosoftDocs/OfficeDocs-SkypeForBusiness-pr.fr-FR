---
title: 'Lync Server 2013 : modifications de schéma dans Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c3733eee90fb1ea0bb3e0a67be88243dee56aa7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510781"
---
# <a name="schema-changes-in-lync-server-2013"></a>Modifications apportées au schéma dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Avant de déployer et d’utiliser Lync Server 2013, vous devez préparer les services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Lync Server 2013.

Lync Server 2013 nécessite plusieurs nouvelles classes et attributs et modifie des classes et des attributs existants. En outre, la plupart des informations de configuration pour Lync Server 2013 sont stockées dans le magasin central de gestion et non dans AD DS comme dans les versions précédentes. Les informations suivantes sont toujours stockées dans les services de domaine Active Directory (AD DS) dans Lync Server 2013 :

  - **Extensions de schéma** :
    
      - Extensions de l’objet utilisateur
    
      - Extensions pour les classes Office Communications Server 2007 et Office Communications Server 2007 R2 pour assurer la compatibilité descendante avec les versions précédentes prises en charge

<!-- end list -->

  - **Données** (stockées dans le schéma étendu Lync Server et dans les classes de schéma existantes) :
    
      - URI (Uniform Resource Identifier) SIP de l’utilisateur et autres paramètres utilisateur
    
      - Objets contact pour des applications telles que le service Response Group et l’Intendant Conférence
    
      - Pointeur vers le magasin central de gestion
    
      - Compte d’authentification Kerberos (un objet ordinateur facultatif)

Cette rubrique décrit les modifications apportées au schéma Active Directory requises par Lync Server 2013. Il ne décrit pas les modifications de schéma qui ont été introduites par des versions antérieures d’Office Communications Server. Pour obtenir la liste des classes et leur description, voir [Schema classes and descriptions in Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Pour obtenir la liste des attributs et de leurs descriptions, voir [attributs et descriptions de schéma dans Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Pour obtenir la liste des classes avec les attributs qu’elles peuvent contenir, voir [Schema Attributes by Class dans Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

Le préfixe msRTCSIP identifie les classes et les attributs spécifiques à Lync Server.

<div>

## <a name="new-active-directory-attributes"></a>Nouveaux attributs Active Directory

Le tableau suivant décrit les attributs Active Directory ajoutés par Lync Server 2013.

### <a name="attributes-added-by-lync-server-2013"></a>Attributs ajoutés par Lync Server 2013

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
<td><p>Cet attribut à valeurs multiples contient les stratégies d’archive qui s’appliquent à l’utilisateur. Les stratégies d’archive conservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la suspension. Cet attribut est partagé avec Exchange 2013.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Il s’agit de l’ID de groupe de groupe de routage SIP. Les utilisateurs du même groupe seront inscrits au même serveur frontal.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Cet attribut est utilisé pour stocker le serveur principal SQL Server mis en miroir utilisé par le pool frontal.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>Classes Active Directory modifiées

Le tableau suivant décrit les classes Active Directory qui sont modifiées par Lync Server 2013.

### <a name="classes-modified-by-lync-server-2013"></a>Classes modifiées par Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Class</th>
<th>Modification</th>
<th>Classe ou attribut</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateur</p></td>
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
<td><p>add: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>ajouté : mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

