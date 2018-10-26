---
title: 'Lync Server 2013 : Enregistrements DNS requis pour un serveur Standard Edition'
TOCTitle: Enregistrements DNS requis pour un serveur Standard Edition
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204936(v=OCS.15)
ms:contentKeyID: 49297348
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enregistrements DNS requis pour un serveur Standard Edition dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section décrit les enregistrements DNS (Domain Name System) requis pour le déploiement de serveurs Standard Edition.

## Enregistrements DNS requis pour les serveurs Standard Edition

Le tableau ci-dessous recense les enregistrements DNS requis pour un déploiement Lync Server 2013 Standard Edition.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scénario de déploiement</th>
<th>Enregistrement DNS requis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serveur Standard Edition</p></td>
<td><p>Un enregistrement interne A qui associe le nom de domaine complet (FQDN) du serveur à son adresse IP.</p></td>
</tr>
<tr class="even">
<td><p>Ouverture de session client automatique</p></td>
<td><p>Pour chaque domaine SIP pris en charge, enregistrement SRV pour _sipinternaltls._tcp.&lt;domaine&gt; sur le port 5061 mappé au nom de domaine complet du serveur Standard Edition chargé d’authentifier et de rediriger les demandes de connexion des clients. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Enregistrements DNS requis pour la connexion automatique des clients dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Détection du service web de mise à jour des périphériques par les périphériques de communications unifiées</p></td>
<td><p>Enregistrement A interne nommé ucupdates-r2.&lt;domaine SIP&gt; et résolu en adresse IP du serveur Standard Edition hébergeant le service web de mise à jour des périphériques. Si un périphérique de communications unifiées est activé, alors qu’un utilisateur ne s’y est jamais connecté, l’enregistrement A permet au périphérique de détecter le serveur hébergeant le service web de mise à jour des périphériques et d’obtenir des mises à jour. Cependant, les périphériques obtiennent ces informations du serveur via une mise en service intrabande côté serveur lorsqu’un utilisateur se connecte pour la première fois. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-device-update-web-service.md">Service web de mise à jour des dispositifs dans Lync Server 2013</a> dans la documentation des opérations.</p></td>
</tr>
<tr class="even">
<td><p>Proxy inverse de prise en charge du trafic HTTP</p></td>
<td><p>Enregistrement A externe qui résout le nom de domaine complet de la batterie de serveurs web externes en l’adresse IP externe du proxy inverse. Les clients et les périphériques de communications unifiées utilisent cet enregistrement pour se connecter au proxy inverse. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-determine-dns-requirements.md">Détermination de la configuration requise pour DNS pour Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Concepts

[Enregistrements DNS requis pour la connexion automatique des clients dans Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  

#### Autres ressources

[Service web de mise à jour des dispositifs dans Lync Server 2013](lync-server-2013-device-update-web-service.md)

