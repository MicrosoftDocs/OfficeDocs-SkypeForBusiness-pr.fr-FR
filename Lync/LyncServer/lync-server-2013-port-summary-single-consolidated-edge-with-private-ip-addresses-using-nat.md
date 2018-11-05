---
title: "LS 2013 : Résumé ports - SE unique cons. avec ad. IP pr. avec conv. ad. rés."
TOCTitle: Résumé des ports - Serveur Edge unique consolidé avec adresses IP privées avecla conversion d’adresses réseau
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425891(v=OCS.15)
ms:contentKeyID: 49296950
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des ports - Serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La fonctionnalité de serveur EdgeLync Server 2013 décrite dans cette architecture de scénario est très similaire à celle implémentée dans Lync Server 2010. L’ajout le plus significatif est l’entrée de port  **5269 sur TCP** pour le protocole XMPP (Extensible Messaging and Presence Protocol). Lync Server 2013 peut aussi déployer un proxy XMPP sur le serveur Edge ou le pool de serveurs Edge et le serveur de passerelle XMPP sur le serveur frontal ou le pool de serveurs frontaux.

Outre le protocole IPv4, le serveur Edge prend désormais en charge le protocole IPv6. Pour plus de clarté, seul le protocole IPv4 est utilisé dans les scénarios.

**Périmètre de réseau pour un serveur Edge consolidé unique avec un adressage IP privé utilisant NAT**

![Serveur Edge consolidé unique](images/JJ204756.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "Serveur Edge consolidé unique")

## Détails sur les ports et protocoles

Nous vous recommandons de n’ouvrir que les ports nécessaires à la prise en charge de la fonctionnalité pour laquelle vous autorisez l’accès externe.

Pour que l’accès à distance fonctionne pour tout service Edge, il est obligatoire d’autoriser un flux bidirectionnel du trafic SIP comme illustré dans la figure Trafic Edge entrant/sortant. En d’autres termes, la messagerie SIP à destination et en provenance du service Edge d’accès intervient dans la messagerie instantanée, la présence, la conférence web, l’audio et la vidéo (A/V), ainsi que la fédération.

### Résumé de la configuration de pare-feu requise pour la topologie Edge unique consolidée avec des adresses IP privées utilisant NAT : interface externe

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
<td><p>serveur Edge service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Vérification et extraction de la liste de révocation de certificats</p></td>
</tr>
<tr class="odd">
<td><p>Accès/DNS/TCP/53</p></td>
<td><p>serveur Edge service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Requête DNS sur TCP</p></td>
</tr>
<tr class="even">
<td><p>Accès/DNS/UDP/53</p></td>
<td><p>serveur Edge service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Requête DNS sur UDP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP(TLS)/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>serveur Edge service Edge d’accès</p></td>
<td><p>Trafic SIP client vers serveur pour l’accès des utilisateurs externes</p></td>
</tr>
<tr class="even">
<td><p>Accès/SIP(MTLS)/TCP/5061</p></td>
<td><p>Indifférente</p></td>
<td><p>serveur Edge service Edge d’accès</p></td>
<td><p>Pour la connectivité fédérée et PIC utilisant SIP</p></td>
</tr>
<tr class="odd">
<td><p>Accès/SIP(MTLS)/TCP/5061</p></td>
<td><p>serveur Edge service Edge d’accès</p></td>
<td><p>Indifférente</p></td>
<td><p>Pour la connectivité fédérée et PIC utilisant SIP</p></td>
</tr>
<tr class="even">
<td><p>Conférence web/PSOM(TLS)/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>serveur Edge service Edge de conférence web</p></td>
<td><p>Média de conférence web</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50 000-59 999</p></td>
<td><p>service Edge A/V du serveur Edge</p></td>
<td><p>Indifférente</p></td>
<td><p>Obligatoire pour la fédération avec les partenaires exécutant Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 et Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50 000-59 999</p></td>
<td><p>service Edge A/V du serveur Edge</p></td>
<td><p>Indifférente</p></td>
<td><p>Requis uniquement pour la fédération avec des partenaires exécutant Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/RTP/TCP/50 000-59 999</p></td>
<td><p>Indifférente</p></td>
<td><p>service Edge A/V du serveur Edge</p></td>
<td><p>Requis uniquement pour la fédération avec des partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/UDP/50 000-59 999</p></td>
<td><p>Indifférente</p></td>
<td><p>service Edge A/V du serveur Edge</p></td>
<td><p>Requis uniquement pour la fédération avec des partenaires exécutant Office Communications Server 2007</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>service Edge A/V du serveur Edge</p></td>
<td><p>Indifférente</p></td>
<td><p>Le port 3478 sortant est utilisé pour déterminer la version du serveur Edge avec lequel Lync Server communique et également pour le trafic de médias de serveur Edge vers serveur Edge. Obligatoire pour la fédération avec Lync Server 2010, Windows Live Messenger et Office Communications Server 2007 R2, mais également en cas de déploiement de plusieurs pools de serveurs Edge dans une société.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Indifférente</p></td>
<td><p>service Edge A/V du serveur Edge</p></td>
<td><p>Négociation STUN/TURN des candidats sur UDP/3478</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>service Edge A/V du serveur Edge</p></td>
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


### Résumé de la configuration de pare-feu requise pour la topologie Edge unique consolidée avec des adresses IP privées utilisant NAT : interface interne

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
<td><p>Indifférent (définissable en tant qu’adresse IP du serveur Standard Edition, adresse IP du serveur Standard Edition ou adresse IP du pool exécutant le service de passerelle XMPP)</p></td>
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
<td><p>Indifférente (définissable en tant qu’adresse IP de serveur frontal ou chaque adresse IP de serveur frontal dans un pool de serveurs frontaux)</p>
<p></p></td>
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

