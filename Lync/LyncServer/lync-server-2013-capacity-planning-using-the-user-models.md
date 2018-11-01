---
title: Planification de capacité pour Lync Server 2013 avec les modèles utilisateur
TOCTitle: Planification de capacité pour Lync Server 2013 avec les modèles utilisateur
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49891441
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de capacité pour Lync Server 2013 avec les modèles utilisateur

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette section fournit des instructions sur le nombre de serveurs dont vous avez besoin sur un site pour le nombre d’utilisateurs sur le site en fonction de l’utilisation décrite dans [Modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).

## Plateforme matérielle testée

Tous les résultats de performance et les recommandations de déploiement de cette section sont basés sur des tests de performances sur des serveurs qui exécutent le matériel décrit dans le tableau ci-dessous. Nous vous recommandons d’utiliser le même matériel. Si vous utilisez du matériel moins puissant, vous pourrez rencontrer des problèmes ou obtenir des performances médiocres. Ces recommandations matérielles sont supérieures à celles des versions précédentes de Lync Server.

### Matériel utilisé dans les tests de performances

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
<p>Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>32 Go</p></td>
</tr>
<tr class="odd">
<td><p>Disque</p></td>
<td><ul><li><p>8 ou plus disques durs d’une vitesse de 10 000 RPM avec au moins 72 Go d’espace disponible.</p>
<p>Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.</p>
<p>- OU -</p></li><li><p>Disques SSD (Solid State Drive) qui fournissent des performances similaires à 8 disques durs mécaniques 10 000 tr/min.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Réseau</p></td>
<td><ul><li><p>1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)</p></li></ul></td>
</tr>
</tbody>
</table>


## Résumé des résultats

Le tableau ci-dessous résume ces recommandations.


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
<td><p>Un pool de serveurs frontaux avec douze serveurs frontaux et un serveur principal ou une paire en miroir de serveurs principaux.</p></td>
<td><p>80 000 utilisateurs uniques connectés simultanément, plus 50 % de points de présence multiples (MPOP) représentant des instances non mobiles, plus 40 % d’utilisateurs activés pour la mobilité pour un total de 152 000 points de terminaison.</p></td>
</tr>
<tr class="even">
<td><p>Conférence A/V</p></td>
<td><p>Le service de conférence A/V fournit par un pool de serveurs frontaux prend en charge les conférences du pool avec une taille de conférence maximale de 250 utilisateurs, et une seule grande conférence s’exécutant à la fois.</p>
<div>

> [!NOTE]  
> De plus, vous pouvez prendre en charge des grandes conférences (250 à 1 000 utilisateurs) en déployant un pool de serveurs frontaux distinct avec deux serveurs frontaux pour héberger les grandes conférences. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-supporting-large-meetings.md">Prise en charge des grandes réunions à l’aide de Lync Server 2013</a>.
</div></td>
</tr>
<tr class="odd">
<td><p>Un serveur Edge</p></td>
<td><p>12 000 utilisateurs distants simultanés</p></td>
</tr>
<tr class="even">
<td><p>Un directeur</p></td>
<td><p>12 000 utilisateurs distants simultanés</p></td>
</tr>
<tr class="odd">
<td><p>Surveillance et archivage</p></td>
<td><p>Dans Lync Server 2013, les services frontaux de surveillance et d’archivage s’exécutent désormais sur chaque serveur frontal, au lieu de rôles serveur distincts.</p>
<p>La surveillance et l’archivage requièrent un magasin de base de données chacun. Si vous exécutez également Exchange 2013, vous pouvez conserver vos données d’archivage dans Exchange, plutôt que dans une base de données SQL dédiée.</p></td>
</tr>
<tr class="even">
<td><p>Un serveur de médiation</p></td>
<td><p>Un serveur de médiation colocalisé avec un serveur frontal s’exécute dans chaque serveur frontal dans un pool et doit fournir suffisamment de capacité pour les utilisateurs du pool. Pour un serveur de médiation autonome, reportez-vous à la section serveur de médiation dans la suite de cette rubrique.</p></td>
</tr>
<tr class="odd">
<td><p>Un serveur Standard Edition</p></td>
<td><p>Si vous utilisez des serveurs Standard Edition pour héberger les utilisateurs, il est fortement recommandé d’utiliser deux serveurs, associés conformément aux recommandations de la rubrique <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</a>. Chaque serveur de la paire peut héberger jusqu’à 2 500 utilisateurs. Si un serveur connaît une défaillance, l’autre peut prendre en charge 5 000 utilisateurs dans le cadre d’un scénario de basculement.</p>
<p>Si votre déploiement présente un trafic audio ou vidéo important, les performances du serveur peuvent être affectées avec plus de 2 500 utilisateurs par serveur. Dans ce cas, il peut être préférable d’ajouter d’autres serveurs Standard Edition ou d’effectuer une mise à niveau vers Lync ServerEnterprise Edition.</p></td>
</tr>
</tbody>
</table>


## serveur frontal

> [!NOTE]  
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Dans un pool de serveurs frontaux, vous devez avoir un serveur frontal pour chaque 6 660 utilisateurs hébergés dans le pool, si hyper-threading est activé sur tous les serveurs du pool et le matériel requis correspond à celui décrit dans [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md). Le nombre maximum d’utilisateurs dans un pool de serveurs frontaux est 80 000, si hyper-threading est activé sur tous les serveurs du pool. Si votre site comporte plus de 80 000 utilisateurs, vous pouvez déployer plusieurs pool de serveurs frontaux.

Lorsque vous comptez le nombre d’utilisateurs d’un pool de serveurs frontaux, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à ce pool de serveurs frontaux.

Lorsqu’un serveur actif est indisponible, ses connexions sont transférées automatiquement aux autres serveurs du pool. Par exemple, si vous avez 30 000 utilisateurs et cinq serveurs frontaux et qu’un serveur est indisponible, les connexions de 6 000 utilisateurs doivent être transférées vers les quatre autres serveurs. Les quatre serveurs restants contiendront chacun 7 500 utilisateurs, ce qui est un nombre plus élevé que celui recommandé.

Si, à la place, vous avez commencé avec serveurs frontaux pour 30 000 utilisateurs et que l’un devient indisponible, un total de 5 000 utilisateurs seront déplacés sur les cinq serveurs restants. Ces cinq serveurs hébergent chacun 6 000 utilisateurs, ce qui est la plage recommandée.

Le nombre maximal d’utilisateurs dans un pool de serveurs frontaux est de 80 000. Le nombre maximal de serveurs frontaux dans un pool est de 12.

Pour un pool de serveurs frontaux avec 80 000 utilisateurs, douze serveurs frontaux sont suffisants pour les performances, dans des déploiements qui suivent les recommandations de [Modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md). Les déploiements conçus pour prendre en charge le basculement de récupération d’urgence présument qu’un maximum de 40 000 utilisateurs peuvent être hébergés dans chacun des deux paires de pools de serveurs frontaux, dans lesquels chaque pool comprend suffisamment de serveurs frontaux pour contenir les utilisateurs des deux pools, si l’un des pools doit basculer sur l’autre.

Le nombre d’utilisateurs pris en charge pour des performances correctes par un pool de serveurs frontaux spécifique peut être différent pour les raisons suivantes :

  - Le matériel utilisé pour vos serveurs frontaux ne répond pas aux recommandations dans [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

  - L’utilisation de votre organisation diffère de manière significative de celle des modèles utilisateur, en raison d’un trafic de conférence plus important par exemple.

> [!IMPORTANT]  
> Dans Lync Server 2013, les bases de données de présence sont désormais hébergées sur des serveurs frontaux, à la différence de Lync Server 2010 où elles étaient hébergées sur le serveur principal. Cela signifie que les performances et les capacités des disques de vos serveurs frontaux ne doivent pas être compromises en raison des recommandations indiquées précédemment dans cette section et dans <a href="lync-server-2013-server-hardware-platforms.md">Plateformes matérielles de serveur pour Lync Server 2013</a>, quel que soit le nombre d’utilisateurs hébergés par vos serveurs frontaux.

Le tableau ci-dessous montre la bande passante moyenne pour la messagerie instantanée et la présence, selon le modèle utilisateur défini dans [Modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Bande passante moyenne par utilisateur</th>
<th>Bande passante requise par serveur frontal avec 6 660 utilisateurs</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1,3 Kbits/s</p></td>
<td><p>13 Mbits/s</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Pour améliorer les performances multimédias du serveur de conférence A/V colocalisé et de la fonctionnalité de serveur de médiation sur vos serveurs frontaux, activez RSS sur les cartes réseau de vos serveurs frontaux. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, reportez-vous à « Améliorations RSS dans Windows Server 2008 » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=268731" class="uri">http://go.microsoft.com/fwlink/?linkid=268731</a>. Pour des informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.

## Nombre maximal de conférences

Selon le modèle utilisateur, 5 % des utilisateurs d’un pool peuvent assister à une conférence en même temps, donc un pool de 80 000 utilisateurs peut avoir 4 000 utilisateurs en conférence simultanément. Ces conférences sont supposées être composées d’un mélange de plusieurs médias (messagerie instantanée uniquement, messagerie instantanée avec audio, audio/vidéo par exemple) et du nombre de participants. Il n’existe pas de limite inconditionnelle au nombre réel de conférences autorisées, et l’utilisation réelle détermine les performances réelles. Par exemple, si le nombre de conférences en mode mixte dans votre organisation est anormalement élevé par rapport au modèle utilisateur, vous devrez peut-être déployer un nombre de serveurs frontaux et de serveurs de conférence A/V plus important que celui recommandé dans ce document. Pour plus d’informations sur les hypothèses du modèle utilisateur, reportez-vous à [Modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).

La taille de conférence prise en charge maximale hébergée par un pool de serveurs frontauxLync Server 2013 qui héberge également des utilisateurs est de 250 participants. Pendant une conférence avec 250 utilisateurs, le pool continue de prendre en charge d’autres conférences, un total de 5 % d’utilisateurs du pool peuvent se trouver dans des conférences simultanées. Par exemple, dans un pool de douze serveurs frontaux et 80 000 utilisateurs, pendant la conférence avec 250 utilisateurs, Lync Server prend en charge 3 750 autres utilisateurs participant à des conférences plus petites.

Quel que soit le nombre d’utilisateurs hébergés sur le pool de serveurs frontaux ou le serveur Standard Edition, Lync Server prend en charge un minimum de 125 autres utilisateurs participant à des conférences plus petites dans le même pool ou serveur qui héberge la conférence de 250 utilisateurs.

Pour activer les conférences avec 250 à 1 000 utilisateurs, vous pouvez configurer un pool de serveurs frontaux distinct uniquement pour héberger ces conférences. Ce pool de serveurs frontaux n’hébergera pas les utilisateurs. Pour plus d’informations, reportez-vous à [Prise en charge des grandes réunions à l’aide de Lync Server 2013](lync-server-2013-supporting-large-meetings.md).

Si le modèle utilisateur de votre organisation prévoit des conférences mixtes, vous devez déployer davantage de serveurs frontaux que le nombre indiqué dans les recommandations de ce document (jusqu’à 12 FE). Pour plus d’informations sur les hypothèses du modèle utilisateur, reportez-vous à [Modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).

## serveur Edge

> [!NOTE]  
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Vous devez déployer un serveur Edge pour 12 000 utilisateurs distants qui accèderont simultanément à un site. Au minimum, nous recommandons deux serveurs Edge pour la haute disponibilité. Ces recommandations présupposent que le matériel pour vos serveurs Edge répond à la configuration décrite dans [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Lorsque vous comptez le nombre d’utilisateurs pour les serveurs Edge, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à un pool de serveurs frontaux sur ce site.

> [!NOTE]  
> Pour améliorer les performances du service Edge de conférence A/V sur vos serveurs Edge, activez RSS sur les cartes réseau de vos serveurs Edge. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, reportez-vous à « Améliorations RSS dans Windows Server 2008 » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=268731" class="uri">http://go.microsoft.com/fwlink/?linkid=268731</a>. Pour des informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.

## directeur

> [!NOTE]  
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Si vous déployez le rôle serveur directeur, nous recommandons de déployer un directeur pour 12 000 utilisateurs distants qui accèderont simultanément à un site. Au minimum, nous recommandons deux directeurs pour la haute disponibilité. Ces recommandations présupposent que le matériel pour vos serveurs Edge répond à la configuration requise décrite dans [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Lorsque vous comptez le nombre d’utilisateurs pour les directeurs, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à un pool de serveurs frontaux sur ce site.

## serveur de médiation

> [!NOTE]  
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Si vous colocalisez un serveur de médiation avec un serveur frontal, le serveur de médiation s’exécute sur chaque serveur frontal du pool, et doit fournir suffisamment de capacité pour les utilisateurs du pool.

Si vous déployez un pool de serveur de médiation autonome, le nombre de serveurs de médiation à déployer dépend de nombreux facteurs, notamment le matériel utilisé pour le serveur de médiation, le nombre d’utilisateurs VoIP, le nombre d’homologues de passerelle contrôlés par le pool de serveurs de médiation, le trafic aux heures de pointe de ces passerelles et le pourcentage d’appels avec média qui contournent le serveur de médiation.

Les tableaux suivants donnent des instructions sur le nombre d’appels simultanés que peut traiter un serveur de médiation, si la configuration matérielle requise pour les serveurs de médiation correspond à celle décrite dans [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md) et si hyper-threading est activé. Pour plus d’informations sur l’extensibilité du serveur de médiation, reportez-vous à [Estimation du trafic et de l’utilisation de la voix pour Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) et [Instructions de déploiement du serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).

Tous les tableaux suivants présupposent une utilisation correspondante à celle décrite dans [Modèles utilisateur dans Lync Server 2013](lync-server-2013-user-models.md).

### Capacité du serveur de médiation autonome : 70 % d’utilisateurs internes, 30 % d’utilisateurs externes sans contournement (transcodage multimédia exécuté par le serveur de médiation)

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
<td><p>Biprocesseur, hexa-cœur, processeur 2,26 GHz multithreads <strong>avec Hyper-Threading désactivé</strong>, avec 32 Go de mémoire et une carte réseau double port.</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>Biprocesseur, hexa-cœur, processeur 2,26 GHz multithreads avec 32 Go de mémoire et une carte réseau double port.</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Même si des serveurs dotés de 32 Go de mémoire ont été utilisés pour tester les performances, les serveurs ayant 16 Go de mémoire sont pris en charge pour un serveur de médiation autonome et sont suffisants pour fournir les performances indiquées dans ce tableau.

### Capacité du serveur de médiation ( serveur de médiation colocalisé avec serveur frontal) 70 % d’utilisateurs internes, 30 % d’utilisateurs externes, sans contournement (traitement multimédia effectué par le serveur de médiation)

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
<td><p>Biprocesseur, hexa-cœur, processeur 2,26 GHz multithreads avec 32 Go de mémoire et 2 cartes réseau d’1 Go.</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Ce nombre est bien plus petit que les chiffres pour le serveur de médiation autonome, car le serveur frontal doit gérer d’autres fonctionnalités pour les 6 600 utilisateurs hébergés, en plus du transcodage nécessaire pour les appels vocaux.

> [!NOTE]  
> Pour améliorer les performances du serveur de médiation, activez RSS sur les cartes réseau de vos serveurs de médiation. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, reportez-vous à « Améliorations RSS dans Windows Server 2008 » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=268731" class="uri">http://go.microsoft.com/fwlink/?linkid=268731</a>. Pour des informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau.

## serveur principal

Dans Lync Server 2013, les bases de données de présence sont situées sur les serveurs frontaux au lieu du serveur principal. La configuration requise de chaque serveur principal dans Lync Server 2013 est désormais plus simple, et elle équivaut à celle définie pour le serveur frontal. Il s’agit d’une différence majeure par rapport Lync Server 2010, qui nécessitait que le serveur principal soit de qualité supérieur avec 25 disques. Cependant, la charge des serveurs principaux est telle qu’il est nécessaire de respecter la configuration requise décrite plus haut dans cette section et dans [Plateformes matérielles de serveur pour Lync Server 2013](lync-server-2013-server-hardware-platforms.md).

Pour permettre la haute disponibilité de votre serveur principal, nous recommandons de déployer la mise en miroir serveur. Pour plus d’informations, reportez-vous à [Haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).

## Surveillance et archivage

Dans Lync Server 2013, si vous déployez la surveillance et l’archivage, les fonctionnalités frontales de ces services s’exécutent sur les serveurs frontaux, plutôt que sur des rôles serveur distincts. La surveillance et l’archivage utilise chacun leur propre magasin de base de données, distincts du magasin frontal. Si vous avez déployé Exchange 2013, vous pouvez stocker les données d’archivage des messages instantanés dans Exchange plutôt quand dans un magasin SQL dédié.

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
<td><p></p></td>
<td><p><strong>CDR (Surveillance)</strong></p></td>
<td><p><strong>QoE (Surveillance)</strong></p></td>
<td><p><strong>Archivage</strong></p></td>
</tr>
<tr class="even">
<td><p>Espace disque requis par utilisateur par jour</p></td>
<td><p>49 Ko</p></td>
<td><p>28 Ko</p></td>
<td><p>57 Ko</p></td>
</tr>
</tbody>
</table>


Microsoft a utilisé le matériel décrit dans le tableau suivant pour le serveur de base de données pour la surveillance et l’archivage lors des tests de performances. Les tests ont collectés les données de deux pools de serveurs frontaux, avec 80 000 utilisateurs chacun.

### Matériel utilisé pour le test des performances d’archivage et de la surveillance

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
<td><p>25 disques durs avec une vitesse de 10 000 RPM et 300 Go sur chaque disque, avec la configuration suivante</p>
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
<td><p>16</p></td>
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
<td><ul><li><p>1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)</p></li></ul></td>
</tr>
</tbody>
</table>


## Dans cette section

  - [Estimation du trafic et de l’utilisation de la voix pour Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Instructions de déploiement du serveur de médiation dans Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md)

