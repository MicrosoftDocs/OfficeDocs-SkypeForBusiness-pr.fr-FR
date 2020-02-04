---
title: Résumé du certificat-SIP, Fédération de XMPP et messagerie instantanée publique
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
ms.openlocfilehash: 0fc3b7a1745d045954fb06403dbb3359fb699a29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Résumé du certificat-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-15_

Les certificats dont vous avez besoin pour la Fédération avec Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server seront généralement satisfaits par les certificats que vous configurez, demandez et attribuez à votre serveur Edge.

Les exigences en matière de certificats pour l’activation et la définition des communications avec les partenaires de messagerie et de présence (en anglais) en fonction du protocole de messagerie extensible nécessitent l’ajout d’entrées pour vos domaines XMPP. L’enregistrement figurant sur le certificat en tant que autre nom de l’objet (SAN) sera le domaine qui peut participer aux communications XMPP. Le domaine peut être le domaine de niveau racine (par exemple, contoso.com) si vous souhaitez activer la XMPP pour l’ensemble de votre domaine ou si vous pouvez sélectionner des domaines enfants (par exemple, corp.contoso.com, finance.contoso.com) si vous activez XMPP pour un sous-ensemble d’utilisateurs.

Pour configurer des certificats pour la connectivité de messagerie instantanée publique, Notez qu’il n’y a rien d’autre que d’autres types de Fédération SIP ou même des certificats de serveur Edge standard, à l’exception que America Online (AOL) nécessite le ou les certificats (en dans le cas d’un pool de bords, le cas échéant, il s’agit de l’utilisation de l’utilisation améliorée du client. L’utilisation améliorée de l’utilisation du client est un ajout du certificat, qui fait partie du certificat public externe affecté à votre serveur Edge.

Pour vérifier que vous remplissez les conditions requises pour les certificats pour le déploiement de Microsoft Edge Server, **reportez-** vous aux rubriques indiquées dans la section Voir aussi.

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
<th>Nom de l’objet</th>
<th>Autres noms d’objet (SAN)</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Périphérie externe/accès</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>contoso.com</p>



> [!NOTE]
> Pour prendre en charge l’espace de noms contoso.com XMPP


<p>sip.fabrikam.com</p>



> [!NOTE]
> Pour prendre en charge l’espace de noms SIP fabrikam.com


<p>fabrikam.com</p>



> [!NOTE]
> Pour prendre en charge l’espace de noms fabrikam.com XMPP

</td>
<td><p>Le certificat doit faire partir d’une autorité de certification publique et doit disposer de l’utilisation de l’utilisation améliorée de l’utilisation du serveur et de l’utilisation améliorée de la messagerie instantanée pour le client. Le certificat est attribué aux interfaces du serveur Edge externe pour les éléments suivants :</p>
<ul>
<li><p>Service Edge d’accès</p></li>
<li><p>Service Edge de conférence web</p></li>
<li><p>Service Edge A/V</p></li>
</ul>



> [!NOTE]
> Techniquement, un certificat n’est pas affecté au bord A/V. La communication et l’authentification sécurisées sont gérées par le biais du service d’authentification par relais de média (MRAS). MRAS utilise le certificat attribué à l’interface interne du serveur Edge.


<p>Notez que les San sont automatiquement ajoutés au certificat en fonction de vos définitions dans le générateur de topologie. Vous pouvez ajouter des entrées SAN selon vos besoins pour des domaines SIP supplémentaires et d’autres entrées que vous devez prendre en charge. Le nom du sujet est répliqué sur le SAN et doit être présent pour une opération correcte.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Résumé des certificats - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[Résumé des certificats - Serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[Résumé des certificats - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[Résumé des certificats - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[Résumé des certificats - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

