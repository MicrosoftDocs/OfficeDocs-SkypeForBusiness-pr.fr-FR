---
title: Carrousel Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
description: Décrit comment les équipes utilise Office 365 flux dans diverses topologies.
ms.openlocfilehash: ecdeb6dc4e1e7219dc8c01c710877437661e0ceb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232090"
---
# <a name="microsoft-teams-call-flows"></a>Carrousel Microsoft Teams

> [!Tip]
> Regarder la session suivante pour savoir comment les équipes s’appuie sur votre réseau et la planification de la connectivité réseau optimale : [Planification des équipes réseau](https://aka.ms/teams-networking)

## <a name="overview"></a>Vue d’ensemble
Cet article explique comment utilise équipes Office 365 appeler le flux dans diverses topologies. En outre, il décrit uniques flux équipes qui sont utilisés pour les communications multimédias d’égal à égal. Le document décrit ces flux, leur objectif et leur origine et terminaison sur le réseau. À des fins de cet article, supposons que les éléments suivants :

- X flux est utilisé par le client Office 365 locale pour communiquer avec le service Office 365 dans le nuage. Il provient du réseau client, et il met fin à un point de terminaison dans Office 365.

- Flux Y est utilisée par le client Office 365 locale pour communiquer avec un service sur Office 365 a une dépendance sur Internet. Il provient du réseau client, et il met fin à un point de terminaison sur Internet.

L’article contient les sections suivantes :

- **Arrière-plan** - fournit des informations générales, telles que les réseaux qui peuvent traverser les flux d’Office 365, type de trafic, les conseils de connectivité de réseau du client pour les points de terminaison de service Office 365, de l’interopérabilité avec des composants tiers, et principes qui sont utilisés par les équipes pour sélectionner les flux multimédias.

- **Appeler le flux dans diverses topologies** - illustre l’utilisation de flux d’appels dans diverses topologies. Pour chaque topologie, la section énumère tous les flux pris en charge et illustre l’utilisation de ces flux via plusieurs cas d’utilisation. Pour chaque cas d’utilisation, il décrit la séquence et la sélection de flux par le biais d’un diagramme de flux. 

- **Les équipes et optimisation d’itinéraire Express** - décrit l’utilisation de ces flux lors de l’itinéraire Express est déployée pour l’optimisation, illustrée par le biais d’une topologie simple.

## <a name="background"></a>Arrière-plan
### <a name="network-segments"></a>Segments de réseau
**Réseau client**: il s’agit le segment de réseau que vous pouvez contrôler et gérer. Cela inclut toutes les connexions client au sein de bureaux client, si avec ou sans fil, entre bâtiments, aux centres de données locale et vos connexions fournisseurs Internet, itinéraire Express ou tout autre peering privé. 

En règle générale, un réseau client a plusieurs périmètres réseau avec pare-feu et/ou serveurs proxy, auquel appliquer les stratégies de sécurité de votre organisation et autorisent uniquement certain le trafic réseau que vous avez installé et configuré. Car vous gérez ce réseau, vous disposez d’un contrôle direct sur les performances du réseau et il est fortement recommandé que vous effectuez évaluations réseau pour valider les performances à la fois dans les sites de votre réseau et de votre réseau pour le réseau d’Office 365. 

**Internet**: il s’agit du segment de réseau qui fait partie de votre réseau global qui sera utilisé par les utilisateurs qui sont connectent à Office 365 à partir d’en dehors du réseau client. Il est également utilisé par certains types de trafic entre le réseau du client à Office 365. 

**Réseau privé visité/invité**: il s’agit du segment de réseau à l’extérieur de votre réseau du client, mais pas dans l’Internet public, qui leurs invités et/ou de vos utilisateurs peuvent visiter. Par exemple, réseau privé ou un réseau privé d’entreprise, qui ne déploie pas les équipes, où leurs clients interagissent avec les équipes services et/ou de vos utilisateurs peuvent résider.

>**Remarque**: la connectivité à Office 365 est également applicable à ces réseaux.

**Office 365**: il s’agit du segment de réseau qui prend en charge des services Office 365. Il est distribué dans le monde entier avec bords à proximité du réseau client dans la plupart des emplacements. Fonctions mentionnées dans ce document incluent relais de Transport, serveur de conférence et processeur média. 

**Itinéraire Express (facultatif)**: il s’agit du segment de réseau qui fait partie de votre réseau global qui offre une connexion privée dédiée au réseau Office 365.

### <a name="types-of-traffic"></a>Types de trafic

**Médias en temps réel**: données encapsulées dans le protocole RTP (Real-Time Transport Protocol) qui prend en charge les paramètres audio, vidéo et partage des charges de travail de l’écran. En règle générale, le trafic multimédia est hautement latence sensible, vous pouvez ce trafic à prendre le chemin le plus direct possible et à utiliser UDP et TCP comme protocole de couche de transport, qui est le meilleur transport multimédias interactifs en temps réel à partir d’un point de vue de la qualité . (Remarque : en dernier ressort, media utilisent le protocole TCP/IP et également être intégré dans le protocole HTTP, mais il n’est pas recommandé en raison des implications en matière de mauvaise qualité.) Flux RTP est sécurisée par le biais du protocole SRTP, dans lequel seule la charge utile est chiffrée.

**Signalisation**: la liaison de communication entre le client et serveur ou d’autres clients qui sont utilisés pour contrôler les activités (par exemple, lorsqu’un appel est lancé) et remettre des messages instantanés. Trafic de signalisation plus utilise les interfaces REST basée sur HTTPS, bien que dans certains scénarios (par exemple, la connexion entre Office 365 et une Session Border Controller) qu’il utilise le protocole SIP. Il est important de comprendre que ce trafic est beaucoup moins sensible à la latence, mais peut entraîner des pannes de service ou de délais d’attente des appels si la latence entre les points de terminaison dépasse quelques secondes. 

### <a name="connectivity-to-office-365"></a>Connectivité à Office 365

Les équipes requièrent une [connectivité à Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10). Les équipes URL du point de terminaison et IP de plages d’adresses sont répertoriés dans [Office 365 URL et plages d’adresses IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). (Remarque : ouvrez connectivité aux ports TCP 80 et 443 et aux ports UDP 3478 via 3481 est nécessaire.) En outre, les équipes a une dépendance sur Skype pour Business Online, qui doit également être connecté à Internet.

Connectivité des équipes médias flux est implémentée par le biais des procédures standard IETF ICE (Interactive Connectivity Establishment).

### <a name="interoperability-restrictions"></a>Restrictions d’interopérabilité
**Relais multimédia tiers**: flux de médias A équipes (autrement dit, un des points de terminaison multimédia est équipes) peut traverser les équipes ou Skype pour relais multimédia d’origine de Business. Interopérabilité avec relais multimédia tiers n’est pas pris en charge. (Remarque : une tierce partie SBC sur la limite de PSTN doit se terminer le flux RTP/RTCP, sécurisé via le protocole SRTP et pas les relais vers le tronçon suivant.)

**Serveurs proxy SIP troisième partie**: équipes A signalisation SIP de boîte de dialogue avec une tierce partie SBC et/ou de la passerelle peut parcourir les équipes ou Skype pour les proxys SIP natifs d’entreprise. Interopérabilité avec proxy SIP tiers n’est pas pris en charge.

**B2BUA tiers (autrement dit, SBC)**: flux de médias A équipes à partir de/vers le réseau RTC se termine par une tierce partie SBC. Toutefois, l’interopérabilité avec des tiers SBC au sein du réseau d’équipes (c'est-à-dire, une tierce partie SBC gère la deux équipes/Skype pour systèmes d’extrémité Business) n’est pas pris en charge.

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Technologies qui ne sont pas recommandées avec Microsoft Teams

**Réseau VPN**: il n’est pas recommandé pour le trafic multimédia (autrement dit, le flux 2 »). Le client VPN doit utiliser fractionné VPN et le routage du trafic multimédia comme n’importe quel utilisateur externe non VPN, tel que spécifié dans https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/.

>**Remarque**: bien que le titre Lync, il est également applicable aux équipes.

**Agressives paquets**: n’importe quel type de snippers de paquets, l’inspection des paquets ou périphériques de mise en forme de paquets ne sont pas recommandées et peut dégrader considérablement la qualité. 

### <a name="principles"></a>Principes
Il existe quatre principes généraux qui vous aident à comprennent les flux d’appels pour Teams Microsoft :
 
1.  Une conférence Microsoft Teams est hébergée par Office 365 dans la même zone où le premier participant rejoint. (Remarque : si sera exceptions à cette règle dans des topologies, puis elles seront décrites dans ce document et illustrés par un flux d’appels appropriée.)

2.  Les équipes un point de terminaison multimédia dans Office 365 est utilisé en fonction des besoins de traitement de support et non basaient sur le type d’appel. (Par exemple, un appel point à point peut utiliser un point de terminaison multimédia dans le nuage pour processus multimédia pour transcription et/ou d’enregistrement, pendant une conférence avec deux participants ne pouvez pas utiliser un point de terminaison multimédia dans le nuage.) Toutefois, la plupart des conférences utilise un point de terminaison multimédia pour le mixage et de routage, allouée où se trouve la conférence. Le trafic multimédia envoyé à partir d’un client au point de terminaison multimédia peuvent être acheminés directement ou utiliser un relais de Transport dans Office 365, si nécessaire, en raison de restrictions de pare-feu du réseau client. 

3.  Pour le trafic multimédia pour les appels d’égal à égal prennent l’itinéraire plus direct qui n’est disponible, en supposant que l’appel n’impose un point de terminaison multimédia dans le nuage (voir #2 ci-dessus). L’itinéraire par défaut est directe à l’homologue à distance (client), mais si cet itinéraire n’est pas disponible, un ou plusieurs relais Transport sera relayer le trafic. Il est recommandé que le trafic multimédia ne doit pas Portrait serveurs tels qu’agressives de paquets, les serveurs VPN et ainsi de suite, car cela aura une incidence sur la qualité des médias.

4.  Toujours le trafic de signalisation atteint le serveur à l’utilisateur le plus proche. 

Pour en savoir plus sur les détails sur le chemin d’accès de média est choisi, voir https://www.youtube.com/watch?v=1tmHMIlAQdo.

## <a name="call-flows-in-various-topologies"></a>Flux d’appels dans diverses topologies
### <a name="teams-topology"></a>Topologie d’équipes
Cette topologie est utilisée par les clients qui exploitent les services des équipes du nuage sans tout déploiement sur site, tel que Skype pour Business Server ou le routage d’un système téléphonique directe. En outre, l’interface vers Office 365 s’effectue par le biais d’Internet sans itinéraire Azure Express. 

[![Les équipes Microsoft appel flux Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Figure 1 : topologie d’équipes*

Notez que :

- La direction des flèches dans le diagramme ci-dessus reflète la direction d’initiation de la communication qui affecte la connectivité au périmètre d’entreprise. Dans le cas de UDP pour le média, le premier paquet peut flux dans le sens inverse, mais ces paquets peuvent être bloquées jusqu'à ce que le flux des paquets dans le sens inverse.
- Équipes est déployé en côte à côte Skype pour Business Online, par conséquent, les clients sont affichés sous forme de « Utilisateur équipes/SFB ».

Vous trouverez plus d’informations sur les topologies suivantes facultatifs ultérieurement dans cet article :

- Skype pour les entreprises locale déploiement est décrit dans **la topologie hybride équipes**.
- Téléphone système routage Direct (connectivité PSTN) est décrit dans les **équipes avec la topologie de routage Direct**.
- Itinéraire Express est décrit dans **les équipes et optimisation d’itinéraire Express**.

**Descriptions de flux**:
- **Flux 2** – représente un flux initié par un utilisateur sur le réseau du client à Internet dans le cadre de l’expérience des équipes de l’utilisateur. DNS et les médias d’égal à égal sont des exemples de ces flux.
- **Flux 2'** – représente un flux initié par un utilisateur d’équipes mobile à distance, avec VPN vers le réseau du client. 
- **Flux de 3** – représente un flux initié par un utilisateur mobile équipes de points de terminaison Office 365/Teams. 
- **Flux 4** – représente un flux initié par un utilisateur sur le réseau du client pour les systèmes d’extrémité Office 365/Teams.
- **Flux de 5** – représente un flux multimédias d’égal à égal entre un utilisateur d’équipes et une autre équipes ou Skype pour l’utilisateur d’entreprise au sein du réseau client.
- **Flux de 6** – représente un flux multimédias d’égal à égal entre un utilisateur équipes mobile à distance et une autre à distance des équipes mobiles ou Skype pour utilisateur professionnel via Internet.

#### <a name="use-case-one-to-one"></a>Cas d’utilisation : conversation
Appels univoque utilisent un modèle commun dans lequel l’appelant obtiendra un ensemble de candidats consistant IP adresses/ports--notamment local, relais et candidats réfléchis (adresse IP publique du client en tant que vue par le relais). L’appelant envoie ces candidats à l’appelé ; la partie appelée également Obtient un ensemble de candidats similaire et les envoie à l’appelant. Vérification de la connectivité STUN messages sont utilisés pour rechercher l’appelant/appelé multimédia utiliser des chemins d’accès et le chemin d’accès de travail meilleures est sélectionné. Multimédia (autrement dit, des paquets RTP/RTCP sécurisés via le protocole SRTP) est envoyées à l’aide de la paire de candidat sélectionné. Le relais de Transport est déployé dans le cadre d’Office 365.

Si l’adresse IP locale adresse/port candidats ou les candidats réflexives disposent d’une connectivité, puis le chemin d’accès direct entre les clients (ou via un NAT) est sélectionné pour le média. Si les clients se trouvent sur le réseau du client, le chemin d’accès direct doit être sélectionné. Cela nécessite une connectivité UDP directe dans le réseau du client. Si les clients sont les deux utilisateurs nomades dans le nuage, puis selon le NAT/Pare-feu, media peut utiliser une connexion directe.

Si un client est interne sur le réseau du client et un client est externe (par exemple, un utilisateur mobile dans le nuage), il est peu probable que la connectivité directe entre les candidats locales ou réflexives fonctionne. Dans ce cas, une option consiste à utiliser une des candidats relais de Transport à partir d’un client (par exemple, le client interne obtenu un candidat relais à partir du relais de Transport dans Office 365, le client externe doit être en mesure d’envoyer des paquets STUN/RTP/RTCP pour le relais de transport). Une autre option est que le client interne envoie le candidat de relais obtenu par le client mobile dans le nuage. Notez que, bien qu’est vivement recommandée de connectivité UDP pour le média, TCP est pris en charge.

**Étapes principales**:
1. L’utilisateur A résout URL nom de domaine (DNS) via Flux2 des équipes
2. Les équipes utilisateur A alloue un support port relais équipes Transport relais via le flux 4
3. Des équipes de l’utilisateur A envoie « inviter » avec les candidats ICE via flux 4 vers Office 365
4. Office 365 envoie une notification à l’utilisateur d’équipes B par le biais du flux de 4
5. Les équipes utilisateur B alloue un support port relais équipes Transport relais via le flux 4
6. Équipes utilisateur B renvoie « réponse » avec les candidats ICE via flux 4, qui est renvoyé à l’utilisateur équipes A via le flux de 4
7. Équipes utilisateur A et équipes utilisateur B appeler des tests de connectivité ICE et le chemin d’accès de supports disponibles meilleures est sélectionnée (voir les diagrammes ci-dessous pour différents cas d’utilisation)
8. Les utilisateurs des équipes envoient télémétrie vers Office 365 par flux 4

**Au sein du réseau client :**

[![Les équipes Microsoft appel flux Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Figure 2 : au sein du réseau de client*
 
À l’étape 7, les flux multimédias d’égal-à-5 est sélectionnée.
 
Multimédia est bidirectionnelle. La direction du flux 5 indique qu’un côté établit la communication entre un point de vue de connectivité compatible avec tous les flux dans ce document. Dans ce cas, peu importe la direction dans laquelle est utilisée, car les deux points de terminaison sont dans le réseau du client.

**Réseau du client pour les utilisateurs externes (media relayés par les équipes Transport relais) :**

[![Les équipes Microsoft appel flux Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*La figure 3 - réseau du client pour les utilisateurs externes (media relayés par les équipes Transport relais)*
 
À l’étape 7, les flux de réseau du client vers Office 365, 4 et les flux de 3, les utilisateurs distants équipes mobile vers Office 365, sont sélectionnés. Ces flux est relayés par relais de Transport équipes au sein d’Office 365.

Multimédia est bidirectionnel, où la direction indique côté qui initie la communication à partir d’un point de vue de connectivité. Dans ce cas, ces flux est utilisés pour la signalisation et des médias, via différents protocoles de transport et d’adresses.

**Réseau du client pour les utilisateurs externes (media direct) :**

[![Les équipes Microsoft appel flux Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Figure 4 : réseau du client pour les utilisateurs externes (media direct)*
 
À l’étape 7, les flux de réseau du client vers Internet (homologue du client), 2, est sélectionné.
- Media direct avec les utilisateurs mobiles distants (c'est-à-dire, pas relayé par Office 365) est facultative. En d’autres termes, le client peut bloquer ce chemin d’accès pour appliquer un chemin d’accès des médias par le biais de relais de Transport dans Office 365.

- Multimédia est bidirectionnelle. La direction du flux 2 pour les utilisateurs mobiles distants indique qu’un côté établit la communication à partir d’un point de vue de connectivité. 

**Utilisateur VPN à un utilisateur interne (media relayés par les équipes Transport relais)**

[![Les équipes Microsoft appel flux Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*La figure 5 - utilisateur VPN à un utilisateur interne (media relayés par les équipes Transport relais)*
 
Signalisation entre le réseau VPN vers le réseau du client est via le flux 2 ». La signalisation entre le réseau du client et Office 365 est via flux 4. Toutefois, média contourne le réseau VPN et est routé via le flux 3 et 4 via le relais multimédia équipes dans Office 365.

**Utilisateur VPN à un utilisateur interne (media direct)**

[![Les équipes Microsoft appel flux Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*La figure 6 - utilisateur VPN à un utilisateur interne (media direct)*

Signalisation entre le réseau VPN vers le réseau du client est via le flux 2 ». La signalisation entre le réseau du client et Office 365 est via flux 4. Toutefois, média contourne le réseau VPN et est routé via le flux 2 à partir du réseau du client à Internet.

Multimédia est bidirectionnelle. La direction du flux de 2 à l’utilisateur distant mobile indique qu’un côté établit la communication à partir d’un point de vue de connectivité.

**Utilisateur VPN pour les utilisateurs externes (media direct)**

[![Microsoft Teams appeler flux Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*La figure 7 - utilisateur VPN pour les utilisateurs externes (media direct)*

Signalisation entre l’utilisateur VPN vers le réseau du client est via flux 2' et flux 4 vers Office 365. Toutefois, média contourne VPN et est routé via le flux de 6.

Multimédia est bidirectionnelle. La direction du flux de 6 à l’utilisateur distant mobile indique qu’un côté établit la communication à partir d’un point de vue de connectivité.

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>Exemple d’utilisation : Équipes PSTN via Office 365 jonction
Office 365 offre un système téléphonique qui permet de passer et recevoir des appels à partir du Public téléphone réseau commuté (RTC). Si la liaison RTC est connecté via le système téléphonique appelant Plan, il n’y a aucune configuration spéciale de connectivité pour ce cas d’utilisation. (Si vous souhaitez connecter votre propre liaison de RTC local à Office 365, vous pouvez utiliser le routage Direct système de téléphone.)

[![Les équipes Microsoft appel flux Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*La figure 8 - équipes PSTN via Office 365 jonction*

#### <a name="use-case-teams-meeting"></a>Cas d’utilisation : Réunion des équipes

L’audio/vidéo/partage d’écran (VBSS) le serveur de conférence fait partie d’Office 365. Il possède une adresse IP publique qui doit être accessible à partir du réseau client et doit être accessible à partir d’un client dans le nuage nomades. Chaque client/point de terminaison doit être en mesure de se connecter au serveur de conférence.

Les clients internes obtiendra candidats relais local et réfléchis de la même manière décrite pour les appels un à un. Les clients envoie au serveur de conférence dans une invitation à ces candidats. Le serveur de conférence n’utilise pas un relais car il dispose d’une adresse IP accessible publiquement, afin qu’il répond avec son candidate d’adresse IP locale. Le serveur de conférence et le client vérifier la connectivité de la manière décrite pour les appels de conversation. 

Notez que :

- Clients équipes ne peuvent pas participer à Skype pour les réunions d’entreprise et Skype pour les clients d’entreprise ne peuvent pas participer à des réunions d’équipes.

- Un utilisateur PSTN éventuellement « Dials cm » ou « Composé OUT », selon l’organisateur de la réunion appel PSTN et/ou la mise en service de conférence. 

- Un utilisateur invité ou un client peut participer depuis un réseau privé invité, qui est protégé par le biais de PARE-FEU/NAT avec des règles strictes.

[![Les équipes Microsoft appel flux Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Figure 9 : des équipes de réunion*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Exemple d’utilisation : Fédération avec Skype pour les entreprises en local

**Media relayés par les équipes Transport relais dans Office 365**

[![Appel équipes Microsoft est disposé à la Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*La figure 10 - Media relayés par les équipes Transport relais dans Office 365*

Notez que :

- La fédération est, par définition, une communication entre deux clients. Dans ce cas, le client A, qui utilise des équipes, se fédère avec le client B, qui utilise Skype pour les entreprises dans les locaux. Si le client B utilise également Office 365, puis le Skype pour client Business auriez utilisé flux 3 de se connecter à Office 365.

- Signalisation et média à partir de la fédérés Skype pour client d’entreprise à locale Skype pour Business Server est hors de portée du présent document. Toutefois, il est illustré ici pour plus de clarté.

- Signalisation entre équipes et Skype pour les entreprises est ponts sont créée par une passerelle dans Office 365.

- Dans ce cas multimédia est relayé par relais de Transport d’équipes dans Office 365 pour le réseau du client et Skype à distance pour le client Business via le flux de 4.

**Media relayés par Skype pour le relais multimédia Business dans client fédéré**

[![Appel en ligne de Microsoft équipes s’enchaîne de la Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*La figure 11 - Media relayés par Skype pour le relais multimédia Business dans client fédéré*

Notez que :

- Signalisation et média à partir de la fédérés Skype pour client d’entreprise pour un Skype locale pour Business Server est hors de portée du présent document. Toutefois, il est illustré ici pour plus de clarté.

- Signalisation entre équipes et Skype pour les entreprises est ponts sont créée par une passerelle dans Office 365.

- Dans ce cas multimédia est relayé par Skype pour le relais multimédia Business local vers le réseau du client par le biais du flux de 2. (Notez que le trafic utilisateur équipes vers le relais multimédia à distance dans le réseau du client fédéré est initialement bloqué par le serveur relais multimédia jusqu’au flux de trafic dans le sens inverse. Toutefois, le flux bidirectionnel s’ouvrent connectivité dans les deux sens.)

**Direct (d’égal à égal)**

[![Appel équipes Microsoft est disposé à la Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*La figure 12 - Direct (d’égal à égal)*

### <a name="teams-hybrid-topology"></a>Topologie d’équipes hybride
Cette topologie inclut des équipes avec un Skype pour le déploiement local de Business.

[![Appel équipes Microsoft est disposé à la Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Figure 13 : topologie hybride d’équipes*
 
- La direction des flèches dans le diagramme ci-dessus reflète la direction d’initiation de la communication qui affecte la connectivité au périmètre d’entreprise. Dans le cas de UDP pour le média, le premier paquet peut flux dans le sens inverse, mais ces paquets peuvent être bloquées jusqu'à ce que le flux des paquets dans le sens inverse.

- Équipes est déployé en côte à côte Skype pour Business Online, par conséquent, les clients sont affichés sous forme de « Utilisateur équipes/SFB ».

Flux supplémentaires (par-dessus topologie équipes) :
- **5 a flux** – représente un flux multimédias d’égal à égal entre un utilisateur équipes au sein du réseau de client et un Skype pour le relais multimédia Business locale en périphérie du réseau de client.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Cas d’utilisation : Équipes Skype pour les entreprises un à un
**Hybride dans le réseau du client**

[![Les équipes Microsoft appel flux Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Figure 14 : hybride au sein du réseau de client*
 
Signalisation entre équipes et Skype pour les entreprises est ponts sont créée par une passerelle dans Office 365. Toutefois, multimédia est routé directement pair à pair dans le client réseau via un flux de 5.

**Réseau de client hybride avec Skype externe pour les utilisateurs des entreprises – relayés par Office 365**

[![Les équipes Microsoft appel flux Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*La figure 15 - réseau du client hybride avec Skype externe pour l’utilisateur d’entreprise - relayés par Office 365*

Notez que :

- Signalisation et média à partir de la Skype pour client d’entreprise pour un Skype locale pour Business Server est hors de portée du présent document. Toutefois, il est illustré ici pour plus de clarté.

- Signalisation entre équipes et Skype pour les entreprises est ponts sont créée par une passerelle dans Office 365.

- Multimédia est relayé par le biais de relais de Transport d’équipes dans Office 365 pour le réseau du client par le biais de flux de 4.

**Réseau de client hybride avec Skype externe pour les utilisateurs des entreprises – relayés par Edge locaux**

[![Les équipes Microsoft appel flux Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*La figure 16 - réseau du client hybride avec Skype externe pour l’utilisateur d’entreprise - relayés par Edge locaux*
 
Notez que :

- Signalisation et média de Skype pour client d’entreprise pour un Skype locale pour Business Server est hors de portée du présent document. Toutefois, il est illustré ici pour plus de clarté.

- Signalisation est ponts sont créée par une passerelle dans Office 365.

- Multimédia est relayé par Skype pour le relais multimédia Business dans Skype pour le serveur Edge Business locale à l’utilisateur des équipes au sein du réseau client via 5 a de flux multimédias.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Équipes et la topologie de routage d’un système téléphonique Direct
Cette topologie inclut des équipes avec le routage d’un système téléphonique Direct. 

Routage direct vous permet d’utiliser un fournisseur de services tiers Public réseau de téléphonique commuté (RTC) en jumelage sur site pris en charge appartenant à un client contrôleur de Session en périphérie (SBC) à un périphérique matériel Office 365, puis connectez la jonction de téléphonie pour ce périphérique. 

Pour prendre en charge ce scénario, le client doit déployer un SBC certifié pour le routage Direct à partir d’un des partenaires certifiés Microsoft. Le contrôleur SBC doit être configuré comme indiqué par le fournisseur et être routable à partir d’Office 365 pour diriger le trafic UDP. Le support peut flux directement à partir des équipes et/ou le Skype pour client d’entreprise pour le contrôleur SBC (sans passer par la passerelle équipes) ou parcourir la passerelle équipes. La connectivité avec le contrôleur SBC, lors de la jonction est configurée pour ignorer la passerelle équipes, est basée sur ICE, où SBC prend en charge ICE Lite prend en charge l’équipes/Skype pour le point de terminaison multimédia Business ICE complet. 

[![Appel en ligne de Microsoft équipes s’enchaîne de la Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

* Figure 17 - équipes avec la topologie de routage d’un système téléphonique Direct

Notez que :

- La direction des flèches dans le diagramme ci-dessus reflète la direction d’initiation de la communication qui affecte la connectivité au périmètre d’entreprise. Dans le cas de UDP pour le média, le premier paquet peut flux dans le sens inverse, mais ces paquets peuvent être bloquées jusqu'à ce que le flux des paquets dans le sens inverse.

- Équipes est déployé en côte à côte Skype pour Business Online, par conséquent, les clients sont affichés sous forme de « Utilisateur équipes/SFB ».

Flux supplémentaires (par-dessus topologie online équipes) :
- **Flux 4'** - représente un flux à partir d’Office 365 pour le réseau du client, utilisé pour établir une connexion entre le serveur de médias équipes dans le nuage avec le contrôleur SBC localement.
- **5 b flux** – représente un flux de médias entre l’utilisateur équipes au sein du réseau de client avec la SBC routage Direct en mode de contournement.
- **Flux 5C** – représente un flux de médias entre le SBC routage Direct vers une autre SBC routage Direct dans un mode de contournement appel PSTN « hairpin ».

**Utilisateur interne avec le routage Direct (media relayés par les équipes Transport relais dans Office 365)**

[![Les équipes Microsoft appel flux Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*La figure 18 - utilisateur interne avec le routage Direct (media relayés par les équipes Transport relais dans Office 365)*

Notez que :
 
- Le contrôleur SBC doit avoir une adresse IP publique est routable à partir d’Office 365.

- Signalisation et média à partir du contrôleur SBC à Office 365 et vice versa utiliser flux 4 et/ou flux 4'.

- Signalisation et média à partir du client au sein du réseau client vers Office 365 utilisent les flux 4.


**Utilisateurs distants avec le routage Direct (media est routé via un serveur multimédia (MP) dans Office 365)**

[![Les équipes Microsoft appel flux Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Figure 19 : les utilisateurs distants avec le routage Direct (media est routé via un serveur multimédia (MP) dans Office 365)*
 
Notez que :

- Le contrôleur SBC doit avoir une adresse IP publique est routable à partir d’Office 365.

- Signalisation et média à partir du contrôleur SBC à Office 365 et vice versa utiliser flux 4 et/ou flux 4'.

- Signalisation et média à partir du client sur Internet à Office 365 utilisent les flux 3.

**Utilisateur interne routage Direct (le contournement de média)**

[![Appel en ligne de Microsoft équipes s’enchaîne de la Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*La figure 20 - utilisateur interne routage Direct (le contournement de média)*
 
Notez que :

- Le contrôleur SBC doit avoir une adresse IP publique est routable à partir d’Office 365.

- Signalisation de SBC vers Office 365 et vice versa utiliser flux 4 et/ou flux 4'.

- Signalisation de client dans le réseau du client à Office 365 utiliser flux 4.

- Support client au sein du réseau client SBC au sein du réseau client utilisez 5 b de flux.

**Utilisateurs distants avec le routage Direct (le contournement de média relayé par les équipes Transport relais dans Office 365)**

[![Les équipes Microsoft appel flux Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*La figure 21 - des utilisateurs distants avec le routage Direct (le contournement de média relayé par les équipes Transport relais dans Office 365)*

Notez que :

- Le contrôleur SBC doit avoir une adresse IP publique est routable, depuis Internet et d’Office 365.

- Le contrôleur SBC vers Office 365 et vice versa de signalisation utilise flux 4 et/ou flux 4'.

- Signalisation à partir du client sur Internet à Office 365 utilise flux 3.

- Support à partir du client sur Internet pour le contrôleur SBC au sein du réseau client utilise flux 3 et 4, relayé par les équipes Transport relais dans Office 365. 

**Utilisateur distant routage Direct (direct du contournement de média)**

[![Les équipes Microsoft appel flux Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*La figure 22 - utilisateur distant routage Direct (direct du contournement de média)*
 
Notez que :

- Le contrôleur SBC doit avoir une adresse IP publique est routable, depuis Internet et d’Office 365.

- Le contrôleur SBC vers Office 365 et vice versa de signalisation utilise flux 4 et/ou flux 4'.

- Signalisation à partir du client sur Internet à Office 365 utilise flux 3.

- Support à partir du client sur Internet pour le contrôleur SBC au sein du réseau client utilise flux 2.

**Routage (le contournement de média) – PSTN hairpin appel direct (en raison de transférer/transfert d’appel)**

[![Les équipes Microsoft appel flux Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Appel de « hairpin » figure 23 - routage Direct (le contournement de média) - PSTN (en raison de transférer/transfert d’appel)*
 
Notez que :

- Le contrôleur SBC doit avoir une adresse IP publique est routable à partir d’Office 365.

- Le contrôleur SBC vers Office 365 et vice versa de signalisation utilise flux 4 et/ou flux 4'.

- Le client est en dehors de la signalisation et média boucle après que l’appel est hairpinned depuis PSTN à PSTN.

- Média d’instance SBC A dans le réseau du client à l’instance SBC B au sein du réseau client (où, A et B peuvent être la même instance) utilise les flux 5 C.

**Routage (media via Office 365) – PSTN hairpin appel direct entre deux clients**

[![Les équipes Microsoft appel flux Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Appel de « hairpin » figure 24 - routage Direct (media via Office 365) – PSTN dans deux clients*
 
Notez que :

- Le contrôleur SBC doit avoir une adresse IP publique est routable à partir d’Office 365.

- Le contrôleur SBC vers Office 365 et vice versa de signalisation utilise flux 4 et/ou flux 4'.

- Le client est en dehors de la signalisation et média boucle après que l’appel est hairpinned depuis PSTN à PSTN.

- Contournement de média à partir de l’instance SBC A au sein du réseau client X à instance SBC B doit être transmis via le serveur de support Office 365 et ne pouvez pas utiliser le mode.

## <a name="teams-with-express-route-optimization"></a>Équipes et optimisation d’itinéraire Express

[![Les équipes Microsoft appel flux Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*La figure 25 - équipes et optimisation d’itinéraire Express*
 
Dans le cas où l’itinéraire Express est justifiée et déployé, puis flux équipes pourraient être réacheminé à partir de flux 4 pour les flux de 1 et de flux de 4' enchaînement 1 ». Toutefois, équipes Application a une dépendance dure sur les autres flux Office 365 sur internet via un flux 4 et 4' ; Par conséquent, ces flux ne doit pas être bloquée. 

Notez que Skype pour hybride Business le trafic Edge est routé vers Internet et non pas au itinéraire Express pour communiquer avec des utilisateurs externes et fédérer avec d’autres clients. 

Pour empêcher le flux asymétriques, le réacheminement doit être dans les deux sens. En d’autres termes, une adresse dans le réseau du client est routable via Internet ou itinéraire Express, basé sur l’optimisation, mais pas à la fois.

Par exemple :

**Réseau du client pour les utilisateurs externes (media relayés par les équipes Transport relais) :**

[![Appel équipes Microsoft est disposé à la Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*La figure 26 - réseau du client pour les utilisateurs externes (media relayés par les équipes Transport relais)*
 
**Étapes principales :**
1. Utilisateur équipes au sein du réseau client résout le nom de domaine (DNS) URL via Flux2
2. Utilisateur d’équipes au sein du réseau client alloue un support port relais équipes Transport relais via le flux 1
3. Utilisateur d’équipes au sein du réseau client envoie « inviter » avec les candidats ICE via le flux de 1 à Office 365
4. OFFICE 365 envoie une notification pour utilisateurs équipes externes via le flux 3
5. Utilisateur externe équipes alloue un support port relais équipes Transport relais via le flux 3
6. Utilisateur externe équipes envoie « réponse » avec les candidats ICE via le flux 3, qui est renvoyé à l’utilisateur d’équipes A via le flux de 1
7. Les équipes utilisateur B équipes utilisateur A appeler les tests de connectivité ICE et sélectionne flux 1 et 3, qui sont transmis par les équipes Transport relais dans Office 365
8. Les utilisateurs des équipes envoient télémétrie vers Office 365 via le flux de 1 et 3

>**Remarque**: flux 4 doit être activé pour prendre en charge les dépendances d’application équipes sur d’autres services-micro que mandats flux 4.
