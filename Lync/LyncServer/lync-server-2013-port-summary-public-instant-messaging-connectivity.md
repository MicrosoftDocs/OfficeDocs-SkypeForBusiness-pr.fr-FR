---
title: 'Lync Server 2013: Résumé des ports-connectivité de messagerie instantanée publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bb6b8d0d9277b7d77440519596da76585b9d91b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Résumé de port-connectivité de messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-16_

Pour configurer votre pare-feu pour les ports et les protocoles nécessaires à la prise en charge de la connectivité de messagerie instantanée publique, notez d’abord que le protocole SIP/MTLS/TCP 5061 est bidirectionnel pour tenir compte de la capacité des contacts du fournisseur de messagerie instantanée publique à contacter les clients Lync, ou pour Lync à Contactez les contacts de la messagerie instantanée publique.

Windows Live Messenger peut participer aux communications audio/vidéo avec les clients Lync. Il s’agit des comptes pour le pare-feu et la configuration de protocole très similaires dont vous disposez généralement sur le pare-feu pour la prise en charge des clients Lync en tant qu’utilisateurs externes.

<div>


> [!IMPORTANT]  
> Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisation/appareil supplémentaire au-delà de la licence d’accès client standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.<BR>Les contacts de la Fédération avec le client Messenger se terminent officiellement le 15 mars 2013, à l’exception de la Chine continentale. Skype deviendra le client de Fédération pour les utilisateurs fédérés qui utilisaient déjà Messenger.



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Résumé du pare-feu-connectivité de messagerie instantanée publique


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rôles/protocole/TCP ou UDP/Port</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/TCP/5061 d’accès/SIP (MTLS)</p></td>
<td><p>Partenaires de connectivité de messagerie instantanée publique</p></td>
<td><p>Interface d’accès Edge Server</p></td>
<td><p>Pour la connectivité de messagerie instantanée fédérée et publique qui utilise SIP.</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 d’accès/SIP (MTLS)</p></td>
<td><p>Interface d’accès Edge Server</p></td>
<td><p>Partenaires de connectivité de messagerie instantanée publique</p></td>
<td><p>Pour la connectivité de messagerie instantanée fédérée et publique qui utilise SIP.</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 d’accès/SIP (TLS)</p></td>
<td><p>Clients</p></td>
<td><p>Interface d’accès Edge Server</p></td>
<td><p>Trafic SIP client vers serveur pour l’accès des utilisateurs externes.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59,999</p></td>
<td><p>Interface d’accès Edge Server</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC (Public IM Connectivity) est configurée.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Interface d’accès Edge Server</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Interface d’accès Edge Server</p></td>
<td><p>Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

