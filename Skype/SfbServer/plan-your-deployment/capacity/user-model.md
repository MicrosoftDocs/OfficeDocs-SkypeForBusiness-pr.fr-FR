---
title: Planification de la capacité de l’utilisation du modèle utilisateur pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: Cet article fournit des instructions sur le nombre de serveurs dont vous avez besoin sur un site pour le nombre d’utilisateurs sur ce site, en fonction de l’utilisation décrite dans les modèles utilisateur dans Skype Entreprise Server.
ms.openlocfilehash: 145e790c0f6c7ceeaa7330c0cd48ad68bc15b331
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846357"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Planification de la capacité de l’utilisation du modèle utilisateur pour Skype Entreprise Server

Cet article fournit des instructions sur le nombre de serveurs dont vous avez besoin sur un site pour le nombre d’utilisateurs sur ce site, en fonction de l’utilisation décrite dans les modèles utilisateur dans [Skype Entreprise Server](user-models.md).

> [!NOTE]
> Toutes les recommandations de cet article supposent que vous avez installé Skype Entreprise mise à jour cumulative de novembre 2015 ou ultérieure sur vos serveurs.

## <a name="tested-hardware-platform"></a>Plateforme matérielle testée

Nous avons effectué nos tests de performances sur le matériel décrit dans le tableau ci-dessous. Toutes nos recommandations et résultats sont basés sur ce matériel. Si vous décidez d’utiliser un matériel moins puissant que celui répertorié ici, sachez que vous pouvez être confronté à des problèmes de fonctionnalité ou à des performances médiocres. Ces recommandations matérielles sont identiques à Lync Server 2013, si cela est utile (et dans les scénarios de mise à niveau, cela peut l’être).

**Matériel utilisé dans les tests de performances**

|Composant matériel|Recommandé|
|:-----|:-----|
|UC   |Bi-processeur 64 bits, hex-core, 2,26 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge Skype Entreprise Server rôles serveur.   |
|Mémoire   |32 gigaoctets (Go).   |
|Disque   |Au moins 8 disques durs de 10 000 TPM avec au moins 72 Go d’espace disque libre. Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.  <br/> - OU - <br/>Disques SSD (Solid State Drive) qui fournissent des performances similaires à 8 disques mécaniques 10 000 RPM.  |
|Réseau   |1 carte réseau double port, 1 Gbits/s ou plus (2 recommandé, ce qui nécessite une seule adresse MAC et une seule adresse IP).   |

## <a name="summary-of-results"></a>Résumé des résultats

Le tableau suivant résume nos recommandations.

|Rôle serveur|Nombre maximal d’utilisateurs pris en charge|
|:-----|:-----|
|Pool frontal avec douze serveurs frontux et un serveur principal ou une paire de serveurs principal en miroir.   |80 000 utilisateurs uniques connectés simultanément, plus 50 % de points de présence multiples (MPOP) représentant des instances non mobiles, plus 40 % d’utilisateurs activés pour la mobilité pour un total de 152 000 points de terminaison.   |
|Conférence A/V   |Le service de conférence A/V fourni par un pool frontal prend en charge les conférences du pool en supposant une taille maximale de conférence de 250 utilisateurs et une seule conférence de ce type s’exécutant à la fois.  <br/> **Remarque :** En outre, vous pouvez prendre en charge de grandes conférences de 250 à 1 000 utilisateurs en déployant un pool frontal distinct avec deux serveurs frontaux pour héberger les grandes conférences. Pour plus d’informations, [voir Planifier les grandes réunions dans Skype Entreprise Server](../../plan-your-deployment/conferencing/large-meetings.md).   |
|Un serveur Edge   |12 000 utilisateurs distants simultanés.   |
|Un directeur   |12 000 utilisateurs distants simultanés.   |
|Surveillance et archivage   |Les services frontaux de surveillance et d’archivage s’exécutent sur chaque serveur frontal, et non sur des rôles serveur distincts.  <br/> La surveillance et l’archivage requièrent chacun leurs propres magasins de bases de données. Si vous exécutez également Exchange 2013 ou une ultérieure, vous pouvez conserver vos données d’archivage dans Exchange, plutôt que dans une base de données SQL dédiée.   |
|Un serveur de médiation   |Le serveur de médiation coqueté avec le serveur frontal s’exécute sur chaque serveur frontal d’un pool et doit fournir une capacité suffisante pour les utilisateurs du pool. Pour un serveur de médiation autonome, consultez la section « Serveur de médiation » plus loin dans cette rubrique.   |
|Un serveur Standard Edition Server   |Si vous utilisez des serveurs Édition Standard pour héberger des utilisateurs, nous vous recommandons vivement d’utiliser toujours deux serveurs, associés à l’aide des recommandations de planning pour la haute disponibilité et la récupération [d’urgence.](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-high-availability-and-disaster-recovery) Chaque serveur de la paire peut héberger jusqu’à 2 500 utilisateurs, et si un serveur tombe en panne, le serveur restant peut prendre en charge 5 000 utilisateurs dans un scénario de failover.  <br/>  Si votre déploiement inclut une quantité importante de trafic audio ou vidéo, les performances du serveur peuvent être en baisse avec plus de 2 500 utilisateurs par serveur. Dans ce cas, vous devez envisager d’ajouter des serveurs Édition Standard serveurs ou de passer à Skype Entreprise Server Êdition Entreprise.  |

## <a name="front-end-server"></a>serveur frontal

> [!NOTE]
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.

Dans un pool frontal, vous devez avoir un serveur frontal pour 6 660 utilisateurs tous les 660 utilisateurs de votre pool, en supposant que l’hyper-threading est activé sur tous les serveurs du pool et que le matériel serveur répond aux recommandations de la configuration requise pour le serveur pour [Skype Entreprise Server 2015](../requirements-for-your-environment/server-requirements.md) ou la configuration requise pour [Skype Entreprise Server 2019](../../../SfBServer2019/plan/system-requirements.md). Le nombre maximal d’utilisateurs dans un pool frontal est de 80 000, en supposant à nouveau que l’hyper-threading est activé sur tous les serveurs de votre pool. Si vous avez plus de 80 000 utilisateurs sur un site, vous pouvez déployer plusieurs pools frontaux.

Lorsque vous comptez le nombre d’utilisateurs dans un pool frontal, incluez tous les utilisateurs qui sont situés sur les Survivable Branch Appliances et les serveurs Survivable Branch Servers des succursales associés à ce pool frontal.

Lorsqu’un serveur actif est indisponible, ses connexions sont transférées automatiquement aux autres serveurs du pool. Dans un scénario où vous avez 30 000 utilisateurs et cinq serveurs frontaux, si un serveur n’est pas disponible, les connexions de 6 000 de vos utilisateurs doivent être transférées vers vos quatre autres serveurs restants. Ces quatre serveurs restants auront chacun 7 500 utilisateurs, ce qui est un nombre supérieur à celui recommandé.

Si, à la place, vous aviez démarré avec six serveurs frontaux pour vos 30 000 utilisateurs et qu’un serveur devient indisponible, un total de 5 000 utilisateurs doit passer aux cinq serveurs restants. Ces cinq serveurs restants hébergeront chacun 6 000 utilisateurs, ce qui se trouve dans la plage recommandée.

Le nombre maximal d’utilisateurs dans un pool frontal est de 80 000. Le nombre maximal de serveurs frontux dans un pool est de 12.

Pour un pool frontal de 80 000 utilisateurs, douze serveurs frontaux sont performants, dans des déploiements classiques qui suivent les modèles utilisateur dans [Skype Entreprise Server](user-models.md). Les déploiements conçus pour prendre en charge leover de récupération d’urgence supposent qu’un maximum de 40 000 utilisateurs peuvent être hébergés dans chacun des deux pools frontaux couplés, dans lesquels chaque pool dispose de suffisamment de serveurs frontaux pour contenir les utilisateurs dans les deux pools, si un pool doit être retenté sur l’autre.

Le nombre d’utilisateurs pris en charge avec de bonnes performances par un pool frontal particulier peut différer de ces nombres pour les raisons suivantes :

- Le matériel de vos serveurs frontaux ne répond pas aux recommandations.

- L’utilisation de votre organisation est très différente des modèles utilisateur, par exemple, si vous avez beaucoup plus de trafic de conférence.

Le tableau suivant indique la bande passante moyenne pour la messagerie instantanée et la présence, selon le modèle utilisateur, tel que défini dans les modèles utilisateur [Skype Entreprise Server](user-models.md).

|Bande passante moyenne par utilisateur|Besoins en bande passante par serveur frontal avec 6 660 utilisateurs|
|:-----|:-----|
|1,3 Kbits/s   |13 Mbits/s   |

> [!NOTE]
> Pour améliorer les performances multimédias des fonctionnalités de conférence A/V et de serveur de médiation sur vos serveurs frontaux, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau de vos serveurs frontaux. RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur. Pour plus d’informations, [voir La mise à l’échelle](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))côté réception (RSS) dans la documentation Windows Server 2012. Pour plus d’informations sur la façon d’activer RSS, vous devez vous référer à la documentation de votre carte réseau.

## <a name="conferencing-maximums"></a>Nombre maximal de conférences

Selon le modèle utilisateur, 5 % des utilisateurs d’un pool peuvent être en même temps dans une conférence, un pool de 80 000 utilisateurs peut avoir environ 4 000 utilisateurs simultanément dans des conférences. Ces conférences sont supposées être composées d’un mélange de plusieurs médias (messagerie instantanée uniquement, messagerie instantanée avec audio, audio/vidéo par exemple) et du nombre de participants. Il n’existe pas de limite difficile pour le nombre réel de conférences autorisées, et l’utilisation réelle détermine les performances réelles. Par exemple, si votre organisation compte beaucoup plus de conférences en mode mixte que ce qui est supposé dans le modèle utilisateur, vous devrez peut-être déployer plus de serveurs frontaux ou de serveurs de conférence A/V que les recommandations de cet article. Pour plus d’informations sur les hypothèses dans le modèle utilisateur, voir [modèles utilisateur dans Skype Entreprise Server](user-models.md).

La taille maximale de conférence prise en charge hébergée par un pool Skype Entreprise Server frontal qui héberge également des utilisateurs est de 250 participants. Pendant qu’une conférence de 250 utilisateurs est en cours, le pool prend également en charge d’autres conférences, de telle façon qu’un total de 5 % des utilisateurs du pool sont en conférences simultanées. Par exemple, dans un pool de douze serveurs frontaux et de 80 000 utilisateurs, alors que la conférence de 250 utilisateurs a lieu, Skype Entreprise Server prend en charge 3 750 autres utilisateurs participant à des conférences plus petites.

Quel que soit le nombre d’utilisateurs sur le pool frontal ou le serveur Édition Standard, Skype Entreprise Server prend en charge un minimum de 125 autres utilisateurs participant à des conférences plus petites sur le même pool ou serveur qui héberge une conférence de 250 utilisateurs.

Pour activer les conférences qui comptent entre 250 et 1 000 utilisateurs, vous pouvez configurer un pool frontal distinct uniquement pour héberger ces conférences. Ce pool frontal n’héberge aucun utilisateur. Pour plus d’informations, voir [Planifier les grandes réunions dans Skype Entreprise Server](../../plan-your-deployment/conferencing/large-meetings.md).

Si votre organisation a beaucoup plus de conférences en mode mixte que ce qui est supposé dans le modèle utilisateur, vous devrez peut-être déployer plus de serveurs frontaux que ce que nous vous avons recommandé dans ce document (jusqu’à une limite de 12 serveurs frontaux). Pour plus d’informations sur les hypothèses dans le modèle utilisateur, voir [modèles utilisateur dans Skype Entreprise Server](user-models.md).

## <a name="edge-server"></a>Serveur Edge

> [!NOTE]
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.

Vous devez déployer un serveur Edge pour 12 000 utilisateurs distants qui accèderont simultanément à un site. Nous vous conseillons au moins deux serveurs Edge pour une disponibilité élevée. Ces recommandations supposent que le matériel de vos serveurs Edge répond aux recommandations des [plateformes matérielles serveur.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Lorsque vous comptez le nombre d’utilisateurs pour les serveurs Edge, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à un pool frontal sur ce site.

> [!NOTE]
> Pour améliorer les performances du service Edge de conférence A/V sur vos serveurs Edge, vous devez activer le partage du trafic entrant (RSS, Receive-Side Scaling) sur les cartes réseau de vos serveurs Edge. RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur. Pour plus d’informations, consultez « Mise à l’échelle côté réception[(RSS) dans Windows Server 2012](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))». Pour plus d’informations sur la façon d’activer RSS, vous devez vous référer à la documentation de votre carte réseau.

## <a name="director"></a>Directeur

> [!NOTE]
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.

Si vous déployez le rôle de serveur directeur, nous vous recommandons de déployer un directeur pour 12 000 utilisateurs distants qui accèderont simultanément à un site. Nous vous conseillons au moins deux directeurs pour une disponibilité élevée. Ces recommandations supposent que le matériel de vos serveurs Edge répond aux recommandations des [plateformes matérielles serveur.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Lorsque vous comptez le nombre d’utilisateurs pour les directeurs, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à un pool frontal sur ce site.

## <a name="mediation-server"></a>Serveur de médiation

> [!NOTE]
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.

Si vous coloyez le serveur de médiation avec un serveur frontal, celui-là s’exécute sur chaque serveur frontal du pool et doit fournir une capacité suffisante pour les utilisateurs du pool.

Si vous déployez un pool de serveurs de médiation autonome, le nombre de serveurs de médiation à déployer dépend de nombreux facteurs, notamment le matériel utilisé pour le serveur de médiation, le nombre d’utilisateurs VoIP que vous avez, le nombre d’homologues de passerelle que chaque pool de serveurs de médiation contrôle, le trafic aux heures de pointe via ces passerelles et le pourcentage d’appels avec média qui contournent le serveur de médiation.

Les tableaux suivants fournissent des indications sur le nombre d’appels simultanés qu’un serveur de médiation peut gérer, en supposant que le matériel des serveurs de médiation répond aux exigences des [plateformes matérielles](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) serveur et que l’hyper-thread est activé. Pour plus d’informations sur l’évolutivité du serveur de médiation, voir [Estimateing voice usage and traffic for Skype Entreprise Server](estimating-voice-traffic.md) and Deployment guidelines for Mediation Server in [Skype Entreprise Server](mediation-server-deployment-guidelines.md).

Tous les tableaux suivants supposent une utilisation telle qu’elle est résumée dans [les modèles utilisateur Skype Entreprise Server](user-models.md).

**Capacité du serveur de médiation autonome : 70 % d’utilisateurs internes, 30 % d’utilisateurs externes avec une capacité d’appel sans contournement (transcodage multimédia effectué par le serveur de médiation)**

|Matériel serveur|Nombre maximal d’appels|Nombre maximal de lignes T1|Nombre maximal de lignes E1|
|:-----|:-----|:-----|:-----|
|Bi-processeur, cœur hexadique, processeur hyper-threadé 2,26 GHz avec **l’hyper-thread désactivé,** avec 32 Go de mémoire et une carte carte réseau double port.   |1100   |46   |35   |
|Bi-processeur, cœur hexadique, processeur hyper-threadé 2,26 GHz, avec 32 Go de mémoire et une carte carte réseau double port.   |1500   |63   |47   |

> [!NOTE]
> Bien que des serveurs dotés de 32 Go de mémoire aient été utilisés pour tester les performances, les serveurs ayant 16 Go de mémoire sont pris en charge pour un serveur de médiation autonome et sont suffisants pour fournir les performances indiquées dans ce tableau.

**Capacité du serveur de médiation (serveur de médiation cocté avec serveur frontal) 70 % d’utilisateurs internes, 30 % d’utilisateurs externes, capacité sans contournement des appels (traitement multimédia effectué par le serveur de médiation)**

|Matériel serveur|Nombre maximal d’appels|
|:-----|:-----|
|Bi-processeur, hex core, processeur hyper-thread 2,26 GHz, avec 32 Go de mémoire et 2 cartes réseau de 1 Go.   |150   |

> [!NOTE]
> Ce nombre est beaucoup plus petit que le nombre pour le serveur de médiation autonome. En effet, le serveur frontal doit gérer d’autres fonctionnalités et fonctions pour les 6 600 utilisateurs qui y sont homed, en plus du transcodage nécessaire pour les appels vocaux.

> [!NOTE]
> Pour améliorer les performances du serveur de médiation, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur vos serveurs de médiation. RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur. Pour plus d’informations, voir « Mise à l’échelle côté[réception Windows Server 2012](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))». Pour plus d’informations sur la façon d’activer RSS, vous devez vous référer à la documentation de votre carte réseau.

## <a name="back-end-server"></a>Serveur principal

Bien que la plupart des informations de base de données sont stockées principalement sur les serveurs frontaux, vous devez vous assurer que vos serveurs frontaux répondent aux recommandations matérielles répertoriées plus haut dans cette section et dans les [plateformes matérielles](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)serveur.

Pour fournir une haute disponibilité de votre serveur principal, nous vous recommandons de déployer des groupes de disponibilité AlwaysOn ou la mise en miroir de serveur. Pour plus d’informations, [voir la haute disponibilité du](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)serveur principal dans Skype Entreprise Server .

## <a name="monitoring-and-archiving"></a>Surveillance et archivage

Si vous déployez la surveillance ou l’archivage, la fonctionnalité frontale de ces services s’exécute sur les serveurs frontaux, la surveillance et l’archivage utilisent chacun leur propre magasin de bases de données, séparément de la banque principale. Si vous avez déployé Exchange 2013, vous pouvez également stocker les données d’archivage des messages instantanés dans Exchange plutôt que dans un magasin de SQL dédié.

Le tableau suivant indique approximativement la quantité de stockage de base de données requise par utilisateur et par jour pour les données de surveillance et d’archivage.

|&nbsp;|CDR (Surveillance)  |QoE (Surveillance)  |Archivage  |
|:-----|:-----|:-----|:-----|
|Espace disque requis par utilisateur et par jour   |49 Ko   |28 Ko   |57 Ko   |

Microsoft a utilisé le matériel du tableau suivant pour le serveur de base de données pour la surveillance et l’archivage lors de ses tests de performances. Le test a collecté les données de deux pools frontaux, chacun contenant 80 000 utilisateurs.

**Matériel utilisé pour les tests de performances de surveillance et d’archivage**

|Composant matériel|Recommandé|
|:-----|:-----|
|UC   |Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur   |
|Mémoire   |48 gigaoctets (Go)   |
|Disque   |25 disques durs 10 000 TPM avec 300 Go sur chaque disque, avec la configuration du tableau suivant   |
|Réseau   | 1 carte réseau double port, 1 Gbps ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)   |

**Configurations de disque recommandées**

|Lecteur  |RAID Configuration  |Nombre de disques  |
|:-----|:-----|:-----|
|Fichiers de données de base de données cdr, QoE et d’archivage, sur un seul lecteur   |1+0   |16   |
|Fichier journal de la base de données d’enregistrement des détails des appels   |1   |2   |
|Fichier journal de la base de données QoE   |1   |2   |
|Fichier journal de la base de données d’archivage   |1   |2   |

## <a name="video-interop-server-capacity"></a>Capacité du serveur d’interconnexion vidéo

Si vous déployez le serveur d’interconnexion vidéo et que vous devez déterminer la capacité, vous devez examiner le nombre maximal de systèmes de téléconférence vidéo (VTC) qui seront en appels simultanés. Par exemple, si votre organisation compte 250 VTC et que votre modèle utilisateur estime qu’au maximum 20 % d’entre eux peuvent être en appels simultanés, vous basez votre planification de capacité sur 50 VTC simultanés.