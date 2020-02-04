---
title: Server Hardware Platforms pour Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95c8b0e9b1e13d845672cff07d30b7f2ac1a5b22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Server Hardware Platforms pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-07-28_

Les rôles serveur Lync Server 2013 et les ordinateurs exécutant des outils d’administration de Lync Server nécessitent 64 bits.

Le matériel spécifique utilisé pour le déploiement de Lync Server 2013 peut varier en fonction de la taille et de l’utilisation requise. Cette section décrit le matériel recommandé. Même s’il s’agit de recommandations, et non d’impératifs, l’utilisation de matériel ne respectant pas ces recommandations peut entraîner des baisses de performance significatives et d’autres problèmes.

<div>

## <a name="recommended-hardware-platform"></a>Plateforme matérielle recommandée

Pour des performances optimales, nous vous recommandons d’exécuter Lync Server sur les serveurs dotés du matériel qui répond aux conditions énoncées dans le tableau suivant. Si vous utilisez un matériel moins puissant, vous pouvez rencontrer des problèmes de fonctionnement ou des performances médiocres. Notez que la configuration matérielle requise est supérieure à celle des versions précédentes de Lync Server, principalement par le biais de Lync Server 2013, tous les serveurs frontaux exécutant SQL Server.

<div>


> [!NOTE]  
> L’Association de cartes réseau est prise en charge et doit être transparente pour Lync Server. Pour plus d’informations, reportez-vous à <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server ou Lync Server et à l’équipe des cartes réseau</A>.



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>Matériel recommandé pour les serveurs frontaux, les serveurs principaux, les serveurs Standard Edition Server, les serveurs de conversation permanente, le magasin de conversation permanente et le magasin de conformité de conversation permanente (rôles Serveur principal pour le serveur de conversation permanente)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant matériel</th>
<th>Recommandation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processeur</p></td>
<td><p>Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur.</p>
<p>Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>32 giga-octets (Go).</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><ul>
<li><p>8 disques durs ou plus 10 000 tr/min avec au moins 72 Go d’espace disponible. </p>
<p>Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.</p>
<p>-Ou</p></li>
<li><p>Disques SSD (Solid State Drive) qui fournissent des performances similaires à 8 disques durs mécaniques 10 000 tr/min.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul>
<li><p>1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP).</p>
<div>

> [!NOTE]  
> Les configurations à double ou à hébergement multiple ne sont pas prises en charge pour les serveurs frontaux, serveurs dorsaux, serveurs Standard Edition et serveurs de chat permanent.<BR>ILO/DRAC/etc. connexions non exposées au système d’exploitation et permettant de surveiller et de gérer le matériel du serveur ne constituent pas un serveur multi-résident et sont donc pris en charge.


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>Matériel recommandé pour les serveurs Edge, les serveurs de médiation autonomes et les directeurs

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant matériel</th>
<th>Recommandation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Processeur</p></td>
<td><ul>
<li><p>processeur double cœur, cadencé à 4 bits, 2,0 gigahertz (GHz) ou version ultérieure. 64</p>
<p>-Ou</p></li>
<li><p>processeur à 4 ou 4 processeurs cadencé à 4 ou 4 processeurs, 2,0 GHz ou supérieur. 64</p></li>
</ul>
<p>Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>16 gigaoctets (Go).</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><ul>
<li><p>4 Mo ou davantage de disques durs 10 000 RPM dotés d’au moins 72 Go d’espace libre sur le disque dur.</p>
<p>La configuration des disques doit être de type 2x RAID 1.</p>
<p>-Ou</p></li>
<li><p>Disques SSD (Solid State Drive) qui fournissent des performances similaires à 4 disques durs mécaniques 10 000 tr/min. </p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul>
<li><p>1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP). 2 interfaces réseau sont requises sur les serveurs Edge et sont prises en charge sur les serveurs de médiation autonomes.</p></li>
</ul>
<div>

> [!NOTE]  
> Les configurations à double ou à hébergement multiple ne sont pas prises en charge pour les directeurs.<BR>ILO/DRAC/etc. connexions non exposées au système d’exploitation et permettant de surveiller et de gérer le matériel du serveur ne constituent pas un serveur multi-résident et sont donc pris en charge.


</div>
<p>Les serveurs Edge requièrent deux interfaces réseau qui sont des cartes réseau à double-port, 1 Gbit/s ou une version ultérieure (ou deux cartes réseau couplées, pour un total de quatre, chaque paire étant associée à une adresse MAC unique et une seule adresse IP, pour un total de deux paires).</p>
<p>L’installation de cartes d’interface réseau supplémentaires (NIC) pour permettre la configuration d’une adresse IP RTC spécifique est prise en charge sur les serveurs de médiation autonomes.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

