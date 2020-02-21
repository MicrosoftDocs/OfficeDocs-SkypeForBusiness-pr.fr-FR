---
title: 'Lync Server 2013 : configuration DNS requise pour les pools frontaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae56cdf07ae76ca0499050574793421864de818
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Configuration DNS requise pour les pools frontaux dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-07_

Cette section décrit les enregistrements DNS (Domain Name System) requis pour le déploiement de pools frontaux.

<div>

## <a name="dns-records-for-front-end-pools"></a>Enregistrements DNS requis pour les pools frontaux

Le tableau suivant spécifie les exigences DNS pour un déploiement de pool frontal Lync Server 2013.

### <a name="dns-requirements-for-a-front-end-pool"></a>Composants DNS requis pour un pool frontal

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
<td><p>Quand vous utilisez l’équilibrage de charge DNS et un équilibreur de la charge matérielle, vous avez besoin d’enregistrements Hôte (A). Créez un enregistrement A interne qui est résolu en nom de domaine complet (FQDN) du pool de serveur frontal pour l’équilibrage de charge DNS. Créez un enregistrement (A) hôte interne pour les services web internes vers l’adresse IP virtuelle (VIP) de l’équilibreur de charge. Vous devez utiliser le nom des services Web internes comme défini dans le générateur de topologie.</p>
<p>Par exemple, si vous utilisez l’équilibrage de charge DNS et l’équilibrage de la charge matérielle, vous devez avoir un enregistrement A pour chaque serveur frontal dans un pool pour l’équilibrage de charge DNS et un enregistrement A pour les services Web internes pointant vers l’adresse IP virtuelle de l’équilibreur de charge matérielle. :</p>
<ul>
<li><p>Équilibrage de charge DNS :   Pool01.contoso.net   Adresse IP du pool   10.10.10.5</p>
<div>

> [!WARNING]  
> Chaque serveur frontal aura également un enregistrement A distinct :


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>Équilibrage de la charge matérielle :   WebInternal.contoso.net   Address IP de HLB VIP   192.168.10.5</p></li>
</ul>
<p>Tout le trafic à l’exception du trafic HTTP/HTTPS utilisera l’enregistrement Pool01.contoso.net. Le trafic HTTP/HTTPS utilisera l’adresse des services web interne 192.168.10.5</p></td>
</tr>
<tr class="even">
<td><p>Un pool frontal avec déploiement de l’équilibrage de la charge DNS.</p></td>
<td><p>Un ensemble d’enregistrements A internes qui associent le nom de domaine complet du pool à l’adresse IP de chaque serveur au sein du pool. Il doit y avoir un enregistrement A pour chaque serveur dans le pool.</p></td>
</tr>
<tr class="odd">
<td><p>Un pool frontal avec déploiement de l’équilibrage de la charge DNS.</p></td>
<td><p>Un ensemble d’enregistrements A internes qui associent le nom de domaine complet à l’adresse IP de chaque serveur au sein du pool. Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-dns-load-balancing.md">DNS Load Balancing in Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
<tr class="even">
<td><p>Un pool frontal avec un seul serveur frontal et une base de données principale dédiée, mais aucun équilibrage de charge.</p></td>
<td><p>Un enregistrement A interne associant le nom de domaine complet du pool frontal à l’adresse IP du serveur frontal Enterprise Edition unique.</p></td>
</tr>
<tr class="odd">
<td><p>Ouverture de session client automatique</p></td>
<td><p>Pour chaque domaine SIP pris en charge, un enregistrement SRV pour _sipinternaltls. _tcp. &lt;domaine&gt; sur le port 5061 qui mappe sur le nom de domaine complet du pool frontal qui authentifie et redirige les demandes client de connexion. Pour plus d’informations, consultez la rubrique <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS Requirements for Automatic client Sign-in dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>Détection du service web de mise à jour des périphériques par les périphériques de communications unifiées</p></td>
<td><p>Un enregistrement A interne portant le nom ucupdates-r2. &lt;Domaine&gt; SIP qui est résolu en adresse IP du pool frontal qui héberge le service Web de mise à jour des périphériques. Dans le cas où un périphérique de communications unifiées est activé, mais qu’un utilisateur ne s’y est jamais connecté, l’enregistrement A permet au périphérique de détecter le pool frontal hébergeant le service de mise à jour des périphériques et d’obtenir des mises à jour. Les périphériques peuvent autrement se procurer ces informations via une mise en service intrabande la première fois qu’un utilisateur se connecte.</p>
<div>

> [!IMPORTANT]  
> Si vous disposez d’un déploiement existant du service Web de mise à jour des périphériques dans Lync Server 2010, vous avez déjà créé un enregistrement A interne avec le nom ucupdates. &lt;Domaine&gt;SIP. Pour Microsoft Office Communications Server 2007 R2, vous devez créer un enregistrement DNS A supplémentaire avec le nom ucupdates-r2. &lt;Domaine&gt;SIP.


</div></td>
</tr>
<tr class="odd">
<td><p>Proxy inverse de prise en charge du trafic HTTP</p></td>
<td><p>Enregistrement A externe qui résout le nom de domaine complet de la batterie de serveurs web externes en adresse IP externe du proxy inverse. Les clients et les périphériques de communications unifiées utilisent cet enregistrement pour se connecter au proxy inverse. Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
</tbody>
</table>


Le tableau qui suit montre un exemple des enregistrements DNS requis pour le nom de domaine complet de la batterie de serveurs web internes.

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>Exemples d’enregistrements DNS requis pour le nom de domaine complet de la batterie de serveurs web internes

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


</div>

</div>

<span> </span>

</div>

</div>

</div>

