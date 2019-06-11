---
title: 'Lync Server 2013: modifications de schéma dans Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bbe1c08b7d03042be2c03511103bfa4e43d39d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a>Modifications de schéma dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-18_

Avant de déployer et d’utiliser Lync Server 2013, vous devez préparer les services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Lync Server 2013.

Lync Server 2013 nécessite plusieurs classes et attributs, et modifie quelques classes et attributs existants. Par ailleurs, de nombreuses informations de configuration pour Lync Server 2013 sont stockées dans le magasin de gestion central plutôt que dans AD DS comme dans les versions précédentes. Les informations suivantes sont toujours stockées dans AD DS dans Lync Server 2013:

  - **Extensions de schéma**:
    
      - Extensions de l’objet utilisateur
    
      - Extensions pour les classes Office Communications Server 2007 et Office Communications Server 2007 R2 pour garantir la compatibilité descendante avec les versions précédentes prises en charge

<!-- end list -->

  - **Data (données** ) (stockés dans le schéma étendu de Lync Server et dans les classes de schéma existantes):
    
      - URL (Uniform Resource Identifier) de l’utilisateur SIP et autres paramètres utilisateur
    
      - Objets de contact pour des applications telles que Response Group et attendant
    
      - Pointeur vers le magasin de gestion central
    
      - Compte d’authentification Kerberos (objet facultatif de l’ordinateur)

Cette rubrique décrit les modifications de schéma Active Directory requises par Lync Server 2013. Elle ne décrit pas les modifications de schéma introduites par des versions antérieures d’Office Communications Server. Pour obtenir la liste des classes et leurs descriptions, voir [classes et descriptions de schéma dans Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Pour obtenir la liste des attributs et leur description, voir [attributs et descriptions de schéma dans Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Pour obtenir la liste des classes avec les attributs qu’ils peuvent contenir, voir [attributs de schéma par classe dans Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

Le préfixe msRTCSIP identifie les classes et attributs spécifiques à Lync Server.

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
<td><p>Cet attribut à plusieurs valeurs contient des identificateurs pour les stratégies de conservation qui s’appliquent à l’utilisateur. Les stratégies de blocage préservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la conservation. Cet attribut est partagé avec Exchange 2013.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Il s’agit de l’ID du groupe de routage SIP. Les utilisateurs du même groupe seront enregistrés sur le même serveur principal.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Cet attribut est utilisé pour stocker le serveur principal SQL Server utilisé par le pool frontal.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>Classes Active Directory modifiées

Le tableau suivant décrit les classes Active Directory modifiées par Lync Server 2013.

### <a name="classes-modified-by-lync-server-2013"></a>Classes modifiées par Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Cours</th>
<th>Modification</th>
<th>Classe ou attribut</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateur</p></td>
<td><p>Ajouter: mayContain</p>
<p>Ajouter: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Locuteur</p></td>
<td><p>Ajouter: mayContain</p>
<p>Ajouter: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-destinataire</p></td>
<td><p>Ajouter: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Ajouter: mayContain</p></td>
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

