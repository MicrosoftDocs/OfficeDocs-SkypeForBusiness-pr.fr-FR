---
title: 'Lync Server 2013: configuration requise pour le service DNS pour les pools front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03759267ea10a4eaf7046fd25390b45265e479f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Configuration DNS requise pour les listes frontales dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-07_

Cette section décrit les enregistrements DNS (Domain Name System) requis pour le déploiement de la gamme frontale.

<div>

## <a name="dns-records-for-front-end-pools"></a>Enregistrements DNS pour les pools front-end

Le tableau suivant indique les exigences DNS pour un déploiement de pool frontal 2013 Lync Server.

### <a name="dns-requirements-for-a-front-end-pool"></a>Configuration requise pour le service DNS pour une liste frontale

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
<td><p>Pool frontal avec plusieurs serveurs frontaux et un équilibreur de charge matérielle (qu’il s’agisse d’un équilibrage de charge DNS ou non)</p></td>
<td><p>Lors de l’utilisation de l’équilibrage de charge DNS et de l’équilibrage de charge matérielle, vous devez héberger (A) des enregistrements. Créer un enregistrement A interne qui résout le nom de domaine complet (FQDN) du pool frontal pour l’équilibrage de charge DNS. Créer un enregistrement d’hôte interne (A) pour les services Web internes vers l’adresse IP virtuelle (VIP) de l’équilibrage de charge. Vous devez utiliser le nom des services Web internes, tel qu’il est défini dans générateur de topologie.</p>
<p>Par exemple, si vous utilisez à la fois l’équilibrage de charge DNS et l’équilibrage de charge matérielle, un enregistrement a pour chaque serveur frontal d’un pool pour l’équilibrage de charge DNS et un enregistrement A pour les services Web internes pointant vers l’adresse IP virtuelle de l’équilibrage de charge matérielle. :</p>
<ul>
<li><p>Équilibrage de charge DNS: adresse IP de Pool01.contoso.net du pool 10.10.10.5</p>
<div>

> [!WARNING]  
> Chaque serveur frontal dispose également d’un enregistrement distinct:


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>Équilibrage de la charge matérielle: adresse IP WebInternal.contoso.net de HLB VIP 192.168.10.5</p></li>
</ul>
<p>Tout le trafic, à l’exception du trafic HTTP/HTTPs, utilise l’enregistrement Pool01.contoso.net. Le trafic HTTP/HTTPs utilise l’adresse de services Web interne définie de 192.168.10.5</p></td>
</tr>
<tr class="even">
<td><p>Réserve frontale déployée par l’équilibrage de charge DNS</p></td>
<td><p>Un ensemble d’enregistrements A internes qui résout le nom de domaine complet (FQDN) du pool sur l’adresse IP de chaque serveur du pool. Un enregistrement A doit être enregistré pour chaque serveur du pool.</p></td>
</tr>
<tr class="odd">
<td><p>Réserve frontale déployée par l’équilibrage de charge DNS</p></td>
<td><p>Un ensemble d’enregistrements A internes qui résout le nom de domaine complet (FQDN) de chaque serveur dans le pool à l’adresse IP du serveur. Pour plus d’informations, voir <a href="lync-server-2013-dns-load-balancing.md">équilibrage de la charge DNS dans Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
<tr class="even">
<td><p>Réserve frontale avec un serveur frontal unique et une base de données principale dédiée, mais pas de solde de charge</p></td>
<td><p>Un enregistrement A interne qui résout le nom de domaine complet (FQDN) du pool frontal vers l’adresse IP du serveur principal Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>Connexion automatique au client</p></td>
<td><p>Pour chaque domaine SIP pris en charge, un enregistrement SRV pour _sipinternaltls. _ TCP. &lt;domaine&gt; sur le port 5061 qui correspond au nom de domaine complet du pool frontal qui authentifie et redirige les demandes de connexion du client. Pour plus d’informations, voir <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">configuration DNS requise pour la connexion automatique au client dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>Découverte du service Web de mise à jour d’appareil par des appareils de communications unifiées (UC)</p></td>
<td><p>Un enregistrement A interne du nom ucupdates-r2. &lt;Domaine&gt; SIP résolu sur l’adresse IP du pool frontal qui héberge le service Web de mise à jour de l’appareil. Dans le cas où un périphérique de communications unifiées est activé, mais qu’aucun utilisateur ne s’est connecté à l’appareil, l’enregistrement A permet à l’appareil de détecter le service Web de mise à jour des périphériques d’hébergement du pool frontal et d’obtenir les mises à jour. Dans le cas contraire, les appareils obtiennent ces informations en même temps que la première fois qu’un utilisateur se connecte.</p>
<div>

> [!IMPORTANT]  
> Si vous avez un déploiement existant du service Web de mise à jour de l’appareil dans Lync Server 2010, vous avez déjà créé un enregistrement A interne avec le nom ucupdates. &lt;Domaine&gt;SIP. Pour Microsoft Office Communications Server 2007 R2, vous devez créer un enregistrement DNS A supplémentaire portant le nom ucupdates-r2. &lt;Domaine&gt;SIP.


</div></td>
</tr>
<tr class="odd">
<td><p>Proxy inverse pour la prise en charge du trafic HTTP</p></td>
<td><p>Un enregistrement A externe qui résout le nom de domaine complet de la batterie de serveurs Web externe à l’adresse IP externe du proxy inverse. Les clients et les appareils UC utilisent cet enregistrement pour se connecter au proxy inverse. Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-determine-dns-requirements.md">déterminer les exigences DNS pour Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
</tbody>
</table>


Le tableau suivant montre un exemple des enregistrements DNS requis pour le nom de domaine complet (FQDN) de la batterie de serveurs Web interne.

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>Exemples d’enregistrements DNS pour le FQDN d’une batterie de serveurs Web interne

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de domaine complet (FQDN) du site Web interne</th>
<th>FQDN du pool</th>
<th>Enregistrement (s) DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Enregistrement DNS A pour le ee-pool.contoso.com résolu vers l’adresse VIP de l’équilibrage de charge utilisé par les serveurs frontaux.</p>
<p>Enregistrement DNS A pour webcon.contoso.com résolu vers l’adresse VIP de l’équilibrage de charge utilisé par les serveurs frontaux.</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Enregistrement DNS A pour ee-pool.contoso.com résolu vers l’adresse IP virtuelle (VIP) de l’équilibrage de charge utilisé par les serveurs frontaux de l’entreprise Edition dans le pool frontal.</p>
<p>Notez que si vous utilisez l’équilibrage de charge DNS sur ce pool, votre pool frontal et votre batterie de serveurs Web interne ne peuvent pas avoir le même nom de domaine complet.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

