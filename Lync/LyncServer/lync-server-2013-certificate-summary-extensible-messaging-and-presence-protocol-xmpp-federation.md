---
title: 'Lync Server 2013: Résumé de certification-Fédération de protocoles de messagerie extensible et de présence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49105661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01b21c8b09d93f8d2788424f2c8f440e1dec66b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Résumé de certification-Fédération de protocoles de messagerie extensible et de présence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-12-23_

Les exigences en matière de certificats pour l’activation et la définition des communications avec les partenaires de messagerie électronique et de présence (XMPP) requièrent l’enregistrement supplémentaire de vos domaines XMPP. L’enregistrement figurant sur le certificat en tant que autre nom de l’objet (SAN) sera le domaine qui peut participer aux communications XMPP. Le domaine peut être le domaine de niveau racine (par exemple, contoso.com) si vous souhaitez activer la XMPP pour l’ensemble de votre domaine ou si vous pouvez sélectionner des domaines enfants (par exemple, corp.contoso.com, finance.contoso.com) si vous activez XMPP pour un sous-ensemble d’utilisateurs.

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
<p>contoso.com</p></td>
<td><p>Les trois premières entrées du SAN sont les entrées SAN normales pour un serveur de périphérie complet. Contoso.com est l’entrée requise pour la Fédération avec le partenaire XMPP au niveau du domaine racine. Cette entrée autorise la fonction XMPP pour tous les domaines dont le suffixe est contoso.com.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  


[Configuration des certificats de serveur Edge pour Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Requête-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

