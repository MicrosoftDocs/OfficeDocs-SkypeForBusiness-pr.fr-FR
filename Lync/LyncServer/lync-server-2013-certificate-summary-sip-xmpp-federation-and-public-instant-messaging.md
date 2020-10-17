---
title: Résumé des certificats-SIP, Fédération XMPP et messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 284a633a2c5ce820009c6672058837bbecb7ecd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517871"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Résumé des certificats-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-15_

Les certificats dont vous avez besoin pour la Fédération avec Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server seront généralement satisfaits par les certificats que vous configurez, demandez et attribuez à votre serveur Edge.

Les certificats requis pour l’activation et l’établissement de communications avec les partenaires XMPP (extensible Messaging and Presence Protocol) nécessitent l’ajout d’entrées pour vos domaines XMPP. L’enregistrement qui est inclus sur le certificat en tant qu’autre nom de l’objet (SAN) est le domaine pouvant participer aux communications XMPP. Ce domaine peut être le domaine de niveau racine (par exemple, contoso.com) si vous voulez activer XMPP pour l’ensemble de votre domaine, ou des domaines enfants sélectionnés (par exemple, corp.contoso.com, finance.contoso.com) si vous activez XMPP pour un sous-ensemble d’utilisateurs.

Pour configurer des certificats pour la connectivité de messagerie instantanée publique, Notez qu’il n’y a rien de différent d’autres types de Fédération SIP ou même des certificats de serveur Edge standard, sauf que America Online (AOL) requiert un ou plusieurs certificats (dans le cas d’un pool de serveurs Edge) pour contenir également l’utilisation améliorée de l’étendue client. L’EKU client est un complément du certificat et fait partie du certificat public externe attribué à votre serveur Edge.

Pour vérifier que vous avez satisfait aux exigences de certificat appropriées pour votre déploiement de serveur Edge, consultez les rubriques répertoriées dans la section intitulée **Voir aussi**.

<div>



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
<th>Autres noms du sujet (SAN)</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Edge externe/d’accès</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> Pour prendre en charge l’espace de noms XMPP contoso.com


<p>sip.fabrikam.com</p>



> [!NOTE]
> Pour prendre en charge l’espace de noms SIP fabrikam.com


<p>fabrikam.com</p>



> [!NOTE]
> Pour prendre en charge l’espace de noms XMPP fabrikam.com

</td>
<td><p>Le certificat doit provenir d’une autorité de certification publique et doit disposer de l’utilisation améliorée de l’étendue du serveur et de l’EKU client si la connectivité PIC avec AOL doit être déployée. Le certificat est affecté aux interfaces du serveur Edge externe pour les éléments suivants :</p>
<ul>
<li><p>service Edge d’accès</p></li>
<li><p>service Edge de conférence Web</p></li>
<li><p>Service Edge A/V</p></li>
</ul>



> [!NOTE]
> Techniquement, un certificat n’est pas affecté au serveur Edge A/V. La communication sécurisée et l’authentification sont gérées par le service d’authentification du serveur relais multimédia (MRAS). MRAS utilise le certificat affecté à l’interface interne du serveur Edge.


<p>Notez que les autres noms du sujet sont automatiquement ajoutés au certificat en fonction de vos définitions dans le Générateur de topologie. Vous ajoutez des entrées SAN selon les besoins liés aux autres domaines SIP et entrées que vous devez prendre en charge. Le nom du sujet est répliqué dans l’autre nom du sujet et doit être présent pour assurer un fonctionnement correct.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Résumé des certificats-serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Résumé des certificats-serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Résumé des certificats-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Résumé des certificats-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Résumé des certificats-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

