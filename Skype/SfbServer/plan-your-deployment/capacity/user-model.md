---
title: Planification de capacité l’utilisation du modèle utilisateur pour Skype pour Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
description: Cet article fournit des instructions sur le nombre de serveurs vous avez besoin sur un site pour le nombre d’utilisateurs sur le site, en fonction de l’utilisation décrite dans modèles utilisateur Skype pour Business Server.
ms.openlocfilehash: c2f6059f909ee3a67f5df1fa0926be204690bf76
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21010299"
---
# <a name="capacity-planning-user-model-usage-for-skype-for-business-server"></a>Planification de capacité l’utilisation du modèle utilisateur pour Skype pour Business Server 
 
Cet article fournit des instructions sur le nombre de serveurs vous avez besoin sur un site pour le nombre d’utilisateurs sur le site, en fonction de l’utilisation décrite dans [modèles utilisateur Skype pour Business Server](user-models.md).
  
> [!NOTE]
> Toutes les recommandations de cet article supposent que vous avez installé la mise à jour cumulative de Skype Entreprise de novembre 2015 ou version ultérieure sur vos serveurs. 
  
## <a name="tested-hardware-platform"></a>Plateforme matérielle testée

Nous avons réalisé nos tests de performances sur le matériel décrit dans le tableau ci-dessous. L’ensemble de nos recommandations et résultats sont fondés sur ce matériel. Si vous décidez d’utiliser du matériel moins puissant que ce qui est répertorié ici, sachez que vous pourrez rencontrer des problèmes de fonctionnalité ou obtenir des performances médiocres. Ces recommandations matérielles sont les mêmes que Lync Server 2013, si c’est utile (et dans les scénarios de mise à niveau, il peut être).
  
**Matériel utilisé dans les tests de performances**

|**Composant matériel**|**Recommandation**|
|:-----|:-----|
|Processeur  <br/> |Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur.  <br/> Les processeurs Intel Itanium ne sont pas pris en charge pour Skype pour les rôles de serveur Business Server.  <br/> |
|Mémoire  <br/> |32 giga-octets (Go).  <br/> &bull;&nbsp;&nbsp;lecteurs de disque dur 8 ou plus de 10 000 RPM avec au moins 72 Go d’espace.  <br/> Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.  <br/> - OU -  <br/> &bull;&nbsp;&nbsp;SSD (Solid) qui fournit des performances similaires à 8 10 000 RPM disques durs mécaniques.  <br/> |
|Disque  <br/> ||
|Réseau  <br/> |&bull;&nbsp;&nbsp;1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association avec une adresse MAC unique et une adresse IP unique).  <br/> |
   
## <a name="summary-of-results"></a>Résumé des résultats

Le tableau ci-dessous résume nos recommandations.
  
|**Rôle serveur**|**Nombre maximal d’utilisateurs pris en charge**|
|:-----|:-----|
|Pool frontal avec douze serveurs frontaux et un serveur principal ou une paire en miroir des serveurs principaux.  <br/> |80 000 utilisateurs uniques connectés simultanément, plus 50 % de points de présence multiples (MPOP) représentant des instances non mobiles, plus 40 % d’utilisateurs activés pour la mobilité pour un total de 152 000 points de terminaison.  <br/> |
|Conférence A/V  <br/> |A / V Conferencing fourni par un pool frontal prend en charge les conférences du pool en supposant une taille maximale de la conférence de 250 utilisateurs et qu’une seule grande conférence en cours d’exécution à la fois.  <br/> **Remarque :** En outre, vous pouvez prendre en charge des grandes conférences d’entre 250 et 1 000 utilisateurs en déployant un pool frontal distinct avec deux serveurs frontaux pour héberger les conférences de grande taille. Pour plus d’informations, voir [planifier des réunions de grande taille dans Skype pour Business Server](../../plan-your-deployment/conferencing/large-meetings.md).  <br/> |
|Un serveur Edge  <br/> |12 000 utilisateurs distants simultanés.  <br/> |
|Un directeur  <br/> |12 000 utilisateurs distants simultanés.  <br/> |
|Surveillance et archivage  <br/> |Les services de frontal surveillance et archivage exécutés sur chaque serveur frontal, au lieu de rôles serveur séparés.  <br/> La surveillance et l’archivage requièrent un magasin de base de données chacun. Si vous exécutez également Exchange 2013 ou version ultérieure, vous pouvez conserver vos données d’archivage dans Exchange, plutôt que dans une base de données SQL dédié.  <br/> |
|Un serveur de médiation  <br/> |Serveur de médiation colocalisé avec le serveur frontal s’exécute sur chaque serveur frontal dans un pool et doit fournir suffisamment de capacité pour les utilisateurs dans le pool. Pour le serveur de médiation autonome, voir la section « Serveur de médiation » plus loin dans cette rubrique.  <br/> |
|Un serveur Standard Edition server  <br/> |Il est vivement recommandé que si vous utilisez des serveurs Standard Edition Server pour héberger des utilisateurs, vous utilisez toujours deux serveurs, couplés en utilisant les recommandations de [planification pour une haute disponibilité et récupération d’urgence](http://technet.microsoft.com/library/15a72073-0336-45dd-b2a0-35e7522c6000.aspx). Chaque serveur de la paire peut héberger jusqu'à 2 500 utilisateurs, et si le restant de la défaillance d’un serveur server peut prendre en charge 5 000 utilisateurs dans un scénario de basculement.  <br/>  Si votre déploiement présente un trafic audio ou vidéo important, les performances du serveur peuvent être affectées avec plus de 2 500 utilisateurs par serveur. Dans ce cas, vous devez envisager l’ajout de plusieurs serveurs Standard Edition Server ou le déplacement à Skype pour Business Server Enterprise Edition. <br/> |
   
## <a name="front-end-server"></a>serveur frontal

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur. 
  
Dans un pool frontal, vous devez disposer d’un que serveur frontal pour chaque 6 660 utilisateurs hébergé dans votre pool, en supposant que la technologie hyper-threading est activé sur tous les serveurs dans le pool et que le matériel du serveur répondent aux recommandations dans [Server requis pour Skype pour Entreprise 2015 Server](../requirements-for-your-environment/server-requirements.md) ou la [configuration système requise pour Skype pour Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Le nombre maximal d’utilisateurs dans un pool frontal redevient 80 000, en supposant que la technologie hyper-threading est activé sur tous les serveurs de votre pool. Si vous avez plus de 80 000 utilisateurs sur un site, vous pouvez déployer plusieurs pool frontal. 
  
Lorsque vous comptez le nombre d’utilisateurs dans un pool frontal, inclut tous les utilisateurs hébergés sur Survivable Branch Appliances et serveurs Survivable Branch Server dans les succursales qui sont associés à ce pool frontal.
  
Lorsqu’un serveur actif est indisponible, ses connexions sont transférées automatiquement vers les autres serveurs du pool. Dans un scénario où vous avez 30 000 utilisateurs et les cinq serveurs frontaux, si un serveur n’est pas disponible, les connexions de 6000 de vos utilisateurs doivent être transférés vers les autres serveurs restants quatre. Ces quatre serveurs restants contiendront chacun 7 500 utilisateurs, ce qui est un nombre supérieur à celui recommandé.
  
Si au lieu de cela vous a démarré avec six serveurs frontaux pour vos utilisateurs de 30 000 et 1 devient indisponible, un total de 5 000 utilisateurs devez déplacer vers les cinq serveurs restants. Ces cinq serveurs restants hébergent chacun 6 000 utilisateurs, ce qui est la plage recommandée.
  
Le nombre maximal d’utilisateurs dans un pool frontal est 80 000. Le nombre maximal de serveurs frontaux dans un pool est 12. 
  
Pour un pool frontal avec 80 000 utilisateurs, serveurs frontaux douze sera bonnes performances déploiements typiques qui suivent les [modèles utilisateur Skype pour Business Server](user-models.md). Conçu pour prendre en charge le basculement de récupération d’urgence de déploiements supposent qu’un maximum de 40 000 utilisateurs peut être hébergé dans chacun des deux pools frontaux couplés, dans lesquels chaque pool a suffisamment de serveurs frontaux pour contenir les utilisateurs dans les deux pools, un pool doit être basculé t o l’autre.
  
Le nombre d’utilisateurs pris en charge des performances correctes par un pool frontal particulier peut-être différer de ces numéros pour les raisons suivantes :
  
- Le matériel pour vos serveurs frontaux ne répond pas aux recommandations.
    
- Utilisation de votre organisation est très différente des modèles utilisateur, par exemple, si vous avez beaucoup de trafic de conférence.
    
Le tableau suivant montre la bande passante moyenne pour la messagerie instantanée et présence, selon le modèle utilisateur défini dans [modèles utilisateur Skype pour Business Server](user-models.md).
  
|**Bande passante moyenne par utilisateur**|**Bande passante requise par le serveur frontal avec 6 660 utilisateurs**|
|:-----|:-----|
|1,3 Kbits/s  <br/> |13 Mbits/s  <br/> |
   
> [!NOTE]
> Pour améliorer les performances multimédias de localisée au même emplacement A / V conférence et le serveur de médiation fonctionnalité sur vos serveurs frontaux, vous devez activer la côté réception montée en puissance (RSS) sur les cartes réseau sur vos serveurs frontaux. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, voir [Côté réception mise à l’échelle (RSS) dans la documentation de Windows Server 2012](https://go.microsoft.com/fwlink/p/?LinkId=620365). Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau. 
  
## <a name="conferencing-maximums"></a>Nombre maximal de conférences

Selon le modèle utilisateur, 5 % des utilisateurs d’un pool peuvent assister à une conférence en même temps, donc un pool de 80 000 utilisateurs peut comporter simultanément 4 000 utilisateurs en conférence. Ces conférences sont supposées être composées d’un mélange de plusieurs médias (messagerie instantanée uniquement, messagerie instantanée avec audio, audio/vidéo, par exemple) et du nombre de participants. Il n’existe pas de limite inconditionnelle au nombre réel de conférences autorisées, et l’utilisation réelle détermine les performances réelles. Par exemple, si votre organisation a un grand nombre de conférences en mode mixte plus que sont considérées comme dans le modèle utilisateur, vous devrez déployer plusieurs serveurs frontaux ou A / V Conferencing Servers que les recommandations présents dans cet article. Pour plus d’informations sur les hypothèses dans le modèle utilisateur, voir [modèles utilisateur Skype pour Business Server](user-models.md).
  
La taille maximale de prise en charge la conférence hébergée par un régulière Skype pour Business Server un pool frontal qui héberge des utilisateurs est de 250 participants. Pendant une conférence avec 250 utilisateurs, le pool continue de prendre en charge d’autres conférences, un total de 5 % d’utilisateurs du pool peuvent se trouver dans des conférences simultanées. Par exemple, dans un pool de serveurs frontaux douze et 80 000 utilisateurs, pendant la conférence 250 utilisateurs, Skype pour Business Server prend en charge 3,750 autres utilisateurs participant à des conférences plus petits.
  
Quel que soit le nombre d’utilisateurs hébergés sur le pool frontal ou serveur Standard Edition server, Skype pour Business Server prend en charge un minimum de 125 autres utilisateurs participant à des conférences plus petits sur le même pool ou serveur qui héberge une conférence de 250 utilisateurs. 
  
Pour activer les conférences qui ont entre 250 et 1 000 utilisateurs, vous pouvez configurer un pool frontal distinct pour héberger les conférences. Ce pool frontal ne sont pas héberger des utilisateurs. Pour plus d’informations, consultez [planification des grandes réunions dans Skype pour Business Server](../../plan-your-deployment/conferencing/large-meetings.md).
  
Si votre organisation a beaucoup plus de conférences en mode mixte que sont considérées comme dans le modèle utilisateur, vous devrez déployer plusieurs serveurs frontaux que nous recommandation dans ce document (jusqu'à une limite de 12 serveurs frontaux). Pour plus d’informations sur les hypothèses dans le modèle utilisateur, voir [modèles utilisateur Skype pour Business Server](user-models.md).
  
## <a name="edge-server"></a>Serveur Edge

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur. 
  
Vous devez déployer un serveur de périphérie pour 12 000 utilisateurs distants qui accèdent à un site simultanément. Au minimum, nous vous recommandons de deux serveurs de périphérie pour une haute disponibilité. Ces recommandations supposent que le matériel pour les serveurs de périphérie répondent aux recommandations dans [Plateformes matérielles de serveur](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).
  
Lorsque vous comptez le nombre d’utilisateurs pour les serveurs de périphérie, ajoutez les utilisateurs hébergés sur Survivable Branch Appliances et serveurs Survivable Branch Server dans les succursales qui sont associés à un pool frontal sur ce site.
  
> [!NOTE]
> Pour améliorer les performances des A / V serveur Edge de conférence de service sur les serveurs Edge, vous devez activer côté réception mise à l’échelle (RSS) sur les cartes réseau sur les serveurs de périphérie. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez «[Côté réception mise à l’échelle (RSS) dans Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)». Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau. 
  
## <a name="director"></a>directeur

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur. 
  
Si vous déployez le rôle serveur directeur, nous vous recommandons de déployer un directeur pour 12 000 utilisateurs distants qui accèdent à un site simultanément. Au minimum, nous vous recommandons de deux directeurs pour une haute disponibilité. Ces recommandations supposent que le matériel pour les serveurs de périphérie répondent aux recommandations dans [Plateformes matérielles de serveur](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).
  
Lorsque vous comptez le nombre d’utilisateurs pour les directeurs, ajoutez les utilisateurs hébergés sur Survivable Branch Appliances et serveurs Survivable Branch Server dans les succursales qui sont associés à un pool frontal sur ce site.
  
## <a name="mediation-server"></a>Serveur de médiation

> [!NOTE]
> Les pools étendus ne sont pas pris en charge pour ce rôle serveur. 
  
Si vous colocalisez le serveur de médiation avec le serveur frontal, serveur de médiation s’exécute sur chaque serveur frontal du pool et doit fournir suffisamment de capacité pour les utilisateurs dans le pool. 
  
Si vous déployez un pool de serveur de médiation autonome, puis le nombre de serveurs de médiation à déployer dépend de nombreux facteurs, notamment le matériel utilisé pour le serveur de médiation, le nombre d’utilisateurs VoIP, le nombre de passerelle homologues que chaque pool de serveur de médiation contrôles, le trafic des heures de pointe via ces passerelles et le pourcentage d’appels avec support contournant le serveur de médiation. 
  
Les tableaux suivants fournissent des instructions pour le nombre d’appels simultanés un serveur de médiation peuvent gérer, en supposant que le matériel pour les serveurs de médiation répond aux exigences de [Plateformes matérielles de serveur](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx) et que la technologie hyper-threading est activé. Pour plus d’informations sur l’évolutivité du serveur de médiation, voir [utilisation de voix d’estimer et le trafic Skype pour Business Server](estimating-voice-traffic.md) et [les instructions de déploiement pour le serveur de médiation dans Skype pour Business Server](mediation-server-deployment-guidelines.md).
  
Tous les tableaux suivants présupposent une utilisation résumées dans [modèles utilisateur Skype pour Business Server](user-models.md).
  
**Capacité du serveur de médiation autonome : 70 % d’utilisateurs internes, 30 % des utilisateurs externes disposant sans contournement (transcodage multimédia effectué par le serveur de médiation) capacité d’appels**

|**Matériel serveur**|**Nombre maximal d’appels**|**Nombre maximal de lignes T1**|**Nombre maximal de lignes E1**|
|:-----|:-----|:-----|:-----|
|Biprocesseur, six cœurs, processeur 2,26 GHz multithreads **avec technologie Hyper-Threading désactivée**, 32 Go de mémoire et une carte réseau double port.  <br/> |1100  <br/> |46  <br/> |35  <br/> |
|Biprocesseur, six cœurs, processeur 2,26 GHz multithreads avec 32 Go de mémoire et une carte réseau double port.  <br/> |1500  <br/> |63  <br/> |47  <br/> |
   
> [!NOTE]
> Bien que les serveurs avec 32 Go de mémoire ont été utilisés pour les tests de performances, les serveurs de 16 Go de mémoire sont pris en charge pour le serveur de médiation autonome et sont suffisantes pour fournir les performances indiquées dans ce tableau. 
  
**Capacité de serveur de médiation (serveur de médiation colocalisé avec le serveur frontal) 70 % d’utilisateurs internes, 30 % des utilisateurs externes, la capacité d’appel sans contournement (traitement multimédia effectué par le serveur de médiation)**

|**Matériel serveur**|**Nombre maximal d’appels**|
|:-----|:-----|
|Biprocesseur, six cœurs, processeur 2,26 GHz multithreads avec 32 Go de mémoire et 2 cartes réseau de 1 Go.  <br/> |150  <br/> |
   
> [!NOTE]
> Ce nombre est beaucoup plus petit que les numéros pour le serveur de médiation autonome. C’est parce que le serveur frontal a gérer les autres fonctionnalités et fonctions pour les 6600 utilisateurs hébergement, outre le transcodage nécessaire pour les appels vocaux. 
  
> [!NOTE]
> Pour améliorer les performances du serveur de médiation, vous devez activer côté réception mise à l’échelle (RSS) sur les cartes réseau sur vos serveurs de médiation. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, voir «[Receive-Side Scaling dans Windows Server 2012](https://go.microsoft.com/fwlink/p/?linkId=268731)». Pour plus d’informations sur l’activation de RSS, vous devrez vous reporter à la documentation de votre carte réseau. 
  
## <a name="back-end-server"></a>serveur principal

Bien que la plupart des informations de base de données est stockée principalement sur les serveurs frontaux, vous devez vous assurer que vos serveurs principaux répondent aux recommandations matérielles répertoriées plus haut dans cette section et [Plateformes matérielles de serveur](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).
  
Pour fournir une haute disponibilité de votre serveur principal, nous vous recommandons de déployer des groupes de disponibilité AlwaysOn ou la mise en miroir du serveur. Pour plus d’informations, voir [serveur principal de haute disponibilité dans Skype pour Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  
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
|Processeur  <br/> |Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur  <br/> |
|Mémoire  <br/> |48 Go  <br/> |
|Disque  <br/> |25 10 000 RPM disques durs de 300 Go sur chaque disque, avec la configuration dans le tableau suivant  <br/> |
|Réseau  <br/> | 1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP)  <br/> |
   
**Configurations de disque recommandées**

|**Lecteur** <br/> |**Configuration RAID** <br/> |**Nombre de disques** <br/> |
|:-----|:-----|:-----|
|Fichiers de données des bases de données CDR, QoE et d’archivage sur un seul disque  <br/> |1+0  <br/> |16  <br/> |
|Fichier journal de la base de données d’enregistrement des détails des appels  <br/> |1  <br/> |2  <br/> |
|Fichier journal de la base de données QoE  <br/> |1  <br/> |2  <br/> |
|Fichier journal de la base de données d’archivage  <br/> |1  <br/> |2  <br/> |
   
## <a name="video-interop-server-capacity"></a>Capacité d’un serveur de l’interopérabilité vidéo

Si vous déployez le serveur d’interopérabilité vidéo et vous devez déterminer la capacité, examinez le nombre maximal de systèmes de téléconférence vidéo (VTCs) qui seront inclus dans les appels simultanés. Par exemple, si vous avez 250 systèmes de téléconférence vidéo dans votre organisation et que votre modèle utilisateur estime qu’au maximum 20 % de ceux-ci peuvent se trouver dans des appels simultanés, vous basez votre capacité sur 50 systèmes de téléconférence vidéo simultanés.
  

