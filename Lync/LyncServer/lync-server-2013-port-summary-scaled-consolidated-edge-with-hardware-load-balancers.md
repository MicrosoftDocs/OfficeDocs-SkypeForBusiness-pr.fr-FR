---
title: Résumé des ports - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle
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
ms.openlocfilehash: 6260a4ad7f2717e0b4eb2446fc5b17671c3e45a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Résumé des ports - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-04-27_

La fonctionnalité Lync Server 2013, Edge Server décrite dans cette architecture de scénario est très similaire à celle implémentée dans Lync Server 2010. Le plus notable est le port **5269 sur entrée TCP** pour le protocole XMPP (extensible Messaging and Presence Protocol). Le serveur Lync Server 2013 déploie éventuellement un proxy XMPP sur le serveur Edge ou le pool de bords et sur le serveur de passerelle XMPP sur le serveur frontal ou le pool frontal.

Outre IPv4, le serveur Edge prend désormais en charge le protocole IPv6. Par souci de clarté, seul le protocole IPv4 est utilisé dans les scénarios.

**Contour consolidé mis à l’échelle à l’aide de l’équilibrage de charge matérielle**

![Ports et protocoles du réseau de périmètre du serveur Edge](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Ports et protocoles du réseau de périmètre du serveur Edge")

<div>

## <a name="port-and-protocol-details"></a>Détails sur les ports et protocoles

Il est recommandé d’ouvrir uniquement les ports requis pour la prise en charge des fonctionnalités pour lesquelles vous fournissez un accès externe.

Pour que l’accès à distance fonctionne pour tous les services Edge, il est obligatoire que le trafic SIP soit autorisé de manière bidirectionnelle, comme indiqué dans le schéma de trafic Edge entrant/sortant. Autrement dit, la messagerie SIP vers et à partir du service Edge d’accès intervient dans les fonctionnalités de messagerie instantanée, de présence, de conférence Web, audio/vidéo (A/V) et de Fédération.

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a>Résumé du pare-feu pour les bords consolidés mis à l’échelle : équilibrage de charge matérielle : interface externe-nœud 1 et nœud 2 (exemple)

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
<td><p>Accès/HTTP/TCP/80</p></td>
<td><p>Adresse IP publique du service Edge d’accès Edge Server</p></td>
<td><p>Indifférente</p></td>
<td><p>Vérification et récupération des certificats</p></td>
</tr>
<tr class="even">
<td><p>Access/DNS/TCP/53</p></td>
<td><p>Adresse IP publique du service Edge d’accès Edge Server</p></td>
<td><p>Indifférente</p></td>
<td><p>Requête DNS sur TCP</p></td>
</tr>
<tr class="odd">
<td><p>Access/DNS/UDP/53</p></td>
<td><p>Adresse IP publique du service Edge d’accès Edge Server</p></td>
<td><p>Indifférente</p></td>
<td><p>Requête DNS via UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59,999</p></td>
<td><p>Adresse IP du service Edge serveur Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>Requis pour la Fédération avec des partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59,999</p></td>
<td><p>Adresse IP publique du service Edge Server A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50000-59,999</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du service Edge Server A/V</p></td>
<td><p>Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50000-59,999</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du service Edge Server A/V</p></td>
<td><p>Requis uniquement pour la Fédération avec les partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Adresse IP publique du service Edge Server A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>3478 en sortie est utilisé pour déterminer la version de Edge Server avec laquelle Lync Server communique et le trafic multimédia à partir d’un serveur Edge serveur à périphérie. Requis pour la Fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que le déploiement de plusieurs pools Edge au sein d’une entreprise.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du service Edge Server A/V</p></td>
<td><p>STUN/activer la négociation des candidats via UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du service Edge Server A/V</p></td>
<td><p>STUN/activer la négociation des candidats via TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Adresse IP publique du service Edge Server A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>STUN/activer la négociation des candidats via TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a>Résumé du pare-feu pour les bords consolidés mis à l’échelle : charge matérielle

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
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Tout (peut être défini comme adresse serveur frontale ou adresse IP virtuelle de pool frontal exécutant le service passerelle XMPP)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic XMPP sortant du service de passerelle XMPP exécuté sur le serveur frontal ou le pool frontal</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Tout (peut être défini en tant que serveur principal serveur ou pool serveur serveur principal)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Réplication des modifications du magasin de gestion central vers le serveur de périphérie</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Tout (peut être défini en tant que adresse IP du directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic de conférences Web entre le déploiement interne et l’interface du serveur Edge interne</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Tout (peut être défini en tant que adresse IP du directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Chemin préféré pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Tout (peut être défini en tant que adresse IP du directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Pour le transfert de média A/V entre des utilisateurs internes et externes, une unité de branchement survivant ou un serveur de succursales survivant si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisé à l’aide de Lync Server Management Shell et des applets de commande de service de journalisation centralisées, de lignes de commande ClsController (ClsController. exe) ou d’agent (ClsAgent. exe) et de collection de journaux</p></td>
</tr>
</tbody>
</table>


Les équilibreurs de charge matérielle nécessitent des exigences spécifiques pour assurer la disponibilité et l’équilibrage de charge de Lync Server. La configuration requise est définie dans les tableaux et figures suivants. Les fournisseurs tiers pourront utiliser une terminologie différente pour les exigences définies ici. Il est nécessaire de mapper les exigences de Lync Server aux options et aux options de configuration fournies par le fournisseur du programme d’équilibrage de la charge matérielle.

Lorsque vous configurez des équilibreurs de charge matérielle, prenez en compte les éléments suivants :

  - La traduction d’adresses réseau source (SNAT) peut être configurée sur l’équilibrage de charge matérielle (HLB) pour le service Edge d’accès et le service Edge de conférence Web.

  - Les données SNAT ne peuvent pas être configurées sur le service Edge A/V : le service Edge A/V doit répondre avec l’adresse réelle du serveur (et non l’adresse IP virtuelle HLB) pour une traversée simple du protocole UDP sur NAT (STUN)/Traversal à l’aide d’un NAT relais (FDÉSACTIVEZ) pour fonctionner correctement
    
      - Si le client envoie une demande à l’HLB, la réponse doit être retirée du VIP HLB
    
      - Si le client envoie une demande à l’Edge, la réponse doit être retirée de l’adresse IP du serveur Edge.

  - Les adresses IP publiques sont utilisées sur chaque interface serveur et sur les adresses IP 2 du HLB et les exigences relatives à l’adresse IP publique sont de N + 1, car il existe une adresse IP publique pour chaque interface de serveur réel et une pour chaque VIP HLB. Lorsque vous avez 2 serveurs de périmètre dans le pool, il s’agit de 9 adresses IP publiques, 3 qui sont utilisées pour les VIP HLB et une pour chaque interface de serveur Edge (un total de six pour les serveurs).

  - Pour le service Edge d’accès et le service Edge de conférence Web (et l’utilisation de la traduction d’adresses réseau sur le HLB), le client contacte l’adresse VIP, l’adresse VIP remplace l’adresse IP source du client par sa propre adresse IP. L’interface du serveur adresse l’adresse d’expéditeur au VIP, l’adresse VIP modifie l’adresse source à partir de l’adresse IP de l’interface du serveur et envoie le paquet au client.

  - Pour le service Edge A/V, l’adresse VIP ne doit pas modifier l’adresse IP source, et l’adresse réelle du serveur est directement renvoyée au client : vous ne pouvez pas configurer le NAT sur le HLB pour le trafic AV
    
      - Si le client envoie une demande à l’adresse VIP de HLB, la réponse doit être retirée du VIP HLB
    
      - Si le client envoie une demande à l’adresse IP du serveur Edge, la réponse doit être retirée de l’adresse IP du serveur Edge.

  - Pour les AV, le pare-feu externe conserve l’adresse IP publique réelle du serveur pour tous les paquets.

  - Une fois établi, le client à la communication de service Edge A/V est destiné au serveur réel et non au HLB

  - Le bord interne des serveurs et clients internes doit être routé et des itinéraires persistants sont définis pour tous les réseaux internes qui hébergent des serveurs ou des clients.

  - Le protocole VIP du service Edge d’accès HLB agit comme passerelle par défaut pour chaque interface de serveur Edge.

<div>


> [!NOTE]
> Pour plus d’informations sur la planification et la fonctionnalité de NAT, voir <A href="lync-server-2013-hardware-load-balancer-requirements.md">Configuration requise pour l’équilibrage de charge matérielle pour Lync Server 2013</A>.



</div>

![Détails des protocoles et des ports du serveur Edge](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Détails des protocoles et des ports du serveur Edge")

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a>Paramètres de port externe requis pour les bords consolidés mis à l’échelle, équilibrage de charge matérielle : IPs virtuel d’interface externe

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
<td><p>XMPP/TCP/5269</p></td>
<td><p>Service proxy XMPP (adresse IP du partage avec service Edge d’accès)</p></td>
<td><p>Indifférente</p></td>
<td><p>Le service de proxy XMPP envoie le trafic aux contacts XMPP dans les fédérations de XMPP définies.</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/443 d’accès/SIP (TLS)</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse VIP publique du service Edge d’accès</p></td>
<td><p>Trafic SIP client à serveur pour l’accès des utilisateurs externes</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 d’accès/SIP (MTLS)</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse VIP publique du service Edge d’accès</p></td>
<td><p>Signalisation SIP, connectivité par messagerie instantanée privée et publique à l’aide du protocole SIP</p></td>
</tr>
<tr class="odd">
<td><p>/TCP/5061 d’accès/SIP (MTLS)</p></td>
<td><p>Adresse VIP publique du service Edge d’accès</p></td>
<td><p>Partenaire fédéré</p></td>
<td><p>Signalisation SIP, connectivité par messagerie instantanée privée et publique à l’aide du protocole SIP</p></td>
</tr>
<tr class="even">
<td><p>PSOM (TLS)/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse VIP publique du service Edge Conferencing Server Web</p></td>
<td><p>Support de conférences Web</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN, MSTURN/UDP/3478</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse VIP publique du service Edge Server A/V</p></td>
<td><p>STUN/activer la négociation des candidats via UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN, MSTURN/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse VIP publique du service Edge Server A/V</p></td>
<td><p>STUN/activer la négociation des candidats via TCP/443</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a>Résumé du pare-feu pour les bords consolidés mis à l’échelle, équilibrage de charge matérielle : IPs virtuel d’interface

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
<td><p>Tout (peut être défini en tant que directeur, adresse IP virtuelle du pool de réalisateurs, serveur frontal ou adresse IP virtuelle de pool frontal)</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>Trafic SIP sortant (à partir du réalisateur, adresse IP virtuelle du pool de directeurs, serveur frontal ou liste d’adresses IP virtuelles) vers l’adresse VIP de périphérie interne</p></td>
</tr>
<tr class="even">
<td><p>/TCP/5061 d’accès/SIP (MTLS)</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>Tout (peut être défini en tant que directeur, adresse IP virtuelle du pool de réalisateurs, serveur frontal ou adresse IP virtuelle de pool frontal)</p></td>
<td><p>Trafic SIP entrant (adresse IP virtuelle du pool de directeurs, serveur frontal ou liste d’adresses IP virtuelle) à partir de l’interface interne du serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Tout (peut être défini en tant qu’adresse IP du serveur frontal ou adresse IP du pool frontal ou tout autre appareil de succursale survivant ou succursale Survivable à l’aide de ce serveur Edge)</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>L’authentification des utilisateurs A/V (service d’authentification A/V) à partir du serveur frontal ou de l’adresse IP du pool frontal ou de tout appareil de succursale ou de succursale survivant utilisant ce serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>Chemin préféré pour le transfert de média A/V entre les utilisateurs internes et externes</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>Chemin de secours pour le transfert de média A/V entre les utilisateurs internes et externes si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interface VIP interne du serveur Edge</p></td>
<td><p>Indifférente</p></td>
<td><p>Chemin de secours pour le transfert de média A/V entre les utilisateurs internes et externes si la communication UDP ne peut pas être établie, le protocole TCP est utilisé pour le transfert de fichiers et le partage de bureau</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

