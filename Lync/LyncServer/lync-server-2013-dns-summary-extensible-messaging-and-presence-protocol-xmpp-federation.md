---
title: "Résumé des enr. DNS - Féd. XMPP (Extensible Messaging and Presence Protocol)"
TOCtitle: "Résumé des enr. DNS - Féd. XMPP (Extensible Messaging and Presence Protocol)"
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49296282
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des enregistrements DNS - Fédération XMPP (Extensible Messaging and Presence Protocol)

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour configurer le protocole XMPP (extensible Messaging and Presence Protocol) pour votre déploiement, créez deux enregistrements DNS (Domain Name System) dans un serveur DNS externe qui résoudra les enregistrements dans le service Edge d’accès de votre serveur Edge ou pool de serveurs Edge.

## Résumé DNS pour le protocole XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement/TYPE/Port</th>
<th>Nom de domaine complet (FQDN)</th>
<th>Adresse IP/Enregistrement d’hôte FQDN</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externe du proxy XMPP sur le service Edge d’accès ou le pool de serveurs Edge. Répétez si nécessaire pour tous les domaines SIP internes avec des utilisateurs prenant en charge Lync où le contact avec des contacts XMPP est autorisé par le biais de la configuration de la stratégie d’accès externe via une stratégie globale, une stratégie de site dans laquelle se trouve l’utilisateur ou une stratégie utilisateur appliquée à l’utilisateur prenant en charge Lync. Un domaine XMPP autorisé doit également être configuré dans la stratégie des partenaires fédérés XMPP. Pour plus d’informations, voir les rubriques dans <strong>Voir aussi</strong>.</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>xmpp.contoso.com (par exemple)</p></td>
<td><p>Adresse IP du service Edge d’accès sur votre serveur Edge ou pool de serveurs Edge hébergeant le proxy XMPP</p></td>
<td><p>Pointe vers le service Edge d’accès ou le pool de serveurs Edge qui héberge le service proxy XMPP. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement (A ou AAAA) d’hôte.</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Tâches

[Configuration de la fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  

#### Concepts

[Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

