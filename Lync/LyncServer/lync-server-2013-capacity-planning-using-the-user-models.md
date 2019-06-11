---
title: Planification de la capacité de Lync Server 2013 à l’aide des modèles utilisateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b7db58e8c6f3e84f95a51ddd393ddca5ec18091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>Planification de la capacité de Lync Server 2013 à l’aide des modèles utilisateur

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-01-14_

Cette section fournit des recommandations sur le nombre de serveurs dont vous avez besoin sur un site pour le nombre d’utilisateurs sur ce site, en fonction de l’utilisation décrite dans la rubrique [modèles d’utilisateur de Lync Server 2013](lync-server-2013-user-models.md).

<div>

## <a name="tested-hardware-platform"></a>Plateforme matérielle testée

Tous les résultats de performance et recommandations de déploiement de cette section sont basés sur le test de performance sur les serveurs exécutant le matériel décrit dans le tableau suivant. Nous vous recommandons d’utiliser un matériel similaire. Si vous utilisez un matériel moins puissant, vous pouvez rencontrer des problèmes de fonctionnement ou des performances médiocres. Notez que ces recommandations en matière de matériel sont supérieures à celles des versions précédentes de Lync Server.

### <a name="hardware-used-in-performance-testing"></a>Matériel utilisé dans les tests de performances

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
<td><p>Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur</p>
<p>Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>32 gigaoctets (Go)</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><ul>
<li><p>8 disques durs ou plus 10 000 tr/min avec au moins 72 Go d’espace disponible.</p>
<p>Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.</p>
<p>-Ou</p></li>
<li><p>Disques SSD (Solid State Drive) qui fournissent des performances similaires à 8 disques durs mécaniques 10 000 tr/min.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul>
<li><p>1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)</p></li>
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
<td><p>Pool frontal avec douze serveurs front-end et un serveur principal ou paire en miroir de serveurs dorsaux.</p></td>
<td><p>80 000 utilisateurs uniques connectés simultanément, plus 50 % de points de présence multiples (MPOP) représentant des instances non mobiles, plus 40 % d’utilisateurs activés pour la mobilité pour un total de 152 000 points de terminaison.</p></td>
</tr>
<tr class="even">
<td><p>Conférence A/V</p></td>
<td><p>Le service de conférence A/V fourni par un pool frontal prend en charge les conférences du pool en supposant la taille maximale d’une conférence d’utilisateurs 250, et une seule conférence de grande envergure exécutée à la fois.</p>
<div>

> [!NOTE]  
> De plus, vous pouvez prendre en charge des conférences de grande envergure entre les utilisateurs de 250 et de 1000 en déployant un pool frontal distinct avec deux serveurs front-end pour héberger les conférences de grande envergure. Pour plus d’informations, consultez <A href="lync-server-2013-supporting-large-meetings.md">prise en charge de grandes réunions à l’aide de Lync Server 2013</A>.


</div></td>
</tr>
<tr class="odd">
<td><p>Un serveur Edge</p></td>
<td><p>12 000 utilisateurs distants concurrents</p></td>
</tr>
<tr class="even">
<td><p>Un réalisateur</p></td>
<td><p>12 000 utilisateurs distants concurrents</p></td>
</tr>
<tr class="odd">
<td><p>Surveillance et archivage</p></td>
<td><p>Dans Lync Server 2013, les services front-end d’analyse et d’archivage s’exécutent désormais sur chaque serveur frontal, et non sur des rôles serveur distincts.</p>
<p>La surveillance et l’archivage requièrent un magasin de base de données chacun. Si vous exécutez également Exchange 2013, vous pouvez conserver vos données d’archivage dans Exchange, au lieu d’une base de données SQL dédiée.</p></td>
</tr>
<tr class="even">
<td><p>Un serveur de médiation</p></td>
<td><p>Le serveur de médiation en fonction du serveur frontal s’exécute sur chaque serveur frontal d’un pool et doit fournir une capacité suffisante aux utilisateurs de la liste. Pour un serveur de médiation autonome, voir la section «serveur de médiation» plus loin dans cette rubrique.</p></td>
</tr>
<tr class="odd">
<td><p>One Standard Edition Server</p></td>
<td><p>Nous vous recommandons vivement de recourir à des serveurs Standard Edition pour héberger les utilisateurs, que vous utilisez toujours deux serveurs, associés à des recommandations en <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">matière de planification de haute disponibilité et de récupération d’urgence dans Lync Server 2013</a>. Chaque serveur dans la paire peut accueillir jusqu’à 2 500 utilisateurs et, si un serveur tombe en panne, le serveur restant peut prendre en charge les utilisateurs 5 000 dans le cas d’un basculement.</p>
<p>Si votre déploiement présente un trafic audio ou vidéo important, les performances du serveur peuvent être affectées avec plus de 2 500 utilisateurs par serveur. Dans ce cas, envisagez d’ajouter d’autres serveurs Standard Edition ou de migrer vers Lync Server Enterprise Edition.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>serveur frontal

<div>


> [!NOTE]  
> Les pools étirés ne sont pas pris en charge pour ce rôle de serveur.



</div>

Dans un pool frontal, vous devez disposer d’un serveur frontal pour chaque 6 660 hébergé dans le pool, en partant du principe que la technologie hyperthreading est activée sur tous les serveurs du pool et que le matériel du serveur répond aux recommandations des [plateformes matérielles pour Lync. Server 2013](lync-server-2013-server-hardware-platforms.md). Le nombre maximal d’utilisateurs dans une liste frontale est de 80 000, en supposant que la technologie hyperthreading est activée sur tous les serveurs du pool. Si vous avez plus d’utilisateurs 80 000 sur un site, vous pouvez déployer plusieurs pools front-end.

Lorsque vous comptez le nombre d’utilisateurs dans un pool frontal, incluez les utilisateurs sur les appareils de succursales Survivables et les serveurs de succursales Survivables dans les succursales associées à ce pool frontal.

Lorsqu’un serveur actif est indisponible, ses connexions sont transférées automatiquement vers les autres serveurs du pool. Par exemple, si vous avez 30 000 utilisateurs et cinq serveurs frontaux, si un serveur n’est pas disponible, les connexions des utilisateurs 6000 doivent être transférées vers les quatre autres serveurs. Les quatre serveurs restants disposent chacun de 7500 utilisateurs, ce qui correspond à un nombre supérieur à celui recommandé.

Si, au lieu de cela, vous avez commencé à utiliser six serveurs front-end pour vos utilisateurs 30 000, le nombre total d’utilisateurs 5000 sera déplacé sur les cinq autres serveurs. Ces cinq serveurs seront chacun des utilisateurs de 6000, qui se trouve dans la plage recommandée.

Le nombre maximal d’utilisateurs dans une liste frontale est de 80 000. Le nombre maximal de serveurs frontaux dans un pool est de 12.

Dans le cas d’un pool frontal avec des utilisateurs 80 000, douze serveurs frontaux sont suffisants pour les performances, dans les déploiements standard qui suivent les [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md). Les déploiements conçus pour prendre en charge le basculement de reprise après sinistre présupposent qu’un maximum de 40 000 utilisateurs peuvent être hébergés dans chacun des deux pools frontaux couplés, dans lesquels chaque pool dispose d’un serveur frontal suffisant pour répondre aux besoins des utilisateurs dans les deux pools doit être en échec. sur l’autre.

Le nombre d’utilisateurs pris en charge avec une bonne performance par un pool frontal particulier peuvent différer de ces numéros pour les raisons suivantes:

  - Le matériel de votre serveur frontal ne répond pas aux recommandations des [plateformes matérielles pour Lync server 2013](lync-server-2013-server-hardware-platforms.md).

  - L’utilisation de votre organisation diffère considérablement de celle des modèles utilisateur, par exemple un trafic de conférences plus important.

<div>


> [!IMPORTANT]  
> Dans Lync Server 2013, les bases de données de présence sont désormais hébergées sur des serveurs frontaux, contrairement à Lync Server 2010 où elles étaient hébergées sur le serveur principal. En d’autres termes, il n’est pas possible de violer les performances et la capacité de votre serveur frontal grâce aux recommandations indiquées dans cette section et dans les <A href="lync-server-2013-server-hardware-platforms.md">plates-formes matérielles pour Lync server 2013</A>, quel que soit le nombre d’utilisateurs hébergés par vos serveurs frontaux.



</div>

Le tableau suivant indique la bande passante moyenne pour la messagerie instantanée et la présence, en fonction du modèle utilisateur, tel qu’il est défini dans [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Bande passante moyenne par utilisateur</th>
<th>Besoins en bande passante par serveur frontal avec les utilisateurs 6 660</th>
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
> Pour améliorer les performances multimédias de la fonctionnalité de conférence A/V et de médiation du serveur de médiation sur votre serveur frontal, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur vos serveurs frontaux. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez la section «améliorations apportées à l’évolutivité du côté <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>réception dans Windows Server 2008» à l’adresse. Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>Nombre maximal de conférences

Dans la plupart des cas, il est possible que 5% des utilisateurs d’un groupe puissent participer à une conférence en une seule fois, un groupe d’utilisateurs 80 000 peut avoir environ 4 000 utilisateurs dans les conférences en même temps. Ces conférences sont supposées être composées d’un mélange de plusieurs médias (messagerie instantanée uniquement, messagerie instantanée avec audio, audio/vidéo, par exemple) et du nombre de participants. Il n’y a pas de limite fixe pour le nombre réel de conférences autorisées, et l’utilisation réelle détermine la performance réelle. Par exemple, si votre organisation possède de nombreuses conférences en mode mixte que celles supposées du modèle utilisateur, il se peut que vous deviez déployer des serveurs frontaux ou des serveurs de conférence A/V à partir des recommandations de ce document. Pour plus d’informations sur les hypothèses du modèle utilisateur, voir [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).

La taille de conférence maximale prise en charge hébergée par un pool frontal Lync Server 2013 standard, qui héberge également les utilisateurs est 250 participants. Pendant une conférence avec 250 utilisateurs, le pool continue de prendre en charge d’autres conférences, un total de 5 % d’utilisateurs du pool peuvent se trouver dans des conférences simultanées. Par exemple, dans une liste de douze serveurs frontaux et d’utilisateurs 80 000, pendant la Conférence 250-utilisateur, Lync Server prend en charge 3 750 utilisateurs qui participent à des conférences plus petites.

Quel que soit le nombre d’utilisateurs hébergés sur le pool frontal ou le serveur Standard Edition Server, Lync Server prend en charge au moins 125 d’autres utilisateurs participant à des conférences plus petites sur le même pool ou serveur hébergeant une conférence 250-utilisateurs.

Pour permettre à des conférences avec des utilisateurs de 250 et 1000, vous pouvez configurer une liste frontale distincte pour qu’elle héberge ces conférences. Ce pool frontal n’hébergera aucun utilisateur. Pour plus d’informations, consultez [prise en charge de grandes réunions à l’aide de Lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Si votre organisation possède de nombreuses conférences en mode mixte que celles supposées du modèle utilisateur, il est possible que vous deviez déployer des serveurs frontaux supplémentaires par rapport aux recommandations de ce document (jusqu’à un maximum de 12 FEs). Pour plus d’informations sur les hypothèses du modèle utilisateur, voir [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).

</div>

<div>

## <a name="edge-server"></a>serveur Edge

<div>


> [!NOTE]  
> Les pools étirés ne sont pas pris en charge pour ce rôle de serveur.



</div>

Vous devez déployer un serveur Edge pour tous les utilisateurs de 12 000 distants qui accèdent à un site en même temps. Au minimum, nous vous conseillons d’utiliser deux serveurs Edge pour une disponibilité élevée. Ces recommandations présupposent que le matériel de votre serveur Edge répond aux recommandations des [plateformes matérielles pour Lync server 2013](lync-server-2013-server-hardware-platforms.md).

Lorsque vous comptez le nombre d’utilisateurs pour les serveurs Edge, incluez les utilisateurs sur les appareils de succursales Survivables et les serveurs de succursales Survivables dans les succursales associées à un pool frontal sur ce site.

<div>


> [!NOTE]  
> Pour améliorer les performances du service Edge de conférence A/V sur votre serveur Edge, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur les serveurs Edge. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez la section «améliorations apportées à l’évolutivité du côté <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>réception dans Windows Server 2008» à l’adresse. Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.



</div>

</div>

<div>

## <a name="director"></a>directeur

<div>


> [!NOTE]  
> Les pools étirés ne sont pas pris en charge pour ce rôle de serveur.



</div>

Si vous déployez le rôle de serveur Directeur, nous vous recommandons de déployer un directeur pour tous les utilisateurs de 12 000 distants qui accèdent à un site en même temps. Nous recommandons au minimum deux directeurs pour une disponibilité élevée. Ces recommandations présupposent que le matériel de votre serveur Edge répond aux recommandations des [plateformes matérielles pour Lync server 2013](lync-server-2013-server-hardware-platforms.md).

Lorsque vous comptez le nombre d’utilisateurs pour les directeurs, incluez les utilisateurs hébergés sur des appareils de succursales Survivables et des serveurs de succursales survivant dans les succursales associées à un pool frontal sur ce site.

</div>

<div>

## <a name="mediation-server"></a>serveur de médiation

<div>


> [!NOTE]  
> Les pools étirés ne sont pas pris en charge pour ce rôle de serveur.



</div>

Si vous collocate un serveur de médiation avec un serveur frontal, le serveur de médiation s’exécute sur chaque serveur frontal du pool et doit fournir une capacité suffisante aux utilisateurs de la liste.

Si vous déployez un pool de serveurs de médiation autonome, le nombre de serveurs de médiation à déployer dépend de nombreux facteurs, dont le matériel utilisé pour le serveur de médiation, le nombre d’utilisateurs VoIP, dont vous disposez, le nombre de pairs de passerelle les contrôles, le trafic horaire occupé par le biais de ces passerelles et le pourcentage d’appels avec des éléments multimédias qui contournent le serveur de médiation.

Les tableaux suivants décrivent le nombre d’appels simultanés qu’un serveur de médiation peut gérer, en partant du principe que le matériel requis pour les serveurs de médiation répond à la configuration requise dans les [plates-formes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) et ce Hyper-Threading. est activé. Pour plus d’informations sur la modularité du serveur de médiation, voir [estimation de l’utilisation de la voix et du trafic pour Lync server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) et [recommandations de déploiement pour le serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Toutes les tables suivantes présupposent que l’utilisation est résumée dans les [modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>Capacité du serveur de médiation autonome: 70% des utilisateurs internes et 30% des utilisateurs externes avec la capacité de non-contournement de l’appel (transcodage de média effectué par le serveur de médiation)

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
<td><p>Biprocesseur, six cœurs, processeur 2,26 GHz multithreads <strong>avec technologie Hyper-Threading désactivée</strong>, 32 Go de mémoire et une carte réseau double port.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>Biprocesseur, six cœurs, processeur 2,26 GHz multithreads avec 32 Go de mémoire et une carte réseau double port.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Bien que les serveurs dotés de 32 Go de mémoire aient été utilisés pour le test de performance, les serveurs dotés de 16 Go de mémoire sont pris en charge pour le serveur de médiation autonome et permettent de fournir les performances indiquées dans le tableau ci-dessous.



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>Capacité du serveur de médiation (serveur de médiation en fonction du serveur frontal) 70% des utilisateurs internes et de 30% des utilisateurs externes, sans ignorer la capacité d’appel (traitement multimédia effectué par le serveur de médiation)

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
<td><p>Biprocesseur, six cœurs, processeur 2,26 GHz multithreads avec 32 Go de mémoire et 2 cartes réseau de 1 Go.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Ce nombre est beaucoup plus petit que les numéros du serveur de médiation autonome dans la mesure où le serveur frontal doit gérer d’autres fonctionnalités et fonctions pour les utilisateurs de 6600 sur le serveur, en plus du transcodage nécessaire pour les appels vocaux.



</div>

<div>


> [!NOTE]  
> Pour améliorer les performances du serveur de médiation, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur les serveurs de médiation. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez la section «améliorations apportées à l’évolutivité du côté <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>réception dans Windows Server 2008» à l’adresse. Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.



</div>

</div>

<div>

## <a name="back-end-server"></a>serveur principal

Dans Lync Server 2013, les bases de données de présence sont situées sur les serveurs frontaux au lieu du serveur principal. Cela a entraîné une nécessité plus simple pour chaque serveur principal de Lync Server 2013, qui équivaut à la configuration matérielle requise pour le serveur frontal. Différences entre ce niveau et Lync Server 2010, où le serveur principal est requis pour être un serveur de qualité nettement supérieur à 25 disques. Toutefois, la charge de travail des serveurs dorsaux est toujours telle que vous ne devriez pas être satisfait aux recommandations en matière de matériel indiquées dans cette section et dans les [plates-formes matérielles pour Lync server 2013](lync-server-2013-server-hardware-platforms.md).

Pour garantir une haute disponibilité de votre serveur principal, nous vous recommandons de déployer la mise en miroir du serveur. Pour plus d’informations, voir [disponibilité du serveur principal dans Lync server 2013](lync-server-2013-back-end-server-high-availability.md).

</div>

<div>

## <a name="monitoring-and-archiving"></a>Surveillance et archivage

Dans Lync Server 2013, si vous déployez la surveillance ou l’archivage, les fonctionnalités frontales de ces services s’exécutent sur les serveurs frontaux, au lieu de rôles de serveur distincts. La surveillance et l’archivage de chacune utilise toujours leur propre magasin de base de données, indépendamment du magasin principal. Par ailleurs, si vous avez déployé Exchange 2013, vous pouvez stocker les données d’archivage des messages instantanés dans Exchange plutôt que dans un magasin SQL dédié.

Le tableau ci-dessous indique approximativement la quantité de stockage de base de données nécessaire par utilisateur par jour pour les données de surveillance et d’archivage.


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
<td><p>Espace disque requis par utilisateur par jour</p></td>
<td><p>49 Ko</p></td>
<td><p>28 Ko</p></td>
<td><p>57 Ko</p></td>
</tr>
</tbody>
</table>


Microsoft a utilisé le matériel décrit dans le tableau ci-dessous pour le serveur de base de données pour la surveillance et l’archivage lors des tests de performances. Le test collectait les données de deux pools front-end, chacun contenant des utilisateurs 80 000.

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>Matériel utilisé pour le test des performances d’archivage et de la surveillance

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
<td><p>Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur</p></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>48 Go</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><p>25 disques durs avec une vitesse de 10 000 tr/min et 300 Go sur chaque disque, avec la configuration suivante</p>
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
<td><p><strong>Lecteur</strong></p></td>
<td><p><strong>Configuration RAID</strong></p></td>
<td><p><strong>Nombre de disques</strong></p></td>
</tr>
<tr class="even">
<td><p>Fichiers de données des bases de données CDR, QoE et d’archivage sur un seul disque</p></td>
<td><p>1+0</p></td>
<td><p>Seiz</p></td>
</tr>
<tr class="odd">
<td><p>Fichier journal de la base de données d’enregistrement des détails des appels</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Fichier journal de la base de données QoE</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>Fichier journal de la base de données d’archivage</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul>
<li><p>1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Estimation du trafic et de l’utilisation de la voix pour Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Recommandations en matière de déploiement pour le serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

