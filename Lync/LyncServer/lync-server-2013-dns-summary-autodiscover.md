---
title: Synthèse DNS - Découverte automatique dans Lync Server 2013
TOCTitle: Synthèse DNS - Découverte automatique dans Lync Server 2013
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945644(v=OCS.15)
ms:contentKeyID: 53095501
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Synthèse DNS - Découverte automatique dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La découverte automatique est un service flexible, dans le sens où elle accepte les communications sur le protocole HTTP ou HTTPS. Pour cela, le système de noms de domaine (DNS, Domain Name System) et les certificats utilisés par les serveurs qui hébergent le service de découverte automatique doivent être configurés correctement. Les exigences liées aux certificats sont traitées dans [Résumé des certificats - découverte automatique](lync-server-2013-certificate-summary-autodiscover.md).

> [!IMPORTANT]  
> La logique de recherche DNS pour les clients Lync Server utilise un ordre de résolution spécifique. Vous devez toujours inclure à la fois lyncdiscoverinternal.&lt;domain&gt; et lyncdiscover.&lt;domain&gt; dans votre système DNS. Si vous excluez l’enregistrement lyncdiscoverinternal.&lt;domain&gt;, les clients internes ne pourront pas se connecter aux services prévus ou recevront une réponse de découverte automatique incorrecte.

### Enregistrements DNS internes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’enregistrement</th>
<th>Nom d’hôte</th>
<th>Résolu en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal.<em>&lt;nom_de_domaine_interne&gt;</em></p></td>
<td><p>Nom de domaine complet interne des services web pour votre pool de directeurs, si vous en avez un, ou pour votre pool de serveurs frontaux si vous n’avez pas de directeur.</p></td>
</tr>
<tr class="even">
<td><p>A (hôte, si IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;nom_de_domaine_interne&gt;</em></p></td>
<td><p>Adresse IP interne des services Web (adresse IP virtuelle [VIP] si vous utilisez un programme d’équilibrage de la charge) de votre pool de directeurs, si vous en avez un, ou de votre pool de serveurs frontaux si vous n’avez pas de directeur.</p></td>
</tr>
</tbody>
</table>


Vous devez créer l’un des enregistrements DNS externes suivants :

### Enregistrements DNS externes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’enregistrement</th>
<th>Nom d’hôte</th>
<th>Résolu en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover.<em>&lt;sipdomain&gt;</em></p></td>
<td><p>Nom de domaine complet externe des services Web pour votre pool de directeurs, si vous en avez un, ou pour votre pool de serveurs frontaux si vous n’avez pas de directeur.</p></td>
</tr>
<tr class="even">
<td><p>A (hôte, si IPv6, AAAA)</p></td>
<td><p>lyncdiscover.<em>&lt;sipdomain&gt;</em></p></td>
<td><p>Adresse IP publique ou externe du proxy inverse.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Le trafic externe passe par le proxy inverse.

> [!NOTE]  
> Les clients d’appareils mobiles ne prennent pas en charge plusieurs certificats SSL (Secure Sockets Layer) de différents domaines. Par conséquent, la redirection CNAME vers différents domaines n’est pas prise en charge sur le protocole HTTPS. Par exemple, un enregistrement DNS CNAME pour lyncdiscover.contoso.com qui redirige vers une adresse director.contoso.net n’est pas pris en charge sur HTTPS. Dans une telle topologie, un client d’appareil mobile doit utiliser le protocole HTTP pour la première demande, de sorte que la redirection CNAME soit résolue sur HTTP. Les demandes ultérieures utilisent ensuite le protocole HTTPS. Pour prendre en charge ce scénario, vous devez configurer votre proxy inverse avec une règle de publication web pour le port 80 (HTTP). Pour plus d’informations, voir « Pour créer une règle de publication web pour le port 80 » dans <a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuration du proxy inverse pour la mobilité dans Lync Server 2013</a>. La redirection CNAME vers le même domaine est prise en charge sur HTTPS. Dans ce cas, le certificat du domaine de destination couvre le domaine d’origine.

## Voir aussi

#### Tâches

[Configuration du proxy inverse pour la mobilité dans Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  

#### Concepts

[Résumé des certificats - découverte automatique](lync-server-2013-certificate-summary-autodiscover.md)

