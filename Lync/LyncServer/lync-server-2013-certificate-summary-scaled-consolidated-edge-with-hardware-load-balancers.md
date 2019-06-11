---
title: Résumé des certificats - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 894a9f3e-7cba-4915-8fdf-e52f2f25126f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398692(v=OCS.15)
ms:contentKeyID: 48184729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccba3f1facf8d687f4448efc7aeff053f50b3be7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Résumé des certificats - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

Microsoft Lync Server 2013 utilise des certificats pour authentifier mutuellement d’autres serveurs et pour chiffrer les données du serveur vers le client et le serveur. Les certificats nécessitent une correspondance de nom des enregistrements DNS (Domain Name System) associés aux serveurs et du nom de l’objet (SN) et du nom de l’objet du certificat. Pour mapper correctement les serveurs, les enregistrements DNS et les entrées de certificat, vous devez planifier soigneusement les noms de domaines complets du serveur prévus inscrits dans DNS et les entrées SN et SAN sur le certificat.

Le certificat attribué aux interfaces externes du serveur Edge est demandé auprès d’une autorité de certification (CA) publique. Les autorités de certification publiques ayant démontré le succès de la fourniture de certificats aux fins de communications unifiées sont indiquées dans [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395)l’article suivant:. Lors de la demande du certificat, vous pouvez utiliser la demande de certificat générée par l’Assistant Déploiement de Lync Server ou créer la requête manuellement ou par un processus fourni par l’autorité de certification publique. Lorsque vous attribuez le certificat, le certificat est attribué à l’interface du service Edge d’accès, à l’interface du service Edge de conférence Web et au service d’authentification audio/vidéo. Le service d’authentification audio/vidéo ne doit pas être confondu avec le service Edge A/V, qui n’utilise pas de certificat pour chiffrer les flux audio et vidéo. L’interface du serveur Edge interne peut utiliser un certificat provenant d’une autorité de certification interne (à votre organisation) ou d’un certificat d’une autorité de certification publique. Le certificat d’interface interne utilise uniquement le SN et n’a pas besoin ou n’utilise pas d’entrées du SAN.

<div>


> [!NOTE]
> Le tableau suivant montre une deuxième entrée SIP (sip.fabrikam.com) dans la liste nom de l’objet. Pour chaque domaine SIP de votre organisation, vous devez ajouter un FQDN correspondant dans la liste nom du sujet du certificat.



</div>

<div>

## <a name="certificates-required-for-scaled-consolidated-edge-with-hardware-load-balancers"></a>Certificats requis pour les bords consolidés mis à l’échelle avec des équilibreurs de charge matérielle


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
<th>Nom de l’objet</th>
<th>Autres noms d’objet (SAN)/Order</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Edge consolidé unique (Edge externe)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Le certificat doit faire partir d’une autorité de certification publique et doit disposer de l’utilisation de l’utilisation améliorée de l’utilisation du serveur et de l’utilisation améliorée de la messagerie instantanée pour le client. De plus, dans le cas de serveurs Edge à l’échelle, la clé privée du certificat doit être exportable et le certificat et la clé privée copiés vers chaque serveur Edge.</p>
<ul>
<li><p>Service Edge d’accès</p></li>
<li><p>Service Edge de conférence web</p></li>
<li><p>Service Edge A/V</p></li>
</ul>
<p>Notez que les San sont automatiquement ajoutés au certificat en fonction de vos définitions dans le générateur de topologie. Vous pouvez ajouter des entrées SAN selon vos besoins pour des domaines SIP supplémentaires et d’autres entrées que vous devez prendre en charge. Le nom du sujet est répliqué sur le SAN et doit être présent pour une opération correcte.</p></td>
</tr>
<tr class="even">
<td><p>Serveur Edge consolidé unique (bord interne)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Aucun SAN requis</p></td>
<td><p>Le certificat peut être émis par une autorité de certification publique ou privée, et doit contenir l’extension améliorée du serveur. Le certificat est attribué à l’interface du serveur Edge interne.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Résumé de certification-connectivité de messagerie instantanée publique


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
<th>Nom de l’objet</th>
<th>Autres noms d’objet (SAN)/Order</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Service Edge externe/Access</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Le certificat doit faire partir d’une autorité de certification publique et doit disposer de l’utilisation de l’utilisation améliorée de l’utilisation du serveur et de l’utilisation améliorée de la messagerie instantanée pour le client. Le certificat est attribué aux interfaces de bord externe pour:</p>
<ul>
<li><p>Service Edge d’accès</p></li>
<li><p>Service Edge de conférence web</p></li>
<li><p>Service Edge A/V</p></li>
</ul>
<p>Notez que les San sont automatiquement ajoutés au certificat en fonction de vos définitions dans le générateur de topologie. Vous pouvez ajouter des entrées SAN selon vos besoins pour des domaines SIP supplémentaires et d’autres entrées que vous devez prendre en charge. Le nom du sujet est répliqué sur le SAN et doit être présent pour une opération correcte.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>Résumé du certificat pour le protocole extensible de messagerie et de présence


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
<th>Nom de l’objet</th>
<th>Autres noms d’objet (SAN)/Order</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Affecter au service Edge d’accès du serveur Edge ou du pool de périphérie</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*.contoso.com</strong></p></td>
<td><p>Les trois premières entrées du SAN sont les entrées SAN normales pour un serveur de périphérie complet. Contoso.com est l’entrée requise pour la Fédération avec le partenaire XMPP au niveau du domaine racine. Cette entrée autorise la fonction XMPP pour tous les domaines dont le suffixe est *. contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

