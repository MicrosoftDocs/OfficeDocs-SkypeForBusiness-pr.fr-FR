---
title: 'Lync Server 2013 : configuration DNS requise pour la connexion automatique des clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b421656d5fefbefa308178962f5c25b9ae72013f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532181"
---
# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Configuration DNS requise pour la connexion automatique des clients dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-19_

Cette section décrit les enregistrements DNS (Domain Name System) nécessaires à la connexion automatique des clients. Quand vous déployez vos serveurs Standard Edition ou pools frontaux, vous pouvez configurer vos clients pour qu’ils utilisent la détection automatique pour se connecter au serveur Standard Edition ou pool frontal approprié. Si vous envisagez de demander à vos clients de se connecter manuellement à Lync Server 2013, vous pouvez ignorer cette rubrique.

Pour prendre en charge la connexion automatique des clients, vous devez :

  - Désignez un seul serveur ou pool pour distribuer et authentifier les demandes de connexion client. Il peut s’agir d’un serveur ou d’un pool existant de votre organisation qui héberge des utilisateurs, ou vous pouvez désigner un serveur ou un pool dédié à cette fin qui n’héberge aucun utilisateur. Pour la haute disponibilité, nous vous recommandons de désigner un pool frontal pour cette fonction.

  - Créez un enregistrement DNS SRV interne pour prendre en charge la connexion automatique des clients pour ce serveur ou ce pool.
    
    <div>
    

    > [!NOTE]  
    > Dans les conditions d’enregistrement suivantes, le domaine SIP fait référence à la partie hôte des URI SIP attribuées aux utilisateurs. Par exemple, si les URI SIP ont la forme * @contoso. com, contoso.com est le domaine SIP. Le domaine SIP est souvent différent du domaine Active Directory interne. Une organisation peut également prendre en charge plusieurs domaines SIP.

    
    </div>

Pour activer la configuration automatique pour vos clients, vous devez créer un enregistrement DNS SRV interne qui mappe l’un des enregistrements suivants au nom de domaine complet (FQDN) du pool frontal ou du serveur Standard Edition qui distribue les demandes de connexion à partir de clients Lync :

  - \_sipinternaltls. \_ TCP.\<domain\> -pour les connexions TLS internes

Il vous suffit de créer un seul enregistrement SRV pour le pool frontal ou le serveur Standard Edition, ou de distribuer des demandes de connexion.

Le tableau suivant présente des exemples d’enregistrements requis pour la société fictive contoso, qui prend en charge les domaines SIP de contoso.com et retail.contoso.com.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Exemple d’enregistrements DNS requis pour la connexion automatique des clients avec plusieurs domaines SIP

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
<td><p>Un enregistrement SRV pour le domaine _sipinternaltls. _ TCP. contoso. com sur le port 5061 qui mappe sur pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Un enregistrement SRV pour le domaine _sipinternaltls. _ TCP. Retail. contoso. com sur le port 5061 qui mappe sur pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Par défaut, les requêtes pour les enregistrements DNS respectent une correspondance de nom de domaine stricte entre le domaine dans le nom d’utilisateur et l’enregistrement SRV. Si vous préférez que les requêtes DNS clientes utilisent la correspondance de suffixe, vous pouvez configurer la stratégie de groupe DisableStrictDNSNaming. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> dans la documentation de planification.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Exemple de certificats et d’enregistrements DNS requis pour les Sign-In client automatiques

Cet exemple utilise les mêmes exemples de noms dans le tableau précédent. L’organisation contoso prend en charge les domaines SIP de contoso.com et retail.contoso.com, et tous ses utilisateurs ont un URI SIP dans l’un des formats suivants :

  - \<user\>@retail. contoso.com

  - \<user\>@contoso. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

