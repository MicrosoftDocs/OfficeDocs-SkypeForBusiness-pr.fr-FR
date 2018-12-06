---
title: Enregistrements DNS requis pour les serveurs Standard Edition Server
TOCTitle: Enregistrements DNS requis pour les serveurs Standard Edition Server
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425900(v=OCS.15)
ms:contentKeyID: 49296967
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enregistrements DNS requis pour les serveurs Standard Edition Server

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section décrit les enregistrements DNS (Domain Name System) requis pour le déploiement de serveurs Standard Edition.

## Enregistrements DNS requis pour les serveurs Standard Edition

Le tableau suivant recense les enregistrements DNS requis pour un déploiement de serveur Lync Server 2013 Standard Edition.

### Enregistrements DNS requis pour les serveurs Standard Edition

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
<td><p>Serveur Standard Edition</p></td>
<td><p>Enregistrement A interne associant le nom de domaine complet (FQDN) du serveur à son adresse IP.</p></td>
</tr>
<tr class="even">
<td><p>Ouverture de session client automatique</p></td>
<td><p>Pour chaque domaine SIP pris en charge, un enregistrement SRV pour _sipinternaltls._tcp.<em>&lt;domaine&gt;</em> sur le port 5061 mappé sur le nom de domaine complet du serveur Standard Edition chargé d’authentifier et de rediriger les demandes d’ouverture de session des clients. Pour plus d’informations, voir <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Enregistrements DNS requis pour la connexion automatique des clients dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Détection du service web de mise à jour des périphériques par les périphériques de communications unifiées</p></td>
<td><p>Enregistrement A interne avec le nom ucupdates-r2.<em>&lt;domaine SIP&gt;</em> qui est résolu en adresse IP du serveur Standard Edition hébergeant le service web de mise à jour des périphériques. Dans le cas où un périphérique de communications unifiées est activé, alors qu’un utilisateur ne s’y est jamais connecté, l’enregistrement A permet au périphérique de détecter le serveur hébergeant le service web de mise à jour des périphériques et d’obtenir des mises à jour. Les périphériques peuvent autrement se procurer ces informations via une mise en service de la bande entrante la première fois qu’un utilisateur se connecte.</p></td>
</tr>
<tr class="even">
<td><p>Proxy inverse de prise en charge du trafic HTTP</p></td>
<td><p>Enregistrement A externe qui résout le nom de domaine complet de la batterie de serveurs web externes en adresse IP externe du proxy inverse. Les clients et les périphériques de communications unifiées utilisent cet enregistrement pour se connecter au proxy inverse. Pour plus d’informations, voir <a href="lync-server-2013-determine-dns-requirements.md">Détermination de la configuration requise pour DNS pour Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
</tbody>
</table>

