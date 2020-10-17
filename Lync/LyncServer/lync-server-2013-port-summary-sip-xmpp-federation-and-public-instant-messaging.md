---
title: Résumé des ports-SIP, Fédération XMPP et messagerie instantanée publique
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
ms.openlocfilehash: 7119bfd6209ac9a7d8eb2c4adfddb75c3601116d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508751"
---
# <a name="port-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Résumé des ports-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-15_

La configuration requise pour les ports, les protocoles et les pare-feu pour la Fédération avec Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server est similaire à celle du serveur Edge déployé. Les clients initient la communication avec le service Edge d’accès via TLS/SIP/TCP 443. Toutefois, les partenaires fédérés initieront des communications vers le service Edge d’accès via MTLS/SIP/TCP 5061.

Pour configurer votre pare-feu pour les ports et les protocoles nécessaires à la prise en charge de la connectivité de messagerie instantanée publique, notez d’abord que SIP/MTLS/TCP 5061 est bidirectionnel afin de tenir compte de la capacité des contacts dans le fournisseur de messagerie instantanée publique à contacter les clients Lync ou à contacter les contacts de messagerie instantanée publique.

Windows Live Messenger peut participer à des communications audio/vidéo avec des clients Lync. Cela tient compte des ports de pare-feu et de la configuration de protocole très similaires dont vous disposez généralement sur le pare-feu pour prendre en charge les clients Lync en tant qu’utilisateurs externes.

<div>


> [!IMPORTANT]
> Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert pas de licences utilisateur/périphérique supplémentaires au-delà de la licence d’accès client (CAL) standard Lync. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.<BR>Les contacts de la Fédération avec des clients Messenger se termineront officiellement le 15 mars 2013, à l’exception de la Chine continentale. Skype devient le client de Fédération pour les utilisateurs fédérés qui utilisaient précédemment Messenger.



</div>

Les ports et protocoles définis pour le proxy XMPP (extensible Messaging and Presence Protocol) déployé sur le serveur Edge autorisent les communications du partenaire fédéré XMPP au serveur Edge et permettent également la communication entre votre serveur Edge et le partenaire fédéré XMPP. Une règle est également définie sur le pare-feu orienté vers l’intérieur du serveur frontal ou du pool frontal vers le serveur Edge ou le pool de serveurs Edge.

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
<th>Rôle/Protocole/TCP ou UDP/Port</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Accès/SIP (MTLS)/TCP/5061</p></td>
<td><p>Adresse IP publique du service Edge d’accès</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Pour la connectivité fédérée et PIC utilisant SIP</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a>Résumé du pare-feu : connectivité de messagerie instantanée publique


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Rôle/Protocole/TCP ou UDP/Port</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Accès/SIP (MTLS)/TCP/5061</p></td>
<td><p>Partenaires de connectivité PIC</p></td>
<td><p>Interface d’accès au serveur Edge</p></td>
<td><p>Pour la connectivité de messagerie instantanée publique et fédérée qui utilisent SIP.</p></td>
</tr>
<tr class="even">
<td><p>Accès/SIP (MTLS)/TCP/5061</p></td>
<td><p>Interface d’accès au serveur Edge</p></td>
<td><p>Partenaires de connectivité PIC</p></td>
<td><p>Pour la connectivité de messagerie instantanée publique et fédérée qui utilisent SIP.</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP (TLS)/TCP/443</p></td>
<td><p>Clients</p></td>
<td><p>Interface d’accès au serveur Edge</p></td>
<td><p>Trafic SIP client à serveur pour l’accès des utilisateurs externes.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-000-59 999</p></td>
<td><p>Interface d’accès au serveur Edge</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Interface d’accès au serveur Edge</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Obligatoire pour la connectivité PIC avec Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Interface d’accès au serveur Edge</p></td>
<td><p>Obligatoire pour la connectivité PIC avec Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary---extensible-messaging-and-presence-protocol-xmpp"></a>Résumé du pare-feu-protocole XMPP (extensible Messaging and Presence Protocol)


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
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès</p></td>
<td><p>Port de communication de serveur à serveur standard pour XMPP. Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Port de communication de serveur à serveur standard pour XMPP. Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>N’importe lequel</p></td>
<td><p>Adresse IP de l’interface du serveur Edge interne</p></td>
<td><p>Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers le serveur Edge</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  


[Gérer les partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

