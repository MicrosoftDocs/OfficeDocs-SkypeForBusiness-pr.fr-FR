---
title: 'Lync Server 2013 : Enregistrements DNS requis pour le pool frontal'
TOCTitle: Enregistrements DNS requis pour le pool frontal
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398082(v=OCS.15)
ms:contentKeyID: 49296081
ms.date: 12/17/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enregistrements DNS requis pour le pool frontal dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-15_

Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.

Vous devez configurer les enregistrements DNS avant de publier la topologie dans le Générateur de topologie. En outre, certains des noms de domaine complets utilisés dans la configuration d’un déploiement de Lync Server 2013 sont des noms de domaine complets de serveur logiques et non physiques, par conséquent vous devez reconfigurer les enregistrements DNS avant de publier la topologie.

> [!WARNING]  
> Lync Server 2013 ne prend pas en charge les domaines en une seule partie. Par exemple, la forêt sans domaine racine <strong>contoso.local</strong> est prise en charge, ce qui n’est pas le cas du domaine racine <strong>local</strong>. Pour plus d’informations, reportez-vous à l’article 300684 de la base de connaissances Microsoft, « Information about configuring Windows for domains with single-label DNS names », à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684" class="uri">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</a>.

> [!IMPORTANT]  
> Le nom défini doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, non un nom de domaine complet. Le Générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. <strong>Utilisez uniquement des caractères standard</strong> (notamment A–Z, a–z, 0–9 et des traits d’union) lors de l’affectation de noms de domaine complets à vos serveurs exécutant Lync Server, des serveurs Edge et des pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard figurant dans un nom de domaine complet ne sont en général pas pris en charge par les serveurs DNS externes et les autorités de certification publiques (lorsque le nom de domaine complet doit être affecté au SN dans le certificat).

Pour pouvoir utiliser la topologie une fois qu’elle a été déployée, vous devez vous assurer que les enregistrements Active Directory et DNS sont créés (en vue de prendre en charge des fonctionnalités spécifiques) :

  - Chaque rôle serveur devant exister dans la topologie est publié en tant qu’objet Active Directory (il suffit pour cela de joindre l’ordinateur au domaine).

  - Un enregistrement DNS A existe pour chaque serveur.

  - Un enregistrement DNS SRV existe pour chaque domaine SIP si vous envisagez d’utiliser l’ouverture de session automatique pour les clients. Cet enregistrement doit avoir la forme suivante : \_sipinternaltls\_tcp. *\<domaine SIP\>* . Si vous envisagez de recourir à la configuration manuelle pour les clients, cet enregistrement n’est pas nécessaire.

  - Un enregistrement DNS A pour chaque URL simple configurée. Il existe quatre types d’URL simple : meet, dialin, lwa et scheduler. Il existe également une URL simple d’administration qui est une URL spéciale, réservée à l’accès au Panneau de configuration Lync Server 2013.

  - Le serveur exécutant SQL Serverdoit être joint au domaine et accessible par l’ordinateur à partir duquel le Générateur de topologie effectue les publications.

Le tableau ci-dessous indique les architectures de référence présentées dans la section Planification. Pour plus d’informations, reportez-vous à [Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) dans la documentation de planification.

### Enregistrements DNS requis pour le pool de serveurs frontaux

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement</th>
<th>Type</th>
<th>FQDN</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (équilibrage de charge DNS). Nécessite un enregistrement DNS A pour l’adresse IP de chaque serveur frontal dans le pool, correspondant au nom de domaine complet du pool.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (adresse IP virtuelle (VIP) de l’équilibreur de la charge matérielle).</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>serveur frontal Pool01 (NŒUD 1)</p>
<p>serveur frontal Pool01 (NŒUD 2)</p>
<p>serveur frontal Pool01 (NŒUD 3)</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>serveur frontal Pool01 (NŒUD 2)</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>Pool01 (VIP) pour le trafic web client à serveur.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>serveur principal Pool01 exécutant SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Requis pour Lync Phone Edition ou l’ouverture de session automatique des clients sans enregistrement DNS SRV et pour une correspondance stricte des domaines. Non requis dans tous les cas.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Suppose qu’il existe un second domaine SIP. Requis pour Lync Phone Edition, l’ouverture de session automatique des clients sans enregistrement DNS SRV et pour une correspondance stricte des domaines. Non requis dans tous les cas.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>URL simple pour les conférences rendez-vous publiées en interne – Le serveur frontal (ou directeur, s’il est installé) répond aux requêtes d’URL simples.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>URL simple pour les conférences publiées en interne – Le serveur frontal (ou directeur, s’il est installé) répond aux requêtes d’URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>admin</p></td>
<td><p>Enregistrement facultatif, URL simple pour le Panneau de configuration Lync Server 2013 publié en interne - Le serveur frontal (ou directeur, s’il est installé) répond aux requêtes d’URL simples. Seul le nom de l’hôte (pas de nom de domaine) est recommandé.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> VIP = adresse IP virtuelle de l’équilibreur de la charge matérielle

## Enregistrements DNS SRV pour le pool de serveurs frontaux


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement</th>
<th>Type</th>
<th>FQDN</th>
<th>FQDN cible</th>
<th>Port</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls._tcp.contoso.com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Requis pour que la configuration automatique des clients Lync 2013 fonctionne en interne</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls._tcp.fabrikam.com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Requis pour que la configuration automatique des clients Lync 2013 fonctionne en interne</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>SRV</p></td>
<td><p>_ntp._udp.contoso.com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Source NTP (Network Time Protocol) requise pour les périphériques exécutant Lync Phone Edition. En interne, cet enregistrement doit pointer vers le contrôleur de domaine. Si le contrôleur de domaine n’est pas défini, l’enregistrement essaiera d’utiliser le serveur NTP time.windows.com</p></td>
</tr>
</tbody>
</table>

