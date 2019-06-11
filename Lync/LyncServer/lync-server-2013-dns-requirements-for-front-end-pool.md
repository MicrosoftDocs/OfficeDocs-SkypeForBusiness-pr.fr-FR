---
title: 'Lync Server 2013 : Enregistrements DNS requis pour le pool frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Enregistrements DNS requis pour le pool frontal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-07_

Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe administrateurs de domaine ou membre du groupe DnsAdmins.

Vous devez configurer les enregistrements DNS (Domain Name System) requis avant de publier votre topologie dans le générateur de topologie. De plus, certains noms de domaine complets (FQDN) utilisés dans la configuration d’un déploiement de Lync Server 2013 sont logiques et non des noms de domaine complets de serveur physique; c’est pourquoi une configuration DNS supplémentaire est requise avant la publication.

<div>


> [!WARNING]  
> Lync Server 2013 ne prend pas en charge les domaines à mention unique. Par exemple, une forêt avec un domaine racine appelé <STRONG>contoso. local</STRONG> est prise en charge, mais un domaine racine nommé <STRONG>local</STRONG> n’est pas pris en charge. Pour plus d’informations, reportez-vous à l’article 300684 de la base de connaissances Microsoft, intitulé «informations sur la configuration de Windows pour les domaines avec les noms DNS en une seule étiquette» <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp, kbid = 300684</A>.



</div>

<div>


> [!IMPORTANT]  
> Le nom spécifié doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom de l’ordinateur d’un ordinateur qui n’est pas joint à un domaine est un nom court qui n’est pas un nom de domaine complet. Le générateur de topologie utilise des noms de domaine complets plutôt que des noms courts. <STRONG>Utiliser uniquement les caractères standard</STRONG> (y compris A – Z, a – z, 0 à 9 et les traits d’Union) lors de l’affectation des noms de domaine complets de vos serveurs exécutant Lync Server, serveurs Edge et pools. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans un nom de domaine complet ne sont généralement pas pris en charge par les autorités de certification DNS et publiques externes (lorsque le nom de domaine complet doit être attribué à l’SN dans le certificat).



</div>

Avant d’activer la topologie après le déploiement de celle-ci, vérifiez que les enregistrements DNS et Active Directory suivants sont créés (à mesure que vous avez besoin de fonctionnalités spécifiques dictées):

  - Chaque rôle de serveur existant dans la topologie est publié en tant qu’objet Active Directory (si vous rejoignez l’ordinateur au domaine).

  - Un enregistrement DNS A existe pour chaque serveur.

  - Un enregistrement SRV DNS existe pour chaque domaine SIP si vous envisagez d’utiliser l’ouverture de session automatique pour \_les\_clients sous la forme de TCP sipinternaltls. \<Domaine\>SIP. Si vous allez utiliser la configuration manuelle pour les clients, cet enregistrement n’est pas nécessaire.

  - Un enregistrement DNS A pour chaque URL simple configurée qui comporte généralement quatre éléments: réunion, Dial, LWA et Scheduler. De plus, il existe une URL simple d’administration, qui est une URL spéciale pour l’accès au panneau de configuration de Lync Server 2013.

  - Le serveur exécutant SQL Server doit être joint au domaine et joignable par l’ordinateur à partir duquel le générateur de topologie publie.

Le tableau suit les architectures de référence présentées dans la section Planning. Pour plus d’informations, reportez-vous à la rubrique [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) dans la documentation de planification.

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
<th>Cartes sur/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (équilibrage de charge DNS). Il est nécessaire de disposer d’un enregistrement DNS A pour l’adresse IP de chaque serveur frontal au sein du pool et de mapper le nom de domaine complet du pool.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (adresse IP virtuelle de l’équilibrage de charge matérielle).</p></td>
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
<td><p>Pool01 (VIP) pour le trafic Web de client à serveur.</p></td>
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
<td><p>Requis pour Lync Phone Edition ou l’ouverture de session automatique de clients sans enregistrements DNS SRV, et pour une concordance de domaine stricte. Ce n’est pas obligatoire dans tous les cas.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>Suppose un deuxième domaine SIP. Requis pour Lync Phone Edition, l’ouverture de session automatique de clients sans enregistrements DNS SRV et pour une concordance de domaine stricte. Ce n’est pas obligatoire dans tous les cas.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>URL simple pour les conférences rendez-vous publiées en interne-serveur frontal (ou directeur, le cas échéant) répond aux requêtes d’URL simples.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>URL simple pour les conférences publiées en interne-serveur frontal (ou réalisateur, le cas échéant) répond aux requêtes d’URL simples.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>administrateur</p></td>
<td><p>Enregistrement facultatif, URL simple pour le panneau de configuration de Lync Server 2013 publié en interne (ou Director, s’il est installé) répond aux requêtes d’URL simples. Nom d’hôte uniquement (il n’y a pas de nom de domaine) recommandé.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = adresse IP virtuelle pour le système d’équilibrage de la charge matérielle



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>Enregistrements SRV DNS pour le pool frontal


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
<th>Nom de domaine complet cible</th>
<th>Port</th>
<th>Cartes sur/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _ TCP. contoso. com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>Requis pour la configuration automatique des clients 2013 Lync pour fonctionner en interne.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls. _ TCP. fabrikam. com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>Requis pour la configuration automatique des clients 2013 Lync pour fonctionner en interne.</p></td>
</tr>
<tr class="odd">
<td><p>DNS interne</p></td>
<td><p>SRV</p></td>
<td><p>_ntp._udp.contoso.com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>Source d’horloge réseau (NTP) requise pour les appareils exécutant Lync Phone Edition. En interne, cela doit pointer sur le contrôleur de domaine. Si le contrôleur de domaine n’est pas défini, il essaiera d’utiliser le serveur NTP time.windows.com.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

