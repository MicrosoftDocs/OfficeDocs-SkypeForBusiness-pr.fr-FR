---
title: Planification de capacité pour Skype pour Business Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Les rubriques de cette section vous aider à comprendre comment planifier et déployer Skype pour Business Server afin que vous pouvez planifier pour le nombre d’utilisateurs dans votre organisation et le plan de la charge du serveur qui génèrent de leurs activités.
ms.openlocfilehash: 1d20ed85c06514f4e999a966c5d137727842726d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875969"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>Planification de capacité pour Skype pour Business Server 2019

Cet article fournit des instructions sur le nombre de serveurs vous avez besoin sur un site pour le nombre d’utilisateurs sur le site, en fonction de l’utilisation décrite dans [modèles utilisateur Skype pour Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md)

## <a name="tested-hardware-platform"></a>Plateforme matérielle testée

Nous avons réalisé nos tests de performances sur le matériel décrit dans le tableau ci-dessous. L’ensemble de nos recommandations et résultats sont fondés sur ce matériel. Si vous décidez d’utiliser du matériel moins puissant que ce qui est répertorié ici, sachez que vous pourrez rencontrer des problèmes de fonctionnalité ou obtenir des performances médiocres.

**Matériel utilisé dans les tests de performances**

|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Intel Xeon E5-2673 v3 double processeur, 6-cœur, 2,4 gigahertz (GHz) ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype pour Business Server 2019 rôles.  <br/> |
|Mémoire  <br/> |32 giga-octets (Go).  <br/> |
|Disque  <br/> |SOIT :  <br/> • 8 ou plus disques durs de 10 000 tpm avec au moins 72 Go d’espace (deux de ces disques RAID 1 et 6 à l’aide de RAID 10).  <br/> OU  <br/> • SSD (Solid) en mesure de fournir le même espace et des performances similaires à 8 10 000 TPM disques durs mécaniques.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Les configurations doubles ou multi-hébergés sont **pas** serveurs pris en charge pour les serveurs frontaux, serveurs principaux et Standard Edition. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et sont utilisés pour surveiller et gérer le matériel du serveur, vous pouvez avoir hors de gestion des systèmes, tels que DRAC ou ILO. Une telle configuration ne constitue pas un serveur à plusieurs connexions et est prise en charge.  <br/> |

## <a name="summary-of-results"></a>Résumé des résultats

Le tableau ci-dessous résume nos recommandations.

|**Rôle serveur**|**Nombre maximal d’utilisateurs pris en charge**|
|:-----|:-----|
|Pool frontal avec seize serveurs frontaux et de serveur principal ou d’une paire de serveurs principaux avec SQL toujours pour une haute disponibilité.  <br/> |106 000 utilisateurs uniques connectés simultanément, plus 50 % plusieurs points de présence (MPOP) représentant des instances non mobiles, plus de 40 % des utilisateurs activés pour la mobilité pour un total de points de terminaison rythme de 210 000.  <br/> |
|Conférence A/V  <br/> |A / V Conferencing fourni par un pool frontal prend en charge les conférences du pool en supposant une taille maximale de la conférence de 250 utilisateurs et qu’une seule grande conférence en cours d’exécution à la fois.  <br/> **Remarque :** En outre, vous pouvez prendre en charge des grandes conférences d’entre 250 et 1 000 utilisateurs en déployant un pool frontal distinct avec deux serveurs frontaux pour héberger les conférences de grande taille. Pour plus d’informations, voir [planifier des réunions de grande taille dans Skype pour Business Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md). <br/> |
|Un serveur Edge  <br/> |18 000 utilisateurs distants simultanés.  <br/> |
|Un directeur  <br/> |18 000 utilisateurs distants simultanés.  <br/> |
|Surveillance et archivage  <br/> |Les services de frontal surveillance et archivage exécutés sur chaque serveur frontal, au lieu de rôles serveur séparés.  <br/> La surveillance et l’archivage requièrent un magasin de base de données chacun. Si vous exécutez également Exchange 2013 ou version ultérieure, vous pouvez conserver vos données d’archivage dans Exchange, plutôt que dans une base de données SQL dédié.  <br/> |
|Un serveur de médiation  <br/> |Serveur de médiation colocalisé avec le serveur frontal s’exécute sur chaque serveur frontal dans un pool et doit fournir suffisamment de capacité pour les utilisateurs dans le pool. Pour le serveur de médiation autonome, voir la section « Serveur de médiation » plus loin dans cette rubrique.  <br/> |
|Un serveur Standard Edition server  <br/> |Il est vivement recommandé que si vous utilisez des serveurs Standard Edition Server pour héberger des utilisateurs, vous utilisez toujours deux serveurs, couplés en utilisant les recommandations de [planification pour une haute disponibilité et récupération d’urgence](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Chaque serveur de la paire peut héberger jusqu'à 2 500 utilisateurs, et si le restant de la défaillance d’un serveur server peut prendre en charge 5 000 utilisateurs dans un scénario de basculement.  <br/>  Si votre déploiement présente un trafic audio ou vidéo important, les performances du serveur peuvent être affectées avec plus de 2 500 utilisateurs par serveur. Dans ce cas, vous devez envisager l’ajout de plusieurs serveurs Standard Edition Server ou le déplacement à Skype pour Business Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>serveur frontal

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Dans un pool frontal, vous devez disposer d’un que serveur frontal pour chaque 6 660 utilisateurs hébergé dans votre pool, en supposant que la technologie hyper-threading est activée sur tous les serveurs du pool, que vous utilisez SQL Server Express Edition et que le matériel du serveur répondent aux recommandations dans la [configuration serveur requise pour Skype pour Business Server 2019](system-requirements.md). Le nombre maximal d’utilisateurs dans un pool frontal est nouveau 106,000, en supposant que la technologie hyper-threading est activé et SQL Server Express Edition est utilisée sur tous les serveurs dans votre pool. Si vous avez plusieurs 106 000 utilisateurs sur un site, vous pouvez déployer plusieurs pool frontal.

Lorsque vous comptez le nombre d’utilisateurs dans un pool frontal, inclut tous les utilisateurs hébergés sur Survivable Branch Appliances et serveurs Survivable Branch Server dans les succursales qui sont associés à ce pool frontal.

Lorsqu’un serveur actif est indisponible, ses connexions sont transférées automatiquement vers les autres serveurs du pool. Dans un scénario où vous avez 30 000 utilisateurs et les cinq serveurs frontaux, si un serveur n’est pas disponible, les connexions de 6000 de vos utilisateurs doivent être transférés vers les autres serveurs restants quatre. Ces quatre serveurs restants contiendront chacun 7 500 utilisateurs, ce qui est un nombre supérieur à celui recommandé.

Si au lieu de cela vous a démarré avec six serveurs frontaux pour vos utilisateurs de 30 000 et 1 devient indisponible, un total de 5 000 utilisateurs devez déplacer vers les cinq serveurs restants. Ces cinq serveurs restants hébergent chacun 6 000 utilisateurs, ce qui est la plage recommandée.

Le nombre maximal d’utilisateurs dans un pool frontal est 106,000. Le nombre maximal de serveurs frontaux dans un pool est de 16.

Pour un pool frontal avec 80 000 utilisateurs, 16 serveurs frontaux est appropriées pour les performances, dans les déploiements standard qui suivent les [modèles utilisateur Skype pour Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md). Conçu pour prendre en charge le basculement de récupération d’urgence de déploiements supposent que 53,000 au maximum peut être hébergée dans chacun des deux pools frontaux couplés, dans lesquels chaque pool a suffisamment de serveurs frontaux pour contenir les utilisateurs dans les deux pools, un pool doit être basculé t o l’autre.

Le nombre d’utilisateurs pris en charge des performances correctes par un pool frontal particulier peut-être différer de ces numéros pour les raisons suivantes :

- Le matériel pour vos serveurs frontaux ne répond pas aux recommandations.
- Au lieu d’utiliser SQL Server Express Edition, vous utilisez un autre SQL Server Edition, vous pourrez pour héberger des utilisateurs supplémentaires dans chaque pool frontal.
- Utilisation de votre organisation est très différente des modèles utilisateur, par exemple, si vous avez beaucoup de trafic de conférence.

Le tableau suivant montre la bande passante moyenne pour la messagerie instantanée et présence, selon le modèle utilisateur défini dans [modèles utilisateur Skype pour Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

|**Bande passante moyenne par utilisateur**|**Bande passante requise par le serveur frontal avec 6 660 utilisateurs**|
|:-----|:-----|
|Kbits/s 3-3,75  <br/> |13 Mbits/s  <br/> |

> [!NOTE]
> Pour améliorer les performances multimédias de localisée au même emplacement A / V conférence et le serveur de médiation fonctionnalité sur vos serveurs frontaux, vous devez activer la côté réception montée en puissance (RSS) sur les cartes réseau sur vos serveurs frontaux. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, voir [Côté réception mise à l’échelle (RSS) dans la documentation de Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau.

## <a name="conferencing-maximums"></a>Nombre maximal de conférences

Étant donné le modèle utilisateur de 5 % des utilisateurs d’un pool peut être une conférence à tout moment, un pool de 106 000 utilisateurs peut avoir environ 5,300 utilisateurs dans les conférences simultanément. Ces conférences sont supposées être composées d’un mélange de plusieurs médias (messagerie instantanée uniquement, messagerie instantanée avec audio, audio/vidéo, par exemple) et du nombre de participants. Il n’existe pas de limite inconditionnelle au nombre réel de conférences autorisées, et l’utilisation réelle détermine les performances réelles. Par exemple, si votre organisation a un grand nombre de conférences en mode mixte plus que sont considérées comme dans le modèle utilisateur, vous devrez déployer plusieurs serveurs frontaux ou A / V Conferencing Servers que les recommandations présents dans cet article. Pour plus d’informations sur les hypothèses dans le modèle utilisateur, voir [modèles utilisateur Skype pour Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

La taille maximale de prise en charge la conférence hébergée par un régulière Skype pour Business Server un pool frontal qui héberge des utilisateurs est de 250 participants. Pendant une conférence avec 250 utilisateurs, le pool continue de prendre en charge d’autres conférences, un total de 5 % d’utilisateurs du pool peuvent se trouver dans des conférences simultanées. Par exemple, dans un pool de 16 serveurs frontaux et 106 000 utilisateurs, pendant la conférence 250 utilisateurs, Skype pour Business Server prend en charge 5,050 autres utilisateurs participant à des conférences plus petits.

Quel que soit le nombre d’utilisateurs hébergés sur le pool frontal ou serveur Standard Edition server, Skype pour Business Server prend en charge un minimum de 125 autres utilisateurs participant à des conférences plus petits sur le même pool ou serveur qui héberge une conférence de 250 utilisateurs.

Pour activer les conférences qui ont entre 250 et 1 000 utilisateurs, vous pouvez configurer un pool frontal distinct pour héberger les conférences. Ce pool frontal ne sont pas héberger des utilisateurs. Pour plus d’informations, consultez [planification des grandes réunions dans Skype pour Business Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md).

Si votre organisation a beaucoup plus de conférences en mode mixte que sont considérées comme dans le modèle utilisateur, vous devrez déployer plusieurs serveurs frontaux que nous recommandation dans ce document (jusqu'à une limite de 16 serveurs frontaux). Pour plus d’informations sur les hypothèses dans le modèle utilisateur, voir [modèles utilisateur Skype pour Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

## <a name="edge-server"></a>serveur Edge

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Vous devez déployer un serveur de périphérie pour chaque 18 000 utilisateurs distants qui accèdent à un site simultanément. Au minimum, nous vous recommandons de deux serveurs de périphérie pour une haute disponibilité. Ces recommandations supposent que le matériel pour les serveurs de périphérie répondent aux recommandations dans [Plateformes matérielles de serveur](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Lorsque vous comptez le nombre d’utilisateurs pour les serveurs de périphérie, ajoutez les utilisateurs hébergés sur Survivable Branch Appliances et serveurs Survivable Branch Server dans les succursales qui sont associés à un pool frontal sur ce site.

> [!NOTE]
> Pour améliorer les performances des A / V serveur Edge de conférence de service sur les serveurs Edge, vous devez activer côté réception mise à l’échelle (RSS) sur les cartes réseau sur les serveurs de périphérie. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez [Côté réception mise à l’échelle (RSS) dans Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731). Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau.

## <a name="director"></a>directeur

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Si vous déployez le rôle serveur directeur, nous vous recommandons de déployer un directeur pour chaque 18 000 utilisateurs distants qui accèdent à un site simultanément. Au minimum, nous vous recommandons de deux directeurs pour une haute disponibilité. Ces recommandations supposent que le matériel pour les serveurs de périphérie répondent aux recommandations dans [Plateformes matérielles de serveur](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Lorsque vous comptez le nombre d’utilisateurs pour les directeurs, ajoutez les utilisateurs hébergés sur Survivable Branch Appliances et serveurs Survivable Branch Server dans les succursales qui sont associés à un pool frontal sur ce site.

## <a name="mediation-server"></a>serveur de médiation

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Si vous colocalisez le serveur de médiation avec le serveur frontal, serveur de médiation s’exécute sur chaque serveur frontal du pool et doit fournir suffisamment de capacité pour les utilisateurs dans le pool.

Si vous déployez un pool de serveur de médiation autonome, puis le nombre de serveurs de médiation à déployer dépend de nombreux facteurs, notamment le matériel utilisé pour le serveur de médiation, le nombre d’utilisateurs VoIP, le nombre de passerelle homologues que chaque pool de serveur de médiation contrôles, le trafic des heures de pointe via ces passerelles et le pourcentage d’appels avec support contournant le serveur de médiation.

Les tableaux suivants fournissent des instructions pour le nombre d’appels simultanés un serveur de médiation peuvent gérer, en supposant que le matériel pour les serveurs de médiation répond aux exigences de [Plateformes matérielles de serveur](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) et que la technologie hyper-threading est activé. Pour plus d’informations sur l’évolutivité du serveur de médiation, voir [utilisation de voix d’estimer et le trafic Skype pour Business Server](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md) et [les instructions de déploiement pour le serveur de médiation dans Skype pour Business Server](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md).

Tous les tableaux suivants présupposent une utilisation résumées dans [modèles utilisateur Skype pour Business Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

**Capacité du serveur de médiation autonome : 70 % d’utilisateurs internes, 30 % des utilisateurs externes disposant sans contournement (transcodage multimédia effectué par le serveur de médiation) capacité d’appels**

|**Matériel serveur**|**Nombre maximal d’appels**|**Nombre maximal de lignes T1**|**Nombre maximal de lignes E1**|
|:-----|:-----|:-----|:-----|
|Intel Xeon E5-2673 v3 double processeur, 6-cœur, 2,4 gigahertz (GHz) ou supérieure **avec hyper-threading désactivé**, avec 64 Go de mémoire et une carte réseau double port.  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Intel Xeon E5-2673 v3 double processeur, 6-cœur, 2,4 gigahertz (GHz) ou supérieur, avec 64 Go de mémoire et une carte réseau double port.  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> Bien que les serveurs avec 64 Go de mémoire ont été utilisés pour les tests de performances, les serveurs avec 32 Go de mémoire sont pris en charge pour le serveur de médiation autonome et sont suffisantes pour fournir les performances indiquées dans ce tableau.

**Capacité de serveur de médiation (serveur de médiation colocalisé avec le serveur frontal) 70 % d’utilisateurs internes, 30 % des utilisateurs externes, la capacité d’appel sans contournement (traitement multimédia effectué par le serveur de médiation)**

|**Matériel serveur**|**Nombre maximal d’appels**|
|:-----|:-----|
|Intel Xeon E5-2673 v3 double processeur, 6-cœur, 2,4 gigahertz (GHz) ou supérieur., avec 64 Go de mémoire et 2 cartes réseau de 1 Go.  <br/> |200  <br/> |

> [!NOTE]
> Ce nombre est beaucoup plus petit que les numéros pour le serveur de médiation autonome. C’est parce que le serveur frontal a gérer les autres fonctionnalités et fonctions pour les 6600 utilisateurs hébergement, outre le transcodage nécessaire pour les appels vocaux.

> [!NOTE]
> Pour améliorer les performances du serveur de médiation, vous devez activer côté réception mise à l’échelle (RSS) sur les cartes réseau sur vos serveurs de médiation. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, voir «[Receive-Side Scaling dans Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)». Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau.

## <a name="back-end-server"></a>serveur principal

Bien que la plupart des informations de base de données est stockée principalement sur les serveurs frontaux, vous devez vous assurer que vos serveurs principaux répondent aux recommandations matérielles répertoriées plus haut dans cette section et [Plateformes matérielles de serveur](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Pour fournir une haute disponibilité de votre serveur principal, nous vous recommandons de déployer des groupes de disponibilité AlwaysOn ou la mise en miroir du serveur. Pour plus d’informations, reportez-vous à la rubrique [Back End Server high availability in Skype for Business Server](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Surveillance et archivage

Si vous déployez l’analyse ou l’archivage, la fonctionnalité front-end de ces services s’exécute sur le Front End Servers, surveillance et archivage utilisent leur propre banque de base de données distinct à partir du magasin du serveur frontal. Sinon, si vous avez déployé de Exchange 2013, vous pouvez stocker données d’archivage des messages instantanés dans Exchange au lieu de dans un magasin SQL dédié.

Le tableau ci-dessous indique approximativement la quantité de stockage de base de données nécessaire par utilisateur par jour pour les données de surveillance et d’archivage.

||**CDR (surveillance)** <br/> |**QoE (surveillance)** <br/> |**Archivage** <br/> |
|:-----|:-----|:-----|:-----|
|Espace disque requis par utilisateur par jour  <br/> |49 Ko  <br/> |28 Ko  <br/> |57 Ko  <br/> |

Microsoft a utilisé le matériel décrit dans le tableau ci-dessous pour le serveur de base de données pour la surveillance et l’archivage lors des tests de performances. Les tests de collecte les données des deux pools frontaux, chacun d'entre eux contenus 80 000 utilisateurs.

**Matériel utilisé pour le test des performances d’archivage et de la surveillance**

|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Intel Xeon E5-2673 v3 double processeur, 6-cœur, 2,4 gigahertz (GHz) ou supérieur.  <br/> |
|Mémoire  <br/> |48 GO  <br/> |
|Disque  <br/> | SOIT :<br/> • 4 ou plus 10 000 TPM disques durs avec au moins 72 Go d’espace (les disques doivent être dans une configuration RAID 1 x 2). <br/>OU <br/>• SSD (Solid) en mesure de fournir le même espace et des performances similaires à 4 10 000 TPM disques durs mécaniques.   <br/> |
|Réseau  <br/> | 1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP).  <br/> |

**Configurations de disque recommandées**

|**Lecteur** <br/> |**Configuration RAID** <br/> |**Nombre de disques** <br/> |
|:-----|:-----|:-----|
|Fichiers de données des bases de données CDR, QoE et d’archivage sur un seul disque  <br/> |1+0  <br/> |16  <br/> |
|Fichier journal de la base de données d’enregistrement des détails des appels  <br/> |1  <br/> |2  <br/> |
|Fichier journal de la base de données QoE  <br/> |1  <br/> |2  <br/> |
|Fichier journal de la base de données d’archivage  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Capacité d’un serveur de l’interopérabilité vidéo

Si vous déployez le serveur d’interopérabilité vidéo et vous devez déterminer la capacité, examinez le nombre maximal de systèmes de téléconférence vidéo (VTCs) qui seront inclus dans les appels simultanés. Par exemple, si vous avez 250 systèmes de téléconférence vidéo dans votre organisation et que votre modèle utilisateur estime qu’au maximum 20 % de ceux-ci peuvent se trouver dans des appels simultanés, vous basez votre capacité sur 50 systèmes de téléconférence vidéo simultanés.

