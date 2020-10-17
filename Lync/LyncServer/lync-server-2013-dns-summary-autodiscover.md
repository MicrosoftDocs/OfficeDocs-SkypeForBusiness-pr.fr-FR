---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc30b787d938825f229f28b10d54907ad26a4d35
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501321"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>Résumé des enregistrements DNS-découverte automatique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-13_

La découverte automatique est un service flexible en ce qu’elle accepte la communication via HTTP ou HTTPs. Pour ce faire, le système DNS (Domain Name System) et les certificats utilisés par les serveurs qui hébergent le service de découverte automatique doivent être configurés correctement. Les exigences de certificat sont traitées dans [Résumé des certificats-découverte automatique dans Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).

<div>


> [!IMPORTANT]  
> La logique de recherche DNS pour les clients Lync Server utilise un ordre de résolution spécifique. Vous devez toujours inclure le lyncdiscoverinternal. &lt; domaine &gt; et lyncdiscover. &lt; domaine &gt; dans votre DNS. À l’exclusion du lyncdiscoverinternal. &lt; l' &gt; enregistrement de domaine entraîne l’échec de la connexion des clients internes aux services prévus ou la réception d’une réponse de découverte automatique incorrecte.



</div>

### <a name="internal-dns-records"></a>Enregistrements DNS internes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’enregistrement</th>
<th>Nom d’hôte</th>
<th>Résolu en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal. &lt; nom de domaine interne&gt;</p></td>
<td><p>Nom de domaine complet (FQDN) des services Web internes pour votre pool Directeur, si vous en avez un, ou pour votre pool frontal si vous n’avez pas de directeur.</p></td>
</tr>
<tr class="even">
<td><p>A (hôte, si IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal. &lt; nom de domaine interne&gt;</p></td>
<td><p>Adresse IP interne des services Web (adresse IP virtuelle (VIP) si vous utilisez un programme d’équilibrage de la charge) de votre pool Directeur, si vous en avez un, ou de votre pool frontal si vous ne disposez pas d’un directeur.</p></td>
</tr>
</tbody>
</table>


Vous devez créer l’un des enregistrements DNS externes suivants :

### <a name="external-dns-records"></a>Enregistrements DNS externes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’enregistrement</th>
<th>Nom d’hôte</th>
<th>Résolu en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt; sipdomain&gt;</p></td>
<td><p>Nom de domaine complet externe des services Web pour votre pool Directeur, si vous en avez un, ou pour votre pool frontal si vous n’avez pas de directeur.</p></td>
</tr>
<tr class="even">
<td><p>A (hôte, si IPv6, AAAA)</p></td>
<td><p>lyncdiscover. &lt; sipdomain&gt;</p></td>
<td><p>Adresse IP externe ou publique du proxy inverse.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Le trafic externe passe par le proxy inverse.



</div>

<div>


> [!NOTE]  
> Les clients d’appareils mobiles ne prennent pas en charge plusieurs certificats SSL (Secure Sockets Layer) de différents domaines. Par conséquent, la redirection CNAME vers différents domaines n’est pas prise en charge sur le protocole HTTPS. Par exemple, un enregistrement DNS CNAME pour lyncdiscover.contoso.com qui redirige vers une adresse director.contoso.net n’est pas pris en charge sur HTTPS. Dans une telle topologie, un client d’appareil mobile doit utiliser le protocole HTTP pour la première demande, de sorte que la redirection CNAME soit résolue sur HTTP. Les demandes ultérieures utilisent ensuite le protocole HTTPS. Pour prendre en charge ce scénario, vous devez configurer votre proxy inverse avec une règle de publication web pour le port 80 (HTTP). Pour plus d’informations, reportez-vous à la section « pour créer une règle de publication Web pour le port 80 » dans <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configuration du proxy inverse pour la mobilité dans Lync Server 2013</A>. La redirection CNAME vers le même domaine est prise en charge sur HTTPS. Dans ce cas, le certificat du domaine de destination couvre le domaine d’origine.



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration du proxy inverse pour la mobilité dans Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Résumé des certificats-découverte automatique dans Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

