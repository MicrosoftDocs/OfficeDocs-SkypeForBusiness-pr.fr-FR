---
title: Résumé des ports-Fédération XMPP (extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72ab2f2912a78ee30e9c032592a704eccbab8bf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Résumé des ports-Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-20_

Les ports et protocoles définis pour le proxy XMPP (extensible Messaging and Presence Protocol) déployé sur le serveur Edge autorisent les communications du partenaire fédéré XMPP au serveur Edge et permettent également la communication entre votre serveur Edge et la fonction XMPP partenaire fédéré. Une règle est également définie sur le pare-feu orienté vers l’intérieur du serveur frontal ou du pool frontal vers le serveur Edge ou le pool de serveurs Edge.

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Résumé du pare-feu pour le protocole XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocole/TCP ou UDP/Port</th>
<th>Source (adresse IP)</th>
<th>Destination (adresse IP)</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès</p></td>
<td><p>Port de communication de serveur à serveur standard pour XMPP. Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Port de communication de serveur à serveur standard pour XMPP. Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP de l’interface du serveur Edge interne</p></td>
<td><p>Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers le serveur Edge</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Gérer les partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

