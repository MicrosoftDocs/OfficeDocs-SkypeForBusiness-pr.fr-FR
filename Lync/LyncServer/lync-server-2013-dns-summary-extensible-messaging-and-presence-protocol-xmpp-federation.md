---
title: Résumé des enregistrements DNS-Fédération XMPP (extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e9aa17374de29c2b7f1f144b45322d075164ab4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Résumé des enregistrements DNS-Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-04-08_

Pour configurer le protocole XMPP (extensible Messaging and Presence Protocol) pour votre déploiement, vous devez créer deux enregistrements DNS (Domain Name System) dans un serveur DNS externe qui résoudra les enregistrements vers le service Edge d’accès de votre serveur Edge ou pool de serveurs Edge.

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Résumé DNS pour le protocole XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement/TYPE/port</th>
<th>FQDN</th>
<th>Adresse IP/Enregistrement d’hôte FQDN</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5269</p></td>
<td><p>_xmpp-Server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externe du proxy XMPP sur le service Edge d’accès ou le pool de serveurs Edge. Répétez cette opération si nécessaire pour tous les domaines SIP internes avec des utilisateurs activés de Lync où les contacts XMPP sont autorisés via la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, de la stratégie de site où se trouve l’utilisateur ou de la stratégie de l’utilisateur appliquée au Utilisateur à extension Lync. Un domaine XMPP autorisé doit également être configuré dans la stratégie des partenaires fédérés XMPP. Voir les rubriques de la <strong>section Voir aussi</strong> pour plus de détails</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>xmpp.contoso.com (par exemple)</p></td>
<td><p>Adresse IP du service Edge d’accès sur votre serveur Edge ou le pool de serveurs Edge qui héberge le proxy XMPP</p></td>
<td><p>Pointe vers le service Edge d’accès ou le pool de serveurs Edge qui héberge le service proxy XMPP. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement (A ou AAAA) d’hôte.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration de la Fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  


[Déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

