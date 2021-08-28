---
title: Planification de la capacité Skype Entreprise Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: Les rubriques de cette section vous aident à comprendre comment planifier et déployer des Skype Entreprise Server afin de pouvoir planifier correctement le nombre d’utilisateurs de votre organisation et la charge de serveur générée par leurs activités.
ms.openlocfilehash: 090d209d1b60d866ddabe976ffb8b04394712525
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600889"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>Planification de la capacité Skype Entreprise Server 2019

Cet article fournit des instructions sur le nombre de serveurs dont vous avez besoin sur un site pour le nombre d’utilisateurs sur ce site, en fonction de l’utilisation décrite dans les modèles utilisateur [dans Skype Entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)

## <a name="tested-hardware-platform"></a>Plateforme matérielle testée

Nous avons effectué nos tests de performances sur le matériel décrit dans le tableau ci-dessous. Toutes nos recommandations et résultats sont basés sur ce matériel. Si vous décidez d’utiliser un matériel moins puissant que celui répertorié ici, sachez que vous pouvez être confronté à des problèmes de fonctionnalité ou à des performances médiocres.

**Matériel utilisé dans les tests de performances**

|**Composant matériel**|**Recommandée**|
|:-----|:-----|
|UC  <br/> |Processeur double Intel Xeon E5-2673 v3, 6 cœurs, 2,4 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype Entreprise Server 2019.  <br/> |
|Mémoire  <br/> |32 gigaoctets (Go).  <br/> |
|Disque  <br/> |SOIT :  <br/> • 8 disques durs ou plus de 1 0000 TPM avec au moins 72 Go d’espace disque libre (deux disques utilisant RAID 1 et 6 utilisant RAID 10).  <br/> OU  <br/> • Des disques SSD (Solid State Drives) capables de fournir le même espace libre et des performances similaires à 8 disques mécaniques 10000 RPM.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbits/s ou plus (2 cartes réseau peuvent être utilisées, mais elles doivent être liées à une seule adresse MAC et une seule adresse IP).  <br/> Les configurations à double  ou multi-accueil ne sont pas pris en charge pour les serveurs frontaux, les serveurs frontaux et les serveurs Édition Standard serveurs. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et qu’ils sont utilisés pour surveiller et gérer le matériel du serveur, vous pouvez avoir des systèmes de gestion hors bande, tels que DRAC ou ILO. Ce scénario ne constitue pas un serveur multi-accueil et il est pris en charge.  <br/> |

## <a name="summary-of-results"></a>Résumé des résultats

Le tableau suivant résume nos recommandations.

|**Rôle serveur**|**Nombre maximal d’utilisateurs pris en charge**|
|:-----|:-----|
|Pool frontal avec 16 serveurs frontux et serveurs frontux ou une paire de serveurs frontux avec SQL Always On pour la haute disponibilité.  <br/> |106 000 utilisateurs uniques connectés simultanément, plus 50 % de points de présence multiples (MPOP) représentant des instances non mobiles, plus 40 % d’utilisateurs activés pour la mobilité pour un total de 210 000 points de terminaison.  <br/> |
|Conférence A/V  <br/> |Le service de conférence A/V fourni par un pool frontal prend en charge les conférences du pool en supposant une taille maximale de conférence de 250 utilisateurs et une seule conférence de ce type s’exécutant à la fois.  <br/> **Remarque :** En outre, vous pouvez prendre en charge de grandes conférences de 250 à 1 000 utilisateurs en déployant un pool frontal distinct avec deux serveurs frontaux pour héberger les grandes conférences. Pour plus d’informations, [voir Planifier les grandes réunions dans Skype Entreprise Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md). <br/> |
|Un serveur Edge  <br/> |18 000 utilisateurs distants simultanés.  <br/> |
|Un directeur  <br/> |18 000 utilisateurs distants simultanés.  <br/> |
|Surveillance et archivage  <br/> |Les services frontaux de surveillance et d’archivage s’exécutent sur chaque serveur frontal, et non sur des rôles serveur distincts.  <br/> La surveillance et l’archivage requièrent chacun leurs propres magasins de bases de données. Si vous exécutez également Exchange 2013 ou une ultérieure, vous pouvez conserver vos données d’archivage dans Exchange, plutôt que dans une base de données SQL dédiée.  <br/> |
|Un serveur de médiation  <br/> |Le serveur de médiation coqueté avec le serveur frontal s’exécute sur chaque serveur frontal d’un pool et doit fournir une capacité suffisante pour les utilisateurs du pool. Pour un serveur de médiation autonome, consultez la section « Serveur de médiation » plus loin dans cette rubrique.  <br/> |
|Un serveur Standard Edition Server  <br/> |Si vous utilisez des serveurs Édition Standard pour héberger des utilisateurs, nous vous recommandons vivement d’utiliser toujours deux serveurs, associés à l’aide des recommandations de planning pour la haute disponibilité et la récupération [d’urgence.](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-high-availability-and-disaster-recovery) Chaque serveur de la paire peut héberger jusqu’à 2 500 utilisateurs, et en cas d’échec d’un serveur, le serveur restant peut prendre en charge 5 000 utilisateurs dans un scénario de failover.  <br/>  Si votre déploiement inclut une quantité importante de trafic audio ou vidéo, les performances du serveur peuvent être en baisse avec plus de 2 500 utilisateurs par serveur. Dans ce cas, vous devez envisager d’ajouter des serveurs Édition Standard serveurs ou de passer à Skype Entreprise Server Êdition Entreprise. <br/> |

## <a name="front-end-server"></a>serveur frontal

> [!NOTE]
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.

Dans un pool frontal, vous devez avoir un serveur frontal pour 6 660 utilisateurs tous les 660 utilisateurs de votre pool, en supposant que l’hyper-threading est activé sur tous les serveurs du pool, que vous utilisez SQL Server Express Edition et que le matériel serveur répond aux recommandations de la configuration serveur requise pour [Skype Entreprise Server 2019](system-requirements.md). Le nombre maximal d’utilisateurs dans un pool frontal est de 106 000, là encore en supposant que l’hyper-threading est activé et que SQL Server Express Edition est utilisé sur tous les serveurs de votre pool. Si vous avez plus de 106 000 utilisateurs sur un site, vous pouvez déployer plusieurs pool frontal.

Lorsque vous comptez le nombre d’utilisateurs dans un pool frontal, incluez tous les utilisateurs qui sont élevés sur les Survivable Branch Appliances et les serveurs Survivable Branch Servers des succursales associés à ce pool frontal.

Lorsqu’un serveur actif est indisponible, ses connexions sont transférées automatiquement aux autres serveurs du pool. Dans un scénario où vous avez 30 000 utilisateurs et cinq serveurs frontaux, si un serveur n’est pas disponible, les connexions de 6 000 de vos utilisateurs doivent être transférées vers vos quatre autres serveurs restants. Ces quatre serveurs restants auront chacun 7 500 utilisateurs, ce qui est un nombre supérieur à celui recommandé.

Si, à la place, vous aviez démarré avec six serveurs frontaux pour vos 30 000 utilisateurs et qu’un serveur devient indisponible, un total de 5 000 utilisateurs doit passer aux cinq serveurs restants. Ces cinq serveurs restants hébergeront chacun 6 000 utilisateurs, ce qui se trouve dans la plage recommandée.

Le nombre maximal d’utilisateurs dans un pool frontal est de 106 000. Le nombre maximal de serveurs frontux dans un pool est de 16.

Pour un pool frontal de 80 000 utilisateurs, 16 serveurs frontaux sont bons pour les performances, dans les déploiements classiques qui suivent les modèles utilisateur dans [Skype Entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md). Les déploiements conçus pour prendre en charge leover de récupération d’urgence supposent qu’un maximum de 53 000 utilisateurs peuvent être hébergés dans chacun des deux pools frontaux couplés, dans lesquels chaque pool dispose de suffisamment de serveurs frontaux pour contenir les utilisateurs dans les deux pools, si un pool doit être re failed vers l’autre.

Le nombre d’utilisateurs pris en charge avec de bonnes performances par un pool frontal particulier peut différer de ces nombres pour les raisons suivantes :

- Le matériel de vos serveurs frontaux ne répond pas aux recommandations.
- Au lieu d’utiliser SQL Server Express Edition, vous utilisez une autre édition SQL Server, vous pourrez peut-être héberger des utilisateurs supplémentaires dans chaque pool frontal.
- L’utilisation de votre organisation est très différente des modèles utilisateur, par exemple, si vous avez beaucoup plus de trafic de conférence.

Le tableau suivant indique la bande passante moyenne pour la messagerie instantanée et la présence, selon le modèle utilisateur, tel que défini dans les modèles utilisateur [Skype Entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

|**Bande passante moyenne par utilisateur**|**Besoins en bande passante par serveur frontal avec 6 660 utilisateurs**|
|:-----|:-----|
|3-3,75 KBits/s  <br/> |13 Mbits/s  <br/> |

> [!NOTE]
> Pour améliorer les performances multimédias des fonctionnalités de conférence A/V et de serveur de médiation sur vos serveurs frontaux, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau de vos serveurs frontaux. RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur. Pour plus d’informations, [voir La mise à l’échelle côté réception (RSS)](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))dans la documentation Windows Server 2012. Pour plus d’informations sur la façon d’activer RSS, vous devez vous référer à la documentation de votre carte réseau.

## <a name="conferencing-maximums"></a>Nombre maximal de conférences

Selon le modèle utilisateur, 5 % des utilisateurs d’un pool peuvent être en même temps dans une conférence, un pool de 106 000 utilisateurs peut avoir environ 5 300 utilisateurs simultanément dans des conférences. Ces conférences sont supposées être composées d’un mélange de plusieurs médias (messagerie instantanée uniquement, messagerie instantanée avec audio, audio/vidéo par exemple) et du nombre de participants. Il n’existe pas de limite difficile pour le nombre réel de conférences autorisées, et l’utilisation réelle détermine les performances réelles. Par exemple, si votre organisation compte beaucoup plus de conférences en mode mixte que ce qui est supposé dans le modèle utilisateur, vous devrez peut-être déployer plus de serveurs frontaux ou de serveurs de conférence A/V que les recommandations de cet article. Pour plus d’informations sur les hypothèses dans le modèle utilisateur, voir [modèles utilisateur dans Skype Entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

La taille maximale de conférence prise en charge hébergée par un pool Skype Entreprise Server frontal qui héberge également des utilisateurs est de 250 participants. Pendant qu’une conférence de 250 utilisateurs est en cours, le pool prend également en charge d’autres conférences, de telle façon qu’un total de 5 % des utilisateurs du pool sont en conférences simultanées. Par exemple, dans un pool de 16 serveurs frontaux et de 106 000 utilisateurs, alors que la conférence de 250 utilisateurs a lieu, Skype Entreprise Server prend en charge 5 050 autres utilisateurs participant à des conférences plus petites.

Quel que soit le nombre d’utilisateurs sur le pool frontal ou le serveur Édition Standard, Skype Entreprise Server prend en charge un minimum de 125 autres utilisateurs participant à des conférences plus petites sur le même pool ou serveur qui héberge une conférence de 250 utilisateurs.

Pour activer les conférences qui comptent entre 250 et 1 000 utilisateurs, vous pouvez configurer un pool frontal distinct uniquement pour héberger ces conférences. Ce pool frontal n’héberge aucun utilisateur. Pour plus d’informations, voir [Planifier les grandes réunions dans Skype Entreprise Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md).

Si votre organisation a beaucoup plus de conférences en mode mixte que ce qui est supposé dans le modèle utilisateur, vous devrez peut-être déployer plus de serveurs frontaux que ce que nous vous avons recommandé dans ce document (jusqu’à une limite de 16 serveurs frontaux). Pour plus d’informations sur les hypothèses dans le modèle utilisateur, voir [modèles utilisateur dans Skype Entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

## <a name="edge-server"></a>Serveur Edge

> [!NOTE]
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.

Vous devez déployer un serveur Edge pour 18 000 utilisateurs distants qui accèderont simultanément à un site. Nous vous conseillons au moins deux serveurs Edge pour une disponibilité élevée. Ces recommandations supposent que le matériel de vos serveurs Edge répond aux recommandations des [plateformes matérielles serveur.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Lorsque vous comptez le nombre d’utilisateurs pour les serveurs Edge, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à un pool frontal sur ce site.

> [!NOTE]
> Pour améliorer les performances du service Edge de conférence A/V sur vos serveurs Edge, vous devez activer le partage du trafic entrant (RSS, Receive-Side Scaling) sur les cartes réseau de vos serveurs Edge. RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur. Pour plus d’informations, [consultez la mise à l’échelle](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))côté réception (RSS) dans Windows Server 2012 . Pour plus d’informations sur la façon d’activer RSS, vous devez vous référer à la documentation de votre carte réseau.

## <a name="director"></a>Directeur

> [!NOTE]
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.

Si vous déployez le rôle de serveur directeur, nous vous recommandons de déployer un directeur pour 18 000 utilisateurs distants qui accèderont simultanément à un site. Nous vous conseillons au moins deux directeurs pour une disponibilité élevée. Ces recommandations supposent que le matériel de vos serveurs Edge répond aux recommandations des [plateformes matérielles serveur.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

Lorsque vous comptez le nombre d’utilisateurs pour les directeurs, ajoutez les utilisateurs hébergés sur les Survivable Branch Appliances et les serveurs Survivable Branch Server des succursales associés à un pool frontal sur ce site.

## <a name="mediation-server"></a>Serveur de médiation

> [!NOTE]
> Les pools étirés ne sont pas pris en charge pour ce rôle serveur.

Si vous coloyez le serveur de médiation avec un serveur frontal, celui-là s’exécute sur chaque serveur frontal du pool et doit fournir une capacité suffisante pour les utilisateurs du pool.

Si vous déployez un pool de serveurs de médiation autonome, le nombre de serveurs de médiation à déployer dépend de nombreux facteurs, notamment le matériel utilisé pour le serveur de médiation, le nombre d’utilisateurs VoIP que vous avez, le nombre d’homologues de passerelle que chaque pool de serveurs de médiation contrôle, le trafic aux heures de pointe via ces passerelles et le pourcentage d’appels avec un média qui contourne le serveur de médiation.

Les tableaux suivants fournissent des indications sur le nombre d’appels simultanés qu’un serveur de médiation peut gérer, en supposant que le matériel des serveurs de médiation répond aux exigences des [plateformes matérielles](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms) serveur et que l’hyper-thread est activé. Pour plus d’informations sur l’évolutivité du serveur de médiation, voir [Estimateing voice usage and traffic for Skype Entreprise Server](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md) and Deployment guidelines for Mediation Server in [Skype Entreprise Server](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md).

Tous les tableaux suivants supposent une utilisation telle qu’elle est résumée dans [les modèles utilisateur Skype Entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

**Capacité du serveur de médiation autonome : 70 % d’utilisateurs internes, 30 % d’utilisateurs externes avec une capacité d’appel sans contournement (transcodage multimédia effectué par le serveur de médiation)**

|**Matériel serveur**|**Nombre maximal d’appels**|**Nombre maximal de lignes T1**|**Nombre maximal de lignes E1**|
|:-----|:-----|:-----|:-----|
|Processeur double Intel Xeon E5-2673 v3, 6 cœurs, 2,4 gigahertz (GHz) ou supérieur avec désactivation de **l’hyperthèque,** avec 64 Go de mémoire et une carte carte réseau double port.  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Processeur double Intel Xeon E5-2673 v3, 6 cœurs, 2,4 gigahertz (GHz) ou supérieur, avec 64 Go de mémoire et une carte carte réseau double port.  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> Bien que les serveurs avec 64 Go de mémoire soient utilisés pour les tests de performances, les serveurs avec 32 Go de mémoire sont pris en charge pour le serveur de médiation autonome et sont suffisants pour fournir les performances indiquées dans ce tableau.

**Capacité du serveur de médiation (serveur de médiation cocté avec serveur frontal) 70 % d’utilisateurs internes, 30 % d’utilisateurs externes, capacité sans contournement des appels (traitement multimédia effectué par le serveur de médiation)**

|**Matériel serveur**|**Nombre maximal d’appels**|
|:-----|:-----|
|Processeur double Intel Xeon E5-2673 v3, 6 cœurs, 2,4 gigahertz (GHz) ou supérieur. Avec 64 Go de mémoire et 2 cartes réseau de 1 Go.  <br/> |200  <br/> |

> [!NOTE]
> Ce nombre est beaucoup plus petit que le nombre pour le serveur de médiation autonome. En effet, le serveur frontal doit gérer d’autres fonctionnalités et fonctions pour les 6 600 utilisateurs qui y sont homed, en plus du transcodage nécessaire pour les appels vocaux.

> [!NOTE]
> Pour améliorer les performances du serveur de médiation, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur vos serveurs de médiation. RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur. Pour plus d’informations, voir « Mise à l’échelle côté[réception Windows Server 2012](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))». Pour plus d’informations sur la façon d’activer RSS, vous devez vous référer à la documentation de votre carte réseau.

## <a name="back-end-server"></a>Serveur principal

Bien que la plupart des informations de base de données sont stockées principalement sur les serveurs frontaux, vous devez vous assurer que vos serveurs frontaux répondent aux recommandations matérielles répertoriées plus haut dans cette section et dans les [plateformes matérielles](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)serveur.

Pour fournir une haute disponibilité de votre serveur principal, nous vous recommandons de déployer des groupes de disponibilité AlwaysOn ou la mise en miroir de serveur. Pour plus d’informations, [voir la haute disponibilité du](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)serveur principal dans Skype Entreprise Server .

## <a name="monitoring-and-archiving"></a>Surveillance et archivage

Si vous déployez la surveillance ou l’archivage, la fonctionnalité frontale de ces services s’exécute sur les serveurs frontaux, la surveillance et l’archivage utilisent chacun leur propre magasin de bases de données, séparément de la banque principale. Si vous avez déployé Exchange 2013, vous pouvez également stocker les données d’archivage des messages instantanés dans Exchange plutôt que dans un magasin de SQL dédié.

Le tableau suivant indique approximativement la quantité de stockage de base de données requise par utilisateur et par jour pour les données de surveillance et d’archivage.

||**CDR (Surveillance)** <br/> |**QoE (Surveillance)** <br/> |**Archivage** <br/> |
|:-----|:-----|:-----|:-----|
|Espace disque requis par utilisateur et par jour  <br/> |49 Ko  <br/> |28 Ko  <br/> |57 Ko  <br/> |

Microsoft a utilisé le matériel du tableau suivant pour le serveur de base de données pour la surveillance et l’archivage lors de ses tests de performances. Le test a collecté les données de deux pools frontaux, chacun contenant 80 000 utilisateurs.

**Matériel utilisé pour les tests de performances de surveillance et d’archivage**

|**Composant matériel**|**Recommandée**|
|:-----|:-----|
|UC  <br/> |Processeur double Intel Xeon E5-2673 v3, 6 cœurs, 2,4 gigahertz (GHz) ou supérieur.  <br/> |
|Mémoire  <br/> |48 Go  <br/> |
|Disque  <br/> | SOIT :<br/> • 4 disques durs ou plus de 1 0000 MPM avec au moins 72 Go d’espace disque libre (les disques doivent être dans une configuration RAID 1 2x). <br/>OU <br/>• Disques SSD (Solid State Drive) capables de fournir le même espace libre et des performances similaires à 4 disques mécaniques 10000 RPM.   <br/> |
|Réseau  <br/> | 1 carte réseau double port, 1 Gbits/s ou plus (2 recommandé, ce qui nécessite une seule adresse MAC et une seule adresse IP).  <br/> |

**Configurations de disque recommandées**

|**Drive** <br/> |**RAID Configuration** <br/> |**Nombre de disques** <br/> |
|:-----|:-----|:-----|
|Fichiers de données de base de données cdr, QoE et d’archivage, sur un seul lecteur  <br/> |1+0  <br/> |16   <br/> |
|Fichier journal de la base de données d’enregistrement des détails des appels  <br/> |1   <br/> |2   <br/> |
|Fichier journal de la base de données QoE  <br/> |1   <br/> |2   <br/> |
|Fichier journal de la base de données d’archivage  <br/> |1   <br/> |2   <br/> |

## <a name="video-interop-server-capacity"></a>Capacité du serveur d’interconnexion vidéo

Si vous déployez le serveur d’interconnexion vidéo et que vous devez déterminer la capacité, vous devez examiner le nombre maximal de systèmes de téléconférence vidéo (VTC) qui seront en appels simultanés. Par exemple, si votre organisation compte 250 VTC et que votre modèle utilisateur estime qu’au maximum 20 % d’entre eux peuvent être en appels simultanés, vous basez votre planification de capacité sur 50 VTC simultanés.