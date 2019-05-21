---
title: Planification de la capacité pour Skype entreprise Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Les rubriques de cette section vous expliquent comment planifier et déployer Skype entreprise Server de façon à ce que vous puissiez planifier le nombre d’utilisateurs de votre organisation de manière appropriée et planifier la charge serveur que leurs activités génèrent.
ms.openlocfilehash: 4dca5470b5512bb8a6310a60442478c761c7411e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284073"
---
# <a name="capacity-planning-for-skype-for-business-server-2019"></a>Planification de la capacité pour Skype entreprise Server 2019

Cet article fournit des recommandations sur le nombre de serveurs dont vous avez besoin sur un site pour le nombre d’utilisateurs sur ce site, en fonction de l’utilisation décrite dans la rubrique [modèles d’utilisateur de Skype entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md) .

## <a name="tested-hardware-platform"></a>Plateforme matérielle testée

Nous avons réalisé nos tests de performances sur le matériel décrit dans le tableau ci-dessous. L’ensemble de nos recommandations et résultats sont fondés sur ce matériel. Si vous décidez d’utiliser du matériel moins puissant que ce qui est répertorié ici, sachez que vous pourrez rencontrer des problèmes de fonctionnalité ou obtenir des performances médiocres.

**Matériel utilisé dans les tests de performances**

|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Processeur Intel Xeon E5-2673 v3 double processeur, 6 cœurs, 2,4 gigahertz (GHz) ou version ultérieure.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles 2019 de Skype entreprise Server.  <br/> |
|Mémoire  <br/> |32 giga-octets (Go).  <br/> |
|Disque  <br/> |SOIT :  <br/> • 8 lecteurs de disque dur, ou plus de 10000, avec au moins 72 Go d’espace libre sur le disque dur (deux des disques avec RAID 1 et 6 avec RAID 10).  <br/> OU  <br/> • Lecteurs d’État SSD (SSDs) en mesure d’offrir un espace libre et des performances similaires pour les disques mécaniques 8 10000 RPM.  <br/> |
|Réseau  <br/> |1 carte réseau double port, 1 Gbit/s ou plus (2 cartes réseaux peuvent être utilisées, mais elles doivent être associées à une seule adresse MAC et à une seule adresse IP).  <br/> Les configurations à double ou à hébergement multiple ne sont **pas** prises en charge pour les serveurs frontaux, les serveurs dorsaux et les serveurs Standard Edition. <br/> Tant qu’ils ne sont pas exposés au système d’exploitation et sont utilisés pour surveiller et gérer le matériel du serveur, vous pouvez disposer de systèmes de gestion hors-bande tels que DRAC ou ILO. Une telle configuration ne constitue pas un serveur à plusieurs connexions et est prise en charge.  <br/> |

## <a name="summary-of-results"></a>Résumé des résultats

Le tableau ci-dessous résume nos recommandations.

|**Rôle serveur**|**Nombre maximal d’utilisateurs pris en charge**|
|:-----|:-----|
|Pool frontal avec seize serveurs frontaux et serveur principal ou paire de serveurs dorsaux avec SQL toujours activé pour une disponibilité élevée.  <br/> |106 000 210 000 40 50, xxxxxxx, xxxxxxx, XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX.  <br/> |
|Conférence A/V  <br/> |Le service de conférence A/V fourni par un pool frontal prend en charge les conférences du pool en supposant la taille maximale d’une conférence d’utilisateurs 250, et une seule conférence de grande envergure exécutée à la fois.  <br/> **Remarque:** De plus, vous pouvez prendre en charge des conférences de grande envergure entre les utilisateurs de 250 et de 1000 en déployant un pool frontal distinct avec deux serveurs front-end pour héberger les conférences de grande envergure. Pour plus d’informations, reportez-vous à la section [planifier des réunions de grande envergure dans Skype entreprise Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md). <br/> |
|Un serveur Edge  <br/> |18 000 utilisateurs distants concurrents.  <br/> |
|Un réalisateur  <br/> |18 000 utilisateurs distants concurrents.  <br/> |
|Surveillance et archivage  <br/> |Les services front-end d’analyse et d’archivage s’exécutent sur chaque serveur frontal, au lieu de rôles de serveur distincts.  <br/> La surveillance et l’archivage requièrent un magasin de base de données chacun. Si vous exécutez également Exchange 2013 ou une version ultérieure, vous pouvez conserver vos données d’archivage dans Exchange, au lieu d’une base de données SQL dédiée.  <br/> |
|Un serveur de médiation  <br/> |Le serveur de médiation en fonction du serveur frontal s’exécute sur chaque serveur frontal d’un pool et doit fournir une capacité suffisante aux utilisateurs de la liste. Pour un serveur de médiation autonome, voir la section «serveur de médiation» plus loin dans cette rubrique.  <br/> |
|One Standard Edition Server  <br/> |Nous vous recommandons vivement de recourir à des serveurs Standard Edition pour héberger les utilisateurs, que vous utilisez toujours deux serveurs, couplés selon les recommandations en [matière de planification d’une haute disponibilité et de récupération d’urgence](https://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Chaque serveur dans la paire peut accueillir jusqu’à 2 500 utilisateurs et, si un serveur tombe en panne, le serveur restant peut prendre en charge les utilisateurs 5 000 dans le cas d’un basculement.  <br/>  Si votre déploiement présente un trafic audio ou vidéo important, les performances du serveur peuvent être affectées avec plus de 2 500 utilisateurs par serveur. Dans ce cas, envisagez d’ajouter d’autres serveurs Standard Edition ou de migrer vers Skype entreprise Server Enterprise Edition. <br/> |

## <a name="front-end-server"></a>serveur frontal

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Dans une liste frontale, vous devez disposer d’un serveur frontal pour chaque 6 660 hébergé dans votre pool, en supposant que la technologie HyperThreading soit activée sur tous les serveurs du pool, que vous utilisez SQL Server Express Edition et que le matériel du serveur répond aux recommandations. dans [Configuration requise pour le serveur Skype entreprise Server 2019](system-requirements.md). Le nombre maximal d’utilisateurs dans une liste frontale est de 106 000, en partant du principe que la technologie hyperthreading est activée et que SQL Server Express Edition est utilisé sur tous les serveurs de votre pool. Si vous avez plus d’utilisateurs 106 000 sur un site, vous pouvez déployer plusieurs pools front-end.

Lorsque vous comptez le nombre d’utilisateurs dans un pool frontal, incluez tous les utilisateurs hébergés sur des appareils de succursales Survivables et des serveurs de succursales survivant dans les succursales associées à ce pool frontal.

Lorsqu’un serveur actif est indisponible, ses connexions sont transférées automatiquement vers les autres serveurs du pool. Dans un scénario dans lequel vous avez 30 000 utilisateurs et cinq serveurs frontaux, si un serveur n’est pas disponible, les connexions d' 6000 de vos utilisateurs doivent être transférées sur les quatre autres serveurs restants. Ces quatre serveurs restants contiendront chacun 7 500 utilisateurs, ce qui est un nombre supérieur à celui recommandé.

Si, au lieu de cela, vous avez commencé à utiliser six serveurs frontaux pour vos utilisateurs 30 000 et que l’un d’eux devient indisponible, le nombre total d’utilisateurs d' 5000 doivent être déplacés vers les cinq serveurs restants. Ces cinq serveurs restants hébergent chacun 6 000 utilisateurs, ce qui est la plage recommandée.

Le nombre maximal d’utilisateurs dans une liste frontale est de 106 000. Le nombre maximal de serveurs frontaux dans un pool est de 16.

Dans le cas d’un pool frontal avec des utilisateurs 80 000, 16 serveurs frontaux est approprié pour les performances, dans les déploiements typiques qui suivent les [modèles utilisateur dans Skype entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md). Les déploiements conçus pour prendre en charge le basculement de reprise après sinistre présupposent qu’un maximum de 53 000 utilisateurs peuvent être hébergés dans chacun des deux pools frontaux couplés, dans lesquels chaque pool dispose de serveurs frontaux suffisants pour contenir les utilisateurs des deux pools, en cas d’échec d’un pool sur t o l’autre.

Le nombre d’utilisateurs pris en charge avec une bonne performance par un pool frontal particulier peuvent différer de ces numéros pour les raisons suivantes:

- Le matériel de votre serveur frontal ne répond pas aux recommandations.
- Au lieu d’utiliser SQL Server Express Edition, vous utilisez une autre version de SQL Server, vous serez peut-être en mesure d’héberger des utilisateurs supplémentaires dans chaque pool frontal.
- L’utilisation de votre organisation est très différente des modèles utilisateur, par exemple, si vous avez beaucoup plus de trafic de conférence.

Le tableau suivant indique la bande passante moyenne pour la messagerie instantanée et la présence, en fonction du modèle utilisateur, tel qu’il est défini dans [modèles utilisateur dans Skype entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

|**Bande passante moyenne par utilisateur**|**Besoins en bande passante par serveur frontal avec les utilisateurs 6 660**|
|:-----|:-----|
|3-3,75 KBps  <br/> |13 MBps  <br/> |

> [!NOTE]
> Pour améliorer les performances multimédias de la fonctionnalité de conférence A/V et de médiation du serveur de médiation sur votre serveur frontal, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur vos serveurs frontaux. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, reportez-vous [à la rubrique réception de la mise à l’échelle latérale (RSS) dans la documentation Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau.

## <a name="conferencing-maximums"></a>Nombre maximal de conférences

Dans la plupart des cas, il est possible que 5% des utilisateurs d’un groupe puissent participer à une conférence en une seule fois, une réserve d’utilisateurs 106 000 peut avoir environ 5 300 utilisateurs lors de conférences simultanément. Ces conférences sont supposées être composées d’un mélange de plusieurs médias (messagerie instantanée uniquement, messagerie instantanée avec audio, audio/vidéo, par exemple) et du nombre de participants. Il n’existe pas de limite inconditionnelle au nombre réel de conférences autorisées, et l’utilisation réelle détermine les performances réelles. Par exemple, si votre organisation possède de nombreuses conférences en mode mixte que celles supposées du modèle utilisateur, il est possible que vous deviez déployer des serveurs frontaux ou des serveurs de conférence A/V à partir des recommandations figurant dans cet article. Pour plus d’informations sur les hypothèses du modèle utilisateur, reportez-vous à la rubrique [modèles utilisateur dans Skype entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

Le nombre maximal de conférences prises en charge par une grappe frontale Skype entreprise Server standard, qui héberge également les utilisateurs, est de 250 participants. Pendant une conférence avec 250 utilisateurs, le pool continue de prendre en charge d’autres conférences, un total de 5 % d’utilisateurs du pool peuvent se trouver dans des conférences simultanées. Par exemple, dans le cas d’un pool de 16 serveurs frontaux et d’utilisateurs 106 000 pendant la Conférence 250-utilisateur, Skype entreprise Server prend en charge 5 050 autres utilisateurs participant à des conférences plus petites.

Quel que soit le nombre d’utilisateurs hébergés sur le pool frontal ou le serveur Standard Edition, Skype entreprise Server prend en charge au moins 125 d’autres utilisateurs participant à des conférences plus petites sur le même pool ou serveur hébergeant une conférence 250-utilisateurs.

Pour permettre aux conférences qui se trouvent entre les utilisateurs 250 et 1000, vous pouvez configurer un pool frontal distinct pour qu’il héberge ces conférences. Ce pool frontal ne héberge aucun utilisateur. Pour plus d’informations, reportez-vous à la rubrique [planification pour les réunions de grande envergure dans Skype entreprise Server](../../SfbServer/plan-your-deployment/conferencing/large-meetings.md).

Si votre organisation a beaucoup plus de conférences en mode mixte que celles supposées être utilisées dans le modèle utilisateur, il est possible que vous deviez déployer plus de serveurs frontaux que nous la recommandons dans ce document (jusqu’à 16 serveurs frontaux). Pour plus d’informations sur les hypothèses du modèle utilisateur, reportez-vous à la rubrique [modèles utilisateur dans Skype entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

## <a name="edge-server"></a>serveur Edge

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Vous devez déployer un serveur Edge pour tous les utilisateurs de 18 000 distants qui accèdent à un site en même temps. Au minimum, nous vous conseillons d’utiliser deux serveurs Edge pour une disponibilité élevée. Ces recommandations présupposent que le matériel de votre serveur Edge répond aux recommandations des [plateformes matérielles serveur](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Lorsque vous comptez le nombre d’utilisateurs pour les serveurs Edge, incluez les utilisateurs sur les appareils de succursales Survivables et les serveurs de succursales Survivables dans les succursales associées à un pool frontal sur ce site.

> [!NOTE]
> Pour améliorer les performances du service Edge de conférence A/V sur votre serveur Edge, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur les serveurs Edge. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, activez la case à cocher [réception de la mise à l’échelle latérale (RSS) dans Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731). Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau.

## <a name="director"></a>directeur

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Si vous déployez le rôle serveur Directeur, nous vous conseillons de déployer un directeur pour tous les utilisateurs de 18 000 distants qui accèdent à un site en même temps. Nous recommandons au minimum deux directeurs pour une disponibilité élevée. Ces recommandations présupposent que le matériel de votre serveur Edge répond aux recommandations des [plateformes matérielles serveur](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).

Lorsque vous comptez le nombre d’utilisateurs pour les directeurs, incluez les utilisateurs hébergés sur des appareils de succursales Survivables et des serveurs de succursales survivant dans les succursales associées à un pool frontal sur ce site.

## <a name="mediation-server"></a>serveur de médiation

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur.

Si vous collocate un serveur de médiation avec un serveur frontal, le serveur de médiation s’exécute sur chaque serveur frontal du pool et doit fournir une capacité suffisante aux utilisateurs de la liste.

Si vous déployez un pool de serveurs de médiation autonome, le nombre de serveurs de médiation à déployer dépend de nombreux facteurs, dont le matériel utilisé pour le serveur de médiation, le nombre d’utilisateurs VoIP, dont vous disposez, le nombre de pairs de passerelle les contrôles, le trafic horaire occupé par le biais de ces passerelles et le pourcentage d’appels avec des éléments multimédias qui contournent le serveur de médiation.

Les tableaux suivants décrivent le nombre d’appels simultanés qu’un serveur de médiation peut gérer, en partant du principe que le matériel requis pour les serveurs de médiation répond à la configuration requise pour les plateformes matérielles de [serveur](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) et que le Hyper-Threading est activé. Pour plus d’informations sur l’évolutivité du serveur de médiation, voir [estimation de l’utilisation de la voix et du trafic pour Skype entreprise Server](../../SfbServer/plan-your-deployment/capacity/estimating-voice-traffic.md) et [instructions de déploiement pour le serveur de médiation dans Skype entreprise Server](../../SfbServer/plan-your-deployment/capacity/mediation-server-deployment-guidelines.md).

Toutes les tables suivantes présupposent que l’utilisation est résumée dans les [modèles utilisateur de Skype entreprise Server](../../SfbServer/plan-your-deployment/capacity/user-models.md).

**Capacité du serveur de médiation autonome: 70% des utilisateurs internes et 30% des utilisateurs externes avec la capacité de non-contournement de l’appel (transcodage de média effectué par le serveur de médiation)**

|**Matériel serveur**|**Nombre maximal d’appels**|**Nombre maximal de lignes T1**|**Nombre maximal de lignes E1**|
|:-----|:-----|:-----|:-----|
|Processeur Intel Xeon E5-2673 de 3 processeurs, 6 cœurs, 2,4 gigahertz (GHz) ou une version ultérieure **avec Hyper-Threading désactivé**, avec 64 Go de mémoire et une carte réseau double-port.  <br/> |1500  <br/> |64  <br/> |49  <br/> |
|Processeur Intel Xeon E5-2673 3 processeur, 6 cœurs, 2,4 gigahertz (GHz) ou version ultérieure, avec mémoire 64 Go et une carte réseau double-port.  <br/> |2000  <br/> |88  <br/> |66  <br/> |

> [!NOTE]
> Bien que les serveurs dotés de 64 Go de mémoire aient été utilisés pour le test de performance, les serveurs possédant 32 Go de mémoire sont pris en charge pour le serveur de médiation autonome et permettent de fournir les performances indiquées dans le tableau ci-dessous.

**Capacité du serveur de médiation (serveur de médiation en fonction du serveur frontal) 70% des utilisateurs internes et de 30% des utilisateurs externes, sans ignorer la capacité d’appel (traitement multimédia effectué par le serveur de médiation)**

|**Matériel serveur**|**Nombre maximal d’appels**|
|:-----|:-----|
|Processeur Intel Xeon E5-2673 3 processeur, 6 cœurs, 2,4 gigahertz (GHz) ou une version ultérieure. avec 64 Go de mémoire et 2 Go de cartes réseau.  <br/> |200  <br/> |

> [!NOTE]
> Ce nombre est beaucoup plus petit que les numéros du serveur de médiation autonome. En effet, le serveur frontal doit gérer d’autres fonctions et fonctions pour les utilisateurs de 6600 sur le serveur, en plus du transcodage nécessaire pour les appels vocaux.

> [!NOTE]
> Pour améliorer les performances du serveur de médiation, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur les serveurs de médiation. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez la section «[mise à l’échelle côté destinataire dans Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)». Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau.

## <a name="back-end-server"></a>serveur principal

Bien que la plupart des informations de base de données soient stockées essentiellement sur les serveurs frontaux, vous devez vous assurer que vos serveurs dorsaux respectent les recommandations en matière de matériel [](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)indiquées plus haut dans cette section et sur les plateformes matérielles.

Pour garantir une haute disponibilité de votre serveur principal, nous vous recommandons de déployer le groupe de disponibilité AlwaysOn ou la mise en miroir du serveur. Pour plus d’informations, reportez-vous à la rubrique [Back End Server high availability in Skype for Business Server](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

## <a name="monitoring-and-archiving"></a>Surveillance et archivage

Si vous déployez la surveillance ou l’archivage, les fonctionnalités frontales de ces services s’exécutent sur les serveurs frontaux, la surveillance et l’archivage de chacun d’eux utilisent leur propre magasin de base de données, en dehors du magasin principal. Par ailleurs, si vous avez déployé Exchange 2013, vous pouvez stocker les données d’archivage des messages instantanés dans Exchange plutôt que dans un magasin SQL dédié.

Le tableau ci-dessous indique approximativement la quantité de stockage de base de données nécessaire par utilisateur par jour pour les données de surveillance et d’archivage.

||**CDR (surveillance)** <br/> |**QoE (surveillance)** <br/> |**Archivage** <br/> |
|:-----|:-----|:-----|:-----|
|Espace disque requis par utilisateur par jour  <br/> |49 Ko  <br/> |28 Ko  <br/> |57 Ko  <br/> |

Microsoft a utilisé le matériel décrit dans le tableau ci-dessous pour le serveur de base de données pour la surveillance et l’archivage lors des tests de performances. Le test collectait les données de deux pools front-end, chacun contenant des utilisateurs 80 000.

**Matériel utilisé pour le test des performances d’archivage et de la surveillance**

|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Processeur Intel Xeon E5-2673 v3 double processeur, 6 cœurs, 2,4 gigahertz (GHz) ou version ultérieure.  <br/> |
|Mémoire  <br/> |48 GO  <br/> |
|Disque  <br/> | SOIT :<br/> • 4 disques durs de 4 Mo ou plus 10000 avec au moins 72 Go d’espace libre sur le disque (les disques doivent être dans une configuration RAID 1 2x). <br/>OU <br/>• Lecteurs d’État SSD (SSDs) en mesure d’offrir un espace libre et des performances similaires pour les disques mécaniques 4 10000 RPM.   <br/> |
|Réseau  <br/> | 1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP).  <br/> |

**Configurations de disque recommandées**

|**Lecteur** <br/> |**Configuration RAID** <br/> |**Nombre de disques** <br/> |
|:-----|:-----|:-----|
|Fichiers de données des bases de données CDR, QoE et d’archivage sur un seul disque  <br/> |1+0  <br/> |Seiz  <br/> |
|Fichier journal de la base de données d’enregistrement des détails des appels  <br/> |1  <br/> |2  <br/> |
|Fichier journal de la base de données QoE  <br/> |1  <br/> |2  <br/> |
|Fichier journal de la base de données d’archivage  <br/> |1  <br/> |2  <br/> |

## <a name="video-interop-server-capacity"></a>Capacité du serveur Video Interop

Si vous déployez le serveur Video Interop et que vous avez besoin de connaître la capacité, vous observez le nombre maximal de systèmes de visioconférence vidéo (VTCs) qui seront dans les appels simultanés. Par exemple, si vous avez 250 systèmes de téléconférence vidéo dans votre organisation et que votre modèle utilisateur estime qu’au maximum 20 % de ceux-ci peuvent se trouver dans des appels simultanés, vous basez votre capacité sur 50 systèmes de téléconférence vidéo simultanés.

