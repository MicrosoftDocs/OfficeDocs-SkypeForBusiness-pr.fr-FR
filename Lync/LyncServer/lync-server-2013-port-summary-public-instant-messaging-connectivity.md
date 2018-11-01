---
title: Résumé des ports - Connectivité PIC (Public IM Connectivity)
TOCTitle: Résumé des ports - Connectivité PIC (Public IM Connectivity)
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49299326
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des ports - Connectivité PIC (Public IM Connectivity)

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour configurer votre pare-feu pour les ports et les protocoles nécessaires à la prise en charge de la connectivité d’une solution PIC, vous devez savoir que SIP/MTLS/TCP 5061 est bidirectionnel pour prendre en compte la capacité des contacts du fournisseur de messagerie instantanée publique de contacter les clients Lync, ou pour que Lync contacte les contacts de messagerie instantanée publique.

Windows Live Messenger peut participer à des communications audio/vidéo avec les clients Lync. Ceci explique que, généralement, configurations du port et du protocole du pare-feu sont similaires pour la prise en charge des clients Lync en tant qu’utilisateurs externes.

> [!IMPORTANT]  
> Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.<br />
La fédération avec les contacts du client Messenger prendra officiellement fin le 15 mars 2013, sauf pour la Chine. Skype deviendra le client de fédération pour les utilisateurs fédérés qui utilisaient Messenger.

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


## Voir aussi

#### Concepts

[Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

