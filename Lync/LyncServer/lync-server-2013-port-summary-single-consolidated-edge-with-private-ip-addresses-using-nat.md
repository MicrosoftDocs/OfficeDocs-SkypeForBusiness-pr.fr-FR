---
title: Résumé des ports - Serveur Edge unique consolidé avec adresses IP privées avecla conversion d’adresses réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a425a07bf5ff615fb4766d50f21c6467512d110e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Résumé des ports - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-04-03_

La fonctionnalité Lync Server 2013, Edge Server décrite dans cette architecture de scénario est très similaire à celle implémentée dans Lync Server 2010. Le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol). Le serveur Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de bords et sur le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.

Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6. Par souci de clarté, seul le protocole IPv4 est utilisé dans les scénarios.

**Périmètre réseau d’un serveur Edge consolidé unique avec adresse IP privée utilisant tar**

![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")

<div>

## <a name="port-and-protocol-details"></a>Détails sur les ports et protocoles

Nous vous recommandons d’ouvrir uniquement les ports requis pour la prise en charge des fonctionnalités pour lesquelles vous fournissez un accès externe.

Pour que l’accès à distance fonctionne pour tous les services Edge, il est obligatoire que le trafic SIP soit autorisé de manière bidirectionnelle, comme indiqué dans le schéma de trafic Edge entrant/sortant. Autrement dit, la messagerie SIP vers et à partir du service Edge d’accès intervient dans la messagerie instantanée, la présence, les conférences Web, les appels audio/vidéo (A/V) et la Fédération.

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a>Résumé du pare-feu pour une périphérie unique consolidée avec des adresses IP privées utilisant tar : interface externe

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>Indifférente</p></td>
<td><p>Service proxy XMPP (adresse IP du partage avec service Edge d’accès)</p></td>
<td><p>Le service proxy XMPP accepte le trafic de contacts XMPP dans les fédérations de XMPP définies</p></td>
</tr>
<tr class="even">
<td><p>Accès/HTTP/TCP/80</p></td>
<td><p>Service Edge d’accès Edge Server</p></td>
<td><p>Indifférente</p></td>
<td><p>Vérification et récupération des certificats</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Service Edge d’accès Edge Server</p></td>
<td><p>Indifférente</p></td>
<td><p>Requête DNS sur TCP</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Service Edge d’accès Edge Server</p></td>
<td><p>Indifférente</p></td>
<td><p>Requête DNS via UDP</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 d’accès/SIP (TLS)</p></td>
<td><p>Indifférente</p></td>
<td><p>Service Edge d’accès Edge Server</p></td>
<td><p>Trafic SIP client à serveur pour l’accès des utilisateurs externes</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 d’accès/SIP (MTLS)</p></td>
<td><p>Indifférente</p></td>
<td><p>Service Edge d’accès Edge Server</p></td>
<td><p>Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/5061 d’accès/SIP (MTLS)</p></td>
<td><p>Service Edge d’accès Edge Server</p></td>
<td><p>Indifférente</p></td>
<td><p>Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</p></td>
</tr>
<tr class="even">
<td><p>PSOM (TLS)/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Service Edge de conférence Web Edge Server</p></td>
<td><p>Support de conférences Web</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59,999</p></td>
<td><p>Service Edge serveur Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>Requis pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59,999</p></td>
<td><p>Service Edge serveur Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50000-59,999</p></td>
<td><p>Indifférente</p></td>
<td><p>Service Edge serveur Edge A/V</p></td>
<td><p>Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50000-59,999</p></td>
<td><p>Indifférente</p></td>
<td><p>Service Edge serveur Edge A/V</p></td>
<td><p>Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Service Edge serveur Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>3478 en sortie est utilisé pour déterminer la version de Edge Server avec laquelle Lync Server communique et le trafic multimédia à partir d’un serveur Edge serveur à périphérie. Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que le déploiement de plusieurs pools Edge au sein d’une entreprise.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Indifférente</p></td>
<td><p>Service Edge serveur Edge A/V</p></td>
<td><p>STUN/activer la négociation des candidats via UDP/3478</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Service Edge serveur Edge A/V</p></td>
<td><p>STUN/activer la négociation des candidats via TCP/443</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Service Edge serveur Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>STUN/activer la négociation des candidats via TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a>Résumé du pare-feu pour une périphérie unique consolidée avec des adresses IP privées utilisant tar : interface interne

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
<td><p>Tout (peut être défini comme Standard Edition Server IP, adresse IP du serveur Standard Edition ou adresse IP du pool exécutant le service passerelle XMPP)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic XMPP sortant du service de passerelle XMPP exécuté sur le serveur frontal ou le pool frontal</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Tout (peut être défini comme directeur, adresse IP du pool de directeurs, adresse IP du serveur frontal ou adresse IP du pool frontal)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic SIP sortant (à partir du réalisateur, adresse IP du pool de réalisateurs, adresse IP du serveur frontal ou de la liste frontale) vers l’interface interne du serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Tout (peut être défini comme directeur, adresse IP du pool de directeurs, adresse IP du serveur frontal ou adresse IP du pool frontal)</p></td>
<td><p>Trafic SIP entrant (adresse IP du pool Directeur, serveur frontal ou adresse IP du pool frontal) à partir de l’interface interne du serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Tout (peut être défini comme adresse IP du serveur frontal ou chaque adresse IP du serveur frontal dans un pool frontal)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic de conférences Web à partir du serveur frontal ou de chaque serveur frontal, s’il se trouve dans un pool, vers l’interface interne du serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Tout (peut être défini en tant qu’adresse IP du serveur frontal ou adresse IP du pool frontal ou tout autre appareil de succursale survivant ou succursale Survivable à l’aide de ce serveur Edge)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>L’authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou de tout appareil de succursale ou de succursale survivant utilisant ce serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Chemin préféré pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Tout (peut être défini en tant qu’adresse IP du serveur frontal ou pool contenant la Banque centrale de gestion).</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Réplication des modifications du magasin de gestion central vers le serveur de périphérie</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a>Résumé du pare-feu pour la Fédération


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
<td><p>Service Edge d’accès Edge Server</p></td>
<td><p>Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 d’accès/SIP (MTLS)</p></td>
<td><p>Service Edge d’accès Edge Server</p></td>
<td><p>Partenaires de connectivité de messagerie instantanée publique</p></td>
<td><p>Pour la connectivité de messagerie instantanée fédérée et publique à l’aide du protocole SIP</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 d’accès/SIP (TLS)</p></td>
<td><p>Clients</p></td>
<td><p>Service Edge d’accès Edge Server</p></td>
<td><p>Trafic SIP client à serveur pour l’accès des utilisateurs externes</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59,999</p></td>
<td><p>Service Edge serveur Edge A/V</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Utilisé pour les sessions A/V avec Windows Live Messenger si la connectivité PIC (Public IM Connectivity) est configurée.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Service Edge serveur Edge A/V</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Service Edge serveur Edge A/V</p></td>
<td><p>Requis pour la connectivité de messagerie instantanée publique avec Windows Live Messenger</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a>Résumé du pare-feu pour le protocole extensible de messagerie et de présence


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
<td><p>Adresse IP de l’interface du service Edge d’accès Edge Server</p></td>
<td><p>Port de communication serveur à serveur standard pour XMPP. Autorise la communication au proxy de serveur Edge XMPP auprès des partenaires XMPP fédérés</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès Edge Server</p></td>
<td><p>Indifférente</p></td>
<td><p>Port de communication serveur à serveur standard pour XMPP. Autorise la communication du proxy de serveur Edge XMPP aux partenaires XMPP fédérés</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Indifférente</p></td>
<td><p>Chaque adresse IP de l’interface du serveur Edge interne</p></td>
<td><p>Trafic de XMPP interne depuis la passerelle XMPP du serveur frontal ou du pool frontal vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool de périphériques</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

