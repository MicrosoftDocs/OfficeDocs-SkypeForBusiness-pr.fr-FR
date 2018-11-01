---
title: "LS 2013 : Rés. des ports - SE consol. màé, éq. de ch. DNS avec des ad. IP pub."
TOCTitle: Résumé des ports - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205394(v=OCS.15)
ms:contentKeyID: 49299370
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des ports - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La fonctionnalité de serveur Edge Lync Server 2013 décrite dans cette architecture de scénario est très similaire à celle implémentée dans Lync Server 2010. L’ajout le plus significatif est l’entrée de port  **5269 sur TCP** pour le protocole XMPP (Extensible Messaging and Presence Protocol). Lync Server 2013 peut également déployer un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge, et le serveur de passerelle XMPP sur le serveur frontal ou le pool de serveurs frontaux.

Outre le protocole IPv4, le serveur Edge prend désormais en charge le protocole IPv6. Pour plus de clarté, seul le protocole IPv4 est utilisé dans les scénarios.

**Réseau de périmètre d’entreprise pour la l’Edge consolidé mis à l’échelle avec équilibrage de charge DNS via des adresses IP publiques**

![Serveur Edge consolidé mis à l’échelle](images/Gg412756.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "Serveur Edge consolidé mis à l’échelle")

## Détails sur les ports et protocoles

Il est conseillé de n’ouvrir que les ports requis pour prendre en charge la fonctionnalité pour laquelle vous fournissez l’accès externe.

Pour que l’accès à distance fonctionne pour tous les services Edge, il est obligatoire que d’autoriser un flux bidirectionnel du trafic SIP, comme illustré dans la figure Trafic Edge entrant/sortant. Autrement dit, la messagerie SIP entrant et sortant du service Edge d’accès est impliquée dans la messagerie instantanée (IM), la présence, les conférences web, l’audio, la vidéo et la fédération.

### Résumé du pare-feu pour l’Edge consolidé mis à l’échelle avec équilibrage de charge DNS via des adresses IP publiques : Interface externe –  Nœud 1 et nœud 2 (exemple)

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
<td><p>Accès/HTTP/TCP/80</p></td>
<td><p>Adresse IP publique du serveur Edge  du service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Vérification et extraction de la liste de révocation de certificats</p></td>
</tr>
<tr class="odd">
<td><p>Accès/DNS/TCP/53</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Requête DNS sur TCP</p></td>
</tr>
<tr class="even">
<td><p>Accès/DNS/UDP/53</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Requête DNS sur UDP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP(TLS)/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge d’accès</p></td>
<td><p>Trafic SIP client vers serveur pour l’accès des utilisateurs externes</p></td>
</tr>
<tr class="even">
<td><p>Accès/SIP(MTLS)/TCP/5061</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du serveur Edge  du service Edge d’accès</p></td>
<td><p>Pour la connectivité fédérée et PIC utilisant SIP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP(MTLS)/TCP/5061</p></td>
<td><p>Adresse IP publique du serveur Edge  du service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Pour la connectivité fédérée et PIC utilisant SIP</p></td>
</tr>
<tr class="even">
<td><p>Conférence web/PSOM(TLS)TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge de conférence web</p></td>
<td><p>Média de conférence web</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50 000-59 999</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>Obligatoire pour la fédération avec les partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50 000-59 999</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>Requis uniquement pour la fédération avec des partenaires exécutant Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50 000-59 999</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Requis uniquement pour la fédération avec des partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50 000-59 999</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Requis uniquement pour la fédération avec des partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Indifférente</p></td>
<td><p>Le port  3478 est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique, ainsi que pour le trafic multimédia du serveur Edge au serveur Edge. Obligatoire en cas de fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, ainsi que lorsque plusieurs pools de serveurs Edge sont déployés dans une société.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Négociation STUN/TURN des candidats sur UDP/3478</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP publique du serveur Edge du service Edge A/V</p></td>
<td><p>Négociation STUN/TURN des candidats sur TCP/443</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Service Edge A/V du serveur Edge</p></td>
<td><p>Indifférente</p></td>
<td><p>Négociation STUN/TURN des candidats sur TCP/443</p></td>
</tr>
</tbody>
</table>


### Résumé du pare-feu pour l’Edge consolidé mis à l’échelle avec équilibrage de charge DNS via des adresses IP publiques : Interface interne –  Nœud 1 et Nœud 2 (exemple)

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
<td><p>Indifférente (peut être définie en tant qu’adresse IP de serveur frontal ou adresse IP du pool de serveurs frontauxexécutant le service de passerelle XMPP)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic XMPP sortant depuis le service de passerelle XMPP exécuté sur le serveur frontal ou le pool de serveurs frontaux</p></td>
</tr>
<tr class="even">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Indifférente (définissable en tant qu’adresse IP de pool de directeurs, directeur, serveur frontal ou pool de serveurs frontaux)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic SIP sortant (en provenance de l’adresse IP de pool de directeurs, directeur, serveur frontal ou pool de serveurs frontaux vers l’interface interne du serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5061</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Indifférente (définissable en tant qu’adresse IP de pool de directeurs, directeur, serveur frontal ou pool de serveurs frontaux)</p></td>
<td><p>Trafic SIP entrant (vers l’adresse IP de pool de directeurs, directeur, serveur frontal ou pool de serveurs frontaux en provenance de l’interface interne du serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>PSOM/MTLS/TCP/8057</p></td>
<td><p>Indifférente (définissable en tant qu’adresse IP de serveur frontal ou chaque adresse IP de serveur frontal dans un pool de serveurs frontaux)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Trafic de conférence web en provenance du serveur frontal ou de chaque serveur frontal d’un pool, vers l’interface interne du serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>SIP/MTLS/TCP/5062</p></td>
<td><p>Indifférente (peut être définie en tant qu’adresse IP du serveur frontal ou du pool de serveurs frontaux, ou tout Survivable Branch Appliance ou serveur Survivable Branch Server utilisant ce serveur Edge)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Authentification des utilisateurs A/V (service d’authentification A/V) en provenance de l’adresse IP du serveur frontal ou pool de serveurs frontaux ou tout Survivable Branch Appliance ou serveur Survivable Branch Server utilisant ce serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>STUN/MSTURN/UDP/3478</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Chemin d’accès préféré pour le transfert multimédia A/V entre utilisateurs internes et externes, Survivable Branch Appliance ou serveur Survivable Branch Server</p></td>
</tr>
<tr class="odd">
<td><p>STUN/MSTURN/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Chemin d’accès de secours pour le transfert multimédia A/V entre les utilisateurs internes et externes, Survivable Branch Appliance ou serveur Survivable Branch Server. En cas d’impossibilité d’établir la communication UDP, le protocole TCP est utilisé pour le transfert de fichiers et le partage du bureau</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Indifférente (définissable en tant qu’adresse IP du serveur frontal ou pool qui héberge le magasin central de gestion)</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Réplication des modifications depuis le magasin central de gestion vers le serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50001</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée avec applets de commande Lync Server Management Shell et service de journalisation centralisée, commandes de ligne de commande ClsController (ClsController.exe) ou de l’agent (ClsAgent.exe) et collecte des journaux</p></td>
</tr>
<tr class="even">
<td><p>MTLS/TCP/50002</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée avec applets de commande Lync Server Management Shell et service de journalisation centralisée, commandes de ligne de commande ClsController (ClsController.exe) ou de l’agent (ClsAgent.exe) et collecte des journaux</p></td>
</tr>
<tr class="odd">
<td><p>MTLS/TCP/50003</p></td>
<td><p>Indifférente</p></td>
<td><p>Interface interne du serveur Edge</p></td>
<td><p>Contrôleur de service de journalisation centralisée avec applets de commande Lync Server Management Shell et service de journalisation centralisée, commandes de ligne de commande ClsController (ClsController.exe) ou de l’agent (ClsAgent.exe) et collecte des journaux</p></td>
</tr>
</tbody>
</table>


## Résumé du pare-feu pour la fédération


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
<td><p>Adresse IP publique du service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Pour la connectivité fédérée et PIC utilisant SIP</p></td>
</tr>
</tbody>
</table>


## Résumé du pare-feu – Messagerie instantanée publique


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
<td><p>Partenaires PIC</p></td>
<td><p>serveur Edge service Edge d’accès</p></td>
<td><p>Pour la connectivité fédérée et PIC utilisant SIP</p></td>
</tr>
<tr class="even">
<td><p>Accès/SIP(MTLS)/TCP/5061</p></td>
<td><p>serveur Edge service Edge d’accès</p></td>
<td><p>Partenaires PIC</p></td>
<td><p>Pour la connectivité fédérée et PIC utilisant SIP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP(TLS)/TCP/443</p></td>
<td><p>Clients</p></td>
<td><p>serveur Edge service Edge d’accès</p></td>
<td><p>Trafic SIP client vers serveur pour l’accès des utilisateurs externes</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50 000-59 999</p></td>
<td><p>service Edge A/V du serveur Edge</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Utilisés pour les sessions A/V avec Windows Live Messenger si la connectivité de messagerie instantanée est configurée.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>service Edge A/V du serveur Edge</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Requis pour la connectivité PIC avec Windows Live Messenger</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>service Edge A/V du serveur Edge</p></td>
<td><p>Requis pour la connectivité PIC avec Windows Live Messenger</p></td>
</tr>
</tbody>
</table>


## Résumé du pare-feu pour XMPP (Extensible Messaging and Presence Protocol)


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
<td><p>XMPP/TCP/5269</p></td>
<td><p>Indifférente</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès du serveur Edge</p></td>
<td><p>Port de communication standard de serveur à serveur pour XMPP. Autorise la communication vers le proxy XMPP du serveur Edge depuis les partenaires XMPP fédérés.</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès du serveur Edge</p></td>
<td><p>Indifférente</p></td>
<td><p>Port de communication standard de serveur à serveur pour XMPP. Autorise la communication depuis le proxy XMPP du serveur Edge vers les partenaires XMPP fédérés.</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/TCP/23456</p></td>
<td><p>Indifférente</p></td>
<td><p>Chaque adresse IP d’interface interne du serveur Edge</p></td>
<td><p>Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool de serveurs frontaux vers l’adresse IP interne du serveur Edge ou l’adresse IP interne de chaque membre du pool de serveurs Edge</p></td>
</tr>
</tbody>
</table>

