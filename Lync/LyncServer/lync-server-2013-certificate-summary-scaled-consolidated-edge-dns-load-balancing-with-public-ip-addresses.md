---
title: 'Lync Server 2013 : Résumé des certificats-serveur Edge consolidé ajusté, équilibrage de charge DNS avec des adresses IP publiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: e87ac448-ee8f-477a-9f33-ce066c1bf093
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205399(v=OCS.15)
ms:contentKeyID: 48185894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 080a0587347dfd7d0b5b4cd32e5fa074413091b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Résumé des certificats-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Microsoft Lync Server 2013 utilise des certificats pour authentifier mutuellement d’autres serveurs et chiffrer les données entre serveurs et serveurs en client. Les certificats exigent que les noms des enregistrements DNS (Domain Name System) associés aux serveurs, au nom du sujet et à l’autre nom du sujet correspondent. Pour mapper correctement les serveurs, les enregistrements DNS et les entrées de certificat, vous devez planifier attentivement les noms de domaine complets de vos serveurs tels qu’ils sont inscrits dans le système DNS et dans les entrées du nom du sujet et de l’autre nom du sujet sur le certificat.

Le certificat affecté aux interfaces externes du serveur Edge est demandé auprès d’une autorité de certification publique. Les autorités de certification publiques ayant démontré la réussite de la fourniture de certificats à des fins de communications unifiées sont répertoriées dans l’article suivant : [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) lors de la demande de certificat, vous pouvez utiliser la demande de certificat générée par l’Assistant Déploiement de Lync Server ou créer la demande manuellement ou par un processus fourni par l’autorité de certification publique. Lors de l’affectation du certificat, le certificat est affecté à l’interface du service Edge d’accès, à l’interface du service Edge de conférence Web et au service d’authentification audio/vidéo. Le service d’authentification audio/vidéo ne doit pas être confondu avec le service Edge A/V qui n’utilise pas de certificat pour chiffrer les flux audio et vidéo. L’interface de serveur Edge interne peut utiliser un certificat d’une autorité de certification interne (vers votre organisation) ou un certificat d’une autorité de certification publique. Le certificat de l’interface interne utilise uniquement le nom du sujet ; il ne requiert pas et n’utilise pas d’entrées SAN.

<div>


> [!NOTE]  
> Le tableau suivant montre une seconde entrée SIP (sip.fabrikam.com) dans la liste des autres noms de sujets pour référence. Pour chaque domaine SIP de votre entreprise, vous devez ajouter un nom de domaine complet correspondant répertorié dans la liste des autres noms de sujets du certificat.



</div>

<div>

## <a name="scaled-consolidated-edge-using-dns-load-balancing-with-public-ip-addresses"></a>Périphérie consolidée à l’échelle utilisant l’équilibrage de charge DNS avec des adresses IP publiques


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant</th>
<th>Nom du sujet</th>
<th>Autres noms du sujet (SAN)/Ordre</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Périphérie consolidée à l’échelle (Périmètre externe)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Le certificat doit provenir d’une autorité de certification publique et comporter l’utilisation améliorée de la clé du serveur et l’utilisation améliorée de la clé du client si la solution PIC (Public IM Connectivity) avec AOL doit être déployée. De plus, pour les serveurs Edge à l’envergure, la clé privée de certificat doit être exportable et le certificat et la clé privée copiés sur chaque serveur Edge. Le certificat est assigné aux interfaces Edge externes pour :</p>
<ul>
<li><p>Serveur Edge d’accès</p></li>
<li><p>Serveur Edge de conférence</p></li>
<li><p>Edge A/V</p></li>
</ul>
<p>Notez que les autres noms du sujet sont automatiquement ajoutés au certificat en fonction de vos définitions dans le Générateur de topologie. Vous ajoutez des entrées SAN selon les besoins liés aux autres domaines SIP et entrées que vous devez prendre en charge. Le nom du sujet est répliqué dans l’autre nom du sujet et doit être présent pour assurer un fonctionnement correct.</p></td>
</tr>
<tr class="even">
<td><p>Périphérie consolidée à l’échelle (Périmètre interne)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Aucun autre nom du sujet requis</p></td>
<td><p>Le certificat peut être émis par une autorité de certification publique ou privée et il doit contenir l’utilisation améliorée de la clé du serveur. Il est assigné à l’interface Edge interne.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Résumé du certificat – Solution PIC (Public IM Connectivity)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant</th>
<th>Nom du sujet</th>
<th>Autres noms du sujet (SAN)/Ordre</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Edge externe/d’accès</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Le certificat doit provenir d’une autorité de certification publique et comporter l’utilisation améliorée de la clé du serveur et l’utilisation améliorée de la clé du client si la solution PIC (Public IM Connectivity) avec AOL doit être déployée. Le certificat est assigné aux interfaces Edge externes pour :</p>
<ul>
<li><p>Serveur Edge d’accès</p></li>
<li><p>Serveur Edge de conférence</p></li>
<li><p>Edge A/V</p></li>
</ul>
<p>Notez que les autres noms du sujet sont automatiquement ajoutés au certificat en fonction de vos définitions dans le Générateur de topologie. Vous ajoutez des entrées SAN selon les besoins liés aux autres domaines SIP et entrées que vous devez prendre en charge. Le nom du sujet est répliqué dans l’autre nom du sujet et doit être présent pour assurer un fonctionnement correct.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Résumé du certificat pour le protocole XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant</th>
<th>Nom du sujet</th>
<th>Autres noms du sujet (SAN)/Ordre</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Attribuer au service Edge d’accès d’un serveur Edge ou d’un pool de serveurs Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*. contoso.com</strong></p></td>
<td><p>Les trois premières entrées SAN sont les entrées SAN normales pour un serveur Edge complet. L’entrée contoso.com correspond à l’entrée requise pour la fédération avec le partenaire XMPP au niveau du domaine racine. Cette entrée autorise le protocole XMPP pour tous les domaines portant le suffixe *.contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

