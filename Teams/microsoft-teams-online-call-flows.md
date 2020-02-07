---
title: Carrousel Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Décrit la façon dont teams utilise les flux d’Office 365 dans différentes topologies.
ms.openlocfilehash: 409af0b815c87e6d8285c3cb9a1bd8a5d61fa98b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832824"
---
# <a name="microsoft-teams-call-flows"></a>Carrousel Microsoft Teams

> [!TIP]
> Regardez cette session pour découvrir comment les équipes tirent parti de votre réseau et comment prévoir une connectivité réseau optimale : [planification du réseau d’équipes](https://aka.ms/teams-networking).

## <a name="overview"></a>Vue d’ensemble

Cet article décrit comment teams utilise les flux d’appels d’Office 365 dans différentes topologies. Par ailleurs, il décrit les flux d’équipes uniques qui sont utilisés pour la communication de médias P2P. Ce document décrit ces flux, leur objet, leur origine et leurs arrêts sur le réseau. Dans le cadre de cet article, procédez comme suit :

- Flow X est utilisé par le client Office 365 local pour communiquer avec le service 365 Office dans le Cloud. Il provient du réseau du client et il se termine par un point de terminaison dans Office 365.

- Le flux Y est utilisé par le client Office 365 local pour communiquer avec un service sur Internet sur lequel Office 365 a une dépendance. Ce service provient du réseau du client et il se termine par un point de terminaison sur Internet.

Cet article aborde les informations suivantes :

- L' **arrière-plan**. Fournit des informations d’arrière-plan telles que des réseaux que le flux d’Office 365 transmet, des types de trafic, des recommandations en matière de connectivité du réseau du client aux points de terminaison du service Office 365, l’interopérabilité avec les composants tiers et les principes utilisés. par teams pour sélectionner les flux multimédias.

- **Flux d’appels dans différentes topologies**. Illustre l’utilisation des flux d’appels dans différentes topologies. Pour chaque topologie, la section énumère tous les flux pris en charge et illustre la façon dont ces flux sont utilisés dans plusieurs cas d’utilisation. Pour chaque cas d’utilisation, il décrit la séquence et la sélection de flux à l’aide d’un diagramme de flux.

- **Équipes avec l’optimisation de l’itinéraire rapide**. Décrit l’utilisation de ces flux lorsque l’itinéraire rapide est déployé pour l’optimisation, illustré par une topologie simple.

## <a name="background"></a>Arrière-plan

### <a name="network-segments"></a>Segments réseau

**Réseau du client**. Il s’agit du segment réseau que vous contrôlez et gérez. Il s’agit de toutes les connexions aux clients au sein des bureaux du personnel, qu’il s’agisse de connexions filaires ou sans fil, de connexions entre les bâtiments d’Office, de connexions aux centres de contenus locaux et de vos connexions à des fournisseurs de services Internet, d’un itinéraire rapide ou de toute autre homologation privée.

En règle générale, un réseau de clients est doté de plusieurs périmètres réseau avec des pare-feu et/ou des serveurs proxy, qui appliquent les stratégies de sécurité de votre organisation, et qui autorisent uniquement le trafic réseau configuré et configuré. Dans la mesure où vous gérez ce réseau, vous disposez d’un contrôle direct sur les performances du réseau et nous vous conseillons d’effectuer des évaluations réseau pour valider les performances des sites de votre réseau et de votre réseau au réseau 365 Office.

**Internet**. Il s’agit du segment réseau qui fait partie de votre réseau global qui sera utilisé par les utilisateurs qui se connectent à Office 365 depuis l’extérieur du réseau du client. Il est également utilisé par du trafic du réseau du client vers Office 365.

**Visité ou réseau privé invité**. Il s’agit du segment réseau hors du réseau de votre client, mais pas sur Internet, que vos utilisateurs et leurs invités peuvent consulter (par exemple, un réseau privé privé ou un réseau privé d’entreprise) qui ne déploie pas Teams, où les utilisateurs et leurs clients interagissent avec les services Teams.

> [!NOTE]
> La connectivité à Office 365 s’applique également à ces réseaux.

**Office 365**. Il s’agit du segment réseau qui prend en charge les services Office 365. Ce service est distribué partout dans le monde avec des bords proches du réseau du client, dans la plupart des pays. Les fonctions incluent relais de transport, serveur de conférence et processeur multimédia.

**Itinéraire rapide (facultatif)**. Il s’agit du segment réseau qui fait partie de votre réseau global et qui vous offrira une connexion privée et dédiée au réseau Office 365.

### <a name="types-of-traffic"></a>Types de trafic

**Média en temps réel**. Données encapsulées en temps réel (RTP) qui prennent en charge les charges de travail de partage d’écran, audio et vidéo. En règle générale, le trafic multimédia est sensible à la latence, de telle sorte que vous souhaitez que ce trafic prenne le plus en chemin direct possible et qu’il utilise le protocole UDP et TCP en tant que protocole de couche de transport, qui est le meilleur transport pour le média en temps réel interactif du point de vue de la qualité . (Notez qu’en dernier recours, les médias peuvent utiliser TCP/IP et être mis en tunnel dans le protocole HTTP, mais cela n’est pas recommandé en raison de mauvaises implications de qualité.) Le flux RTP est sécurisé à l’aide de SRTP, dont seule la charge utile est chiffrée.

**Signalisation**. Lien de communication entre le client et le serveur ou d’autres clients qui sont utilisés pour contrôler les activités (par exemple, quand un appel est lancé) et livrer des messages instantanés. La plupart du trafic de signalisation utilise les interfaces REST basées sur HTTPs, mais dans certains scénarios (par exemple, connexion entre Office 365 et contrôleur de bordure de session), elle utilise le protocole SIP. Il est important de comprendre que ce trafic est beaucoup plus sensible à la latence, mais qu’il peut entraîner des délais d’expiration de service ou des délais d’expiration de l’appel si la latence entre les points de terminaison est supérieure à plusieurs secondes.

### <a name="connectivity-to-office-365"></a>Connectivité à Office 365

Teams nécessite une [connexion à Internet](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity). Les URL et plages d’adresses IP du point de terminaison équipes sont répertoriées dans les [URL et plages d’adresses IP Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). (Notez qu’il est nécessaire d’ouvrir la connectivité aux ports TCP 80 et 443 et aux ports UDP 3478 à 3481.) Par ailleurs, teams est lié à Skype entreprise Online et doit également être connecté à Internet.

La connectivité des flux multimédias de teams est implémentée à l’aide de procédures standard d’établissement de la connectivité IETF.

### <a name="interoperability-restrictions"></a>Restrictions d’interopérabilité

**Relais multimédias tiers**. Le flux multimédia d’équipes (autrement dit, l’un des points de terminaison de média est Teams) peut uniquement traverser des équipes ou des relais multimédias natifs Skype entreprise. L’interopérabilité avec un relais multimédia tiers n’est pas pris en charge. (Notez qu’un SBC tiers sur la limite du réseau PSTN doit arrêter le flux RTP/RTCP, sécurisé à l’aide de SRTP, et ne pas le relayer vers le saut suivant.)

**Serveurs proxy SIP tiers**. Une boîte de dialogue SIP de Microsoft teams avec un SBC et/ou une passerelle tierce est susceptible de traverser des équipes ou des proxys SIP de Skype entreprise. L’interopérabilité avec un proxy SIP tiers n’est pas pris en charge.

**B2BUA tiers (ou SBC)**. Un flux multimédia d’équipes vers et depuis le RTC est arrêté par un SBC tiers. Toutefois, l’interopérabilité avec un SBC tiers au sein du réseau de Teams (dans le cadre d’une tierce partie de l’équipe ou de points de terminaison Skype entreprise) n’est pas prise en charge.

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Technologies non recommandées par Microsoft teams

**Réseau VPN**. Ce n’est pas recommandé pour le trafic multimédia (ou le flux 2). Le client VPN doit utiliser une connexion VPN fractionnée et router le trafic multimédia comme n’importe quel utilisateur externe non VPN, comme indiqué dans [la rubrique activation de médias Lync pour ignorer un tunnel VPN](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210).

> [!NOTE]
> Même si le titre indique Lync, il s’applique également aux équipes.

Les **formes de paquets**. Tout type de paquets Snippers, d’inspection de paquets ou de périphériques de type paquet est déconseillé et risque de dégrader la qualité.

### <a name="principles"></a>Exposés

Il existe quatre principes généraux qui vous permettent de comprendre les flux d’appels pour Microsoft teams :

- Une conférence Microsoft teams est hébergée par Office 365 dans la même région où le premier participant rejoint. (Notez que s’il existe des exceptions à cette règle dans certaines topologies, celles-ci sont décrites dans ce document et illustrées par un flux d’appels approprié.)

- Un point de terminaison de média teams dans Office 365 est utilisé en fonction du traitement multimédia requis et non en fonction du type d’appel. Par exemple, un appel point à point est susceptible d’utiliser un point de terminaison de média dans le Cloud pour traiter du contenu multimédia à des fins de transcription ou d’enregistrement, tandis qu’une conférence avec deux participants n’utilise pas de point de terminaison multimédia dans le Cloud.) Toutefois, la plupart des conférences utilisent un point de terminaison de média à des fins de mixage et de routage, qui est alloué au lieu d’hébergement de la Conférence. Le trafic multimédia envoyé d’un client à un point de terminaison de média est acheminé directement ou utiliser un relais de transport dans Office 365 si cela est requis en raison de restrictions de pare-feu du réseau du client.

- Le trafic multimédia pour les appels d’égal à égal utilise l’itinéraire le plus direct disponible, en supposant que l’appel n’impose pas de point de terminaison multimédia dans le Cloud (voir principe précédent). L’itinéraire par défaut est diriger vers l’homologue distant (client), mais si ce routage n’est pas disponible, un ou plusieurs relais de transport relayeront le trafic. Il est recommandé que le trafic multimédia ne soit pas transforme des serveurs tels que les formes de paquets, les serveurs VPN, etc., car cela aura un impact sur la qualité du média.

- Le trafic de signalisation passe toujours au serveur le plus proche de l’utilisateur.

Pour en savoir plus sur les détails sur le chemin multimédia choisi, voir [Présentation des flux multimédias dans Microsoft teams-BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo).

## <a name="call-flows-in-various-topologies"></a>Flux d’appels dans différentes topologies

### <a name="teams-topology"></a>Topologie teams

Cette topologie est utilisée par les clients qui tirent parti des services d’équipe du Cloud sans déploiement local, tels que Skype entreprise Server ou le routage direct du système téléphonique. Par ailleurs, l’interface à Office 365 est exécutée sur Internet sans Azure Express route.

[![Flux d’appels de Microsoft teams Online figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Figure 1 : topologie teams*

Notez que :

- Le sens des flèches sur le diagramme ci-dessus correspond au sens de début de la communication qui affecte la connectivité aux périmètres d’entreprise. Dans le cas d’UDP pour le média, le (s) premier (s) fichier (s) peut s’afficher dans le sens inverse, mais ces paquets peuvent être bloqués jusqu’à ce que les paquets dans l’autre direction soient acheminés.
- Les équipes sont déployées côte à côte avec Skype entreprise Online, de sorte que les clients apparaissent comme un « teams/marketing User ».

Vous trouverez plus d’informations sur les topologies facultatives suivantes, plus loin dans cet article :

- Le déploiement local de Skype entreprise est décrit dans **topologie hybride teams**.
- Le routage direct du système téléphonique (pour la connectivité PSTN) est décrit dans **teams avec une topologie de routage direct**.
- L’itinéraire rapide est décrit dans **teams avec l’optimisation de l’itinéraire rapide**.

**Descriptions de flux**:

- **Flux 2** : représente un flux initié par un utilisateur sur le réseau du client sur Internet dans le cadre de l’utilisation des équipes de l’utilisateur. Le DNS et le média d’égal à égal sont des exemples de ces flux.
- **Flux 2 '** – représente un flux déclenché par un utilisateur d’équipes mobiles distantes, avec VPN pour le réseau du client.
- **Flux 3** – représente un flux initié par un utilisateur d’équipes mobiles distant aux points de terminaison Office 365/Teams.
- **Flux 4** – représente un flux initié par un utilisateur sur le réseau du client aux points de terminaison Office 365/Teams.
- **Flux 5** : représente un flux multimédia d’égal à égal entre une équipe et un utilisateur de teams ou Skype entreprise au sein du réseau du client.
- **Flux 6** : représente un flux multimédia P2P entre un utilisateur de l’équipe mobile distant et une autre équipe mobile distante ou un utilisateur Skype entreprise sur Internet.

#### <a name="use-case-one-to-one"></a>Cas d’utilisation : un-à-un

Les appels un-à-un utilisent un modèle courant dans lequel l’appelant obtiendra un ensemble de candidatures composées d’adresses IP et de ports, y compris local, Relay et réflexive (adresse IP publique du client visible par le relais). L’appelant envoie ces candidats à la partie appelée ; le tiers appelé obtient également un ensemble de candidats similaire et les envoie à l’appelant. STUNx, xxx xxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx. Les médias (c’est-à-dire les paquets RTP/RTCP sécurisés à l’aide de SRTP) sont ensuite envoyés en utilisant la paire de candidats sélectionnée. Le relais de transport est déployé dans le cadre d’Office 365.

Si l’adresse IP locale/le port candidats ou les candidats réflexives ont une connectivité, le chemin d’accès direct entre les clients (ou à l’aide d’un NAT) est sélectionné pour le média. Si les clients sont sur le réseau du client, le chemin d’accès direct doit être sélectionné. Cela nécessite une connectivité UDP directe au sein du réseau du client. Si les clients sont les utilisateurs du Cloud Nomadic, puis, en fonction du NAT/pare-feu, le contenu multimédia pourra utiliser une connectivité directe.

Si un client est interne sur le réseau du client et si un client est externe (par exemple, un utilisateur du Cloud mobile), il est peu probable que la connectivité directe entre les candidats local ou réflexive fonctionne. Dans ce cas, il est possible d’utiliser l’un des candidats de relais de transport à partir de l’un des clients (par exemple, le client interne a obtenu un candidat de relais à partir du relais de transport dans Office 365 ; le client externe doit être en mesure d’envoyer des paquets STUN/RTP/RTCP au relais de transport). Une autre option consiste à ce que le client interne envoie à la candidature de relais obtenu par le client Cloud mobile. Notez que, même si la connectivité UDP pour le média est fortement recommandée, TCP est pris en charge.

**Étapes de niveau supérieur**:

1. L’utilisateur teams A résout le nom de domaine d’URL (DNS) à l’aide du flux 2.
1. L’utilisateur de teams A alloue un port de relais multimédia sur Team Relay Relay à l’aide de Flow 4.
1. L’utilisateur teams A envoie une invitation à une glace en utilisant le flux 4 au bureau 365.
1. Office 365 envoie une notification à l’utilisateur de teams B à l’aide du flux 4.
1. L’utilisateur de teams B alloue un port de relais multimédia sur Team Relay Relay à l’aide de Flow 4.
1. L’utilisateur de teams B envoie « Answer » avec les candidats de glace en utilisant Flow 4, qui est renvoyé à l’utilisateur de teams A à l’aide de Flow 4.
1. Les utilisateurs teams A et équipe B appellent des tests de connectivité ICE et le meilleur chemin multimédia disponible est sélectionné (voir les diagrammes ci-dessous pour de nombreux cas d’utilisation).
1. Les utilisateurs de teams envoient une télémétrie à Office 365 à l’aide de Flow 4.

**Au sein du réseau du client :**

[![Flux d’appels de Microsoft teams Online figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Figure 2 : au sein du réseau du client*

À l’étape 7, le flux de média d’égal à égal (5) est sélectionné.

Le média est bidirectionnel. Le sens du flux 5 indique qu’un côté initialise la communication du point de vue de la connectivité, conformément à tous les flux figurant dans ce document. Dans le cas présent, il n’y a pas d’importance quant à la direction utilisée, car les deux points de terminaison sont au sein du réseau du client.

**Connexion du réseau du client aux utilisateurs externes (médias relayés par teams Relay Relay) :**

[![Flux d’appels de Microsoft teams Online figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Figure 3 : réseau des clients pour les utilisateurs externes (média relayée par Team Relay Relay)*

À l’étape 7, flux 4, du réseau du client vers Office 365 et flux 3, à partir de l’application mobile teams vers Office 365, sont sélectionnées. Ces flux sont relayés par teams transport Relay dans Office 365.

Le média est bidirectionnel, la direction indiquant le côté qui initialise la communication du point de vue de la connectivité. Dans ce cas, ces flux sont utilisés pour le signalement et le contenu multimédia à l’aide de différents protocoles et adresses de transport.

**Connexion du réseau du client aux utilisateurs externes (médias directs) :**

[![Flux d’appels de Microsoft teams Online figure 4](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Figure 4 : réseau du client pour les utilisateurs externes (médias directs)*

À l’étape 7, l’option flux 2 du réseau du client vers Internet (homologue du client) est sélectionnée.

- Les éléments multimédias directs avec les utilisateurs mobiles distants (non relayés via Office 365) sont facultatifs. En d’autres termes, le client doit bloquer ce chemin pour appliquer un chemin multimédia par le biais du relais de transport dans Office 365.

- Le média est bidirectionnel. Le sens du flux 2 vers l’utilisateur mobile distant indique qu’un côté initialise la communication du point de vue de la connectivité.

**Utilisateur VPN pour un utilisateur interne (médias relayés par Team Relay Relay)**

[![Flux d’appels de Microsoft teams Online figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Figure 5 : utilisateur VPN pour un utilisateur interne (média relayée par Team Relay Relay)*

Le signalement du réseau VPN au réseau du client utilise le flux 2. La signalisation entre le réseau du client et le 365 Office utilise le flux 4. Toutefois, le contenu multimédia passe outre le VPN et est acheminé via les flux 3 et 4 via Team Media Relay dans Office 365.

**Utilisateur VPN pour un utilisateur interne (médias directs)**

[![Flux d’appels de Microsoft teams Online, figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Figure 6-utilisateur VPN pour un utilisateur interne (médias directs)*

Le signalement du réseau VPN au réseau du client utilise le flux 2. La signalisation entre le réseau du client et le 365 Office utilise le flux 4. Toutefois, le contenu multimédia passe outre le VPN et est acheminé via le flux 2 du réseau du client vers Internet.

Le média est bidirectionnel. Le sens du flux 2 vers l’utilisateur mobile distant indique qu’un côté initialise la communication du point de vue de la connectivité.

**Utilisateur VPN pour un utilisateur externe (médias directs)**

[![Flux d’appels de Microsoft Teams, figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Figure 7 : utilisateur VPN pour un utilisateur externe (médias directs)*

La signalisation entre l’utilisateur VPN sur le réseau du client consiste à utiliser Flow 2» et à utiliser Flow 4 vers Office 365. Toutefois, le média passe par un réseau privé virtuel et est routé à l’aide du flux 6.

Le média est bidirectionnel. Le sens du flux 6 vers l’utilisateur mobile distant indique qu’un côté initialise la communication du point de vue de la connectivité.

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>Cas d’utilisation : teams RTC par le biais d’Office 365 Trunk

Le système téléphonique d’Office 365 permet de passer et de recevoir des appels à partir du réseau téléphonique public commuté (RTC). Si le Trunking RTC est connecté à l’aide de l’offre téléphonique du système téléphonique, il n’existe aucune exigence de connectivité spéciale pour ce cas d’utilisation. (Si vous voulez connecter votre propre Trunk PSTN local à Office 365, vous pouvez utiliser le routage direct du système téléphonique.)

[![Flux d’appels de Microsoft teams Online figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Figure 8 : équipe RTC via le Trunking d’Office 365*

#### <a name="use-case-teams-meeting"></a>Cas d’utilisation : réunion teams

Le serveur de conférence audio/vidéo/de partage d’écran (VBSS) fait partie d’Office 365. Il possède une adresse IP publique qui doit être accessible à partir du réseau du client et être accessible à partir d’un client Cloud Nomadic. Chaque client/point de terminaison doit être en mesure de se connecter au serveur de conférence.

Les clients internes obtiennent des candidats locaux, réflexurs et Relay de la même manière que pour les appels One-to-One. Les clients envoient ces candidats au serveur de conférence dans une invitation. Le serveur de conférence n’utilise pas de relais car il dispose d’une adresse IP publique et publique, de sorte qu’il répond avec son candidat d’adresse IP local. Le client et le serveur de conférence vérifient la connectivité de la même manière que pour les appels One-to-One.

Notez que :

- Les clients Teams ne peuvent pas participer à des réunions Skype entreprise et les clients Skype entreprise ne peuvent pas participer à des réunions d’équipes.

- Un utilisateur RTC peut éventuellement « se connecter » ou est « composé », en fonction de l’organisateur de la réunion et/ou de la mise en service de la conférence téléphonique.

- Un utilisateur invité ou un utilisateur client peut rejoindre un réseau privé invité, qui est protégé à l’aide du microprotocole et de la NAT avec des règles strictes.

[![Flux d’appels de Microsoft teams Online, figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Figure 9 : réunion teams*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Cas d’utilisation : Fédération avec Skype entreprise sur site

**Media relayés par teams transport Relay dans Office 365**

[![Flux d’appels de Microsoft teams Online figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Figure 10 : contenu multimédia relayée par teams transport Relay dans Office 365*

Notez que :

- La Fédération est, par définition, une communication entre deux clients. Dans ce cas, le locataire A, qui utilise Teams, est fédérer avec le locataire B, qui utilise Skype entreprise sur site. Si le client B utilise également Office 365, le client Skype entreprise aurait utilisé le flux 3 pour me connecter à Office 365.

- Le signalement et le contenu multimédia du client fédéré Skype entreprise à Skype entreprise Server sur site n’est pas le cadre de ce document. Toutefois, il est illustré ici pour plus de clarté.

- La signalisation entre teams et Skype entreprise est bridgeée par une passerelle dans Office 365.

- Dans le cas présent, les éléments multimédias sont relayés par teams transport Relay dans Office 365 vers le réseau du client et le client Skype entreprise distant à l’aide du flux 4.

**Média relayée par Skype entreprise Media Relay dans le client fédéré**

[![Flux d’appels de Microsoft teams Online figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Figure 11-média relayée par Skype entreprise Media Relay dans le client fédéré*

Notez que :

- Le signalement et le contenu multimédia du client fédéré Skype entreprise à un serveur Skype entreprise local ne figurent pas dans ce document. Toutefois, il est illustré ici pour plus de clarté.

- La signalisation entre teams et Skype entreprise est bridgeée par une passerelle dans Office 365.

- Dans le cas présent, les éléments multimédias sont relayés par Skype entreprise sur site sur le réseau du client à l’aide du flux 2. (Notez que le trafic de l’utilisateur teams vers le relais de média distant dans le réseau de clients fédérés sera bloqué initialement par le relais multimédia jusqu’à ce que le trafic de la direction inverse commence à circuler. Toutefois, le flux bidirectionnel s’ouvre dans les deux sens.)

**Direct (pair à pair)**

[![Flux d’appels de Microsoft teams Online figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Figure 12-directe (pair à pair)*

### <a name="teams-hybrid-topology"></a>Topologie hybride teams

Cette topologie inclut les équipes ayant un déploiement local de Skype entreprise.

[![Flux d’appels de Microsoft teams Online figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Figure 13 : topologie hybride teams*

- Le sens des flèches sur le diagramme ci-dessus correspond au sens de début de la communication qui affecte la connectivité aux périmètres d’entreprise. Dans le cas d’UDP pour le média, le (s) premier (s) fichier (s) peut s’afficher dans le sens inverse, mais ces paquets peuvent être bloqués jusqu’à ce que les paquets dans l’autre direction soient acheminés.

- Les équipes sont déployées côte à côte avec Skype entreprise Online, de sorte que les clients apparaissent comme un « teams/marketing User ».

Flux supplémentaire (en haut de la topologie Teams) :

- **Flux 5A** : représente un flux multimédia P2P entre un utilisateur de teams au sein du réseau du client et un relais multimédia local Skype entreprise sur le réseau du client.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Cas d’utilisation : équipes dans Skype entreprise One-en-One

**Hybride au sein du réseau du client**

[![Flux d’appels de Microsoft teams Online (figure 14)](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Figure 14-hybride au sein du réseau du client*

La signalisation entre teams et Skype entreprise est bridgeée par une passerelle dans Office 365. Toutefois, le média est routé directement d’égal à égal au sein du réseau du client à l’aide du flux 5.

**Réseau client hybride avec des utilisateurs Skype entreprise externes : relayée par Office 365**

[![Flux d’appels de Microsoft teams Online figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Figure 15-réseau de clients hybride avec des utilisateurs Skype entreprise externes relayés par Office 365*

Notez que :

- Le signalement et le contenu multimédia du client Skype entreprise à un serveur Skype entreprise local ne figurent pas dans le cadre de ce document. Toutefois, il est illustré ici pour plus de clarté.

- La signalisation entre teams et Skype entreprise est bridgeée par une passerelle dans Office 365.

- Le média est relayée via le relais de transport teams dans Office 365 vers le réseau du client via le flux 4.

**Réseau client hybride avec des utilisateurs Skype entreprise externes : relayés par le bord local**

[![Flux d’appels de Microsoft teams Online figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Figure 16-réseau de clients hybride avec des utilisateurs Skype entreprise externes relayés par le biais d’un réseau local*

Notez que :

- Le signalement et le contenu multimédia du client Skype entreprise à un serveur Skype entreprise local ne figurent pas dans le cadre de ce document. Toutefois, il est illustré ici pour plus de clarté.

- La signalisation est bridgeée par une passerelle dans Office 365.

- Le contenu multimédia est relayée par Skype entreprise Media Relay dans Skype entreprise local vers l’utilisateur teams au sein du réseau du client à l’aide du flux multimédia 5A.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Équipe avec le système téléphonique-topologie de routage directe

Cette topologie inclut les équipes avec le routage direct du système téléphonique.

Le routage direct vous permet d’utiliser un fournisseur de services RTC (réseau téléphonique commuté) tiers pris en charge par le jumelage d’un 365 appareil matériel de contrôleur de bordure de session (SBC) sur site, puis de connecter le Trunk de téléphonie à Cet appareil.

Pour prendre en charge ce scénario, le client doit déployer un SBC certifié pour le routage direct auprès de l’un des partenaires certifiés de Microsoft. Le SBC doit être configuré conformément aux recommandations du fournisseur et être routable à partir d’Office 365 pour le trafic UDP direct. Le contenu multimédia risque d’être acheminé directement à partir d’équipes et/ou du client Skype entreprise vers l’SBC (contournement de la passerelle Teams) ou de traverser la passerelle Teams. La connectivité avec le SBC, lorsque le Trunk est configuré pour ignorer la passerelle Teams, est basée sur la glace, où SBC prend en charge ICE-Lite, tandis que le point de terminaison teams/Skype entreprise prend en charge la gestion des contenus multimédias.

[![Flux d’appels de Microsoft teams Online figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

* Figure 17-équipes avec topologie de routage directe du système téléphonique

Notez que :

- Le sens des flèches sur le diagramme ci-dessus correspond au sens de début de la communication qui affecte la connectivité aux périmètres d’entreprise. Dans le cas d’UDP pour le média, le (s) premier (s) fichier (s) peut s’afficher dans le sens inverse, mais ces paquets peuvent être bloqués jusqu’à ce que les paquets dans l’autre direction soient acheminés.

- Les équipes sont déployées côte à côte avec Skype entreprise Online, de sorte que les clients apparaissent comme un « teams/marketing User ».

Flux supplémentaires (en haut de la topologie teams Online) :

- **Flux 4 '** -représente un flux d’Office 365 vers le réseau du client, utilisé pour établir une connexion entre le serveur de média teams dans le Cloud et les SBC en local.
- **Flux 5B** : représente un flux multimédia entre l’utilisateur teams au sein du réseau du client et l’SBC du routage direct en mode Bypass.
- **Flux 5C** – représente un flux multimédia entre l’SBC du routage direct vers un autre SBC de routage direct dans un mode de contournement d’appel cheveux PSTN.

**Utilisateur interne avec routage direct (média relayée par teams transport Relay dans Office 365)**

[![Flux d’appels de Microsoft teams Online figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Figure 18-utilisateur interne avec routage direct (médias relayés par Team Relay dans Office 365)*

Notez que :

- L’SBC doit avoir une adresse IP publique qui est routable à partir d’Office 365.

- Le signalement et le contenu multimédia de l’SBC à Office 365 et inversement utilisent le flux 4 et/ou le flux 4.

- Le signalement et le contenu multimédia du client au sein du réseau du client vers Office 365 utilisent le flux 4.

**Utilisateur distant avec routage direct (le média est routé par le biais d’un serveur multimédia dans Office 365)**

[![Flux d’appels de Microsoft teams Online figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Figure 19-utilisateur distant avec routage direct (le média est routé par le biais d’un serveur multimédia dans Office 365)*

Notez que :

- L’SBC doit avoir une adresse IP publique qui est routable à partir d’Office 365.

- Le signalement et le contenu multimédia de l’SBC à Office 365 et inversement utilisent le flux 4 et/ou le flux 4.

- Le signalement et le contenu multimédia du client sur Internet à Office 365 utilisent le flux 3.

**Routage direct de l’utilisateur interne (contournement du support multimédia)**

[![Flux d’appels de Microsoft teams Online figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Figure 20-routage direct de l’utilisateur interne (contournement du support multimédia)*

Notez que :

- L’SBC doit avoir une adresse IP publique qui est routable à partir d’Office 365.

- Le signalement de SBC à Office 365 et vice versa utilisent le flux 4 et/ou le flux 4.

- La signalisation du client au sein du réseau du client vers Office 365 utilise le flux 4.

- Le média du client sur le réseau du client vers SBC au sein du réseau du client utilise le flux 5B.

**Utilisateur distant avec routage direct (contournement de média relayée par Team Relay Relay dans Office 365)**

[![Flux d’appels de Microsoft teams Online figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Figure 21-utilisateur distant avec routage direct (contournement de média relayée par Team Relay Relay dans Office 365)*

Notez que :

- L’SBC doit avoir une adresse IP publique qui est routable à partir d’Office 365 et Internet.

- Le signalement de l’SBC à Office 365 et inversement utilise le flux 4 et/ou le flux 4.

- Le signalement du client sur Internet à Office 365 utilise le flux 3.

- Le contenu multimédia du client sur Internet à l’SBC au sein du réseau du client utilise les flux 3 et 4, relayés par teams transport Relay dans Office 365.

**Routage direct de l’utilisateur distant (Bypass du support direct)**

[![Flux d’appels de Microsoft teams Online figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Figure 22-routage direct de l’utilisateur distant (relais de média direct)*

Notez que :

- L’SBC doit avoir une adresse IP publique qui est routable depuis Office 365 et Internet.

- Le signalement de l’SBC à Office 365 et inversement utilise le flux 4 et/ou le flux 4.

- Le signalement du client sur Internet à Office 365 utilise le flux 3.

- Le contenu multimédia du client sur Internet à l’SBC au sein du réseau du client utilise le flux 2.

**Routage direct (contournement du support multimédia) – appel cheveux RTC (en raison du transfert d’appel ou du transfert d’appel)**

[![Flux d’appels de Microsoft teams Online figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Figure 23-routage direct (contournement de média)-appel cheveux RTC (en raison d’un renvoi d’appel/transfert)*

Notez que :

- L’SBC doit avoir une adresse IP publique qui est routable à partir d’Office 365.

- Le signalement de l’SBC à Office 365 et inversement utilise le flux 4 et/ou le flux 4.

- Le client n’est pas dans la boucle de signalisation et de média une fois que l’appel est hairpinned de RTC à PSTN.

- Les éléments multimédias de l’instance SBC A au sein du réseau du client à l’instance SBC B au sein du réseau du client (où, A et B peuvent être de la même instance) utilise le flux 5C.

**Routage direct (média via Office 365) – appel RTC cheveux sur deux clients**

[![Flux d’appels de Microsoft teams Online figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Figure 24-routage direct (média via Office 365)-appel cheveux RTC sur deux clients*

Notez que :

- L’SBC doit avoir une adresse IP publique qui est routable à partir d’Office 365.

- Le signalement de l’SBC à Office 365 et inversement utilise le flux 4 et/ou le flux 4.

- Le client n’est pas dans la boucle de signalisation et de média une fois que l’appel est hairpinned de RTC à PSTN.

- Les éléments multimédias de l’instance SBC A au sein de l’instance du réseau du client X à l’instance SBC B doivent être relayés via le serveur multimédia Office 365 et ne peuvent pas utiliser le mode de contournement.

## <a name="teams-with-express-route-optimization"></a>Équipes avec l’optimisation de l’itinéraire rapide

[![Flux d’appels de Microsoft teams Online figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Figure 25 : équipe avec l’optimisation de l’itinéraire rapide*

Dans le cas où l’itinéraire rapide est justifié et déployé, les flux d’équipes peuvent être redirigés du flux 4 au flux 1 et du flux 4 'vers le flux 1 '. Toutefois, l’application teams dispose d’une dépendance matérielle par rapport à d’autres flux d’Office 365 sur Internet à l’aide des flux 4 et 4. ces flux ne doivent donc pas être bloqués.

Notez que le trafic Edge hybride Skype entreprise est routé vers Internet et ne peut pas être utilisé pour communiquer avec des utilisateurs externes et fédérer avec d’autres clients.

Pour éviter les flux asymétriques, le rétablissement du routage doit être dans les deux directions. En d’autres termes, une adresse au sein du réseau du client est routable à partir d’Internet ou d’un itinéraire rapide, en fonction de l’optimisation, mais pas par les deux.


**Connexion du réseau du client aux utilisateurs externes (médias relayés par teams Relay Relay) :**

[![Flux d’appels de Microsoft teams Online figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*Figure 26-réseau client pour les utilisateurs externes (média relayée par Team Relay Relay)*

**Étapes de niveau supérieur :**

1. Un utilisateur de teams au sein du réseau du client résout le nom de domaine d’URL (DNS) à l’aide de flow2.
1. L’utilisateur de teams au sein du réseau du client alloue un port de relais multimédia sur le relais de transport teams via le flux 1.
1. Les utilisateurs d’teams au sein du réseau du client envoient une invitation à une glace en utilisant le flux 1 au bureau 365.
1. Office 365 envoie une notification à un utilisateur d’équipe externe à l’aide du flux 3.
1. Les utilisateurs externes d’équipes allouent un port de relais multimédia sur teams Relay Relay à l’aide de Flow 3.
1. Les utilisateurs externes d’équipes envoient une réponse avec des candidats de glace en utilisant Flow 3, qui est renvoyé à l’utilisateur de teams A à l’aide de Flow 1.
1. Les utilisateurs teams A et équipe B appellent des tests de connectivité ICE et sélectionne les flux 1 et 3 qui sont relayés par teams Relay Relay dans Office 365.
1. Les utilisateurs de teams envoient de la télémétrie à Office 365 à l’aide des flux 1 et 3.

> [!NOTE]
> Le flux 4 doit être activé pour prendre en charge les dépendances de l’application teams sur d’autres micro-services qui autorisent le flux 4.
