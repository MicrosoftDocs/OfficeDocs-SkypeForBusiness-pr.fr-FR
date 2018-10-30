---
title: Configuration DNS requise pour les pools frontaux
TOCTitle: Configuration DNS requise pour les pools frontaux
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412910(v=OCS.15)
ms:contentKeyID: 49298668
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration DNS requise pour les pools frontaux

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section décrit les enregistrements DNS (Domain Name System) requis pour le déploiement de pools frontaux.

## Enregistrements DNS requis pour les pools frontaux

Le tableau suivant spécifie les composants DNS requis pour le déploiement de pools frontaux Lync Server 2013.

### Composants DNS requis pour un pool frontal

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
<td><p>Un pool frontal avec plusieurs serveurs frontaux et un programme d’équilibrage de la charge matérielle (que l’équilibrage de la charge DNS soit également déployé dans ce pool ou non).</p></td>
<td><p>Lors de l’utilisation de l’équilibrage de la charge DNS et d’un programme d’équilibrage de la charge matérielle, vous avez besoin d’enregistrements d’hôtes (A). Créez un enregistrement A interne qui résout le nom de domaine complet du pool frontal pour l’équilibrage de la charge DNS. Créez un enregistrement d’hôte (A) interne pour les services web internes à l’adresse IP virtuelle du programme d’équilibrage de la charge. Vous devez utiliser les services web internes comme défini dans l’Générateur de topologie.</p>
<p>Par exemple, si vous utilisez à la fois l’équilibrage de la charge DNS et l’équilibrage de la charge matérielle, vous aurez un enregistrement A pour chaque serveur frontal dans un pool pour l’équilibrage de la charge DNS et un enregistrement A pour les services web internes pointant vers l’adresse IP virtuelle du programme d’équilibrage de la charge matérielle :</p>
<ul>
<li><p>Équilibrage de la charge DNS :   Pool01.contoso.net   adresse IP du pool   10.10.10.5</p>

> [!WARNING]  
> Chaque serveur frontal aura également un enregistrement A distinct :

<ol>
<li><p>FE01.contoso.net    10.10.10.1</p></li>
<li><p>FE02.contoso.net    10.10.10.2</p></li>
<li><p>FE03.contoso.net    10.10.10.3</p></li>
<li><p>FE04.contoso.net    10.10.10.4</p></li>
</ol></li>
<li><p>Équilibrage de la charge :   WebInternal.contoso.net   adresse IP virtuelle de l’équilibrage de charge matérielle   192.168.10.5</p></li>
</ul>
<p>Tout le trafic à l’exception du trafic HTTP/HTTPS utilisera l’enregistrement Pool01.contoso.net. Le trafic HTTP/HTTPS utilisera l’adresse des services web internes définie, 192.168.10.5</p></td>
</tr>
<tr class="even">
<td><p>Un pool frontal avec déploiement de l’équilibrage de la charge DNS.</p></td>
<td><p>Un ensemble d’enregistrements A internes qui associent le nom de domaine complet du pool à l’adresse IP de chaque serveur au sein du pool. Il doit y avoir un enregistrement A pour chaque serveur dans le pool.</p></td>
</tr>
<tr class="odd">
<td><p>Un pool frontal avec déploiement de l’équilibrage de la charge DNS.</p></td>
<td><p>Un ensemble d’enregistrements A internes qui associent le nom de domaine complet à l’adresse IP de chaque serveur au sein du pool. Pour plus d’informations, voir <a href="lync-server-2013-dns-load-balancing.md">Équilibrage de charge DNS dans Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
<tr class="even">
<td><p>Un pool frontal avec un seul serveur frontal et une base de données principale dédiée, mais aucun équilibrage de charge.</p></td>
<td><p>Un enregistrement A interne associant le nom de domaine complet du pool frontal à l’adresse IP du serveur frontal Enterprise Edition unique.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>Ouverture de session client automatique</p></td>
<td><p>Pour chaque domaine SIP pris en charge, un enregistrement SRV pour _sipinternaltls._tcp.&lt;domaine&gt; sur le port 5061 mappé sur le nom de domaine complet du pool frontal chargé d’authentifier et de rediriger les demandes d’ouverture de session des clients. Pour plus d’informations, voir <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Enregistrements DNS requis pour la connexion automatique des clients dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>Détection du service web de mise à jour des périphériques par les périphériques de communications unifiées</p></td>
<td><p>Un enregistrement A interne avec le nom ucupdates-r2.&lt;domaine SIP&gt; associé à l’adresse IP du pool frontal qui héberge le service web de mise à jour des périphériques. Dans le cas où un périphérique de communications unifiées est activé, mais qu’un utilisateur ne s’y est jamais connecté, l’enregistrement A permet au périphérique de détecter le pool frontal hébergeant le service de mise à jour des périphériques et d’obtenir des mises à jour. Les périphériques peuvent autrement se procurer ces informations via une mise en service intrabande la première fois qu’un utilisateur se connecte.</p>

> [!IMPORTANT]  
> Si le service web de mise à jour des périphériques est déjà déployé dans Lync Server 2010, vous avez déjà créé un enregistrement A interne nommé ucupdates.<em>&lt;domaine SIP&gt;</em>. Pour Microsoft Office Communications Server 2007 R2, vous devez créer un enregistrement DNS A supplémentaire nommé ucupdates-r2.<em>&lt;domaine SIP&gt;</em>.

</td>
</tr>
<tr class="odd">
<td><p>Proxy inverse de prise en charge du trafic HTTP</p></td>
<td><p>Enregistrement A externe qui résout le nom de domaine complet de la batterie de serveurs web externes en l’adresse IP externe du proxy inverse. Les clients et les périphériques de communications unifiées utilisent cet enregistrement pour se connecter au proxy inverse. Pour plus d’informations, voir <a href="lync-server-2013-determine-dns-requirements.md">Détermination de la configuration requise pour DNS pour Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
</tbody>
</table>


Le tableau qui suit montre un exemple des enregistrements DNS requis pour le nom de domaine complet de la batterie de serveurs web internes.

### Exemples d’enregistrements DNS requis pour le nom de domaine complet de la batterie de serveurs web internes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de domaine complet de la batterie de serveurs web internes</th>
<th>Nom de domaine complet du pool</th>
<th>Enregistrement(s) DNS A</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Enregistrement DNS A pour le nom ee-pool.contoso.com associé à l’adresse IP virtuelle du programme d’équilibrage de charge utilisé par les serveurs frontaux.</p>
<p>Enregistrement DNS A pour le nom webcon.contoso.com associé à l’adresse IP virtuelle du programme d’équilibrage de charge utilisé par les serveurs frontaux.</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Enregistrement DNS A pour le nom ee-pool.contoso.com associé à l’adresse IP virtuelle du programme d’équilibrage de charge utilisé par les serveurs frontaux Enterprise Edition du pool frontal.</p>
<p>Notez que si vous avez recours à l’équilibrage de la charge DNS dans ce pool, votre pool frontal et votre batterie de serveurs web internes ne peuvent pas avoir le même nom de domaine complet.</p></td>
</tr>
</tbody>
</table>

