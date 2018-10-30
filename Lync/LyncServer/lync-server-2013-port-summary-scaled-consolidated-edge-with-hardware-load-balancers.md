---
title: "Lync Server 2013 : Résumé des ports - SE cons. màé avec des éq. de ch. Mat."
TOCTitle: Résumé des ports - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398739(v=OCS.15)
ms:contentKeyID: 49298069
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des ports - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-04-27_

La fonctionnalité de serveur Edge Lync Server 2013 décrite dans cette architecture de scénario est très similaire à celle implémentée dans Lync Server 2010. L’ajout le plus significatif est l’entrée de port  **5269 sur TCP** pour le protocole XMPP (Extensible Messaging and Presence Protocol). Lync Server 2013 peut également déployer un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge, et le serveur de passerelle XMPP sur le serveur frontal ou le pool de serveurs frontaux.

Outre le protocole IPv4, le serveur Edge prend désormais en charge le protocole IPv6. Pour plus de clarté, seul le protocole IPv4 est utilisé dans les scénarios.

**Topologie Edge consolidée mise à l’échelle avec équilibrage de la charge matérielle**

![Ports et protocoles du réseau de périmètre du serveur Edge](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Ports et protocoles du réseau de périmètre du serveur Edge")

## Détails sur les ports et protocoles

Il est conseillé de n’ouvrir que les ports requis pour prendre en charge la fonctionnalité pour laquelle vous fournissez l’accès externe.

Pour que l’accès à distance fonctionne pour n’importe quel service Edge, il est obligatoire que le trafic SIP puisse circuler de manière bidirectionnelle comme le montre la figure Topologie Edge consolidée mise à l’échelle (avec charge matérielle équilibrée). En d’autres termes, la messagerie SIP de et vers le service Edge d’accès intervient dans la messagerie instantanée, la présence, la conférence web, l’audio et la vidéo (A/V) ainsi que la fédération.

### Résumé du pare-feu pour le serveur Edge consolidé ajusté avec équilibrage de charge matérielle : interface externe – Nœud 1 et nœud 2 (Exemple)

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
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Accès/HTTP/TCP/80</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Vérification et extraction de la liste de révocation de certificats</p></td>
</tr>
<tr class="even">
<td><p>Accès/DNS/TCP/53</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Requête DNS sur TCP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/DNS/UDP/53</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Requête DNS sur UDP</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50 000-59 999</p></td>
<td><p>Adresse IP du service Edge A/V du serveur Edge</p></td>
<td><p>Indifférente</p></td>
<td><p>Obligatoire pour la fédération avec les partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50 000-59 999</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>Requis uniquement pour la fédération avec des partenaires exécutant Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50 000-59 999</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Requis uniquement pour la fédération avec des partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/UDP/50 000-59 999</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Requis uniquement pour la fédération avec des partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>Le port  3478 est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique, ainsi que pour le trafic multimédia du serveur Edge au serveur Edge. Obligatoire en cas de fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que lorsque plusieurs pools de serveurs Edge sont déployés dans une société.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Négociation STUN/TURN des candidats sur UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Négociation STUN/TURN des candidats sur TCP/443</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>Négociation STUN/TURN des candidats sur TCP/443</p></td>
</tr>
</tbody>
</table>


### Résumé du pare-feu pour le serveur Edge consolidé ajusté avec équilibrage de charge matérielle : interface interne – Nœud 1 et nœud 2 (Exemple)

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
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Indifférente (peut être définie en tant qu’adresse IP de serveur frontal ou adresse IP virtuelle du pool de serveurs frontauxexécutant le service de passerelle XMPP)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic XMPP sortant depuis le service de passerelle XMPP exécuté sur le serveur frontal ou le pool de serveurs frontaux</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Indifférent (définissable en tant qu’adresse IP du serveur serveur frontal ou pool qui héberge le magasin central de gestion)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Indifférente (peut être définie en tant qu’adresse IP du directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic de conférence web depuis le déploiement interne vers l’interface du serveur Edge interne</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Indifférente (peut être définie en tant qu’adresse IP du directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Chemin d’accès préféré pour le transfert multimédia A/V entre utilisateurs internes et externes, Survivable Branch Appliance ou serveur Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Indifférente (peut être définie en tant qu’adresse IP du directeur, adresse IP du serveur frontal ou adresse IP virtuelle du pool)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Chemin d’accès de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou serveur Survivable Branch Server. En cas d’impossibilité d’établir la communication UDP, le protocole TCP est utilisé pour le transfert de fichiers et le partage du bureau</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée avec applets de commande Lync Server Management Shell et service de journalisation centralisée, commandes de ligne de commande ClsController (ClsController.exe) ou de l’agent (ClsAgent.exe) et collecte des journaux</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée avec applets de commande Lync Server Management Shell et service de journalisation centralisée, commandes de ligne de commande ClsController (ClsController.exe) ou de l’agent (ClsAgent.exe) et collecte des journaux</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée avec applets de commande Lync Server Management Shell et service de journalisation centralisée, commandes de ligne de commande ClsController (ClsController.exe) ou de l’agent (ClsAgent.exe) et collecte des journaux</p></td>
</tr>
</tbody>
</table>


Les équilibreurs de charge matérielle ont des exigences spécifiques lorsqu’ils sont déployés pour fournit la disponibilité et l’équilibrage de charge pour Lync Server. Ces exigences sont définies dans la figure et les tableaux ci-dessous. Les fabricants tiers peuvent utiliser une autre terminologie pour les exigences décrites ici. Il sera nécessaire de faire correspondre ces exigences de Lync Server aux fonctionnalités et options de configuration fournies par le fabricant de l’équilibreur de charge matérielle.

Lors de la configuration des équilibreurs de charge matérielle, prenez en compte les éléments requis suivants :

  - La conversion d’adresses réseau source (SNAT) peut être configurée sur l’équilibreur de charge matérielle (HLB) pour le service Edge d’accès et le service Edge de conférence web

  - SNAT ne peut pas être configuré sur le service Edge A/V– le service Edge A/V doit répondre avec l’adresse serveur réelle, et non l’adresse IP virtuel (VIP) du HLB, pour que la traversée UDP over NAT (STUN)/traversée avec NAT relais (TURN)/TURN fédération (FTURN) fonctionnent correctement

  - Les adresses IP publiques sont utilisées sur chaque interface serveur et sur les adresses IP virtuelles (VIP) du HLB, et les exigences en matière d’adresse IP publique sont N+1 (une adresse IP publique pour chaque interface serveur réelle et une pour chaque VIP HLB). Quand vous avez 2 serveurs Edge dans le pool, cela donne 9 adresses IP publiques, 3 étant utilisées pour les VIP HLB et une pour chaque interface de serveur Edge (soit un total de six pour les serveurs)

  - Pour le service Edge d’accès et le service Edge de conférence web, (avec NAT sur le HLB) le client contact l’adresse IP virtuelle, L’adresse IP virtuelle transforme l’adresse IP source à partir du client en sa propre adresse IP. L’interface serveur envoie l’adresse de retour à l’adresse IP virtuelle, l’adresse IP virtuelle change l’adresse source de l’adresse IP de l’interface serveur et envoie le paquet au client

  - Pour le service Edge A/V, l’adresse VIP NE doit PAS changer l’adresse IP source, et l’adresse serveur réelle est renvoyée directement au client, vous ne pouvez pas configurer NAT sur le HLB pour du trafic AV

  - Pour AV, le pare-feu externe conserver l’adresse IP publique réelle pour tous les paquets

  - Une fois établie, la communication du client vers le service Edge A/V est le serveur réelle et non le HLB

  - Le serveur Edge interne vers les serveurs internes et les clients doit être routé, et des itinéraires persistants sont définis pour tous les réseaux internes qui hébergent des serveurs ou des clients

  - L’adresse VIP service Edge d’accès du HLB joue le rôle de passerelle par défaut pour chaque interface serveur Edge

![Détails des protocoles et des ports du serveur Edge](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Détails des protocoles et des ports du serveur Edge")

### Paramètres de port externes requis pour le serveur Edge consolidé ajusté avec équilibrage de charge matérielle : IP virtuelles d’interface externe

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
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Indifférente</p></td>
<td><p>Service proxy XMPP (adresse IP partagée avec le service Edge d’accès)</p></td>
<td><p>Le service proxy XMPP accepte le trafic en provenance de contacts XMPP dans les fédérations XMPP définies.</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Service proxy XMPP (adresse IP partagée avec le service Edge d’accès)</p></td>
<td><p>Indifférente</p></td>
<td><p>Le service proxy XMPP envoie le trafic vers les contacts XMPP dans les fédérations XMPP définies</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP(TLS)/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse VIP publique service Edge d’accès</p></td>
<td><p>Trafic SIP client vers serveur pour l’accès des utilisateurs externes</p></td>
</tr>
<tr class="even">
<td><p>Accès/SIP(MTLS)/TCP/5061</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse VIP publique service Edge d’accès</p></td>
<td><p>Signalisation SIP, connectivité fédérée et PIC avec SIP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP(MTLS)/TCP/5061</p></td>
<td><p>Adresse VIP publique service Edge d’accès</p></td>
<td><p>Partenaire fédéré</p></td>
<td><p>Signalisation SIP, connectivité fédérée et PIC avec SIP</p></td>
</tr>
<tr class="even">
<td><p>Conférence web/PSOM(TLS)/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP virtuelle publique du serveur Edge du service Edge de conférence web</p></td>
<td><p>Média de conférence web</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP virtuelle publique du service Edge A/V du serveur Edge</p></td>
<td><p>Négociation STUN/TURN des candidats sur UDP/3478</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP virtuelle publique du service Edge A/V du serveur Edge</p></td>
<td><p>Négociation STUN/TURN des candidats sur TCP/443</p></td>
</tr>
</tbody>
</table>


### Résumé du pare-feu pour le serveur Edge consolidé ajusté avec équilibrage de charge matérielle : IP virtuelles d’interface interne

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
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Accès/SIP(MTLS)/TCP/5061</p></td>
<td><p>Indifférente (définissable en tant qu’adresse IP virtuelle de pool de directeurs, directeur, serveur frontal ou pool de serveurs frontaux)</p></td>
<td><p>Interface d’adresse virtuelle interne du serveur Edge</p></td>
<td><p>Trafic SIP sortant (en provenance de l’adresse IP virtuelle de pool de directeurs, directeur, serveur frontal ou pool de serveurs frontaux vers l’adresse IP virtuelle Edge interne</p></td>
</tr>
<tr class="even">
<td><p>Accès/SIP(MTLS)/TCP/5061</p></td>
<td><p>Interface d’adresse virtuelle interne du serveur Edge</p></td>
<td><p>Indifférente (définissable en tant qu’adresse IP virtuelle de pool de directeurs, directeur, serveur frontal ou pool de serveurs frontaux)</p></td>
<td><p>Trafic SIP entrant (vers l’adresse IP virtuelle de pool de directeurs, directeur, serveur frontal ou pool de serveurs frontaux en provenance de l’interface interne du serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Indifférente (peut être définie en tant qu’adresse IP du serveur frontal ou du pool de serveurs frontaux, ou tout Survivable Branch Appliance ou serveur Survivable Branch Server utilisant ce serveur Edge)</p></td>
<td><p>Interface d’adresse virtuelle interne du serveur Edge</p></td>
<td><p>Authentification des utilisateurs A/V (service d’authentification A/V) en provenance de l’adresse IP du serveur frontal ou pool de serveurs frontaux ou tout Survivable Branch Appliance ou serveur Survivable Branch Server utilisant ce serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface d’adresse virtuelle interne du serveur Edge</p></td>
<td><p>Chemin préféré pour le transfert multimédia A/V entre utilisateurs internes et externes</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface d’adresse virtuelle interne du serveur Edge</p></td>
<td><p>Chemin de secours pour le transfert multimédia A/V entre utilisateurs internes et externes ; en cas d’impossibilité d’établir la communication UDP, utilisation du protocole TCP pour le transfert de fichiers et le partage de Bureau</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Interface d’adresse virtuelle interne du serveur Edge</p></td>
<td><p>Indifférente</p></td>
<td><p>Chemin de secours pour le transfert multimédia A/V entre utilisateurs internes et externes ; en cas d’impossibilité d’établir la communication UDP, utilisation du protocole TCP pour le transfert de fichiers et le partage de Bureau</p></td>
</tr>
</tbody>
</table>

