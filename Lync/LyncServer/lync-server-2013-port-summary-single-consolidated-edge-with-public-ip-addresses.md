---
title: Résumé des ports-serveur Edge unique consolidé avec adresses IP publiques
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9020821da26c39094e7c04f3cbf72875b91ffaff
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Résumé des ports-serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

La fonctionnalité de serveur Edge de Lync Server 2013 décrite dans cette architecture de scénario est très semblable à celle qui a été implémentée dans Lync Server 2010. L’ajout le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol). Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal. Les informations de planification pour le proxy inverse et la Fédération sont disponibles dans [scénarios de proxy inverse dans Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) et [planification pour SIP, Fédération XMPP et messagerie instantanée publique dans les sections Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivement.

Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6. Par souci de clarté, seul IPv4 est utilisé dans les scénarios.

**Réseau de périmètre d’entreprise pour un serveur Edge consolidé unique avec adressage IP public**

![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")

<div>

## <a name="port-and-protocol-details"></a>Détails des ports et protocoles

Nous vous recommandons de n’ouvrir que les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous autorisez l’accès externe.

Pour l’accès distant à un service Edge, il est obligatoire d’autoriser le trafic SIP à circuler dans les deux sens, comme le montre l’illustration « Trafic Edge bidirectionnel ». Autrement dit, la messagerie SIP vers et depuis le service Edge d’accès est impliquée dans la messagerie instantanée, la présence, la conférence Web, l’audio/vidéo (A/V) et la Fédération.

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a>Résumé du pare-feu pour un serveur Edge consolidé unique avec des adresses IP publiques : interface externe

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</p></td>
<td><p>Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations XMPP définies</p></td>
</tr>
<tr class="even">
<td><p>Accès/HTTP/TCP/80</p></td>
<td><p>Adresse IP publique du service Edge d’accès au serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Vérification et extraction de la liste de révocation de certificats</p></td>
</tr>
<tr class="odd">
<td><p>Accès/DNS/TCP/53</p></td>
<td><p>Adresse IP publique du service Edge d’accès au serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Requête DNS sur TCP</p></td>
</tr>
<tr class="even">
<td><p>Accès/DNS/UDP/53</p></td>
<td><p>Adresse IP publique du service Edge d’accès au serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Requête DNS sur UDP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP (TLS)/TCP/443</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge d’accès au serveur Edge</p></td>
<td><p>Trafic SIP client vers serveur pour l’accès des utilisateurs externes</p></td>
</tr>
<tr class="even">
<td><p>Accès/SIP (MTLS)/TCP/5061</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge d’accès au serveur Edge</p></td>
<td><p>Pour la connectivité fédérée et PIC avec SIP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP (MTLS)/TCP/5061</p></td>
<td><p>Adresse IP publique du service Edge d’accès au serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Pour la connectivité fédérée et PIC utilisant SIP</p></td>
</tr>
<tr class="even">
<td><p>Conférence Web/PSOM (TLS)/TCP/443</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge de conférence Web du serveur Edge</p></td>
<td><p>Support de conférence Web</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-000-59 999</p></td>
<td><p>Adresse IP publique du service Edge d’accès au serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Obligatoire pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-000-59 999</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-000-59 999</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-000-59 999</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic multimédia à partir du serveur Edge de serveur à serveur Edge. Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que si plusieurs pools Edge sont déployés au sein d’une entreprise.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>STUN/activer la négociation des candidats via UDP/3478</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>STUN/activer la négociation des candidats sur TCP/443</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>STUN/activer la négociation des candidats sur TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a>Résumé du pare-feu pour un serveur Edge consolidé unique avec des adresses IP publiques : interface interne

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
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (peut être défini en tant qu’adresse IP Standard Edition Server, Standard Edition Server ou adresse IP du pool exécutant le service de passerelle XMPP)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic XMPP sortant du service de passerelle XMPP exécuté sur un serveur frontal ou un pool frontal</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal)</p></td>
<td><p>Adresse IP du serveur Edge ou pool qui contient l’interface interne</p></td>
<td><p>Trafic SIP sortant (depuis le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) vers l’interface interne du serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Any (peut être défini en tant que directeur, adresse IP du pool Directeur, serveur frontal ou adresse du pool frontal)</p></td>
<td><p>Trafic SIP entrant (vers le directeur, l’adresse IP du pool Directeur, le serveur frontal ou l’adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (peut être défini en tant qu’adresse IP de serveur frontal ou chaque adresse IP de serveur frontal dans un pool frontal)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic de conférence Web à partir du serveur frontal ou de chaque serveur frontal dans un pool, vers l’interface interne du serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (peut être défini comme adresse IP du serveur frontal ou adresse IP du pool frontal ou n’importe quel serveur Survivable Branch Server ou Survivable Branch Server à l’aide de ce serveur Edge)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou d’un serveur Survivable Branch Appliance ou d’un serveur Survivable Branch à l’aide de ce serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Chemin préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes, le Survivable Branch Appliance ou le serveur Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou le serveur Survivable Branch Server si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (peut être défini comme adresse IP du serveur frontal ou pool qui contient le magasin central de gestion)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>Résumé du pare-feu pour la fédération


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
<td><p>N'importe lequel</p></td>
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
<td><p>Service Edge d’accès au serveur Edge</p></td>
<td><p>Pour la connectivité fédérée et PIC avec SIP</p></td>
</tr>
<tr class="even">
<td><p>Accès/SIP (MTLS)/TCP/5061</p></td>
<td><p>Service Edge d’accès au serveur Edge</p></td>
<td><p>Partenaires de connectivité PIC</p></td>
<td><p>Pour la connectivité fédérée et PIC avec SIP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP (TLS)/TCP/443</p></td>
<td><p>Clients</p></td>
<td><p>Service Edge d’accès au serveur Edge</p></td>
<td><p>Trafic SIP client vers serveur pour l’accès des utilisateurs externes</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-000-59 999</p></td>
<td><p>Service Edge A/V du serveur Edge</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC est configurée.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Service Edge A/V du serveur Edge</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Requis pour la connectivité PIC avec Windows Live Messenger</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Service Edge A/V du serveur Edge</p></td>
<td><p>Requis pour la connectivité PIC avec Windows Live Messenger</p></td>
</tr>
</tbody>
</table>


</div>

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
<td><p>Adresse IP de l’interface du service Edge d’accès au serveur Edge</p></td>
<td><p>Port de communication de serveur à serveur standard pour XMPP. Autorise la communication vers le proxy XMPP du serveur Edge à partir de partenaires XMPP fédérés</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès au serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Port de communication de serveur à serveur standard pour XMPP. Autorise la communication du proxy XMPP serveur Edge aux partenaires XMPP fédérés</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP de chaque interface de serveur Edge interne</p></td>
<td><p>Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool Edge</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

