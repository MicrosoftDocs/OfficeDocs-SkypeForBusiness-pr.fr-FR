---
title: 'Lync Server 2013 : configuration DNS requise pour le pool frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eff0ab4c6ee2f6582c8274345c15af681d242561
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532171"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Configuration DNS requise pour le pool frontal dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-07_

Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.

Vous devez configurer les enregistrements DNS (Domain Name System) requis avant de publier votre topologie dans le générateur de topologies. De plus, certains des noms de domaine complets utilisés dans la configuration d’un déploiement Lync Server 2013 sont logiques et non des noms de domaine complets de serveur physiques, de sorte que la configuration DNS supplémentaire est requise avant la publication.

<div>


> [!WARNING]  
> Lync Server 2013 ne prend pas en charge les domaines à étiquette unique. Par exemple, une forêt comportant le domaine racine <STRONG>contoso.local</STRONG> est prise en charge alors que le domaine racine <STRONG>local</STRONG> ne l’est pas. Pour plus d’informations, consultez l’article 300684 de la base de connaissances Microsoft, « informations sur la configuration de Windows pour les domaines avec des noms DNS en une seule partie » à l’adresse <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> Le nom que vous spécifiez doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom court, pas un nom de domaine complet (FQDN). Le Générateur de topologies utilise des noms de domaine complets (FQDN), non des noms courts. <STRONG>Utilisez uniquement des caractères standard</STRONG> (tels que a – z, a – z, 0 – 9 et des tirets) lorsque vous affectez des noms de domaine complets à vos serveurs exécutant Lync Server, des serveurs Edge et des pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard figurant dans un nom de domaine complet ne sont en général pas pris en charge par les serveurs DNS externes et les autorités de certification publiques (lorsque le nom de domaine complet doit être affecté au SN dans le certificat).



</div>

Avant de faire fonctionner la topologie une fois qu’elle a été déployée, vérifiez que les enregistrements Active Directory et DNS suivants sont créés (en fonction de vos besoins en matière de fonctionnalités spécifiques) :

  - Chaque rôle serveur qui existe dans la topologie est publié en tant qu’objet Active Directory (le fait de joindre l’ordinateur au domaine effectue cette opération).

  - Un enregistrement DNS A existe pour chaque serveur.

  - Un enregistrement DNS SRV existe pour chaque domaine SIP si vous envisagez d’utiliser l’ouverture de session automatique pour les clients sous la forme d' \_ sipinternaltls \_ TCP. \<SIP domain\> . Si vous utilisez la configuration manuelle pour les clients, cet enregistrement n’est pas nécessaire.

  - Un enregistrement DNS A pour chaque URL simple configurée, dont il y a généralement quatre : réunion, numérotation, LWA et planificateur. De plus, il existe une URL simple d’administration qui est une URL spéciale pour accéder au panneau de configuration Lync Server 2013.

  - Le serveur exécutant SQL Server doit être joint au domaine et accessible par l’ordinateur à partir duquel le générateur de topologies est publié.

Le tableau suivant indique les architectures de référence présentées dans la section Planification. Pour plus d’informations, reportez-vous à [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) dans la documentation de planification.

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>Enregistrements DNS requis pour le pool frontal

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
<td><p>Pool01 (équilibrage de charge DNS). Nécessite un enregistrement DNS A pour l’adresse IP de chaque serveur frontal dans le pool, mappé au nom de domaine complet du pool.</p></td>
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
<td><p>Serveur frontal Pool01 (nœud 1).</p>
<p>Serveur frontal Pool01 (nœud 2).</p>
<p>Serveur frontal Pool01 (nœud 3).</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Serveur frontal Pool01 (nœud 2).</p></td>
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
<td><p>Serveur principal Pool01 exécutant SQL Server 2008 R2.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Requis pour Lync Phone Edition, ou ouverture de session automatique des clients sans enregistrements DNS SRV, et pour une correspondance de domaine stricte. Non requis dans tous les cas.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Suppose qu’il existe un second domaine SIP. Obligatoire pour Lync Phone Edition, l’ouverture de session automatique des clients sans enregistrements DNS SRV et pour une correspondance de domaine stricte. Non requis dans tous les cas.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>URL simple pour les conférences rendez-vous publiées en interne : le serveur frontal (ou directeur, s’il est installé) répond aux requêtes d’URL simples.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>URL simple pour les conférences publiées en interne – le serveur frontal (ou directeur, s’il est installé) répond aux requêtes d’URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>administration</p></td>
<td><p>Enregistrement facultatif, URL simple pour le panneau de configuration Lync Server 2013 publié en interne (ou directeur, s’il est installé) répond aux requêtes d’URL simples. Seul le nom de l’hôte (pas de nom de domaine) est recommandé.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = adresse IP virtuelle de l’équilibreur de la charge matérielle



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>Enregistrements DNS SRV pour le pool frontal


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
<td><p>_sipinternaltls _sipinternaltls._tcp. contoso. com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Nécessaire pour que la configuration automatique des clients Lync 2013 fonctionne en interne.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls _sipinternaltls._tcp. fabrikam. com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Nécessaire pour que la configuration automatique des clients Lync 2013 fonctionne en interne.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>SRV</p></td>
<td><p>_ntp _ntp._udp. contoso. com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Source NTP (Network Time Protocol) requise pour les appareils exécutant Lync Phone Edition. En interne, cet enregistrement doit pointer vers le contrôleur de domaine. Si le contrôleur de domaine n’est pas défini, l’enregistrement essaiera d’utiliser le serveur NTP time.windows.com</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

