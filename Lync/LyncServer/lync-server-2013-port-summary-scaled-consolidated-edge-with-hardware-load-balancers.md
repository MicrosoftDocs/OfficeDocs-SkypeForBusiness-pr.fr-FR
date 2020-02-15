---
title: Résumé des ports-serveur Edge consolidé ajusté avec équilibreurs de charge matérielle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cad84208df5129b3a10c1e80aa28442ebcbd44
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Résumé des ports-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-04-27_

La fonctionnalité de serveur Edge de Lync Server 2013 décrite dans cette architecture de scénario est très semblable à celle qui a été implémentée dans Lync Server 2010. L’ajout le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol). Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.

Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6. Par souci de clarté, seul IPv4 est utilisé dans les scénarios.

**Serveur Edge consolidé ajusté à l’aide de l’équilibrage de charge matérielle**

![Protocoles et ports du réseau de périmètre du serveur Edge](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Protocoles et ports du réseau de périmètre du serveur Edge")

<div>

## <a name="port-and-protocol-details"></a>Détails des ports et protocoles

Il est recommandé d’ouvrir uniquement les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous fournissez un accès externe.

Pour que l’accès à distance fonctionne pour tout service Edge, il est obligatoire d’autoriser un flux bidirectionnel du trafic SIP comme illustré dans la figure Trafic Edge entrant/sortant. Autrement dit, la messagerie SIP vers et depuis le service Edge d’accès est impliquée dans la messagerie instantanée, la présence, la conférence Web, l’audio/vidéo (A/V) et la Fédération.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>Résumé du pare-feu pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : interface externe – nœud 1 et nœud 2 (exemple)

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
<td><p>Accès/HTTP/TCP/80</p></td>
<td><p>Adresse IP publique du service Edge d’accès au serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Vérification et extraction de la liste de révocation de certificats</p></td>
</tr>
<tr class="even">
<td><p>Accès/DNS/TCP/53</p></td>
<td><p>Adresse IP publique du service Edge d’accès au serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Requête DNS sur TCP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/DNS/UDP/53</p></td>
<td><p>Adresse IP publique du service Edge d’accès au serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Requête DNS sur UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-000-59 999</p></td>
<td><p>Adresse IP du service Edge A/V du serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Obligatoire pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-000-59 999</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-000-59 999</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-000-59 999</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>Requis uniquement pour la Fédération avec des partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic multimédia à partir du serveur Edge de serveur à serveur Edge. Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que si plusieurs pools Edge sont déployés au sein d’une entreprise.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>STUN/activer la négociation des candidats via UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>STUN/activer la négociation des candidats sur TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>STUN/activer la négociation des candidats sur TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>Résumé du pare-feu pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : nœud d’interface interne 1 et nœud 2

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Any (peut être défini en tant qu’adresse de serveur frontal ou adresse IP virtuelle du pool frontal exécutant le service de passerelle XMPP)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic XMPP sortant du service de passerelle XMPP exécuté sur un serveur frontal ou un pool frontal</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Any (peut être défini comme le pool ou l’adresse IP du serveur frontal qui contient le magasin central de gestion)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Any (peut être défini en tant que IP de directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic de conférence Web depuis le déploiement interne vers l’interface de serveur Edge interne</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Any (peut être défini en tant que IP de directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Chemin préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes, le Survivable Branch Appliance ou le serveur Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Any (peut être défini en tant que IP de directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou le serveur Survivable Branch Server si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée à l’aide de Lync Server Management Shell et des applets de commande du service de journalisation centralisée, de la ligne de commande ClsController (ClsController. exe) ou de la collection de journaux de l’agent (ClsAgent. exe)</p></td>
</tr>
</tbody>
</table>


Les programmes d’équilibrage de la charge matérielle ont des exigences spécifiques lorsqu’ils sont déployés pour assurer la disponibilité et l’équilibrage de la charge pour Lync Server. Les conditions requises sont définies dans les tableaux et les figures suivants. Les fournisseurs tiers peuvent utiliser une terminologie différente pour les exigences définies ici. Il sera nécessaire de mapper les exigences de Lync Server aux options de configuration et aux fonctionnalités fournies par votre fournisseur d’équilibreur de charge matériel.

Lors de la configuration des programmes d’équilibrage de la charge matérielle, tenez compte des exigences suivantes :

  - La traduction d’adresses réseau source (SNAT) peut être configurée sur le programme d’équilibrage de la charge matérielle (charge matérielle) pour le service Edge d’accès et le service Edge de conférence Web

  - SNAT ne peut pas être configuré sur le service Edge A/V : le service Edge A/V doit répondre avec l’adresse de serveur réelle, et non avec l’adresse IP virtuelle charge matérielle, pour une simple traversée des/Traversal UDP sur NAT (STUN) à l’aide de l’interface NAT relais (TURN)/Federation TURN (FTURN) pour fonctionner correctement
    
      - Si le client envoie une demande au charge matérielle, la réponse doit être renvoyée à partir de l’adresse IP virtuelle charge matérielle
    
      - Si le client envoie une demande au serveur Edge, la réponse doit être renvoyée à partir de l’adresse IP du serveur Edge.

  - Les adresses IP publiques sont utilisées sur chaque interface de serveur et sur les VIP du charge matérielle, et les exigences de votre adresse IP publique sont N + 1, où il y a une adresse IP publique pour chaque interface de serveur réel et une pour chaque VIP charge matérielle. Lorsque vous avez 2 serveurs Edge dans le pool, il en résulte 9 adresses IP publiques, où 3 sont utilisées pour les VIP charge matérielle et une pour chaque interface de serveur Edge (un total de six pour les serveurs)

  - Pour le service Edge d’accès et le service Edge de conférence Web (et l’utilisation de la fonctionnalité NAT sur le charge matérielle), le client contacte l’adresse IP virtuelle, l’adresse IP virtuelle modifie l’adresse IP source du client vers sa propre adresse IP. L’interface serveur adresse l’adresse de retour au VIP, l’adresse IP virtuelle modifie l’adresse source à partir de l’adresse IP de l’interface du serveur et envoie le paquet au client.

  - Pour le service Edge A/V, l’adresse IP virtuelle ne doit pas modifier l’adresse IP source et l’adresse du serveur réel est directement renvoyée au client : vous ne pouvez pas configurer la traduction d’adresses réseau (NAT) sur le charge matérielle pour le trafic AV
    
      - Si le client envoie une demande au VIP charge matérielle, la réponse doit être renvoyée à partir de l’adresse IP virtuelle charge matérielle
    
      - Si le client envoie une demande à l’adresse IP Edge, la réponse doit être renvoyée à partir de l’adresse IP du serveur Edge.

  - Pour les AV, le pare-feu externe conservera l’adresse IP publique réelle du serveur pour tous les paquets.

  - Une fois la communication de service Edge A/V établie, le client vers le serveur réel et non le charge matérielle

  - Le périmètre interne vers les serveurs internes et les clients doit être routé, et les itinéraires persistants sont définis pour tous les réseaux internes hébergeant des serveurs ou des clients.

  - Le VIP du service Edge d’accès charge matérielle agira comme passerelle par défaut pour chaque interface de serveur Edge

<div>


> [!NOTE]
> Pour plus d’informations sur la planification et les fonctionnalités de NAT, reportez-vous à la rubrique <A href="lync-server-2013-hardware-load-balancer-requirements.md">Configuration requise pour l’équilibreur de charge matérielle pour Lync Server 2013</A>.



</div>

![Détails des protocoles et ports du serveur Edge](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Détails des protocoles et ports du serveur Edge")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>Paramètres de ports externes requis pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : adresses IP virtuelles d’interface externe

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>Service proxy XMPP (partage une adresse IP avec le service Edge d’accès)</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Le service proxy XMPP envoie le trafic vers les contacts XMPP dans les fédérations XMPP définies</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP (TLS)/TCP/443</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge d’accès</p></td>
<td><p>Trafic SIP client vers serveur pour l’accès des utilisateurs externes</p></td>
</tr>
<tr class="even">
<td><p>Accès/SIP (MTLS)/TCP/5061</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge d’accès</p></td>
<td><p>Signalisation SIP, connectivité de messagerie instantanée publique et fédérée à l’aide de SIP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP (MTLS)/TCP/5061</p></td>
<td><p>Adresse IP publique du service Edge d’accès</p></td>
<td><p>Partenaire fédéré</p></td>
<td><p>Signalisation SIP, connectivité de messagerie instantanée publique et fédérée à l’aide de SIP</p></td>
</tr>
<tr class="even">
<td><p>Conférence Web/PSOM (TLS)/TCP/443</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge de conférence Web du serveur Edge</p></td>
<td><p>Support de conférence Web</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>STUN/activer la négociation des candidats via UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Adresse IP publique du service Edge A/V du serveur Edge</p></td>
<td><p>STUN/activer la négociation des candidats sur TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>Résumé du pare-feu pour le serveur Edge consolidé ajusté, avec charge matérielle équilibrée : adresses IP virtuelles de l’interface interne

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
<td><p>Any (peut être défini en tant que directeur, adresse IP virtuelle du pool Directeur, serveur frontal ou adresse IP virtuelle du pool frontal)</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>Trafic SIP sortant (depuis le directeur, l’adresse IP virtuelle du pool Directeur, le serveur frontal ou l’adresse IP virtuelle du pool frontal) vers le protocole VIP interne</p></td>
</tr>
<tr class="even">
<td><p>Accès/SIP (MTLS)/TCP/5061</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>Any (peut être défini en tant que directeur, adresse IP virtuelle du pool Directeur, serveur frontal ou adresse IP virtuelle du pool frontal)</p></td>
<td><p>Trafic SIP entrant (vers le directeur, adresse IP virtuelle du pool Directeur, serveur frontal ou adresse IP virtuelle du pool frontal) à partir de l’interface interne du serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Any (peut être défini comme adresse IP du serveur frontal ou adresse IP du pool frontal ou n’importe quel serveur Survivable Branch Server ou Survivable Branch Server à l’aide de ce serveur Edge)</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>Authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou d’un serveur Survivable Branch Appliance ou d’un serveur Survivable Branch à l’aide de ce serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>Chemin d’accès préféré pour le transfert multimédia A/V entre les utilisateurs internes et externes</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Chemin de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

