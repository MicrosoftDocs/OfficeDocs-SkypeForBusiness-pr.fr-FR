---
title: Planification de la capacité de Lync Server 2013 à l’aide des modèles utilisateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d315de4f8b18a5ecbeabe7ba29231c70ff893e8a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508141"
---
# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>Planification de la capacité pour Lync Server 2013 à l’aide des modèles utilisateur

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-01-14_

Cette section fournit des instructions sur le nombre de serveurs dont vous avez besoin sur un site pour le nombre d’utilisateurs sur ce site, en fonction de l’utilisation décrite dans [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).

<div>

## <a name="tested-hardware-platform"></a>Plateforme matérielle testée

Tous les résultats de performances et les recommandations de déploiement de cette section sont basés sur les tests de performances sur les serveurs qui exécutent le matériel décrit dans le tableau suivant. Nous vous recommandons d’utiliser un matériel similaire. Si vous utilisez un matériel moins puissant, vous pouvez rencontrer des problèmes de fonctionnement ou des performances médiocres. Notez que ces recommandations matérielles sont plus élevées que celles des versions précédentes de Lync Server.

### <a name="hardware-used-in-performance-testing"></a>Matériel utilisé dans les tests de performances

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
<td><p>Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur</p>
<p>Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>32 Go</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><ul>
<li><p>8 disques durs 10 000-RPM avec au moins 72 Go d’espace disque disponible.</p>
<p>Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.</p>
<p>- Des</p></li>
<li><p>Disques SSD (Solid State Drive) qui fournissent des performances similaires à 8 disques durs mécaniques 10 000 tours/minute.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul>
<li><p>1 carte réseau double port, 1 Gbps ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a>Résumé des résultats

Le tableau suivant résume ces recommandations.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Rôle serveur</th>
<th>Nombre maximal d’utilisateurs pris en charge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Pool frontal avec douze serveurs frontaux et un serveur principal ou une paire de serveurs principaux en miroir.</p></td>
<td><p>80 000 utilisateurs uniques connectés simultanément, plus 50% de points de présence multiples (MPOP) représentant des instances non mobiles, plus 40% d’utilisateurs activés pour la mobilité pour un total de 152 000 points de terminaison.</p></td>
</tr>
<tr class="even">
<td><p>Conférence A/V</p></td>
<td><p>Le service de conférence A/V fourni par un pool frontal prend en charge les conférences du pool en supposant une taille maximale de conférence de 250 utilisateurs, et une seule de ces grandes conférences en cours d’exécution à la fois.</p>
<div>

> [!NOTE]  
> En outre, vous pouvez prendre en charge des conférences importantes entre 250 et 1000 utilisateurs en déployant un pool frontal distinct avec deux serveurs frontaux pour héberger les grandes conférences. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-supporting-large-meetings.md">prise en charge de grandes réunions à l’aide de Lync Server 2013</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Un serveur Edge</p></td>
<td><p>12 000 utilisateurs distants simultanés</p></td>
</tr>
<tr class="even">
<td><p>Un directeur</p></td>
<td><p>12 000 utilisateurs distants simultanés</p></td>
</tr>
<tr class="odd">
<td><p>Surveillance et archivage</p></td>
<td><p>Dans Lync Server 2013, les services frontaux de surveillance et d’archivage s’exécutent désormais sur chaque serveur frontal, et non sur des rôles serveur distincts.</p>
<p>La surveillance et l’archivage nécessitent toujours leurs propres magasins de base de données. Si vous exécutez également Exchange 2013, vous pouvez conserver vos données d’archivage dans Exchange, plutôt que dans une base de données SQL dédiée.</p></td>
</tr>
<tr class="even">
<td><p>Un serveur de médiation</p></td>
<td><p>Le serveur de médiation colocalisé avec le serveur frontal s’exécute sur chaque serveur frontal d’un pool et doit fournir une capacité suffisante pour les utilisateurs du pool. Pour un serveur de médiation autonome, consultez la section « serveur de médiation » plus loin dans cette rubrique.</p></td>
</tr>
<tr class="odd">
<td><p>Un serveur Standard Edition Server</p></td>
<td><p>Si vous utilisez des serveurs Standard Edition pour héberger des utilisateurs, nous vous recommandons vivement d’utiliser deux serveurs, associés à l’aide des recommandations de <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</a>. Chaque serveur de la paire peut héberger jusqu’à 2 500 utilisateurs et, si un serveur échoue, le serveur restant peut prendre en charge 5 000 utilisateurs dans un scénario de basculement.</p>
<p>Si votre déploiement inclut une quantité importante de trafic audio ou vidéo, les performances du serveur peuvent être affectées à plus de 2 500 utilisateurs par serveur. Dans ce cas, vous devez envisager d’ajouter des serveurs Standard Edition ou de passer à Lync Server Enterprise Edition.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>serveur frontal

<div>


> [!NOTE]  
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.



</div>

Dans un pool frontal, vous devez disposer d’un serveur frontal pour tous les 6 660 utilisateurs hébergés dans le pool, en supposant que la technologie Hyper-Threading est activée sur tous les serveurs du pool et que le matériel du serveur répond aux recommandations dans les [plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md). Le nombre maximal d’utilisateurs dans un pool frontal est de 80 000, en supposant que la technologie Hyper-Threading est activée sur tous les serveurs du pool. Si vous avez plus de 80 000 utilisateurs sur un site, vous pouvez déployer plusieurs pools frontaux.

Lorsque vous comptez le nombre d’utilisateurs d’un pool frontal, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à ce pool frontal.

Lorsqu’un serveur actif est indisponible, ses connexions sont transférées automatiquement aux autres serveurs du pool. Par exemple, si vous avez 30 000 utilisateurs et cinq serveurs frontaux, si un serveur est indisponible, les connexions de 6000 doivent être transférées vers les quatre autres serveurs. Les quatre serveurs restants auront chacun 7500 utilisateurs, ce qui est plus grand que recommandé.

Si, au lieu de cela, vous avez commencé avec six serveurs frontaux pour vos utilisateurs de 30 000 et que l’autre est devenu indisponible, un total de 5000 utilisateurs seront déplacés vers les cinq serveurs restants. Ces cinq serveurs sont tous les utilisateurs de l’hôte 6000, qui se trouvent dans la plage recommandée.

Le nombre maximal d’utilisateurs dans un pool frontal est de 80 000. Le nombre maximal de serveurs frontaux dans un pool est de 12.

Pour un pool frontal avec des utilisateurs 80 000, douze serveurs frontaux sont suffisants pour les performances, dans des déploiements classiques qui suivent les [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md). Les déploiements conçus pour prendre en charge le basculement de récupération d’urgence supposent qu’un maximum de 40 000 utilisateurs peuvent être hébergés dans chacun des deux pools frontaux couplés, où chaque pool dispose de serveurs frontaux suffisants pour accueillir les utilisateurs des deux pools en cas de nécessité de basculement d’un pool vers l’autre.

Le nombre d’utilisateurs pris en charge avec de bonnes performances par un pool frontal particulier peut différer de ces chiffres pour les raisons suivantes :

  - Le matériel de vos serveurs frontaux ne répond pas aux recommandations des [plateformes matérielles de serveur pour Lync server 2013](lync-server-2013-server-hardware-platforms.md).

  - L’utilisation de votre organisation diffère de manière significative de celle des modèles utilisateur, en raison d’un trafic de conférence plus important par exemple.

<div>


> [!IMPORTANT]  
> Dans Lync Server 2013, les bases de données de présence sont désormais hébergées sur des serveurs frontaux, contrairement à Lync Server 2010 où elles étaient hébergées sur le serveur principal. Cela signifie que les performances de disque et la capacité de vos serveurs frontaux ne doivent pas être compromises par les recommandations répertoriées plus haut dans cette section et dans les <A href="lync-server-2013-server-hardware-platforms.md">plateformes matérielles de serveur pour Lync Server 2013</A>, quel que soit le nombre d’utilisateurs hébergés par vos serveurs frontaux.



</div>

Le tableau suivant indique la bande passante moyenne pour la messagerie instantanée et la présence, étant donné le modèle utilisateur, tel qu’il est défini dans [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Bande passante moyenne par utilisateur</th>
<th>Besoins en bande passante par serveur frontal avec 6 660 utilisateurs</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1,3 Kbits/s</p></td>
<td><p>13 Mbits/s</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Pour améliorer les performances multimédia de la fonctionnalité de conférence A/V et du serveur de médiation colocalisée sur vos serveurs frontaux, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau de vos serveurs frontaux. RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur. Pour plus d’informations, reportez-vous à la section « améliorations de l’évolutivité côté réception dans Windows Server 2008 » à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> . Pour plus d’informations sur l’activation de RSS, consultez la documentation de votre carte réseau.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>Nombre maximal de conférences

Selon le modèle utilisateur, 5 % des utilisateurs d’un pool peuvent assister à une conférence en même temps, donc un pool de 80 000 utilisateurs peut avoir 4 000 utilisateurs en conférence simultanément. Ces conférences sont supposées être composées d’un mélange de plusieurs médias (messagerie instantanée uniquement, messagerie instantanée avec audio, audio/vidéo par exemple) et du nombre de participants. Il n’existe pas de limite inconditionnelle au nombre réel de conférences autorisées, et l’utilisation réelle détermine les performances réelles. Par exemple, si le nombre de conférences en mode mixte dans votre organisation est anormalement élevé par rapport au modèle utilisateur, vous devrez peut-être déployer un nombre de serveurs frontaux et de serveurs de conférence A/V plus important que celui recommandé dans ce document. Pour plus d’informations sur les hypothèses du modèle utilisateur, voir [User Models in Lync Server 2013](lync-server-2013-user-models.md).

La taille de conférence maximale prise en charge par un pool frontal Lync Server 2013 classique qui héberge également les utilisateurs est de 250 participants. Pendant une conférence de 250 utilisateurs, le pool prend toujours en charge d’autres conférences, de sorte qu’un total de 5% des utilisateurs du pool se trouvent dans des conférences simultanées. Par exemple, dans un pool de douze serveurs frontaux et 80 000 utilisateurs, tandis que la Conférence utilisateur 250 se produit, Lync Server prend en charge 3 750 autres utilisateurs participant à des conférences plus petites.

Quel que soit le nombre d’utilisateurs hébergés sur le pool frontal ou le serveur Standard Edition, Lync Server prend en charge un minimum de 125 autres utilisateurs participant à des conférences plus petites sur le même pool ou serveur qui héberge une conférence de 250 utilisateurs.

Pour activer les conférences avec des utilisateurs entre 250 et 1000, vous pouvez configurer un pool frontal distinct pour héberger ces conférences. Ce pool frontal n’héberge aucun utilisateur. Pour plus d’informations, consultez la rubrique [prise en charge de grandes réunions à l’aide de Lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Si votre organisation a de nombreuses conférences en mode mixte que celles supposées dans le modèle utilisateur, vous devrez peut-être déployer davantage de serveurs frontaux que les recommandations de ce document (jusqu’à une limite de 12 FEs). Pour plus d’informations sur les hypothèses du modèle utilisateur, voir [User Models in Lync Server 2013](lync-server-2013-user-models.md).

</div>

<div>

## <a name="edge-server"></a>Serveur Edge

<div>


> [!NOTE]  
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.



</div>

Vous devez déployer un serveur Edge pour chaque 12 000 utilisateurs distants qui accèdent simultanément à un site. Nous vous conseillons au moins deux serveurs Edge pour une disponibilité élevée. Ces recommandations supposent que le matériel de vos serveurs Edge répond aux recommandations des [plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Lorsque vous comptez le nombre d’utilisateurs pour les serveurs Edge, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à un pool frontal sur ce site.

<div>


> [!NOTE]  
> Pour améliorer les performances du service Edge de conférence A/V sur vos serveurs Edge, vous devez activer le partage du trafic entrant (RSS, Receive-Side Scaling) sur les cartes réseau de vos serveurs Edge. RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur. Pour plus d’informations, reportez-vous à la section « améliorations de l’évolutivité côté réception dans Windows Server 2008 » à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> . Pour plus d’informations sur l’activation de RSS, consultez la documentation de votre carte réseau.



</div>

</div>

<div>

## <a name="director"></a>Directeur

<div>


> [!NOTE]  
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.



</div>

Si vous déployez le rôle de serveur Directeur, nous vous recommandons de déployer un directeur pour chaque 12 000 utilisateurs distants qui accèdent simultanément à un site. Nous vous conseillons au moins deux directeurs pour une disponibilité élevée. Ces recommandations supposent que le matériel de vos serveurs Edge répond aux recommandations des [plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Lorsque vous comptez le nombre d’utilisateurs pour les directeurs, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à un pool frontal sur ce site.

</div>

<div>

## <a name="mediation-server"></a>Serveur de médiation

<div>


> [!NOTE]  
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.



</div>

Si vous colocaliser serveur de médiation avec un serveur frontal, le serveur de médiation s’exécute sur chaque serveur frontal du pool et doit fournir une capacité suffisante pour les utilisateurs du pool.

Si vous déployez un pool de serveurs de médiation autonome, le nombre de serveurs de médiation à déployer dépend de nombreux facteurs, dont le matériel utilisé pour le serveur de médiation, le nombre d’utilisateurs VoIP dont vous disposez, le nombre d’homologues de passerelle que chaque pool de serveurs de médiation contrôle, le trafic d’heures de sollicitation via ces passerelles et le pourcentage d’appels avec des médias qui

Les tableaux suivants fournissent une indication du nombre d’appels simultanés qu’un serveur de médiation peut gérer, en supposant que le matériel pour les serveurs de médiation répond aux exigences des [plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) et que la technologie Hyper-Threading soit activée. Pour plus d’informations sur l’extensibilité du serveur de médiation, voir [estimation de l’utilisation et du trafic vocaux pour Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) et [les instructions de déploiement pour le serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Tous les tableaux ci-dessous présupposent une utilisation telle que résumée dans les [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>Capacité de serveur de médiation autonome : 70% d’utilisateurs internes, 30% d’utilisateurs externes avec une capacité d’appel sans contournement (transcodage multimédia effectué par le serveur de médiation)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Matériel serveur</th>
<th>Nombre maximal d’appels</th>
<th>Nombre maximal de lignes T1</th>
<th>Nombre maximal de lignes E1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Double processeur, principal, cadencé à 2,26 GHz <strong>avec Hyper-Threading désactivé</strong>, avec une mémoire de 32 Go et une carte réseau double port.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>Dual Processor, hex Core, processeur Hyper-Threading 2,26 GHz, 1 32 Go de mémoire et une carte réseau double port.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Bien que des serveurs dotés de 32 Go de mémoire aient été utilisés pour tester les performances, les serveurs ayant 16 Go de mémoire sont pris en charge pour un serveur de médiation autonome et sont suffisants pour fournir les performances indiquées dans ce tableau.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>Capacité du serveur de médiation (serveur de médiation colocalisé avec le serveur frontal) 70% d’utilisateurs internes, 30% d’utilisateurs externes, capacité d’appel sans contournement (traitement multimédia effectué par le serveur de médiation)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Matériel serveur</th>
<th>Nombre maximal d’appels</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dual Processor, hex Core, processeur Hyper-Threading 2,26 GHz, avec une mémoire de 32 Go et 2 cartes réseau 1 Go.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Ce nombre est plus petit que les numéros pour le serveur de médiation autonome car le serveur frontal doit gérer d’autres fonctionnalités et fonctions pour les 6600 utilisateurs hébergés dessus, en plus du transcodage nécessaire pour les appels vocaux.



</div>

<div>


> [!NOTE]  
> Pour améliorer les performances du serveur de médiation, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau de vos serveurs de médiation. RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur. Pour plus d’informations, reportez-vous à la section « améliorations de l’évolutivité côté réception dans Windows Server 2008 » à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> . Pour plus d’informations sur l’activation de RSS, consultez la documentation de votre carte réseau.



</div>

</div>

<div>

## <a name="back-end-server"></a>serveur principal

Dans Lync Server 2013, les bases de données de présence se trouvent sur les serveurs frontaux et non sur le serveur principal. Cela a permis une configuration plus simple pour chaque serveur principal de Lync Server 2013, ce qui équivaut à la configuration matérielle requise pour le serveur frontal. À la différence de Lync Server 2010, le serveur principal devait être un serveur de plus grande qualité avec 25 disques. Toutefois, la charge de travail des serveurs principaux est toujours telle que vous ne devriez pas ne pas faire face aux recommandations matérielles répertoriées plus haut dans cette section et dans les [plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Pour fournir une haute disponibilité de votre serveur principal, nous vous recommandons de déployer la mise en miroir du serveur. Pour plus d’informations, reportez-vous à la rubrique [back end Server High Availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).

</div>

<div>

## <a name="monitoring-and-archiving"></a>Surveillance et archivage

Dans Lync Server 2013, si vous déployez la surveillance ou l’archivage, les fonctionnalités frontales de ces services s’exécutent sur les serveurs frontaux, et non sur des rôles serveur distincts. La surveillance et l’archivage utilisent toujours leur propre magasin de bases de données, distinct du magasin principal. Sinon, si vous avez déployé Exchange 2013, vous pouvez stocker les données d’archivage des messages instantanés dans Exchange au lieu d’un magasin SQL dédié.

Le tableau suivant indique approximativement la proportion de stockage de base de données requise par utilisateur et par jour pour les données de surveillance et d’archivage.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>CDR (surveillance)</strong></p></td>
<td><p><strong>QoE (surveillance)</strong></p></td>
<td><p><strong>Archivage</strong></p></td>
</tr>
<tr class="even">
<td><p>Espace disque requis par utilisateur et par jour</p></td>
<td><p>49 KO</p></td>
<td><p>28 KO</p></td>
<td><p>57 KO</p></td>
</tr>
</tbody>
</table>


Microsoft a utilisé le matériel du tableau suivant pour le serveur de base de données pour la surveillance et l’archivage pendant le test des performances. Les tests ont collecté les données de deux pools frontaux, chacun contenant 80 000 utilisateurs.

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>Matériel utilisé dans les tests de performances de surveillance et d’archivage

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
<td><p>Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur</p></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>48 gigaoctets (Go)</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><p>disques durs 25 10 000-RPM avec 300 Go sur chaque disque, avec la configuration suivante</p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Drive</strong></p></td>
<td><p><strong>Configuration RAID</strong></p></td>
<td><p><strong>Nombre de disques</strong></p></td>
</tr>
<tr class="even">
<td><p>Fichiers de données de base de données d’archivage, d’enregistrement des détails des appels, QoE et archivage, sur un seul lecteur</p></td>
<td><p>1 + 0</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>Fichier journal de la base de données d’enregistrement des détails des appels</p></td>
<td><p>0,1</p></td>
<td><p>n°2</p></td>
</tr>
<tr class="even">
<td><p>Fichier journal de la base de données QoE</p></td>
<td><p>0,1</p></td>
<td><p>n°2</p></td>
</tr>
<tr class="odd">
<td><p>Fichier journal de la base de données d’archivage</p></td>
<td><p>0,1</p></td>
<td><p>n°2</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul>
<li><p>1 carte réseau double port, 1 Gbps ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Estimation du trafic et de l’utilisation de la voix pour Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Instructions de déploiement pour le serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

