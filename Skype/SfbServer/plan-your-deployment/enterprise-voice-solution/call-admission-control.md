---
title: Planifier le contrôle d’admission des appels d’appel dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
description: Découvrez le contrôle d’admission des appels, qui peut empêcher des appels à partir du lieu si elles auront la qualité des médias médiocre, dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: f02952c45badf26fa2e02a9d3d8349d087bbe6e8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897712"
---
# <a name="plan-for-call-admission-control-in-skype-for-business-server"></a>Planifier le contrôle d’admission des appels d’appel dans Skype pour Business Server

Découvrez le contrôle d’admission des appels, qui peut empêcher des appels à partir du lieu si elles auront la qualité des médias médiocre, dans Skype pour Business Server Enterprise Voice.

Pour les applications basées sur IP, comme la téléphonie, la vidéo et le partage d’application, la bande passante disponible des réseaux d’entreprise n’est généralement pas perçue comme un facteur limitatif dans les environnements de réseau local. En revanche, la bande passante réseau peut être limitée sur des liaisons de réseau étendu qui assurent l’interconnexion des sites.

Lorsque le trafic réseau afflue et sature une liaison de réseau étendu, les mécanismes courants, comme la mise en attente, la mise en mémoire tampon et l’abandon de paquets, sont utilisés pour résoudre le problème de congestion. Le trafic supplémentaire est généralement retardé jusqu’à ce que le réseau ne soit plus saturé. Si nécessaire, le trafic peut également être interrompu. Avec un trafic de données conventionnel, le client qui reçoit les données peut facilement surmonter ce type de problème. Avec un trafic en temps réel, la saturation du réseau ne peut pas être résolue de cette manière, car les communications unifiées sont sensibles à la latence et à la perte de paquets. Si le réseau étendu est saturé, la qualité de l’expérience (QoE) des utilisateurs peut s’en ressentir. Lorsque le trafic en temps réel est saturé, il vaut mieux refuser des appels plutôt que de fournir des connexions de mauvaise qualité.

Le contrôle d’admission des appels (CAC) détermine si la bande passante réseau est suffisante pour établir une session en temps réel de qualité acceptable. Dans Skype pour Business Server, CAC contrôle le trafic en temps réel uniquement pour l’audio et vidéo, mais elle n’affecte pas le trafic de données. Si la bande passante n’est pas suffisante sur le chemin du réseau étendu par défaut, le contrôle d’admission des appels peut essayer d’acheminer l’appel via un chemin Internet ou sur le réseau téléphonique commuté (RTC).

Cette section décrit le contrôle d’admission des appels et explique comment le planifier.

> [!NOTE]
> Skype pour Business Server comporte trois fonctionnalités voix entreprise : appeler le contrôle d’admission des appels (CAC), les services d’urgence (E9-1-1) et le contournement de média. Pour une vue d’ensemble de la planification des informations qui sont communes aux trois de ces fonctionnalités, voir [paramètres réseau pour les fonctionnalités Enterprise Voice dans Skype pour Business Server](network-settings-for-advanced-features.md).

La conception CAC dans Skype pour Business Server offre quatre principaux attributs :

- Le contrôle d’admission des appels est simple à déployer et à gérer sans recours à un équipement supplémentaire, tel que des routeurs configurés spécialement.

- Il traite les scénarios d’utilisation des communications unifiées critiques, tels que les utilisateurs itinérants et les points de présence multiples. Les stratégies du contrôle d’admission des appels sont appliquées selon l’emplacement du point de terminaison et non pas de l’emplacement où est hébergé l’utilisateur.

- Outre les appels vocaux, ce contrôle peut être appliqué à d’autres trafics, tels que les appels vidéo et les sessions de conférence audio/vidéo.

- Il fournit suffisamment de flexibilité pour permettre la représentation de différents types de topologies réseau.

Si ou nouvelle session audio ou vidéo dépasse les limites de bande passante définies sur une liaison de réseau étendu, la session est bloquée ou (pour les appels téléphoniques uniquement) réacheminée sur RTC.

Le contrôle d’admission des appels contrôle le trafic en temps réel pour la voix et la vidéo uniquement. Il ne contrôle pas le trafic de données.

Administrateurs de définissent des stratégies CAC, qui sont appliquées par le Service de stratégie de bande passante qui est installé avec chaque pool frontal. Paramètres CAC sont propagées automatiquement à tous les Skype pour les serveurs frontaux Business Server dans votre réseau.

Pour les appels qui échouent en raison des stratégies de contrôle d’admission des appels, l’ordre de priorité de réacheminement des appels est le suivant :

1. Internet

2. PSTN

3. Messagerie vocale

L’enregistrement des détails des appels capture les informations concernant les appels réacheminés vers RTC ou la messagerie vocale. L’enregistrement des détails des appels ne capture pas les informations des appels non réacheminés sur Internet, car Internet est traité comme un autre chemin d’accès plutôt qu’une autre option.

> [!NOTE]
> Les dépôts de messages vocaux ne seront pas refusés en raison des contraintes de bande passante.

Le service de stratégie de bande passante génère deux types de fichiers journaux au format CSV (valeurs séparées par des virgules). Le fichier journal du **nombre d’échecs de vérification** capture les informations lorsque les demandes de bande passante sont refusées. Le fichier journal d’**utilisation des liaisons** capture un instantané de la topologie réseau et de l’utilisation de la bande passante de la liaison de réseau étendu. Ces deux fichiers journaux peuvent vous aider à affiner vos stratégies de contrôle d’admission des appels en fonction de l’utilisation.

## <a name="call-admission-control-considerations"></a>Considérations relatives au contrôle d’admission des appels

L’administrateur choisit d’installer le service de stratégie de bande passante sur le premier pool configuré dans le site central. Puisqu’il existe un seul site central par région réseau, il existe un seul service de stratégie de bande passante par région réseau, lequel gère la stratégie de bande passante pour cette région, ses sites associés et les liens vers ces sites. Le Service de stratégie de bande passante s’exécute dans le cadre des serveurs frontaux, et par conséquent, une haute disponibilité est intégrée dans ce pool. Le Service de stratégie de bande passante en cours d’exécution sur chaque serveur frontal synchronise toutes les 15 secondes. Si le pool frontal échoue, stratégies CAC ne s’appliquent plus de ce site jusqu'à ce que le pool frontal et, par conséquent, le Service de stratégie de bande passante redevient opérationnel. Cela signifie que tous les appels sont transmis pendant la durée d’interruption du service de stratégie de bande passante. Par conséquent, il existe un risque de surabonnement de bande passante pour vos liens durant cette période.

Le Service de stratégie de bande passante fournit une haute disponibilité au sein d’un pool frontal ; Toutefois, il ne fournit pas la redondance entre les pools frontaux. Le Service de stratégie de bande passante ne peut pas basculer d’un pool frontal à un autre. Une fois que le service pour le pool frontal est restaurée, le Service de stratégie de bande passante est repris et peut appliquer les vérifications de stratégie de bande passante à nouveau.

### <a name="network-considerations"></a>Considérations relatives au réseau

Bien que la restriction de bande passante pour l’audio et vidéo est appliquée par le Service de stratégie de bande passante dans Skype pour Business Server, cette restriction n’est pas appliquée au niveau du routeur de réseau (couche 2 et 3). Le contrôle d’admission des appels ne peut pas, par exemple, empêcher une application de données de consommer l’intégralité de la bande passante du réseau sur une liaison de réseau étendu, dont la bande passante réservée pour l’audio et la vidéo par votre stratégie de contrôle d’admission des appels. Pour protéger la bande passante nécessaire sur votre réseau, vous pouvez déployer un protocole de qualité de service (QoS) tel que les services différenciés (DiffServ). Par conséquent, la meilleure pratique consiste à coordonner les stratégies de bande passante du contrôle d’admission des données que vous définissez avec les paramètres QoS que vous pouvez déployer.

### <a name="media-and-signaling-paths-over-vpn"></a>Chemins d’accès des médias et de la signalisation sur réseau privé virtuel (VPN)

Si votre entreprise prend en charge les médias via VPN, assurez-vous que les flux multimédia et de signalisation passent tous deux via le VPN ou qu’ils sont routés par le biais d’Internet. Par défaut, les flux multimédia et de signalisation passent par le tunnel VPN.

### <a name="call-admission-control-of-outside-users"></a>Contrôle d’admission des appels des utilisateurs extérieurs

Appeler le contrôle n’est pas appliqué au-delà des limites de la Skype pour organisation Business Server d’admission des appels. CAC pour le trafic multimédia transitant par Internet, qui n’est pas géré par Skype pour Business Server ne peut pas être appliquée. Vérifications CAC seront effectuées sur la partie de l’appel qui circule dans le réseau d’entreprise si le point de terminaison appelé appartient à l’organisation et le serveur Edge a été ajouté à la configuration réseau, comme décrit dans le contrôle d’admission des appels [ déploiement : liste de vérification finale pour Skype pour Business Server](../../deploy/deploy-enterprise-voice/final-checklist.md). Si le point de terminaison appelé n’appartient pas à l’organisation, comme dans le cas d’un utilisateur fédéré ou PIC, aucune vérification de stratégie de bande passante ne sera effectuée et l’appel sortant ignorera les restrictions du service Contrôle d’admission des appels.

### <a name="call-admission-control-of-pstn-connections"></a>Contrôle d’admission des appels des connexions RTC

Contrôle d’admission des appels est exécutoire sur le serveur de médiation indépendamment si elle est connecté à une jonction SIP, une passerelle PSTN ou un PBX IP. Étant donné que le serveur de médiation est un agent utilisateur DOS à DOS (B2BUA), il termine multimédia. Il a deux côtés de la connexion : une partie qui est connectée à Skype pour Business Server et un côté passerelle, qui est connecté à des passerelles PSTN, IP/PBX ou jonctions SIP. Pour plus d’informations sur les connexions RTC, voir [planifier la connectivité PSTN dans Skype pour Business Server](pstn-connectivity-0.md).

CAC peut être appliquée sur les deux côtés du serveur de médiation, sauf si le contournement de média est activé. Si le contournement de média est activé, le trafic multimédia ne parcourir le serveur de médiation, mais plutôt flux directement entre le Skype pour client d’entreprise et la passerelle. Dans ce cas, le contrôle d’admission des appels n’est pas nécessaire. Pour plus d’informations, voir [Plan pour le média de contournement dans Skype pour les entreprises](media-bypass.md).

La figure suivante illustre la façon dont le contrôle d’admission des appels est appliqué sur les connexions RTC avec ou sans la déviation du trafic multimédia activée.

**Application du contrôle d’admission des appels sur des connexions RTC**

![Application de connexion de contournement de média CAC vocal](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)

## <a name="defining-your-requirements-for-call-admission-control"></a>Définition de la configuration requise pour le contrôle d’admission des appels

La planification du contrôle d’admission des appels (CAC) requiert des informations détaillées sur votre topologie de réseau d’entreprise. Pour vous aider à planifier vos stratégies de contrôle d’admission des appels, procédez comme suit.

1. Identifiez les concentrateurs/dorsales principales (appelés régions réseau) dans votre réseau d’entreprise.

2. Identifiez les bureaux et emplacements (appelés sites réseau) dans chaque région réseau.

3. Déterminez l’itinéraire réseau entre chaque paire de régions réseau.

4. Déterminez les limites de bande passante pour chaque liaison réseau étendu (WAN).

    > [!NOTE]
    > Limites de bande passante faire référence à la quantité de bande passante sur une liaison WAN est allouée pour Enterprise Voice et le trafic audio/vidéo. Lorsqu’une liaison WAN est décrite sous la forme « bande passante restreinte », la liaison WAN possède une limite de bande passante est inférieure au trafic prévu pointe sur le lien.

5. Identifiez les sous-réseaux IP affectés à chaque site réseau.

Pour expliquer ces concepts, nous allons utiliser l’exemple de topologie réseau indiqué dans la figure suivante.

**Exemple de topologie pour le contrôle d’admission des appels**

![Exemple de topologie réseau Litware Inc.](../../media/Plan_CS_VoiceCAC_Litwarenetworktopo.jpg)

> [!NOTE]
> Tous les sites réseau sont associés à une région réseau. Par exemple, Portland, Reno et Albuquerque sont inclus dans la région Amérique du Nord. Dans cette figure, seules les liaisons réseau étendu auxquelles des stratégies de service Contrôle d’admission des appels sont appliquées sont présentées, avec des limites de bande passante. Les sites réseau Chicago, New York et Détroit s’affichent dans l’ovale de la région Amérique du Nord, car ils ne sont soumis à aucune limite de bande passante et ne nécessitent donc aucune stratégie de service Contrôle d’admission des appels.

Les composants de cet exemple de topologie sont décrits dans les sections suivantes. Pour plus d’informations sur la façon dont cette topologie a été planifiée, y compris les limites de bande passante, voir [exemple : collecte des conditions requises pour le contrôle d’admission des appels dans Skype pour Business Server](example-gathering-requirements.md).

### <a name="identify-network-regions"></a>Identifier les régions réseau

Une région réseau représente une dorsale principale ou un concentrateur réseau.

Une dorsale principale ou un concentrateur réseau fait partie de l’infrastructure réseau informatique qui interconnecte différents éléments du réseau, fournissant ainsi un chemin pour l’échange des informations entre différents réseaux locaux (LAN) ou sous-réseaux. Une dorsale principale peut lier divers réseaux d’un petit emplacement à une zone géographique étendue. La capacité de la dorsale principale est généralement plus grande que celle des réseaux qui s’y connectent.

Notre exemple de topologie comporte trois régions réseau : Amérique du Nord, EMEA et APAC. Une région réseau contient un ensemble de sites réseau (voir la définition des sites réseau dans la suite de cette rubrique). Collaborez avec votre équipe responsable des opérations réseau pour identifier vos régions réseau.

### <a name="associating-a-central-site-with-each-network-region"></a>Association d’un site central avec chaque région réseau

CAC requiert qu’un Skype pour le site central Business Server est défini pour chaque région réseau. Le site central est sélectionné en fonction de la meilleure connectivité réseau et de la bande passante la plus élevée parmi les autres sites de la région réseau. L’exemple précédent de topologie réseau montre trois régions réseau, chacune comportant un site central qui gère les décisions du service Contrôle d’admission des appels. Dans l’exemple précédent, l’association appropriée est indiquée dans le tableau ci-après.

> [!NOTE]
> Les sites centraux ne correspondent pas nécessairement aux sites réseau. Dans les exemples de cette documentation, certains sites centraux (Chicago, Londres et Pékin) portent les mêmes noms que les sites réseau. Toutefois, même si un site central et un site réseau partagent le même nom, le site central est un élément de la Skype pour la topologie de serveurs d’entreprise, tandis que le site de réseau est une partie de l’ensemble du réseau dans lequel réside le Skype pour la topologie du serveur d’entreprise.

**Régions réseau, sites centraux et sites réseau**

|**Région réseau**|**Site Central**|**Sites réseau**|
|:-----|:-----|:-----|
|Amérique du Nord  <br/> |Chicago  <br/> |Chicago  <br/> New York  <br/> Detroit  <br/> Portland  <br/> Reno  <br/> Albuquerque  <br/> |
|EMEA  <br/> |Londres  <br/> |Londres  <br/> Cologne  <br/> |
|APAC  <br/> |Pékin  <br/> |Pékin  <br/> Manille  <br/> |

### <a name="identify-network-sites"></a>Identifier les sites réseau

Un site réseau représente un lieu physique pour votre organisation, par exemple, des bureaux, un ensemble de bâtiments ou un campus. Tout lieu physique qui comporte un réseau local (LAN) et une connectivité de réseau étendu (WAN) vers d’autres sites est considéré comme un site réseau. Commencez par l’inventaire des bureaux de votre organisation. Dans notre exemple de topologie, la région réseau Amérique du Nord comporte les sites réseau suivants : New York, Chicago, Détroit, Portland, Reno et Albuquerque.

Vous devez associer chaque site réseau à une région réseau. Selon que le site réseau dispose d’une liaison réseau étendu restreinte, une stratégie de bande passante est associée au site réseau. Pour plus d’informations sur les stratégies de service Contrôle d’admission des appels et la bande passante que vous allouez en les utilisant, reportez-vous à « Définir des stratégies de bande passante » dans la suite de cette rubrique. Pour configurer le service Contrôle d’admission des appels, associez des sites réseau à des régions réseau, puis créez des stratégies d’allocation de bande passante qui doivent être appliquées aux connexions à bande passante restreinte entre un site ou une région spécifique, mais aussi aux connexions réseau étendu entre des sites et des régions.

### <a name="identify-network-links"></a>Identifier des liaisons réseau

Les liaisons réseau représentent les connexions au réseau étendu physique qui relient différentes régions et différents sites. Dans notre exemple de topologie, il y a deux liaisons réseau régionales, cinq liaisons réseau entre des régions et des sites, et une liaison réseau entre deux sites.

Les deux liaisons régionales sont entre Amérique du Nord et EMEA, représentés par NA-EMEA-LINK, et entre APAC et EMEA, représentés par EMEA-APAC-LINK.

Les liaisons de sites sont indiquées par des traits connectant Portland, Reno et Albuquerque à la région Amérique du Nord, Manille à la région APAC et Cologne à la région EMEA. Le trait entre Reno et Albuquerque indique une liaison réseau directe entre ces deux sites.

### <a name="define-bandwidth-policies"></a>Définir des stratégies de bande passante

Collaborez avec votre équipe responsable des opérations réseau pour déterminer la quantité de bande passante de réseau étendu mise à disposition du trafic audio et vidéo en temps réel sur les liaisons réseau étendu de votre organisation. Les stratégies de bande passante sont généralement appliquées aux liaisons réseau étendu si l’utilisation de la bande passante est restreinte ; c’est-à-dire, si on pense qu’elle sera supérieure à la bande passante pouvant être allouée aux modes audio et vidéo.

Les stratégies de bande passante du service Contrôle d’admission des appels définissent la bande passante maximale qui peut être réservée aux modes audio et vidéo en temps réel. Comme le service Contrôle d’admission des appels ne limite pas la bande passante d’un autre trafic de données, il ne peut pas empêcher les autres trafics de données (par exemple, un transfert de fichiers volumineux ou la diffusion en continu de morceaux de musique) d’utiliser toute la bande passante réseau.

Les stratégies de bande passante CAC peuvent définir un ou plusieurs des éléments suivants :

- Bande passante totale maximale allouée à l’audio.

- Bande passante totale maximale allouée à la vidéo.

- Bande passante maximale allouée à un appel audio unique (session).

- Bande passante maximale allouée à un appel vidéo unique (session).

> [!NOTE]
> Toutes les valeurs de bande passante CAC représentent les limites de bande passante maximale *unidirectionnelle* .

> [!NOTE]
> Le Skype pour les fonctionnalités de stratégie de voix entreprise Server fournissent des vérifications de la possibilité de remplacer la stratégie de bande passante pour les appels entrants à l’utilisateur (pas pour les appels sortants sont passés par l’utilisateur). Une fois la session établie, la consommation de bande passante est calculée avec précision. Ce paramètre doit être utilisé avec modération. Pour plus d’informations, voir [créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype pour les entreprises](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) ou [Modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN](https://technet.microsoft.com/library/6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd.aspx) dans la documentation de déploiement.

Pour optimiser l’utilisation de la bande passante par session, tenez compte du type des codecs audio et vidéo qui seront utilisés. Plus particulièrement, allouez suffisamment de bande passante pour un codec que vous pensez utiliser fréquemment. À l’inverse, si vous souhaitez empêcher le média d’utiliser un codec nécessitant davantage de bande passante, définissez une bande passante maximale par session qui soit suffisamment basse pour décourager ce type d’utilisation. Pour l’audio, tous les codecs ne sont pas disponibles pour chaque scénario. Par exemple :

- Appels audio d’égal à égal entre Skype pour systèmes d’extrémité Business utiliseront RTAudio (8kHz) ou RTAudio (16kHz) quand vous prendrez en la bande passante et la définition des priorités des codecs.

- Téléconférences entre Skype pour systèmes d’extrémité Business et A / V Conferencing service utilise G.722 ou Siren.

- Les appels vers le réseau téléphonique commuté (RTC), vers ou depuis Skype pour systèmes d’extrémité Business utiliseront G.711 ou RTAudio (8kHz).

Utilisez le tableau suivant pour optimiser les paramètres de bande passante par session maximale.

**Utilisation de la bande passante par codecs**

|**Codec**|**Besoin en bande passante sans correction des erreurs de transfert (FEC)**|**Besoin en bande passante avec correction des erreurs de transfert (FEC)**|
|:-----|:-----|:-----|
|RTAudio (8kHz)  <br/> |49,8 Kbits/s  <br/> |61,6 Kbits/s  <br/> |
|RTAudio (16 kHz)  <br/> |67 Kbits/s  <br/> |96 Kbits/s  <br/> |
|Siren  <br/> |57,6 Kbits/s  <br/> |73,6 Kbits/s  <br/> |
|G.711  <br/> |102 Kbits/s  <br/> |166 Kbits/s  <br/> |
|G.722  <br/> |105,6 Kbits/s  <br/> |169,6 Kbits/s  <br/> |
|RTVideo (CIF 15 i/s)  <br/> |260 Kbits/s  <br/> |Non applicable  <br/> |
|RTVideo (VGA 30 i/s)  <br/> |610 Kbits/s  <br/> |Non applicable  <br/> |

> [!NOTE]
> Les besoins en bande passante prennent en compte le traitement des éléments suivants : Ethernet II, IP, UDP (User Datagram Protocol), RTP (Real-Time Transport Protocol) et SRTP (Secure Real-Time Transport Protocol). Ils incluent également 10 Kbits/s pour le traitement RTCP.

Les codecs G.722.1 et Siren sont similaires, mais offrent différentes vitesses de transmission.

G.722, codec par défaut de Skype pour la conférence Business Server, est complètement différent des codecs G.722.1 et Siren.

Le codec Siren est utilisé dans Skype pour Business Server dans les situations suivantes :

- La stratégie de bande passante est définie sur une valeur trop basse pour permettre l’utilisation de G.722.

- Si un client de Communications Server 2007 ou Communications Server 2007 R2 se connecte à un Skype pour le service de conférence Business Server (car ces clients ne prennent pas en charge le codec G.722).

**Utilisation de la bande passante par scénario**

|**Scénario**|**Besoins en bande passante optimisés pour la quantité (Kbits/s)**|**Besoins en bande passante pour le mode équilibré (Kbits/s)**|**Besoins en bande passante optimisés pour la qualité (Kbits/s)**|
|:-----|:-----|:-----|:-----|
|Appels audio P2P  <br/> |45 Kbits/s  <br/> |62 Kbits/s  <br/> |91 Kbits/s  <br/> |
|Téléconférences  <br/> |53 Kbits/s  <br/> |101 Kbits/s  <br/> |165 Kbits/s  <br/> |
|Appels PSTN (entre Skype pour l’entreprise et une passerelle PSTN, avec contournement de média)  <br/> |97 Kbits/s  <br/> |97 Kbits/s  <br/> |161 Kbits/s  <br/> |
|Appels PSTN entre (Skype pour les entreprises) et le serveur de médiation, sans contournement de média  <br/> |45 Kbits/s  <br/> |97 Kbits/s  <br/> |161 Kbits/s  <br/> |
|Appels PSTN (entre le serveur de médiation et passerelle PSTN, sans contournement de média)  <br/> |97 Kbits/s  <br/> |97 Kbits/s  <br/> |161 Kbits/s  <br/> |
|Skype pour les entreprises - Polycom appelle  <br/> |101 Kbits/s  <br/> |101 Kbits/s  <br/> |101 Kbits/s  <br/> |

### <a name="identify-ip-subnets"></a>Identifier les sous-réseaux IP

Pour chaque site réseau, vous devrez collaborer avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Si votre administrateur réseau a déjà organisé les sous-réseaux IP en régions réseau et sites réseau, votre travail est considérablement simplifié.

Dans notre exemple, le site New York de la région Amérique du Nord se voit affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Supposons que Bob, qui travaille généralement à Détroit, se rende dans les bureaux de New York pour suivre une formation. Quand il allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages réservées à New York (par exemple, 172.29.80.103).

> [!CAUTION]
> Les sous-réseaux IP spécifiés pendant la configuration du réseau sur le serveur doivent correspondre au format fourni par les ordinateurs clients afin d’être correctement utilisés pour la déviation du trafic multimédia. Un Skype pour client Business prend son adresse IP locale et masque l’adresse IP avec le masque de sous-réseau associés. Lors de la détermination de l’ID de contournement associé à chaque client, le serveur d’inscriptions comparera la liste des sous-réseaux IP associés à chaque site réseau avec le sous-réseau fourni par le client pour obtenir une correspondance exacte. Pour cette raison, il est important que les sous-réseaux entrés lors de la configuration du réseau sur le serveur soient des sous-réseaux réels et non des sous-réseaux virtuels. (Si vous déployez le contrôle d’admission des appels d’appel, mais pas le contournement de média, le contrôle d’admission des appels d’appel peut fonctionner même si vous configurez les sous-réseaux virtuels.) Par exemple, si un client se connecte sur un ordinateur disposant d’une adresse IP de 172.29.81.57 avec un masque de sous-réseau de 255.255.255.0, Skype pour les entreprises demander l’ID de contournement associée au sous-réseau 172.29.81.0. Si le sous-réseau est défini comme 172.29.0.0/16, même si le client appartient au sous-réseau virtuel, le serveur d’inscriptions ne considérera pas cela comme une correspondance, car le serveur d’inscriptions recherche spécifiquement le sous-réseau 172.29.81.0. Par conséquent, il est important que l’administrateur entre les sous-réseaux fournie par Skype pour les clients d’entreprise (qui sont mis en service avec les sous-réseaux lors de la configuration réseau statique ou par DHCP.)

## <a name="best-practices-for-call-admission-control"></a>Meilleures pratiques liées au contrôle d’admission des appels

Pour améliorer les performances et faciliter le déploiement, appliquez les recommandations suivantes lors du déploiement du contrôle d’admission des appels :

- Vérifiez que les réseaux étendus (WAN) sont configurés en conséquence pour le trafic multimédia actuel et envisagé.

    > [!NOTE]
    > Nous vous conseillons de définir un facteur en mémoire tampon quant aux limites de votre bande passante. Il existe des scénarios de condition de concurrence qui agissent sur la bande passante totale utilisée et qui peuvent entraîner des situations de dépassement de la limite de la bande. Prenons l’exemple de deux appels amorcés alors que le trafic multimédia approche de la limite de la bande passante : l’un des appels pourra être refusé, car l’autre a été configuré pour démarrer en premier.

- Contrôlez l’utilisation du réseau et les enregistrements des détails des appels pour pouvoir choisir les meilleurs paramètres de contrôle d’admission des appels (CAC) et les mettre à jour en fonction de l’évolution de l’utilisation du réseau.

- Utilisez les stratégies de bande passante CAC pour compléter les paramètres QoS.

- Si vous souhaitez réacheminer des appels bloqués sur le réseau RTC, vérifiez les fonctionnalités et capacités correspondantes. Pour plus d’informations, reportez-vous à [Planning Outbound Call Routing](https://technet.microsoft.com/library/37c55fa4-175a-4190-b9e4-c2e5ac7b9261.aspx).

    > [!NOTE]
    > La capacité fait référence au nombre de ports à ouvrir pour prendre en charge un éventuel réacheminement vers le réseau RTC.


