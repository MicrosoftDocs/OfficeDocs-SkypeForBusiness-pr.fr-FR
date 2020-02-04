---
title: Résumé de port-SIP, Fédération de XMPP et messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - SIP, XMPP federation, and public instant messaging
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49105660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae19fb2477f61c0e408ebad3a8abf97fb75b9c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Résumé de port-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-15_

Les exigences en matière de port, de protocole et de pare-feu pour la Fédération avec Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server sont similaires à celles du serveur Edge déployé. Les clients entament une communication avec le service Edge d’accès via TLS/SIP/TCP 443. Les partenaires fédérés peuvent toutefois lancer des communications avec le service Edge d’accès via MTLS/SIP/TCP 5061.

Pour configurer votre pare-feu pour les ports et les protocoles nécessaires à la prise en charge de la connectivité de messagerie instantanée publique, notez d’abord que le protocole SIP/MTLS/TCP 5061 est bidirectionnel afin de tenir compte de la capacité des contacts du fournisseur de messagerie instantanée publique à contacter les clients Lync ou à communiquer avec des contacts de messagerie instantanée publics.

Windows Live Messenger peut participer aux communications audio/vidéo avec les clients Lync. Il s’agit des comptes pour le pare-feu et la configuration de protocole très similaires dont vous disposez généralement sur le pare-feu pour la prise en charge des clients Lync en tant qu’utilisateurs externes.

<div>


> [!IMPORTANT]
> Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisation/appareil supplémentaire au-delà de la licence d’accès client standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.<BR>Les contacts de la Fédération avec le client Messenger se terminent officiellement le 15 mars 2013, à l’exception de la Chine continentale. Skype deviendra le client de Fédération pour les utilisateurs fédérés qui utilisaient déjà Messenger.



</div>

Les ports et protocoles définis pour le proxy d’extension de messagerie et de présence (XMPP) déployés sur le serveur Edge autorisent les communications du partenaire fédéré de XMPP au serveur Edge et permettent également la communication entre votre serveur Edge et la fonction XMPP. partenaire fédéré. Une règle est également définie pour le pare-feu à l’intérieur du serveur frontal ou du pool frontal du serveur Edge ou du pool Edge.

<div>

## <a name="firewall-summary---sip-federation"></a>Résumé du pare-feu-Fédération SIP


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
<td><p>Adresse IP publique du service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</p></td>
</tr>
</tbody>
</table>


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

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Résumé de pare-feu-protocole de messagerie extensible et de présence


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
<th>Source (adresse IP)</th>
<th>Destination (adresse IP)</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès</p></td>
<td><p>Port de communication serveur à serveur standard pour XMPP. Autorise la communication au proxy de serveur Edge XMPP auprès des partenaires XMPP fédérés</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Port de communication serveur à serveur standard pour XMPP. Autorise la communication du proxy de serveur Edge XMPP aux partenaires XMPP fédérés</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP de l’interface du serveur Edge interne</p></td>
<td><p>Trafic de XMPP interne provenant de la passerelle XMPP du serveur frontal ou du pool frontal sur le serveur Edge</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

