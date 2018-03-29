---
title: Utilisation du modèle utilisateur de planification de capacité dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: Cet article fournit des conseils sur le nombre de serveurs nécessaires à un site pour le nombre d’utilisateurs sur ce site, en fonction de l’utilisation décrite dans les modèles de l’utilisateur dans Skype pour Business Server 2015.
ms.openlocfilehash: b8395e1fdec1a9d4ed100a911fccd6177b03c665
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server-2015"></a>Utilisation du modèle utilisateur de planification de capacité dans Skype Entreprise Server 2015
 
Cet article fournit des conseils sur le nombre de serveurs nécessaires à un site pour le nombre d’utilisateurs sur ce site, en fonction de l’utilisation décrite dans les [modèles de l’utilisateur dans Skype pour Business Server 2015](user-models.md).
  
> [!NOTE]
> Toutes les recommandations de cet article supposent que vous avez installé la mise à jour cumulative de Skype Entreprise de novembre 2015 ou version ultérieure sur vos serveurs. 
  
## <a name="tested-hardware-platform"></a>Plateforme matérielle testée

Nous avons réalisé nos tests de performances sur le matériel décrit dans le tableau ci-dessous. L’ensemble de nos recommandations et résultats sont fondés sur ce matériel. Si vous décidez d’utiliser du matériel moins puissant que ce qui est répertorié ici, sachez que vous pourrez rencontrer des problèmes de fonctionnalité ou obtenir des performances médiocres. Ces recommandations sont les mêmes que Lync Server 2013, si utile (et dans les scénarios de mise à niveau, il peut être).
  
**Matériel utilisé dans les tests de performances**

|**Composant matériel**|**Recommandé**|
|:-----|:-----|
|Processeur  <br/> |Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype pour les rôles de serveur de serveur d’entreprise.  <br/> |
|Mémoire  <br/> |32 giga-octets (Go).  <br/> &bull;&nbsp;&nbsp;lecteurs de disque dur 8 ou plus de 10 000 TPM au moins 72 Go d’espace libre de l’espace disque.  <br/> Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.  <br/> - OU -  <br/> &bull;&nbsp;&nbsp;Disques SSD (SSD) qui offrent des performances similaires à 8-10 000 RPM des lecteurs de disque mécaniques.  <br/> |
|Disque  <br/> ||
|Réseau  <br/> |&bull;&nbsp;&nbsp;1 carte réseau de deux ports, 1 Gbit/s ou supérieur (2 recommandé, qui passe par une collaboration avec une seule adresse MAC et l’adresse IP unique).  <br/> |
   
## <a name="summary-of-results"></a>Résumé des résultats

Le tableau ci-dessous résume nos recommandations.
  
|**Rôle de serveur**|**Nombre maximal d’utilisateurs pris en charge**|
|:-----|:-----|
|Pool de fin avant avec un serveur principal ou une paire en miroir, de sauvegarder les serveurs principaux et douze serveurs frontaux.  <br/> |80 000 utilisateurs uniques connectés simultanément, plus 50 % de points de présence multiples (MPOP) représentant des instances non mobiles, plus 40 % d’utilisateurs activés pour la mobilité pour un total de 152 000 points de terminaison.  <br/> |
|Conférence A/V  <br/> |A / V Conferencing service fourni par un pool frontal prend en charge les conférences du pool en supposant une taille maximale de la conférence de 250 utilisateurs et qu’une telle conférence importante en cours d’exécution à la fois.  <br/> **Remarque :** En outre, vous pouvez prendre en charge les conférences volumineux d’entre 250 et 1000 utilisateurs en déployant un pool frontal distinct avec deux serveurs frontaux pour héberger les conférences de grande taille. Pour plus d’informations, consultez [planification de réunions de grande taille dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Un côté serveur  <br/> |12 000 utilisateurs distants simultanés.  <br/> |
|Un directeur  <br/> |12 000 utilisateurs distants simultanés.  <br/> |
|Surveillance et archivage  <br/> |Les services de front-end de suivi et d’archivage se sur chaque serveur principal avant, au lieu de rôles serveur distincts.  <br/> La surveillance et l’archivage requièrent un magasin de base de données chacun. Si vous exécutez également Exchange 2013 ou ultérieurement, vous pouvez conserver vos données d’archivage dans Exchange, plutôt que dans une base de données SQL dédiée.  <br/> |
|Un serveur de médiation  <br/> |Serveur de médiation colocalisé avec s’exécute le serveur frontal sur chaque serveur frontal dans un pool et doit fournir une capacité suffisante pour les utilisateurs dans le pool. Pour le serveur de médiation autonome, consultez la section « Serveur de médiation » plus loin dans cette rubrique.  <br/> |
|Un serveur Standard Edition server  <br/> |Nous recommandons vivement que si vous utilisez des serveurs Standard Edition Server pour héberger des utilisateurs, vous utilisez toujours deux serveurs associés en utilisant les recommandations de [planification pour la haute disponibilité et reprise après sinistre](http://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Chaque serveur de la paire peut héberger jusqu'à 2 500 utilisateurs, et si un serveur échoue les autres serveur peut prendre en charge 5 000 utilisateurs dans un scénario de basculement sur incident.  <br/>  Si votre déploiement présente un trafic audio ou vidéo important, les performances du serveur peuvent être affectées avec plus de 2 500 utilisateurs par serveur. Dans ce cas, vous devez envisager d’ajouter plusieurs serveurs Standard Edition Server ou le déplacement à Skype pour Business Server Édition entreprise. <br/> |
   
## <a name="front-end-server"></a>serveur frontal

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur. 
  
Dans un pool frontal, vous devez disposer d’un que serveur frontal pour tous les 6,660 utilisateurs hébergé dans le pool, en supposant que la technologie hyper-threading est activé sur tous les serveurs dans la liste et que le matériel du serveur répondent aux recommandations de [Plateformes matérielles de serveur](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx). Le nombre maximal d’utilisateurs dans un seul pool de Front-End est de nouveau 80 000, en supposant que la technologie hyper-threading est activé sur tous les serveurs dans le pool. Si vous avez plus de 80 000 utilisateurs sur un site, vous pouvez déployer plusieurs pools de Front-End. 
  
Lorsque vous en tenir compte pour le nombre d’utilisateurs dans un pool frontal, incluent tous les utilisateurs hébergés sur Survivable Branch Appliances et Survivable Branch serveurs de succursales qui sont associés à ce pool de Front-End.
  
Lorsqu’un serveur actif est indisponible, ses connexions sont transférées automatiquement vers les autres serveurs du pool. Dans un scénario où vous disposez de 30 000 utilisateurs et cinq serveurs frontaux, si un serveur est indisponible, les connexions de 6000 de vos utilisateurs doivent être transférés vers les quatre autres serveurs restants. Ces quatre serveurs restants contiendront chacun 7 500 utilisateurs, ce qui est un nombre supérieur à celui recommandé.
  
Si en revanche vous l’aviez lancée avec six serveurs frontaux pour votre compte 30 000 utilisateurs et un devient indisponible, un total de 5 000 utilisateurs devez déplacer vers les autres serveurs de cinq. Ces cinq serveurs restants hébergent chacun 6 000 utilisateurs, ce qui est la plage recommandée.
  
Le nombre maximal d’utilisateurs dans un pool frontal est de 80 000. Le nombre maximal de serveurs frontaux dans un pool est 12. 
  
Pour un pool frontal de 80 000 utilisateurs, douze serveurs frontaux seront bénéfiques pour les performances, dans les déploiements typiques qui suivent les [modèles utilisateur dans Skype pour Business Server 2015](user-models.md). Conçu pour prendre en charge le basculement de récupération après sinistre de déploiements supposent qu’un maximum de 40 000 utilisateurs peut être hébergé dans chacune des deux paires pools Front-End, dans lesquels chaque pool a suffisamment serveurs frontaux pour contenir les utilisateurs dans les deux pools, un pool doit être basculé de t o l’autre.
  
Le nombre d’utilisateurs pris en charge avec de bonnes performances à un pool frontal particulier peut-être différer de ces nombres pour les raisons suivantes :
  
- Le matériel de vos serveurs frontaux ne répond pas aux recommandations de [Plateformes matérielles de serveur](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).
    
- L’utilisation de votre organisation est très différente des modèles utilisateur, par exemple, si vous avez beaucoup plus le trafic de téléconférence.
    
Le tableau suivant montre la bande passante moyenne pour la messagerie instantanée et de présence, étant donné le modèle utilisateur, telle que définie dans les [modèles de l’utilisateur dans Skype pour Business Server 2015](user-models.md).
  
|**Bande passante moyenne par utilisateur**|**Bande passante par le serveur frontal avec 6,660 utilisateurs**|
|:-----|:-----|
|1,3 Kbits/s  <br/> |13 Mbits/s  <br/> |
   
> [!NOTE]
> Pour améliorer les performances de media de la situés A / V Conferencing et serveur de médiation des fonctionnalités sur vos serveurs frontaux, vous devez activer côté réception mise à l’échelle de (flux RSS) sur les cartes réseau sur vos serveurs frontaux. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez [Côté réception mise à l’échelle (RSS) dans la documentation de Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau. 
  
## <a name="conferencing-maximums"></a>Nombre maximal de conférences

Selon le modèle utilisateur, 5 % des utilisateurs d’un pool peuvent assister à une conférence en même temps, donc un pool de 80 000 utilisateurs peut comporter simultanément 4 000 utilisateurs en conférence. Ces conférences sont supposées être composées d’un mélange de plusieurs médias (messagerie instantanée uniquement, messagerie instantanée avec audio, audio/vidéo, par exemple) et du nombre de participants. Il n’existe pas de limite inconditionnelle au nombre réel de conférences autorisées, et l’utilisation réelle détermine les performances réelles. Par exemple, si votre organisation possède un grand nombre de conférences en mode mixte plus que sont considérés comme étant dans le modèle utilisateur, vous devrez déployer plusieurs serveurs frontaux ou A / V des serveurs de conférence que les recommandations trouvé dans cet article. Pour plus d’informations sur les hypothèses du modèle utilisateur, voir [modèles d’utilisateurs de Skype pour Business Server 2015](user-models.md).
  
La taille maximale prise en charge de la conférence hébergée par un Skype régulière pour le pool d’entreprise serveur frontal qui héberge également les utilisateurs est 250 participants. Pendant une conférence avec 250 utilisateurs, le pool continue de prendre en charge d’autres conférences, un total de 5 % d’utilisateurs du pool peuvent se trouver dans des conférences simultanées. Par exemple, dans un pool de serveurs frontaux douze et de 80 000 utilisateurs, pendant la conférence de 250 utilisateurs, Skype pour Business Server prend en charge 3,750 autres utilisateurs participent aux conférences de plus petits.
  
Quel que soit le nombre d’utilisateurs hébergés par le pool frontal ou le serveur Standard Edition server, Skype pour Business Server prend en charge un minimum de 125 autres utilisateurs participent aux conférences plus petits sur le pool ou le serveur qui héberge une conférence 250-utilisateur même. 
  
Pour activer les conférences comptant entre 250 et 1000 utilisateurs, vous pouvez configurer un pool frontal distinct pour héberger les conférences. Ce pool frontal n’héberge tous les utilisateurs. Pour plus d’informations, consultez [planification de réunions de grande taille dans Skype pour Business Server 2015](../../plan-your-deployment/conferencing/large-meetings.md).
  
Si votre organisation a beaucoup plus de conférences en mode mixte que sont considérés comme étant dans le modèle utilisateur, vous devrez déployer plusieurs serveurs frontaux que nous recommandation dans ce document (dans la limite de 12 serveurs frontaux). Pour plus d’informations sur les hypothèses du modèle utilisateur, voir [modèles d’utilisateurs de Skype pour Business Server 2015](user-models.md).
  
## <a name="edge-server"></a>Serveur Edge

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur. 
  
Vous devez déployer un serveur de transport Edge pour 12 000 utilisateurs distants qui accèdent simultanément à un site. Au minimum, nous vous recommandons de deux serveurs de périphérie pour une haute disponibilité. Ces recommandations supposent que le matériel de vos serveurs Edge répondent aux recommandations de [Plateformes matérielles de serveur](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).
  
Lorsque vous en tenir compte pour le nombre d’utilisateurs pour les serveurs Edge, incluent les utilisateurs hébergés sur Survivable Branch Appliances et Survivable Branch serveurs de succursales qui sont associées à un pool frontal sur ce site.
  
> [!NOTE]
> Pour améliorer les performances de l’A / V Conferencing Edge de service sur les serveurs Edge, vous devez activer le côté réception mise à l’échelle (RSS) sur les cartes réseau sur vos serveurs Edge. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez «[Améliorations de mise à l’échelle côté réception dans Windows Server 20081](https://go.microsoft.com/fwlink/p/?linkId=268731)». Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau. 
  
## <a name="director"></a>directeur

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur. 
  
Si vous déployez le rôle de serveur directeur, nous vous recommandons de déployer un directeur pour 12 000 utilisateurs distants qui accèdent simultanément à un site. Au minimum, nous vous recommandons de deux directeurs pour une haute disponibilité. Ces recommandations supposent que le matériel de vos serveurs Edge répondent aux recommandations de [Plateformes matérielles de serveur](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).
  
Lorsque vous en tenir compte pour le nombre d’utilisateurs pour les administrateurs, les utilisateurs hébergés sur Survivable Branch Appliances et Survivable Branch serveurs de succursales qui sont associées à un pool frontal sur ce site.
  
## <a name="mediation-server"></a>Serveur de médiation

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur. 
  
Si vous colocaliser serveur de médiation avec le serveur frontal, serveur de médiation s’exécute sur chaque serveur frontal dans le pool et doit fournir une capacité suffisante pour les utilisateurs dans le pool. 
  
Si vous déployez un pool de serveur de médiation autonome, puis le nombre de serveurs de médiation pour déployer dépend de nombreux facteurs, notamment le matériel utilisé pour le serveur de médiation, le nombre d’utilisateurs VoIP, le numéro de passerelle homologues que chaque pool de serveur de médiation contrôles, le trafic d’heure occupé par le biais de ces passerelles et le pourcentage des appels avec des médias qui contourne le serveur de médiation. 
  
Les tableaux suivants fournissent une indication pour le nombre d’appels simultanés un serveur de médiation peuvent traiter, en supposant que le matériel pour les serveurs de médiation répond aux exigences de [Plateformes matérielles de serveur](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) et que la technologie hyper-threading est activée. Pour plus d’informations sur l’évolutivité du serveur de médiation, consultez [utilisation de voix d’estimer le trafic Skype pour Business Server 2015](estimating-voice-traffic.md) et [instructions de déploiement pour le serveur de médiation dans Skype pour Business Server 2015](mediation-server-deployment-guidelines.md).
  
Toutes les tables suivantes supposent l’utilisation comme indiqué dans [modèles de l’utilisateur dans Skype pour Business Server 2015](user-models.md).
  
**Capacité de serveur de médiation autonome : 70 % des utilisateurs internes, 30 % des utilisateurs externes avec non contournement de capacité d’appel (effectuée par le serveur de médiation de transcodage média)**

|**Matériel du serveur**|**Nombre maximal d’appels**|**Nombre maximal de lignes T1**|**Nombre maximal de lignes de E1**|
|:-----|:-----|:-----|:-----|
|Biprocesseur, six cœurs, processeur 2,26 GHz multithreads **avec technologie Hyper-Threading désactivée**, 32 Go de mémoire et une carte réseau double port.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Biprocesseur, six cœurs, processeur 2,26 GHz multithreads avec 32 Go de mémoire et une carte réseau double port.  <br/> |1500  <br/> |63  <br/> |47  <br/> |
   
> [!NOTE]
> Bien que les serveurs disposant de 32 Go de mémoire ont été utilisés pour les tests de performances, serveurs avec 16 Go de mémoire sont pris en charge pour le serveur de médiation autonome et sont suffisantes pour fournir les performances indiquées dans ce tableau. 
  
**Capacité de serveur de médiation (le serveur de médiation colocalisé avec serveur frontal) utilisateurs internes de 70 %, 30 % des utilisateurs externes, capacité de dérivation Non appel (traitement multimédia exécutée par le serveur de médiation)**

|**Matériel du serveur**|**Nombre maximal d’appels**|
|:-----|:-----|
|Biprocesseur, six cœurs, processeur 2,26 GHz multithreads avec 32 Go de mémoire et 2 cartes réseau de 1 Go.  <br/> |150  <br/> |
   
> [!NOTE]
> Ce nombre est beaucoup plus petit que les nombres pour le serveur de médiation autonome. C’est parce que le serveur frontal a gérer d’autres fonctionnalités et fonctions pour les 6600 utilisateurs est associé, en plus du transcodage requis pour les appels vocaux. 
  
> [!NOTE]
> Pour améliorer les performances du serveur de médiation, vous devez activer le côté réception mise à l’échelle (RSS) sur les cartes réseau sur vos serveurs de médiation. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, reportez-vous à la section «[Améliorations de mise à l’échelle côté réception dans Windows Server 2008](https://go.microsoft.com/fwlink/p/?linkId=268731)». Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau. 
  
## <a name="back-end-server"></a>serveur principal

Bien que la plupart des informations de base de données est stockée principalement sur les serveurs frontaux, il se peut que vous devez vous assurer que vos serveurs principaux en respecter les recommandations matérielles répertoriées plus haut dans cette section et dans les [Plates-formes de serveur](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).
  
Pour fournir une haute disponibilité de votre serveur principal, nous vous recommandons de déployer des groupes de disponibilité AlwaysOn ou la mise en miroir de serveur. Pour plus d’informations, reportez-vous à la section [haute disponibilité de serveur principal dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  
## <a name="monitoring-and-archiving"></a>Surveillance et archivage

Si vous déployez la surveillance ou l’archivage, les fonctionnalités front-end de ces services s’exécute sur les serveurs avant, la surveillance et l’archivage de leur propre magasin de base de données, séparé à partir du magasin de Back-End utilisent. Ou bien, si vous avez Exchange 2013 est déployé, vous pouvez stocker données d’archivage des messages instantanés dans Exchange au lieu de dans un magasin SQL dédié.
  
Le tableau ci-dessous indique approximativement la quantité de stockage de base de données nécessaire par utilisateur par jour pour les données de surveillance et d’archivage.
  
|||||
|:-----|:-----|:-----|:-----|
||**CDR (surveillance)** <br/> |**QoE (surveillance)** <br/> |**Archivage** <br/> |
|Espace disque requis par utilisateur par jour  <br/> |49 Ko  <br/> |28 Ko  <br/> |57 Ko  <br/> |
   
Microsoft a utilisé le matériel décrit dans le tableau ci-dessous pour le serveur de base de données pour la surveillance et l’archivage lors des tests de performances. Les tests de collecte les données des deux pools de Front-End, dont chacun contenue 80 000 utilisateurs.
  
**Matériel utilisé dans la surveillance et l’archivage des tests de performances**

|**Composant matériel**|**Recommandé**|
|:-----|:-----|
|Processeur  <br/> |Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur  <br/> |
|Mémoire  <br/> |48 Go  <br/> |
|Disque  <br/> |25-10 000 RPM disques durs de 300 Go sur chaque disque, avec la configuration dans le tableau suivant  <br/> |
|Réseau  <br/> | 1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)  <br/> |
   
**Configurations de disque recommandées**

||||
|:-----|:-----|:-----|
|**Lecteur** <br/> |**Configuration RAID** <br/> |**Nombre de disques** <br/> |
|Fichiers de données des bases de données CDR, QoE et d’archivage sur un seul disque  <br/> |1+0  <br/> |16  <br/> |
|Fichier journal de la base de données d’enregistrement des détails des appels  <br/> |1  <br/> |2  <br/> |
|Fichier journal de la base de données QoE  <br/> |1  <br/> |2  <br/> |
|Fichier journal de la base de données d’archivage  <br/> |1  <br/> |2  <br/> |
   
## <a name="video-interop-server-capacity"></a>Capacité d’interopérabilité serveur vidéo

Si vous déployez vidéo Interop serveur et vous devez déterminer la capacité, vous observez le nombre maximal de systèmes de téléconférence vidéo (VTCs) dans des appels simultanés. Par exemple, si vous avez 250 systèmes de téléconférence vidéo dans votre organisation et que votre modèle utilisateur estime qu’au maximum 20 % de ceux-ci peuvent se trouver dans des appels simultanés, vous basez votre capacité sur 50 systèmes de téléconférence vidéo simultanés.
  

