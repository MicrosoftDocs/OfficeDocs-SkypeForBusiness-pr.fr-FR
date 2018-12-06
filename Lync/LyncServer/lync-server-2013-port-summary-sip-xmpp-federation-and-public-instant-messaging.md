---
title: "Résumé des ports - Féd. SIP, XMPP et messagerie instantanée publique"
TOCtitle: "Résumé des ports - Féd. SIP, XMPP et messagerie instantanée publique"
ms:assetid: ab05bdd6-e9b0-4b1b-9dd9-29ab88e8befe
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ618373(v=OCS.15)
ms:contentKeyID: 49298516
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des ports - Fédération SIP, fédération XMPP et messagerie instantanée publique

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les exigences relatives au port, au protocole et au pare-feu pour la fédération avec Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server sont semblables à celles applicables au serveur Edge déployé. Les clients initient la communication avec le service Edge d’accès par le biais du port TLS/SIP/TCP 443. Les partenaires fédérés, quant à eux, initient la communication au service Edge d’accès par le biais du port MTLS/SIP/TCP 5061.

Pour configurer votre pare-feu pour les ports et les protocoles nécessaires à la prise en charge de la connectivité d’une solution PIC, vous devez savoir que SIP/MTLS/TCP 5061 est bidirectionnel pour prendre en compte la capacité des contacts du fournisseur de messagerie instantanée publique de contacter les clients Lync, ou pour que Lync contacte les contacts de messagerie instantanée publique.

Windows Live Messenger peut participer à des communications audio/vidéo avec les clients Lync. Ceci explique que, généralement, configurations du port et du protocole du pare-feu sont similaires pour la prise en charge des clients Lync en tant qu’utilisateurs externes.

> [!IMPORTANT]  
> Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.<br />
La fédération avec les contacts du client Messenger prendra officiellement fin le 15 mars 2013, sauf pour la Chine. Skype deviendra le client de fédération pour les utilisateurs fédérés qui utilisaient Messenger.

Les ports et protocoles définis pour le proxy XMPP (Extensible Messaging and Presence Protocol) déployé sur le serveur Edge autorisent les communications d’un partenaire fédéré XMPP au serveur Edge ainsi que de votre serveur Edge au partenaire fédéré XMPP. Une règle est également définie sur le pare-feu côté interne du serveur frontal ou du pool de serveurs frontaux au serveur Edge ou au pool de serveurs Edge.

## Résumé du pare-feu - Fédération SIP


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
<td><p>Access/SIP(MTLS)/TCP/5061</p></td>
<td><p>Partenaires PIC</p></td>
<td><p>Interface Access du serveur Edge</p></td>
<td><p>Pour la connectivité fédérée et PIC qui utilise SIP.</p></td>
</tr>
<tr class="even">
<td><p>Access/SIP(MTLS)/TCP/5061</p></td>
<td><p>Interface Access du serveur Edge</p></td>
<td><p>Partenaires PIC</p></td>
<td><p>Pour la connectivité fédérée et PIC qui utilise SIP.</p></td>
</tr>
<tr class="odd">
<td><p>Access/SIP(TLS)/TCP/443</p></td>
<td><p>Clients</p></td>
<td><p>Interface Access du serveur Edge</p></td>
<td><p>Trafic SIP client vers serveur pour l’accès des utilisateurs externes.</p></td>
</tr>
<tr class="even">
<td><p>A/V/RTP/TCP/50,000-59,999</p></td>
<td><p>Interface Access du serveur Edge</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Utilisés pour les sessions A/V avec Windows Live Messenger si la connectivité de messagerie instantanée est configurée.</p></td>
</tr>
<tr class="odd">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Interface Access du serveur Edge</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Requis pour la connectivité PIC avec Windows Live Messenger.</p></td>
</tr>
<tr class="even">
<td><p>A/V/STUN,MSTURN/UDP/3478</p></td>
<td><p>Clients Live Messenger</p></td>
<td><p>Interface Access du serveur Edge</p></td>
<td><p>Requis pour la connectivité PIC avec Windows Live Messenger.</p></td>
</tr>
</tbody>
</table>


## Résumé du pare-feu - Protocole XMPP (Extensible Messaging and Presence Protocol)


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
<td><p>Indifférent</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès</p></td>
<td><p>Port de communication standard de serveur à serveur pour XMPP. Autorise la communication vers le proxy XMPP du serveur Edge depuis les partenaires XMPP fédérés.</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès</p></td>
<td><p>Indifférent</p></td>
<td><p>Port de communication standard de serveur à serveur pour XMPP. Autorise la communication depuis le proxy XMPP du serveur Edge vers les partenaires XMPP fédérés.</p></td>
</tr>
<tr class="odd">
<td><p>XMPP/MTLS/23456</p></td>
<td><p>Indifférent</p></td>
<td><p>Adresse IP du serveur Edge interne</p></td>
<td><p>Trafic XMPP interne depuis la passerelle XMPP sur le serveur frontal ou le pool de serveurs frontaux vers le serveur Edge</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Concepts

[Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  

#### Autres ressources

[Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

