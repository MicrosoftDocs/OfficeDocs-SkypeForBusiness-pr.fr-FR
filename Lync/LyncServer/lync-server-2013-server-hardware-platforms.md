---
title: Plateformes matérielles de serveur Lync Server 2013
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
ms.openlocfilehash: ddcfc08ff983ec080bd2382394bfc4b8c3bae3a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Plateformes matérielles de serveur pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-07-28_

Les rôles serveur Lync Server 2013 et les ordinateurs exécutant des outils d’administration Lync Server requièrent du matériel 64 bits.

Le matériel spécifique utilisé pour le déploiement de Lync Server 2013 peut varier en fonction de la taille et des besoins d’utilisation. Cette section décrit le matériel recommandé. Bien qu’il s’agisse de recommandations, et non d’impératifs, l’utilisation de matériel ne respectant pas ces recommandations peut entraîner des baisses de performance significatives et d’autres problèmes.

<div>

## <a name="recommended-hardware-platform"></a>Plateforme matérielle recommandée

Pour de meilleures performances, nous vous recommandons d’exécuter Lync Server sur des serveurs dotés de matériel répondant aux exigences indiquées dans le tableau suivant. Si vous utilisez un matériel moins puissant, vous pouvez rencontrer des problèmes de fonctionnement ou des performances médiocres. Notez que la configuration matérielle requise est supérieure à celle des versions précédentes de Lync Server, principalement parce que dans Lync Server 2013, tous les serveurs frontaux exécutent SQL Server.

<div>


> [!NOTE]  
> L’Association de cartes réseau est prise en charge et doit être transparente pour Lync Server. Pour plus d’informations, reportez-vous à <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server ou Lync Server et cartes réseau</A>.



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>Matériel recommandé pour les serveurs frontaux, les serveurs principaux, les serveurs Standard Edition, les serveurs de conversation permanente et le magasin de conversation permanente et le magasin de conformité de conversation permanente (rôles de serveur principal pour le serveur de conversation permanente)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant matériel</th>
<th>Recommandé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UC</p></td>
<td><p>biprocesseur de 64 bits, hex-Core, 2,26 gigahertz (GHz) ou supérieur.</p>
<p>Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>32 gigaoctets (Go).</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><ul>
<li><p>8 disques durs ou plus 10 000 tours/minute avec au moins 72 Go d’espace disponible.</p>
<p>Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.</p>
<p>-Des</p></li>
<li><p>Disques SSD (Solid State Drive) qui fournissent des performances similaires à 8 disques durs mécaniques 10 000 tours/minute.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul>
<li><p>1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’Association à une seule adresse MAC et une seule adresse IP).</p>
<div>

> [!NOTE]  
> Les configurations double ou multi-résidents ne sont pas prises en charge pour les serveurs frontaux, les serveurs principaux, les serveurs Standard Edition Server et les serveurs de conversation permanente.<BR>ILO/DRAC/etc. les connexions non exposées au système d’exploitation et utilisées pour surveiller et gérer le matériel de serveur ne constituent pas un serveur multi-hébergement et sont donc prises en charge.


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
<th>Recommandé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UC</p></td>
<td><ul>
<li><p>Double processeur 64 bits, quadruple cœur, 2,0 gigahertz (GHz) ou supérieur.</p>
<p>-Des</p></li>
<li><p>processeur 4 ou 4 voies, double cœur, 2,0 GHz ou supérieur. 64</p></li>
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
<li><p>4 disques durs ou plus 10 000 RPM avec au moins 72 Go d’espace disque disponible.</p>
<p>Les disques doivent se trouver dans une configuration 2x RAID 1.</p>
<p>-Des</p></li>
<li><p>Disques SSD (Solid State Drive) qui fournissent des performances similaires à 4 disques durs mécaniques 10 000 tours/minute.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul>
<li><p>1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’Association à une seule adresse MAC et une seule adresse IP). 2 les interfaces réseau sont requises sur les serveurs Edge et sont prises en charge sur les serveurs de médiation autonomes.</p></li>
</ul>
<div>

> [!NOTE]  
> Les configurations Dual ou multi-hébergement ne sont pas prises en charge pour les directeurs.<BR>ILO/DRAC/etc. les connexions non exposées au système d’exploitation et utilisées pour surveiller et gérer le matériel de serveur ne constituent pas un serveur multi-hébergement et sont donc prises en charge.


</div>
<p>Les serveurs Edge nécessitent deux interfaces réseau qui sont des cartes réseau à deux ports, 1 Gbits/s ou supérieur (ou deux cartes réseau couplées, pour un total de quatre, chaque paire étant associée à une seule adresse MAC et une seule adresse IP, pour un total de deux paires).</p>
<p>L’installation de cartes d’interface réseau (NIC) supplémentaires pour permettre la configuration d’une adresse IP RTC spécifique est prise en charge sur les serveurs de médiation autonomes.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

