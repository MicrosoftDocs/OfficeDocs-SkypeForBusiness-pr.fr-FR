---
title: Guide de sécurité pour Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Conseils et apprentissages en matière de sécurité pour ITAdmins lors de l’installation, de la configuration et de la maintenance de Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0ee261f145f256e82db55aa869623505ff3c3dc3
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43034069"
---
# <a name="security-and-microsoft-teams"></a>Sécurité et Microsoft Teams

Microsoft Teams, dans le cadre du service Microsoft 365 (M365), respecte toutes les pratiques recommandées en matière de sécurité et des procédures telles que la sécurité de niveau de service, notamment les contrôles client de défense approfondie au sein du service, le renforcement de la sécurité et le fonctionnement optimal. techniques. Pour plus d’informations, voir le [centre de gestion de la confidentialité de Microsoft](https://microsoft.com/trustcenter).

## <a name="trustworthy-by-design"></a>Confiance en conception

Teams a été conçu et développé conformément au cycle de développement Microsoft Trustworthy Computing Security Development Lifecycle (SDL), décrit [Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/sdl/default.aspx). Pour créer un système de communications unifiées plus sûr, la première étape a consisté à concevoir des modèles de menace, puis à tester chaque nouvelle fonctionnalité durant sa conception. Plusieurs améliorations liées à la sécurité ont été intégrées au processus et aux pratiques de codage. Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final. Bien sûr, il est impossible de prévoir toutes les menaces de sécurités inconnues lors de la conception. Aucun système ne peut garantir une sécurité totale. Toutefois, dans la mesure où le développement du produit utilise des règles de conception prenant en compte la sécurité dès le départ, les technologies de sécurité standard font partie intégrante de l’architecture de Teams.

## <a name="trustworthy-by-default"></a>Confiance par défaut

Par défaut, les communications réseau dans les équipes sont chiffrées. Avec l’exigence que tous les serveurs utilisent des certificats et avec l'utilisation d'OAUTH, de TLS, du protocole SRTP (Secure Real-Time Transport Protocol) et d'autres techniques de chiffrement standard, notamment le chiffrement AES (Advanced Encryption Standard) 256 bits, toutes les données de Skype Entreprise Online sont protégées sur le réseau.

## <a name="how-teams-handles-common-security-threats"></a>Comment les équipes gèrent les menaces de sécurité courantes

Cette section identifie les menaces les plus courantes à la sécurité du service SfBO et la manière dont Microsoft fait face à chaque menace.

### <a name="compromised-key-attack"></a>Attaques par clé compromise

Teams utilise les fonctionnalités de l’infrastructure à clé publique dans le système d’exploitation Windows Server pour protéger les données de clé utilisées pour le chiffrement des connexions TLS (Transport Layer Security). Les clés utilisées pour le chiffrement multimédia sont échangées via des connexions TLS.

### <a name="network-denial-of-service-attack"></a>Attaque par déni de service réseau

L’attaque par déni de service se produit lorsque l’agresseur empêche l’utilisation normale du réseau et la fonctionnement par des utilisateurs valides. À l’aide d’une attaque par déni de service, l’agresseur peut :

- envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;
- envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;
- masquer les signes d’attaque ;
- empêcher les utilisateurs d’accéder aux ressources réseau.
Teams atténue ces attaques en exécutant la protection réseau Azure DDOS et en limitant la bande passante des demandes des clients provenant des mêmes nœuds finaux, sous-réseaux et entités fédérées.

### <a name="eavesdropping"></a>Protection contre l’écoute

Une attaque par écoute peut se produire lorsqu’une personne malveillante parvient à accéder au chemin d’accès des données d’un réseau et qu’elle peut ainsi surveiller et lire le trafic. Cette attaque est également appelée reniflage (« sniffing ») ou surveillance (« snooping »). Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données.

Teams utilise MTLS (mutual TLS) pour les communications serveur au sein d’O365 et TLS des clients au service, rendant cette attaque très difficile à réaliser, voire impossible, dans le délai pendant lequel une conversation donnée pourrait être attaquée. Le protocole TLS authentifie toutes les parties et chiffre le trafic. Ceci n’empêche pas les attaques par écoute, mais l’intrus ne peut pas lire le trafic à moins que le chiffrement ne soit rompu. Ajouter des sections/lignes OAuth.

Le protocole TURN est utilisé pour les médias en temps réel. Le protocole TURN n’impose pas de chiffrement du trafic et les informations qu’il envoie sont protégées par l’intégrité des messages. Bien qu’il soit ouvert à l’écoute électronique, les informations qu’il envoie (autrement dit les adresses IP et le port) peuvent être extraites directement en regardant simplement les adresses source et de destination des paquets. Le service Teams s’assure que les données sont valides par la vérification de l’intégrité du message en utilisant la clé dérivée de quelques éléments comprenant un mot de passe TURN, qui n'est jamais envoyé en clair. SRTP est utilisé pour le trafic multimédia et est également chiffré.

### <a name="identity-spoofing-ip-address-spoofing"></a>Usurpation d’identité (usurpation d’adresse IP)

On parle d’usurpation d’identité lorsqu’une personne malveillante parvient à déterminer et à utiliser l’adresse IP d’un réseau, d’un ordinateur ou d’un composant réseau, sans y avoir été autorisée. Une attaque réussie permet à l’agresseur de fonctionner comme si l’utilisateur malveillant était l’entité identifiée normalement par l’adresse IP.

TLS authentifie toutes les parties et chiffre tout le trafic. L’utilisation de TLS empêche les agresseurs d’effectuer l’usurpation d’adresse IP sur une connexion spécifique (par exemple, des connexions Mutual TLS). Un attaquant pourrait tout de même usurper l’adresse du serveur DNS. Comme l’authentification est assurée à l’aide de certificats dans Teams, un intrus n’aurait pas de certificat valide nécessaire pour usurper l’identité d’une des parties dans la communication.

### <a name="man-in-the-middle-attack"></a>Attaque de l’intercepteur

Une attaque de l’intercepteur se produit lorsqu’une personne malveillante redirige les communications entre deux utilisateurs via son propre ordinateur, à l’insu des deux participants. L’intrus peut surveiller et lire le trafic avant de l’acheminer vers le destinataire concerné. Chacun des utilisateurs envoie et reçoit du trafic vers/de l’intrus, alors qu’il pense communiquer avec l’utilisateur concerné uniquement. Cela peut se produire si une personne malveillante modifie les services de domaine Active Directory pour ajouter son serveur en tant que serveur approuvé, ou si elle modifie DNS (Domain Name System) pour faire en sorte que les clients se connectent au serveur via l’ordinateur de l’intrus à l’origine de l’attaque.

Une attaque de l’intercepteur peut également se produire avec le trafic multimédia entre deux clients, sauf que dans Teams, les flux audio, vidéo et de partage d’applications point à point sont chiffrés avec SRTP à l’aide de clés cryptographiques négociées entre les homologues utilisant le protocole SIP (Session Initiation Protocol) sur TLS.

### <a name="rtp-replay-attack"></a>Attaque par relecture RTP

Une attaque par relecture se produit lorsqu’une transmission multimédia valide entre deux correspondants est interceptée, puis retransmise à des fins malveillantes. Teams utilise SRTP conjointement avec un protocole de signalisation sécurisé qui protège les transmissions des attaques par relecture en permettant au destinataire de conserver un index des paquets RTP déjà reçus et de comparer chaque nouveau paquet à ceux figurant déjà dans l’index.

### <a name="spim"></a>SPIM

Il s’agit de messages instantanés commerciaux non sollicités ou de demandes d’abonnement de présence, tels que le courrier indésirable, mais sous forme de message instantané. Bien qu’elle ne soit pas isolée du réseau, elle est agaçante au moins, peut réduire la disponibilité des ressources et la production, et peut entraîner la compromission du réseau. Par exemple, les utilisateurs se font du spimming mutuellement en envoyant des demandes. Les utilisateurs peuvent se bloquer pour empêcher cela, mais avec la fédération, si une attaque de spim coordonné est établie, cela peut être difficile à surmonter, sauf si vous désactivez la fédération pour le partenaire.

### <a name="viruses-and-worms"></a>Virus et vers

Un virus est une unité de code ayant pour finalité la reproduction d’unités de code similaires supplémentaires. Pour fonctionner, un virus a besoin d’un hôte, par exemple un fichier, un e-mail ou un programme. Comme un virus, un ver est une unité de code codée pour reproduire des unités de code similaires, mais contrairement à un virus, il n’a pas besoin d’hôte. Les virus et les vers apparaissent principalement lors des transferts de fichiers entre clients ou lorsque des URL sont envoyées par d’autres utilisateurs. Si vous avez un virus sur votre ordinateur, il peut, par exemple, utiliser votre identité et envoyer des messages instantanés en votre nom. Les meilleures pratiques standard de sécurité client, telles que la recherche périodique de virus, peuvent atténuer ce problème.

## <a name="security-framework-for-teams"></a>Infrastructure de sécurité pour Teams

Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent une infrastructure de sécurité pour Microsoft Teams.

Les principaux éléments sont les suivants :

- Azure Active Directory (AAD) fournit un référentiel unique de back-end de confiance pour les comptes d’utilisateurs. Les informations de profil utilisateur sont stockées dans AAD via les actions de Microsoft Graph.
  - Il est possible que plusieurs jetons soient émis, ce que vous pouvez voir si vous suivez le trafic de votre réseau. Cela inclut les jetons Skype que vous pouvez voir dans les traces tout en regardant la conversation et le trafic audio.
- TLS (Transport Layer Security) et Mutual TLS (MTLS) qui chiffre le trafic de messages instantanés et active l’authentification de point de terminaison. Les flux de données audio, vidéo et de partage d’applications point à point sont chiffrés et l’intégrité est vérifiée à l’aide du protocole SRTP (Secure Real-Time Transport Protocol). Vous pouvez également voir le trafic OAuth dans votre trace, en particulier autour des autorisations de négociation, lorsque vous basculez entre les onglets dans Teams, par exemple, pour passer d’une publication à une autre. Pour consulter un exemple de flux OAuth pour les onglets, [consultez ce document](https://docs.microsoft.com/microsoftteams/platform/tabs/how-to/authentication/auth-flow-tab).
- Les équipes utilisent des protocoles standard pour l’authentification des utilisateurs, autant que possible.

Les sections suivantes décrivent certaines de ces technologies de base.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure Active Directory sert de service d’annuaire pour Office 365 (O365). Il stocke toutes les affectations de stratégie et les informations de l’annuaire utilisateur.

#### <a name="crl-distribution-points"></a>Points de distribution

Le trafic Office 365 a lieu sur les canaux chiffrés TLS/HTTPs, ce qui signifie que les certificats sont utilisés pour le chiffrement de tout le trafic. Teams exige que tous les certificats de serveur contiennent un ou plusieurs points de distribution de liste de révocation de certificats (CRL). Les points de distribution CRL (CDP) sont des emplacements à partir desquels les CRL peuvent être téléchargés en vue de vérifier que le certificat n’a pas été révoqué depuis son émission et qu’il est toujours dans sa période de validité. Un point de distribution CRL est indiqué dans les propriétés du certificat sous forme d’URL et il s’agit d’une adresse HTTP sécurisée. Le service Teams vérifie la liste de révocation de certificats avec chaque authentification de certificat.

#### <a name="enhanced-key-usage"></a>Utilisation avancée de la clé :

Toutes les composantes du service Teams exigent que tous les certificats de serveur prennent en charge l’utilisation améliorée de la clé (EKU) aux fins de l’authentification du serveur. La configuration du champ EKU pour l’authentification du serveur signifie que le certificat est valide pour l’authentification des serveurs. Cette EKU est essentielle pour MTLS.

### <a name="tls-and-mtls-for-teams"></a>TLS et MTLS pour les équipes

Les protocoles TLS et MTLS fournissent des communications chiffrées et une authentification de point de terminaison sur Internet. Teams utilise ces deux protocoles pour créer le réseau de serveurs approuvés et pour garantir que toutes les communications sur ce réseau sont chiffrées. Toutes les communications entre les serveurs interviennent sur MTLS. Toutes les communications SIP restantes ou héritées du client au serveur ont lieu via TLS.

TLS permet aux utilisateurs, via leur logiciel client, d’authentifier les serveurs Teams auxquels ils se connectent. Sur une connexion TLS, le client demande un certificat valide au serveur. Pour être valide, le certificat doit avoir été émis par une autorité de certification qui est également approuvée par le client et le nom DNS du serveur doit correspondre au nom DNS dans le certificat. Si le certificat est valide, le client utilise la clé publique du certificat pour chiffrer les clés de chiffrement symétriques à utiliser pour la communication, de sorte que seul le propriétaire d’origine du certificat peut utiliser sa clé privée pour déchiffrer le contenu de la communication. La connexion résultante est approuvée et à partir de ce point n’est pas contestée par d’autres serveurs ou clients approuvés.

Les connexions de serveur à serveur reposent sur le protocole TLS (MTLS) mutuel pour l’authentification mutuelle. Sur une connexion MTLS, le serveur à l’origine d’un message et le serveur le recevant échangent des certificats à partir d’une autorité de certification mutuellement approuvée. Les certificats prouvent l’identité d’un serveur à un autre. Cette procédure est suivie dans le service Teams.

Les protocoles TLS et MTLS évitent les attaques par écoute clandestine et les attaques d’homme intercepteurs. Dans le cas d’une attaque d’intercepteur, l’attaquant réachemine les communications entre deux entités de réseau via l’ordinateur de l’attaquant sans que l’autre partie n’en ait connaissance. TLS et la spécification Teams des serveurs approuvés limitent partiellement le risque d’une attaque d’intercepteur sur la couche de l’application en utilisant un chiffrement de bout en bout coordonné à l’aide du chiffrement de clé publique entre les deux points de terminaison ; un attaquant devrait disposer d’un certificat valide et approuvé avec la clé privée correspondante et émise au nom du service sur lequel le client communique pour déchiffrer la communication.

### <a name="encryption-for-teams"></a>Chiffrement pour Teams

Teams utilise TLS et MTLS pour encrypter les messages instantanés. Tout le trafic de serveur à serveur requiert MTLS, que le trafic soit confiné au réseau interne ou qu’il traverse le périmètre réseau interne.

Ce tableau résume les protocoles utilisés par les équipes.

***Chiffrement du trafic***

|||
|:-----|:-----|
|**Type de trafic**|**Encrypté par**|
|Serveur à serveur|MTLS|
|Client-vers-serveur (par exemple. Messagerie instantanée et présence|TLS|
|Flux multimédias (par exemple. partage de fichiers audio et vidéo|TLS|
|Partage de fichiers audio et vidéo|SRTP/TLS|
|Signalisation|TLS|
|||

#### <a name="media-encryption"></a>Chiffrement multimédia

Le trafic multimédia est chiffré à l'aide du protocole SRTP (Secure Real-time Transport Protocol), un profil du protocole RTP (Real-Time Transport Protocol) qui offre confidentialité, authentification et protection contre les attaques sur le trafic RTP. SRTP utilise une clé de session produite à l’aide d’un générateur de nombres aléatoires sécurisé et échangée en utilisant le canal TLS de signalisation.

Teams utilise un jeton basé sur les informations d’identification pour sécuriser l’accès aux relais multimédias à la main. Les relais de contenu échangent le jeton via un canal sécurisé TLS.

#### <a name="fips"></a>FIPS

Teams utilise des algorithmes qui sont conformes aux normes FIPS (Federal Information Processing Standard) pour les échanges de clés de chiffrement.

### <a name="user-and-client-authentication"></a>Authentification utilisateur et client

Un utilisateur approuvé est un utilisateur dont les informations d’identification ont été authentifiées par das dans Office 365/Microsoft 365.

L’authentification consiste à fournir des informations d’identification d’utilisateur à un serveur approuvé ou service. Teams utilise les protocoles d’authentification suivants, en fonction du statut et de l’emplacement de l’utilisateur.

- **L’authentification moderne (AM)** est l’implémentation Microsoft d’OAUTH 2.0 pour la communication client à serveur. Il active les fonctionnalités de sécurité telles que l’authentification multi-facteur Office 365 et l’accès conditionnel Office 365. Pour utiliser AM, les clients online et client doivent être activés pour AM. Les clients Teams sur PC et mobiles, ainsi que sur le client Web, [prennent tous en charge AM](https://docs.microsoft.com/microsoftteams/sign-in-teams).

> [!NOTE]
> Si vous devez vous conformer aux méthodes d’authentification et d’autorisation Azure AD, cet article explique comment les sections « concepts de base de l’authentification dans Azure AD » sont utiles.

L’authentification des équipes est effectuée via AAD et OAuth. Le processus d’authentification peut être simplifié pour :

- Accès utilisateur > émission de jetons > demande ultérieure utilisez un jeton émis.

Les demandes de client à serveur sont authentifiées par l’intermédiaire de Das et utilisant OAuth. Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés et passent par le même processus que les utilisateurs natifs. Toutefois, des restrictions complémentaires peuvent être mises en place par les administrateurs.

Pour l’authentification multimédias, les protocoles de glace et de tournage utilisent également la stimulation Digest, comme décrit dans l’IETF TURN RFC.

### <a name="windows-powershell-and-team-management-tools"></a>Windows PowerShell et outils de gestion Teams

Dans Teams, les administrateurs informatiques peuvent gérer leur service via le portail d’administration O365 ou à l’aide de client Remote PowerShell (TRPS). Les administrateurs de client utilisent l’authentification moderne pour s’authentifier auprès de TRPS.

### <a name="configuring-access-to-teams-at-your-internet-boundary"></a>Configuration de l'accès à Teams à votre frontière Internet

Pour que Teams fonctionne correctement (pour permettre aux utilisateurs de participer à des réunions, etc.), les clients doivent configurer leur accès à Internet de telle sorte que le trafic UDP et TCP sortant vers les services dans le Cloud Teams soit autorisé. Pour Informations supplémentaires, voir [URL Office 365 et plages d’adresses IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 et TCP 443

Les ports UDP 3478-3481 et TCP 443 sont utilisés par les clients pour demander un service pour les visuels audio. Un client utilise ces deux ports pour allouer les ports UDP et TCP respectivement pour activer ces flux multimédias. Les flux de médias sur ces ports sont protégés par une clé qui est échangée via un canal de signalisation sécurisé TLS.

### <a name="udptcp-5000059999-optional"></a>UDP/TCP 50,000–59,999 (facultatif)

Les ports de la gamme haute ne sont pas utilisés par le relais de transport. Étant donné qu’il s’agit de ports facultatifs, ils ne sont pas répertoriés dans les URL et plages d’adresses IP Office 365. Cela signifie également que Teams fonctionne si ces ports sont bloqués, en raison du trafic utilisant les plages de ports 3478-3481 (relais de transport). Elles sont utilisées pour le transit multimédia, mais même si celles-ci sont débloquées, la réduction du délai est minime (quelques millisecondes). Dans la plupart des cas, les problèmes de qualité des médias ne sont pas affectés par le déblocage et l’utilisation de ces ports. Toutes les investigations de ces problèmes doivent se concentrer ailleurs.

### <a name="federation-safeguards-for-teams"></a>Protection de la Fédération pour Teams

La Fédération offre à votre organisation la possibilité de communiquer avec d’autres organisations afin de partager la messagerie instantanée et la présence. La Fédération de Teams est activée par défaut. En revanche, les administrateurs de client peuvent contrôler cet environnement via le portail d’administration O365.

## <a name="addressing-threats-to-teams-meetings"></a>Répondre aux réunions Teams

Deux options s’offrent à vous pour contrôler les personnes qui ont atteint les réunions Teams et qui auront accès aux informations que vous présentez.

1. Vous pouvez contrôler les personnes qui joignent vos réunions via les paramètres de la **lobby**.</p>

|Qui peut contourner  |Paramètre de contournement  | Jointures directes| Arrive en salle d’attente|
|---------|---------|---------|---------|
|EveryoneInCompany (tout le monde sauf les utilisateurs externes)     |  Oui    |  Dans-client, invités, PSTN Dial-in      | Utilisateurs fédérés, utilisateurs anonymes        |
|EveryoneInCompany (tout le monde sauf les utilisateurs externes)    |  Non     |  Au sein des clients et des utilisateurs invités       |   Utilisateurs fédérés, utilisateurs anonymes, utilisateurs distants PSTN      |
|EveryoneInCompany (tout le monde sauf les utilisateurs externes) et les utilisateurs fédérés     |  Oui    | Utilisateurs d’appels entrants client, invité, fédéré et PSTN        | Utilisateurs anonymes        |
|EveryoneInCompany (tout le monde sauf les utilisateurs externes) et les utilisateurs fédérés     |  Non     |   Utilisateurs du client, invité et fédéré      |  Utilisateurs distants anonymes et PSTN      |
|Tout le monde     |  Oui    | Les utilisateurs des appels entrants client, invité, fédéré, anonyme et PSTN        | S/O        |

2. La deuxième méthode consiste à passer par **les réunions structurées** (où les Présentateurs peuvent faire quelque chose à faire, et les participants ont une expérience contrôlée). Une fois que vous avez rejoint une réunion structurée, les présentateurs contrôlent ce que les participants peuvent faire pendant la réunion. </p>

|Actions  |Présentateurs  |Participants  |
|---------|---------|---------|
|Parlez et partagez leur vidéo     |   O      |   v      |
|Participer à une conversation de réunion     |   O    |    v     |
|Modifier les paramètres dans les options de réunion     |   v      |  N       |
|Désactiver le son des participants| v | N |
|Supprimer les autres participants      |  v       |   N      |
|Partager le contenu     |     v    |     N    |
|Admettre d’autres participants de la salle d’attente|  v       |   N      |
|Rendre les présentateurs ou participants d’autres participants     |   v      | N        |
|Démarrer ou arrêter l’enregistrement     |     v    |    N     |
|Prise de contrôle lorsqu’un autre participant partage un PowerPoint     |  v         | N        |

Teams offre aux utilisateurs d’entreprise la possibilité de créer et de participer à des réunions en temps réel. Les utilisateurs d’entreprise peuvent également inviter des utilisateurs externes ne possédant pas de compte AAD/Office 365 à participer à ces réunions. Les utilisateurs qui sont employés par des partenaires externes avec une identité sécurisée et authentifiée peuvent également participer à des réunions et, s’ils sont promus, ils peuvent agir en tant que présentateurs. Les utilisateurs anonymes ne peuvent pas créer ou participer à une réunion en tant que présentateur, mais ils peuvent être promus au présentateur une fois qu’ils ont rejoint la réunion.

Pour que les utilisateurs anonymes puissent participer aux réunions Teams, le paramètre réunions des participants dans le centre d’administration teams doit être activé.  

> [!NOTE]
> Le terme *utilisateurs anonymes* indique que les utilisateurs qui ne sont pas authentifiés auprès du locataire des organisations. Dans ce contexte, tous les utilisateurs externes sont considérés comme anonymes. Les utilisateurs authentifiés incluent les utilisateurs clients et les utilisateurs invités du locataire.

Permettre aux utilisateurs externes de participer à des réunions Teams peut être très utile, mais implique des risques en matière de sécurité. Pour résoudre ces problèmes, Teams exploite les garanties supplémentaires suivantes :

- Les rôles de participants déterminent les privilèges de contrôle de réunion.
- Les types de participants vous permettent de limiter l’accès à des réunions spécifiques.
- La planification de réunions est réservée aux utilisateurs qui ont un compte AAD et une licence Teams.
- Les utilisateurs anonymes, qui ne sont pas authentifiés, ont besoin de participer à une conférence rendez-vous en utilisant un numéro de conférence. Si le paramètre « toujours autoriser les appelants à contourner le lobby » est *activé*, il doit également patienter jusqu’à ce qu’un présentateur ou utilisateur authentifié se connecte à la réunion.

Il est également possible pour un organisateur de configurer les paramètres de façon à ce que les appelants entrants soient la première personne participant à une réunion. Ce paramètre est configuré dans les paramètres de conférence audio pour les utilisateurs et s’applique à toutes les réunions planifiées par l’utilisateur.

> [!NOTE]
> Pour plus d’informations sur l’accès invité et externe dans Teams, voir cet [article ](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations). Il couvre les fonctionnalités que les utilisateurs invités ou externes peuvent espérer voir et utiliser lorsqu’ils se connectent à Teams.

### <a name="participant-roles"></a>Rôles des participants

Les participants à la réunion se répartissent en trois groupes, chacun ayant ses propres privilèges et restrictions :

- ** Organisateur **L’utilisateur qui crée une réunion, qu’elle soit impromptue ou programmée. Un organisateur doit être un utilisateur de client authentifié et contrôler tous les aspects d’un utilisateur final d’une réunion.
- **Présentateur** Un utilisateur autorisé à présenter des informations lors d’une réunion, quel que soit le média pris en charge. Un organisateur de réunion est par définition également un présentateur et détermine qui d’autre peut être un présentateur. Il peut effectuer cette détermination lorsqu’une réunion est planifiée ou pendant son déroulement.
- **Participant** Un utilisateur qui a été invité à participer à une réunion, mais qui n’est pas autorisé à agir en tant que présentateur.

Un présentateur peut également promouvoir un participant au rôle de présentateur pendant la réunion.

### <a name="participant-types"></a>Types de participants

Les participants à la réunion sont également classés par localisation et informations d’identification. Vous pouvez utiliser ces deux caractéristiques pour préciser les utilisateurs pouvant avoir accès à des réunions spécifiques. Les utilisateurs peuvent être répartis dans les catégories suivantes :

1. **Les utilisateurs qui appartiennent au client** ces utilisateurs ont une information d’identification dans Azure Active Directory pour le client.
    a. *Membres de mon organisation* : ces utilisateurs ont une information d’identification dans Azure Active Directory pour le client. *Membres de mon organisation* inclut les comptes invités invités.
    b. *Utilisateurs distants* : ces utilisateurs se rejoignent en dehors du réseau de l’entreprise. Ce sont, par exemple, des employés qui travaillent à domicile ou en déplacement, ou d’autres personnes, comme les employés de fournisseurs de confiance, qui ont reçu des informations d’identification d’entreprise pour leurs conditions d’utilisation du service. Les utilisateurs distants peuvent créer et participer à des réunions et se comporter comme présentateurs.
.
2. **Les utilisateurs qui n’appartiennent pas au client** ces utilisateurs n’ont pas d’informations d’identification dans Azure AD pour le client.
    a. *Les utilisateurs fédérés* les utilisateurs fédérés ont des informations d’identification valides avec les partenaires fédérés et sont donc traités comme authentifiés par Teams, mais restent anonymes pour le client organisateur de la réunion. Les utilisateurs fédérés peuvent participer à des réunions et être promus aux présentateurs une fois qu’ils ont rejoint la réunion, mais ils ne peuvent pas créer de réunions dans les entreprises avec lesquelles ils sont fédérés.
    b. *Les utilisateurs anonymes*-les utilisateurs anonymes n’ont pas d’identité Active Directory et ne sont pas fédérés avec le client.

De nombreuses réunions impliquent des utilisateurs externes. Ces mêmes clients veulent également être rassurés en ce qui concerne l’identité des utilisateurs externes avant de permettre à ces utilisateurs de participer à une réunion. La section suivante décrit comment les équipes limitent l’accès aux types d’utilisateurs qui ont été explicitement autorisés et nécessite que tous les types d’utilisateur présentent les* informations d’identification* lors de la saisie d’une réunion.

### <a name="participant-admittance"></a>Admission des participant

Dans Teams, les utilisateurs anonymes peuvent être transférés vers une zone d’attente appelée salle d’attente. Les présentateurs peuvent ensuite *admettre *ces utilisateurs à la réunion ou les *rejeter*. Lorsque ces utilisateurs sont transférés vers la salle d’attente, le présentateur et les participants reçoivent une notification et les utilisateurs anonymes doivent patienter jusqu’à ce qu’ils soient acceptés ou rejetés, ou que leur connexion arrive à expiration.

Par défaut, les participants qui accèdent à partir du RTC accèdent directement à la réunion une fois qu’un utilisateur authentifié rejoint la réunion, mais cette option peut être modifiée pour forcer les participants à appeler la salle d’attente.

Les organisateurs de la réunion contrôlent si les participants peuvent rejoindre une réunion sans attendre dans la salle d’attente. Chaque réunion peut être configurée pour autoriser l’accès à l’aide de l’une des méthodes suivantes :

Les valeurs par défaut sont les suivantes :

- *Les membres de mon organisation* – toutes les personnes extérieures à l’organisation attendent dans la salle d’attente jusqu’à leur admission.
- *Les membres de mon organisation et les organisations approuvées*-utilisateurs authentifiés et les utilisateurs externes de Teams et des domaines Skype Entreprise figurant dans la liste verte d’accès externe peuvent contourner la salle d’attente. Tous les autres utilisateurs attendent dans la salle d’attente jusqu’à leur admission.
- *Tout le monde* – tous les participants à la réunion ignorent la salle d’attente une fois qu’un utilisateur authentifié a rejoint la réunion.

### <a name="presenter-capabilities"></a>Fonctions du présentateur

Les organisateurs de la réunion contrôlent si les participants peuvent présenter lors d’une réunion. Chaque réunion peut être configurée pour limiter les présentateurs à l’une des entités suivantes :

- *Les membres de mon organisation*-tous les utilisateurs clients, y compris les invités, peuvent présenter
- *Les membres de mon organisation et les organisations de confiance* – toutes dans les utilisateurs des clients, y compris les invités, peuvent présenter des utilisateurs et externes d’équipes et de domaines Skype Entreprise dans la liste verte d’accès externe.  
- *Tout le monde* – tous les participants à la réunion sont des présentateurs.

### <a name="modify-while-meeting-is-running"></a>Modifier pendant l’exécution d’une réunion

Il est possible de modifier les options de réunion pendant la réunion. La modification, lors de son enregistrement, a un impact sur la réunion en cours en quelques secondes. Il affecte également les occurrences ultérieures de la réunion.

## <a name="related-topics"></a>Sujets associés

[Centre de gestion de la confidentialité Microsoft](https://microsoft.com/trustcenter)

[Gérer les paramètres de réunion dans Microsoft Teams](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams)
