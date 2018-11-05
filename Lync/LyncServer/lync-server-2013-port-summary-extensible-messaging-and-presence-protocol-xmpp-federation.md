---
title: "Résumé des ports - Féd. XMPP (Extensible Messaging and Presence Protocol)"
TOCtitle: "Résumé des ports - Féd. XMPP (Extensible Messaging and Presence Protocol)"
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49297409
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des ports - Fédération XMPP (Extensible Messaging and Presence Protocol)

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les ports et protocoles définis pour le proxy XMPP (Extensible Messaging and Presence Protocol) déployé sur le serveur Edge autorisent les communications d’un partenaire fédéré XMPP au serveur Edge ainsi que de votre serveur Edge au partenaire fédéré XMPP. Une règle est également définie sur le pare-feu côté interne du serveur frontal ou du pool de serveurs frontaux au serveur Edge ou au pool de serveurs Edge.

## Résumé du pare-feu pour le protocole XMPP


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
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Indifférent</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès</p></td>
<td><p>Port de communication de serveur à serveur standard pour XMPP. Permet la communication vers le proxy XMPP du serveur Edge depuis les partenaires XMPP fédérés.</p></td>
</tr>
<tr class="even">
<td><p>XMPP/TCP/5269</p></td>
<td><p>Adresse IP de l’interface du service Edge d’accès</p></td>
<td><p>Indifférent</p></td>
<td><p>Port de communication de serveur à serveur standard pour XMPP. Permet la communication depuis le proxy XMPP du serveur Edge vers les partenaires XMPP fédérés.</p></td>
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

#### Tâches

[Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Autres ressources

[Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

