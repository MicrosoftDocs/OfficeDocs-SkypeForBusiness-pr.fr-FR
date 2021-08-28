---
title: Aperçu du guide de sécurité pour Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 10/15/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Conseils et enseignements en matière de sécurité pour les administrateurs informatiques lors de l’installation, de la configuration et de la maintenance de Microsoft Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7aaf996d32b67a85ec5fd7146dd29cc0f998e743
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592198"
---
# <a name="security-and-microsoft-teams"></a>Sécurité et Microsoft Teams

> [!IMPORTANT]
> Le modèle de service Teams est susceptible d’être modifié pour améliorer les expériences des clients. Par exemple, il est possible que les heures d’expiration des jetons d’actualisation ou d’accès par défaut soient sujettes à des modifications pour améliorer les performances et la résilience de l’authentification pour les personnes qui utilisent Teams. Ces modifications sont apportées dans le but de maintenir la sécurité de Teams et la confiance en conception.

Microsoft Teams, dans le cadre des services Microsoft 365 et Office 365, respecte toutes les pratiques recommandées en matière de sécurité et des procédures telles que la sécurité de niveau de service, notamment les contrôles client de défense approfondie au sein du service, le renforcement de la sécurité et le fonctionnement optimal. techniques. Pour plus d’informations, voir le [centre de gestion de la confidentialité de Microsoft](https://microsoft.com/trustcenter).

## <a name="trustworthy-by-design"></a>Confiance en conception

Teams a été conçu et développé conformément au cycle de développement Microsoft Trustworthy Computing Security Development Lifecycle (SDL), décrit [Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/sdl/default.aspx). Pour créer un système de communications unifiées plus sûr, la première étape a consisté à concevoir des modèles de menace, puis à tester chaque nouvelle fonctionnalité durant sa conception. Plusieurs améliorations liées à la sécurité ont été intégrées au processus et aux pratiques de codage. Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final. Bien sûr, il est impossible de prévoir toutes les menaces de sécurités inconnues lors de la conception. Aucun système ne peut garantir une sécurité totale. Toutefois, dans la mesure où le développement du produit utilise des règles de conception prenant en compte la sécurité dès le départ, les technologies de sécurité standard font partie intégrante de l’architecture de Teams.

## <a name="trustworthy-by-default"></a>Confiance par défaut

Les communications réseau dans Teams sont cryptées par défaut. En exigeant que tous les serveurs utilisent des certificats et en utilisant OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP), toutes les données de Teams sont protégées sur le réseau.

## <a name="how-teams-handles-common-security-threats"></a>Comment Teams gère les menaces de sécurité courantes

Cette section identifie les menaces les plus courantes à la sécurité du service SfBO et la manière dont Microsoft fait face à chaque menace.

### <a name="compromised-key-attack"></a>Attaques par clé compromise

Teams utilise les fonctionnalités PKI du système d'exploitation Windows Server pour protéger les données des clés utilisées pour le cryptage des connexions TLS ( Sécurité de la couche de transport ). Les clés utilisées pour le cryptage des médias sont échangées via des connexions TLS.

### <a name="network-denial-of-service-attack"></a>Attaque par déni de service réseau

L’attaque par déni de service se produit lorsque l’agresseur empêche l’utilisation normale du réseau et la fonctionnement par des utilisateurs valides. À l’aide d’une attaque par déni de service, l’agresseur peut :

- envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;
- envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;
- masquer les signes d’attaque ;
- Empêcher les utilisateurs d'accéder aux ressources du réseau. Teams se protège contre ces attaques en exécutant la protection réseau Azure DDOS et en limitant les demandes des clients provenant des mêmes points d'extrémité, sous-réseaux et entités fédérées.

### <a name="eavesdropping"></a>Protection contre l’écoute

Une attaque par écoute peut se produire lorsqu’une personne malveillante parvient à accéder au chemin d’accès des données d’un réseau et qu’elle peut ainsi surveiller et lire le trafic. Cette attaque est également appelée reniflage (« sniffing ») ou surveillance (« snooping »). Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données.

Teams utilise MTLS (mutual TLS) pour les communications serveur au sein de Microsoft 365 et Office 365 et utiles également TLS des clients au service, rendant cette attaque très difficile à réaliser, voire impossible, dans le délai pendant lequel une conversation donnée pourrait être attaquée. TLS authentifie toutes les parties et chiffre tout le trafic. Ceci n’empêche pas les attaques par écoute, mais l’intrus ne peut pas lire le trafic à moins que le chiffrement ne soit rompu.

Le protocole TURN est utilisé pour les médias en temps réel. Le protocole TURN n'exige pas que le trafic soit crypté et les informations qu'il envoie sont protégées par l'intégrité du message. Bien qu'il soit ouvert aux écoutes, les informations qu'il envoie (c'est-à-dire les adresses IP et le port) peuvent être extraites directement en regardant simplement les adresses source et destination des paquets. Le service Teams s'assure de la validité des données en vérifiant l'intégrité du message à l'aide de la clé dérivée de quelques éléments, dont un mot de passe TURN, qui n'est jamais envoyé en clair. SRTP est utilisé pour le trafic média et est également crypté.

### <a name="identity-spoofing-ip-address-spoofing"></a>Usurpation d'identité (usurpation d'adresse IP)

L'usurpation d'identité se produit lorsque l'attaquant détermine et utilise l'adresse IP d'un réseau, d'un ordinateur ou d'un composant du réseau sans y être autorisé. Une attaque réussie permet à l'attaquant de fonctionner comme s'il était l'entité normalement identifiée par l'adresse IP.

TLS authentifie toutes les parties et crypte tout le trafic. L'utilisation de TLS empêche un attaquant d'effectuer une usurpation d'adresse IP sur une connexion spécifique (par exemple, les connexions TLS mutuelles). Un attaquant peut toujours usurper l'adresse du serveur DNS. Cependant, comme l'authentification dans Teams est effectuée à l'aide de certificats, un attaquant ne disposerait pas du certificat valide nécessaire pour usurper l'adresse d'une des parties de la communication.

### <a name="man-in-the-middle-attack"></a>Attaque de l'homme du milieu

Une attaque de type homme du milieu se produit lorsqu'un attaquant réachemine la communication entre deux utilisateurs par son propre ordinateur, à l'insu des deux utilisateurs en question. L'attaquant peut surveiller et lire le trafic avant de l'envoyer au destinataire prévu. Chaque utilisateur de la communication envoie sans le savoir du trafic à l'attaquant et en reçoit de ce dernier, tout en pensant qu'il ne communique qu'avec l'utilisateur prévu. Cela peut se produire si un attaquant peut modifier les services de domaine Active Directory pour ajouter son serveur comme serveur de confiance ou modifier le système de noms de domaine (DNS) pour que les clients se connectent via l'attaquant avant d'atteindre le serveur.

Les attaques d’homme-intermédiaire sur le trafic multimédia entre deux points de terminaison qui participent dans l’audio, la vidéo et le partage d’applications dans Teams sont évitées en utilisant SRTP pour chiffrer le flux de données multimédia. Les clés cryptographiques sont négociées entre les deux points de terminaison sur un protocole de signalisation propriétaire (Team Calling Protocol) qui utilise TLS 1,2 et AES-256 (en mode GCM) canal UDP/TCP chiffré.

### <a name="rtp-replay-attack"></a>Attaque par relecture RTP

Une attaque par relecture se produit lorsqu'une transmission média valide entre deux parties est interceptée et retransmise à des fins malveillantes. Teams utilise SRTP en conjonction avec un protocole de signalisation sécurisé qui protège les transmissions contre les attaques par relecture en permettant au récepteur de maintenir un index des paquets RTP déjà reçus et de comparer chaque nouveau paquet avec ceux déjà répertoriés dans l'index.

### <a name="spim"></a>Spim

Le Spim est un message instantané commercial non sollicité ou une demande d'abonnement à une présence, comme le spam, mais sous forme de message instantané. Bien qu'il ne constitue pas en soi une compromission du réseau, il est pour le moins agaçant, peut réduire la disponibilité et la production des ressources et peut éventuellement conduire à une compromission du réseau. Un exemple de ce phénomène est celui des utilisateurs qui s'espionnent mutuellement en s'envoyant des requêtes. Les utilisateurs peuvent se bloquer les uns les autres pour éviter cela, mais avec la fédération, si une attaque spim coordonnée est établie, cela peut être difficile à surmonter à moins de désactiver la fédération pour le partenaire.

### <a name="viruses-and-worms"></a>Virus et vers

Un virus est une unité de code dont le but est de reproduire d'autres unités de code similaires. Pour fonctionner, un virus a besoin d'un hôte, tel qu'un fichier, un courriel ou un programme. Comme un virus, un ver est une unité de code qui est codée pour reproduire d'autres unités de code similaires, mais qui, contrairement à un virus, n'a pas besoin d'un hôte. Les virus et les vers apparaissent principalement lors des transferts de fichiers entre clients ou lorsque des URL sont envoyés par d'autres utilisateurs. Si un virus se trouve sur votre ordinateur, il peut, par exemple, utiliser votre identité et envoyer des messages instantanés en votre nom. Les meilleures pratiques standard en matière de sécurité des clients, telles que l'analyse périodique des virus, peuvent atténuer ce problème.

## <a name="security-framework-for-teams"></a>Infrastructure de sécurité pour Teams

Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent une infrastructure de sécurité pour Microsoft Teams.

Les principaux éléments sont les suivants :

- Azure Active Directory (Azure AD) fournit un unique référentiel back-end fiable pour les comptes d’utilisateurs. Les informations de profil utilisateur sont stockées dans Azure AD via les actions de Microsoft Graph.
  - Il est possible que plusieurs jetons soient émis, ce que vous pouvez voir si vous suivez le trafic de votre réseau. Cela inclut les jetons Skype que vous pouvez voir dans les traces tout en regardant la conversation et le trafic audio.
- TLS (Transport Layer Security) et Mutual TLS (MTLS) qui chiffre le trafic de messages instantanés et active l’authentification de point de terminaison. Les flux de données audio, vidéo et de partage d’applications point à point sont chiffrés et l’intégrité est vérifiée à l’aide du protocole SRTP (Secure Real-Time Transport Protocol). Vous pouvez également voir le trafic OAuth dans votre trace, en particulier autour des autorisations de négociation, lorsque vous basculez entre les onglets dans Teams, par exemple, pour passer d’une publication à une autre. Pour consulter un exemple de flux OAuth pour les onglets, [consultez ce document](/microsoftteams/platform/tabs/how-to/authentication/auth-flow-tab).
- Les équipes utilisent des protocoles standard pour l’authentification des utilisateurs, autant que possible.

Les sections suivantes décrivent certaines de ces technologies de base.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure Active Directory sert de service d’annuaire pour Microsoft 365 et Office 365. Il stocke toutes les affectations de stratégie et les informations de l’annuaire utilisateur.

#### <a name="crl-distribution-points"></a>Points de distribution

Le trafic Microsoft 365 et Office 365 s'effectue sur des canaux cryptés TLS/HTTPS, ce qui signifie que des certificats sont utilisés pour le cryptage de tout le trafic. Teams exige que tous les certificats de serveur contiennent un ou plusieurs points de distribution de listes de révocation de certificats (CRL). Les points de distribution CRL (CDP) sont des emplacements à partir desquels les CRL peuvent être téléchargées afin de vérifier que le certificat n'a pas été révoqué depuis son émission et que le certificat est toujours en cours de validité. Un point de distribution de CRL est noté dans les propriétés du certificat comme une URL et est sécurisé par HTTP. Le service Teams vérifie la CRL à chaque authentification de certificat.

#### <a name="enhanced-key-usage"></a>Utilisation améliorée des clés

Tous les composants du service Teams exigent que tous les certificats de serveur prennent en charge l'utilisation améliorée des clés (EKU) aux fins de l'authentification du serveur. La configuration du champ EKU pour l'authentification du serveur signifie que le certificat est valide pour l'authentification des serveurs. Cet EKU est essentiel pour MTLS.

### <a name="tls-and-mtls-for-teams"></a>TLS et MTLS pour Teams

Les protocoles TLS et MTLS assurent des communications cryptées et l'authentification des points d'extrémité sur Internet. Teams utilise ces deux protocoles pour créer le réseau de serveurs de confiance et pour s'assurer que toutes les communications sur ce réseau sont cryptées. Toutes les communications entre les serveurs se font par MTLS. Toutes les communications SIP restantes ou anciennes, du client au serveur, se font via TLS.

TLS permet aux utilisateurs, par le biais de leur logiciel client, d'authentifier les serveurs Teams auxquels ils se connectent. Lors d'une connexion TLS, le client demande un certificat valide au serveur. Pour être valide, le certificat doit avoir été émis par une autorité de certification (CA) à laquelle le client fait également confiance et le nom DNS du serveur doit correspondre au nom DNS du certificat. Si le certificat est valide, le client utilise la clé publique du certificat pour chiffrer les clés de chiffrement symétrique à utiliser pour la communication, de sorte que seul le propriétaire initial du certificat peut utiliser sa clé privée pour déchiffrer le contenu de la communication. La connexion qui en résulte est de confiance et, à partir de ce moment, elle n'est pas contestée par d'autres serveurs ou clients de confiance.

Les connexions de serveur à serveur reposent sur le protocole TLS (MTLS) mutuel pour l’authentification mutuelle. Sur une connexion MTLS, le serveur à l’origine d’un message et le serveur le recevant échangent des certificats à partir d’une autorité de certification mutuellement approuvée. Les certificats prouvent l’identité d’un serveur à un autre. Cette procédure est suivie dans le service Teams.

TLS et MTLS permettent d'éviter à la fois l'écoute clandestine et les attaques de type homme du milieu.Dans une attaque de type homme du milieu , l'attaquant redirige les communications entre deux entités du réseau via son ordinateur, à l'insu des deux parties.TLS et la spécification des serveurs de confiance de Teams atténuent le risque d'une attaque de type homme du milieu en partie sur la couche application en utilisant un cryptage coordonné à l'aide de la cryptographie à clé publique entre les deux points d'extrémité.Pour décrypter la communication, un attaquant devrait disposer d'un certificat valide et fiable, accompagné de la clé privée correspondante et émis au nom du service auquel le client s'adresse.

> [!NOTE]
> Les données Teams sont chiffrées pendant le transit et au repos dans les centres de données Microsoft. Microsoft utilise les technologies standard du secteur telles que TLS et SRTP pour chiffrer toutes les données en transit entre les appareils des utilisateurs et les centres de données Microsoft, ainsi qu’entre les centres de données Microsoft. Elles comprennent les messages, fichiers, réunions et d’autres contenus. Les données de l’entreprise sont également chiffrées au repos dans les centres de données de Microsoft, ce qui permet aux organisations de déchiffrer du contenu le cas échéant, dans le but de respecter leurs obligations en matière de sécurité et de conformité, telles que eDiscovery.

### <a name="encryption-for-teams"></a>Chiffrement pour Teams

Teams utilise TLS et MTLS pour chiffrer les messages instantanés. Tout le trafic de serveur à serveur nécessite MTLS, que le trafic soit confiné au réseau interne ou qu'il traverse le périmètre du réseau interne.

Ce tableau résume les protocoles utilisés par les équipes.

***Chiffrement du trafic***


|**Type de trafic**|**Encrypté par**|
|:-----|:-----|
|Serveur à serveur|MTLS|
|Client-vers-serveur (par exemple. Messagerie instantanée et présence|TLS|
|Flux multimédias (par exemple. partage de fichiers audio et vidéo|TLS|
|Partage de fichiers audio et vidéo|SRTP/TLS|
|Signalisation|TLS|
|||

#### <a name="media-encryption"></a>Chiffrement multimédia

Le trafic multimédia est chiffré à l'aide du protocole SRTP (Secure Real-time Transport Protocol), un profil du protocole RTP (Real-Time Transport Protocol) qui offre confidentialité, authentification et protection contre les attaques sur le trafic RTP. SRTP utilise une clé de session produite à l’aide d’un générateur de nombres aléatoires sécurisé et échangée en utilisant le canal TLS de signalisation. Le trafic multimédia du client au client est négocié via un signal de connexion du client au serveur, mais il est chiffré à l’aide de SRTP lors d’une relation directe du client au client.

Teams utilise un jeton basé sur les informations d’identification pour sécuriser l’accès aux relais multimédias à la main. Les relais de contenu échangent le jeton via un canal sécurisé TLS.

#### <a name="fips"></a>FIPS

Teams utilise des algorithmes qui sont conformes aux normes FIPS (Federal Information Processing Standard) pour les échanges de clés de chiffrement. Pour plus d’informations sur l’implémentation de la norme FIPS, consultez la [Publication 140-2 du Federal Information Processing Standard (FIPS)](/microsoft-365/compliance/offering-fips-140-2).

### <a name="user-and-client-authentication"></a>Authentification utilisateur et client

Un utilisateur approuvé est un utilisateur dont les informations d’identification ont été authentifiées par Azure AD dans Microsoft 365 et Office 365.

L'authentification consiste à fournir les informations d'identification de l'utilisateur à un serveur ou un service de confiance. Teams utilise les protocoles d'authentification suivants, en fonction du statut et de l'emplacement de l'utilisateur.

- **L’authentification moderne (AM)** est l’implémentation Microsoft d’OAUTH 2.0 pour la communication client à serveur. Il active les fonctionnalités de sécurité telles que l’authentification multi-facteur et accès conditionnel. Pour utiliser AM, les clients online et client doivent être activés pour AM. Les clients Teams sur PC et mobiles, ainsi que sur le client Web, [prennent tous en charge AM](./sign-in-teams.md).

> [!NOTE]
> Si vous devez vous conformer aux méthodes d’authentification et d’autorisation Azure AD, cet article explique comment les sections « concepts de base de l’authentification dans Azure AD » sont utiles.

L’authentification des équipes est effectuée via Azure AD et OAuth. Le processus d’authentification peut être simplifié pour :

- Accès utilisateur > émission de jetons > demande ultérieure utilisez un jeton émis.

Les demandes de client à serveur sont authentifiées par l’intermédiaire de Azure AD et utilisant OAuth. Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés et passent par le même processus que les utilisateurs natifs. Toutefois, des restrictions complémentaires peuvent être mises en place par les administrateurs.

Pour l’authentification multimédias, les protocoles de glace et de tournage utilisent également la stimulation Digest, comme décrit dans l’IETF TURN RFC.

### <a name="windows-powershell-and-team-management-tools"></a>Windows PowerShell et outils de gestion Teams

Dans Teams, les administrateurs informatiques peuvent gérer leur service via le centre d'administration Microsoft 365 ou en utilisant Tenant Remote PowerShell (TRPS). Les administrateurs Tenant utilisent Modern Authentication pour s'authentifier auprès de TRPS.

### <a name="configuring-access-to-teams-at-your-internet-boundary"></a>Configuration de l'accès à Teams à votre frontière Internet

Pour que Teams fonctionne correctement (pour permettre aux utilisateurs de participer à des réunions, etc.), les clients doivent configurer leur accès à Internet de telle sorte que le trafic UDP et TCP sortant vers les services dans le Cloud Teams soit autorisé. Pour Informations supplémentaires, voir [URL Office 365 et plages d’adresses IP](/office365/enterprise/urls-and-ip-address-ranges).

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 et TCP 443

Les ports UDP 3478-3481 et TCP 443 sont utilisés par les clients pour demander un service pour les visuels audio. Un client utilise ces deux ports pour allouer les ports UDP et TCP respectivement pour activer ces flux multimédias. Les flux de médias sur ces ports sont protégés par une clé qui est échangée via un canal de signalisation sécurisé TLS.

### <a name="federation-safeguards-for-teams"></a>Protection de la Fédération pour Teams

La Fédération offre à votre organisation la possibilité de communiquer avec d’autres organisations afin de partager la messagerie instantanée et la présence. La Fédération de Teams est activée par défaut. En revanche, les administrateurs de client peuvent contrôler cet environnement via le centre d’administration Microsoft 365.

## <a name="addressing-threats-to-teams-meetings"></a>Répondre aux réunions Teams

Deux options s’offrent à vous pour contrôler les personnes qui ont atteint les réunions Teams et qui auront accès aux informations que vous présentez.

1. Vous pouvez contrôler les personnes qui joignent vos réunions via les paramètres de la **lobby**.</p>

    |Options de paramètre « Qui peut éviter la salle d’attente ? » disponibles sur la page d’options Meeting   |Types d’utilisateurs participant directement à la réunion  |Types d’utilisateurs passant par la salle d’attente   |
    |---------|---------|---------|
    |Membres de mon organisation     |  -Locataire hébergé  </br>-Invité du client         |  -Fédéré</br>  -Anonyme</br>  -Rendez-vous PSTN</br>     |
    |Membres de mon organisation et organisations approuvées      |  -Locataire hébergé</br> -Invité du client</br> -Fédéré</br>        |  -Anonyme</br>  -Rendez-vous PSTN</br>      |
    |Tout le monde      |   -Locataire hébergé</br>  -Invité du client</br>  -Anonyme fédéré</br>  -Rendez-vous PSTN</br>       |         |

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

Teams offre aux utilisateurs d’entreprise la possibilité de créer et de participer à des réunions en temps réel. Les utilisateurs d’entreprise peuvent également inviter des utilisateurs externes ne possédant pas de compte Azure AD, Microsoft 365 ou Office 365 à participer à ces réunions. Les utilisateurs qui sont employés par des partenaires externes avec une identité sécurisée et authentifiée peuvent également participer à des réunions et, s’ils sont promus, ils peuvent agir en tant que présentateurs. Les utilisateurs anonymes ne peuvent pas créer ou participer à une réunion en tant que présentateur, mais ils peuvent être promus au présentateur une fois qu’ils ont rejoint la réunion.

Pour que les utilisateurs anonymes puissent participer aux réunions Teams, le paramètre réunions des participants dans le centre d’administration teams doit être activé.

> [!NOTE]
> Le terme *utilisateurs anonymes* indique que les utilisateurs qui ne sont pas authentifiés auprès du locataire des organisations. Dans ce contexte, tous les utilisateurs externes sont considérés comme anonymes. Les utilisateurs authentifiés incluent les utilisateurs clients et les utilisateurs invités du locataire.

Permettre aux utilisateurs externes de participer à des réunions Teams peut être très utile, mais implique des risques en matière de sécurité. Pour résoudre ces problèmes, Teams exploite les garanties supplémentaires suivantes :

- Les rôles de participants déterminent les privilèges de contrôle de réunion.
- Les types de participants vous permettent de limiter l’accès à des réunions spécifiques.
- La planification de réunions est réservée aux utilisateurs qui ont un compte AAD et une licence Teams.
- Les utilisateurs anonymes, qui ne sont pas authentifiés, ont besoin de participer à une conférence rendez-vous en utilisant un numéro de conférence. Si le paramètre « toujours autoriser les appelants à contourner le lobby » est *activé*, il doit également patienter jusqu’à ce qu’un présentateur ou utilisateur authentifié se connecte à la réunion.

  > [!CAUTION]
  > Si vous ne souhaitez pas que les utilisateurs anonymes (usagers que vous n'invitez pas explicitement) participent à une réunion, vous devez vous assurer que **Les utilisateurs anonymes peuvent participer à une réunion** sont définis sur **Désactivée** pour la section réunion des **Participants**.

Il est également possible pour un organisateur de configurer les paramètres de façon à ce que les appelants entrants soient la première personne participant à une réunion. Ce paramètre est configuré dans les paramètres de conférence audio pour les utilisateurs et s’applique à toutes les réunions planifiées par l’utilisateur.

> [!NOTE]
> Pour plus d’informations sur l’accès invité et externe dans Teams, voir cet [article ](./communicate-with-users-from-other-organizations.md). Il couvre les fonctionnalités que les utilisateurs invités ou externes peuvent espérer voir et utiliser lorsqu’ils se connectent à Teams. <p> Si vous enregistrez des réunions et souhaitez voir une matrice d’autorisations concernant l’accès au contenu, veuillez consulter [cet article](./tmr-meeting-recording-change.md) et sa matrice.

### <a name="participant-roles"></a>Rôles des participants

Les participants à la réunion se répartissent en trois groupes, chacun ayant ses propres privilèges et restrictions :

- **Organisateur** L’utilisateur qui crée une réunion, qu’elle soit impromptue ou programmée. Un organisateur doit être un utilisateur de client authentifié et contrôler tous les aspects d’un utilisateur final d’une réunion.
- **Présentateur** Un utilisateur autorisé à présenter des informations lors d’une réunion, quel que soit le média pris en charge. Un organisateur de réunion est par définition également un présentateur et détermine qui d’autre peut être un présentateur. Il peut effectuer cette détermination lorsqu’une réunion est planifiée ou pendant son déroulement.
- **Participant** Un utilisateur qui a été invité à participer à une réunion, mais qui n’est pas autorisé à agir en tant que présentateur.

Un présentateur peut également promouvoir un participant au rôle de présentateur pendant la réunion.

### <a name="participant-types"></a>Types de participants

Les participants à la réunion sont également classés par localisation et informations d’identification. Vous pouvez utiliser ces deux caractéristiques pour préciser les utilisateurs pouvant avoir accès à des réunions spécifiques. Les utilisateurs peuvent être répartis dans les catégories suivantes :

1. **Les utilisateurs qui appartiennent au client** ces utilisateurs ont une information d’identification dans Azure Active Directory pour le client.
    a. *Membres de mon organisation* : ces utilisateurs ont une information d’identification dans Azure Active Directory pour le client. *Membres de mon organisation* inclut les comptes invités invités.
    b. *Utilisateurs distants* : ces utilisateurs se rejoignent en dehors du réseau de l’entreprise. Ce sont, par exemple, des employés qui travaillent à domicile ou en déplacement, ou d’autres personnes, comme les employés de fournisseurs de confiance, qui ont reçu des informations d’identification d’entreprise pour leurs conditions d’utilisation du service. Les utilisateurs distants peuvent créer et participer à des réunions et se comporter comme présentateurs.
.
2. **Les utilisateurs qui n’appartiennent pas au client** ces utilisateurs n’ont pas d’informations d’identification dans Azure AD pour le client.
    a. *Les utilisateurs fédérés* les utilisateurs fédérés ont des informations d’identification valides avec les partenaires fédérés et sont donc traités comme authentifiés par Teams, mais restent externe pour le client organisateur de la réunion. Les utilisateurs fédérés peuvent participer à des réunions et être promus aux présentateurs une fois qu’ils ont rejoint la réunion, mais ils ne peuvent pas créer de réunions dans les entreprises avec lesquelles ils sont fédérés.
    b. *Les utilisateurs anonymes*-les utilisateurs anonymes n’ont pas d’identité Active Directory et ne sont pas fédérés avec le client.

De nombreuses réunions impliquent des utilisateurs externes. Ces mêmes clients veulent également être rassurés en ce qui concerne l’identité des utilisateurs externes avant de permettre à ces utilisateurs de participer à une réunion. La section suivante décrit comment les équipes limitent l’accès aux types d’utilisateurs qui ont été explicitement autorisés et nécessite que tous les types d’utilisateur présentent les *informations d’identification* lors de la saisie d’une réunion.

### <a name="participant-admittance"></a>Admission des participant

> [!CAUTION]
> Si vous ne souhaitez pas que les utilisateurs anonymes (usagers que vous n'invitez pas explicitement) participent à une réunion, vous devez vous assurer que **Les utilisateurs anonymes peuvent participer à une réunion** sont définis sur **Désactivée** pour la section réunion des **Participants**.

Dans Teams, les utilisateurs anonymes peuvent être transférés vers une zone d’attente appelée salle d’attente. Les présentateurs peuvent ensuite *admettre* ces utilisateurs à la réunion ou les *rejeter*. Lorsque ces utilisateurs sont transférés vers la salle d’attente, le présentateur et les participants reçoivent une notification et les utilisateurs anonymes doivent patienter jusqu’à ce qu’ils soient acceptés ou rejetés, ou que leur connexion arrive à expiration.

Par défaut, les participants qui accèdent à partir du RTC accèdent directement à la réunion une fois qu’un utilisateur authentifié rejoint la réunion, mais cette option peut être modifiée pour forcer les participants à appeler la salle d’attente.

Les organisateurs de la réunion contrôlent si les participants peuvent rejoindre une réunion sans attendre dans la salle d’attente. Chaque réunion peut être configurée pour autoriser l’accès à l’aide de l’une des méthodes suivantes :

Les valeurs par défaut sont les suivantes :

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

## <a name="related-topics"></a>Voir aussi

[12 premières tâches pour les équipes de sécurité qui prennent en charge le travail à domicile](/microsoft-365/security/top-security-tasks-for-remote-work)

[Centre de gestion de la confidentialité Microsoft](https://microsoft.com/trustcenter)

[Gérer les paramètres de réunion dans Microsoft Teams](./meeting-settings-in-teams.md)

[Optimiser la connectivité de Microsoft 365 ou Office 365 pour les utilisateurs à distance à l’aide de la segmentation de tunnel VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)

- [Implémentation de la segmentation de tunnel VPN](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

[Enregistrements de réunions dans Teams, emplacement de stockage de ces enregistrements et personnes autorisées à y accéder](./tmr-meeting-recording-change.md)
