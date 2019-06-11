---
title: 'Lync Server 2013: configuration requise pour DNS pour la connexion automatique au client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afd8ac315222a5582bde9802c22ab7b4911ddfe3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Configuration DNS requise pour la connexion automatique au client dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-19_

Cette section décrit les enregistrements DNS (Domain Name System) nécessaires à la connexion automatique du client. Lorsque vous déployez vos serveurs Standard Edition ou pools frontal, vous pouvez configurer vos clients de manière à utiliser la découverte automatique pour vous connecter au serveur Standard Edition Server ou au pool frontal approprié. Si vous envisagez de nécessiter la connexion manuelle de vos clients à Lync Server 2013, vous pouvez ignorer cette rubrique.

Pour prendre en charge la connexion automatique au client, vous devez:

  - Désigner un serveur ou un pool unique pour distribuer et authentifier les demandes de connexion au client. Il peut s’agir d’un serveur ou d’un pool de votre organisation qui héberge des utilisateurs ou d’un serveur dédié ou d’un pool dédié à cette fin qui n’héberge aucun utilisateur. Pour une disponibilité élevée, nous vous recommandons de désigner un pool frontal pour cette fonction.

  - Créer un enregistrement SRV DNS interne pour prendre en charge la connexion automatique du client pour ce serveur ou pool.
    
    <div>
    

    > [!NOTE]  
    > Dans les exigences d’enregistrement suivantes, le domaine SIP fait référence à la partie hôte des URI SIP attribués aux utilisateurs. Par exemple, si les URI SIP sont du type * @contoso. com, contoso.com est le domaine SIP. Le domaine SIP est souvent différent du domaine interne d’Active Directory. Une organisation peut également prendre en charge plusieurs domaines SIP.

    
    </div>

Pour activer la configuration automatique pour vos clients, vous devez créer un enregistrement SRV DNS interne qui mappe l’un des enregistrements suivants au nom de domaine complet (FQDN) du pool frontal ou du serveur Standard Edition qui répartit les demandes de connexion provenant de Lync clients

  - \_sipinternaltls. \_TCP. \<Domain\> -pour les connexions TLS internes

Vous n’avez besoin de créer qu’un seul enregistrement SRV pour le pool frontal ou le serveur Standard Edition Server, ou la distribution de demandes de connexion.

Le tableau suivant montre quelques exemples d’enregistrements nécessaires pour l’entreprise fictive contoso, qui prend en charge les domaines SIP de contoso.com et retail.contoso.com.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Exemple d’enregistrements DNS requis pour la connexion automatique du client avec plusieurs domaines SIP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de domaine complet du pool frontal utilisé pour distribuer les demandes de connexion</th>
<th>Domaine SIP</th>
<th>Enregistrement DNS SRV</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Un enregistrement SRV pour le domaine _sipinternaltls. _ TCP. contoso. com sur le port 5061 qui correspond à pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Un enregistrement SRV pour le domaine _sipinternaltls. _ TCP. Retail. contoso. com sur le port 5061 qui correspond à pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Par défaut, les requêtes pour les enregistrements DNS respectent le strict rapprochement de nom de domaine entre le domaine figurant dans le nom d’utilisateur et l’enregistrement SRV. Si vous préférez que les requêtes DNS du client utilisent plutôt une correspondance de suffixes, vous pouvez configurer la stratégie de groupe DisableStrictDNSNaming. Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-planning-for-clients-and-devices.md">planification des clients et des appareils dans Lync Server 2013</A> dans la documentation de planification.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Exemple de certificats et d’enregistrements DNS requis pour la connexion automatique au client

Cet exemple utilise les mêmes noms d’exemples dans le tableau précédent. L’organisation contoso prend en charge les domaines SIP de contoso.com et retail.contoso.com, et tous les utilisateurs ont un URI SIP dans l’une des formes suivantes:

  - \<@retail\>utilisateur. contoso.com

  - \<@contoso\>utilisateur. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

