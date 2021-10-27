---
title: Aperçu du guide de sécurité pour Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 10/23/2021
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Conseils et apprentissages en matière de sécurité pour les administrateurs informatiques relatifs à l’installation, la configuration et la gestion de Microsoft Teams.
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
ms.openlocfilehash: 9fadf6685ada5f0625f7347efe3c1e4d8840af96
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579634"
---
# <a name="security-and-microsoft-teams"></a>Sécurité et Microsoft Teams

> [!IMPORTANT]
> Le modèle de service Teams est susceptible d’être modifié pour améliorer les expériences des clients. Par exemple, il est possible que les heures d’expiration des jetons d’actualisation ou d’accès par défaut soient sujettes à des modifications pour améliorer les performances et la résilience de l’authentification pour les personnes qui utilisent Teams. Ces modifications sont apportées dans le but de maintenir la sécurité de Teams et la confiance en conception.

Microsoft Teams, dans le cadre des services Microsoft 365 et Office 365, suit toutes les meilleures pratiques et procédures en matière de sécurité, telles que la sécurité au niveau du service via la défense en profondeur, les contrôles client au sein du service, la sécurité renforcée et les meilleures pratiques opérationnelles. Pour plus d’informations, consultez le [Centre de gestion de la confidentialité Microsoft](https://microsoft.com/trustcenter).

## <a name="trustworthy-by-design"></a>Fiable par nature

Teams a été conçu et développé conformément au cycle de développement Microsoft Trustworthy Computing Security Development Lifecycle (SDL), décrit [Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/sdl/default.aspx). Pour créer un système de communications unifiées plus sûr, la première étape a consisté à concevoir des modèles de menace, puis à tester chaque nouvelle fonctionnalité durant sa conception. Plusieurs améliorations liées à la sécurité ont été intégrées au processus et aux pratiques de codage. Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final. Il est impossible de concevoir contre toutes les menaces de sécurité inconnues. Aucun système ne peut garantir une sécurité totale. Toutefois, dans la mesure où le développement du produit utilise des règles de conception prenant en compte la sécurité dès le départ, les technologies de sécurité standard font partie intégrante de l’architecture de Teams.

## <a name="trustworthy-by-default"></a>Fiable par défaut

Par défaut, les communications réseau dans Teams sont chiffrées. En exigeant que tous les serveurs utilisent des certificats et à l’aide d’OAUTH, du TLS (Transport Layer Security) et du protocole SRTP (Secure Real-Time Transport Protocol), toutes les données Teams sont protégées sur le réseau.

## <a name="how-teams-handles-common-security-threats"></a>Comment Teams gère les menaces de sécurité courantes

Cette section identifie les menaces les plus courantes à la sécurité du service SfBO et la manière dont Microsoft fait face à chaque menace.

### <a name="compromised-key-attack"></a>Attaque par touche compromise

Teams utilise les fonctionnalités PKI du système d’exploitation Windows Server pour protéger les données clés utilisées pour le chiffrement des connexions TLS. Les clés utilisées pour le chiffrement multimédia sont échangées via des connexions TLS.

### <a name="network-denial-of-service-attack"></a>Attaque par déni de service réseau

Une attaque par déni de service distribué (DDOS) se produit lorsqu’une malveillante empêche l’utilisation et le fonctionnement normale du réseau par des utilisateurs valides. À l’aide d’une attaque par déni de service, l’agresseur peut :

- envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;
- envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;
- masquer les signes d’attaque ;
- Empêcher les utilisateurs d'accéder aux ressources du réseau. Teams se protège contre ces attaques en exécutant la protection réseau Azure DDOS et en limitant les demandes des clients provenant des mêmes points d'extrémité, sous-réseaux et entités fédérées.

### <a name="eavesdropping"></a>Protection contre l’écoute

L’écoute clandestine se produit quand une personne malveillante accède au chemin d’accès des données dans un réseau et peut surveiller et lire le trafic. L’écoute clandestine est également appelée « sniffing » ou « snooping ». Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données.

Teams utilise un système TLS (MTLS) commun pour les communications de serveur au sein de Microsoft 365 et Office 365 et utilise également le TLS des clients vers le service. La MTLS rend l’écoute clandestine difficile, voire impossible à réaliser, pendant la durée d’une seule conversation. TLS authentifie toutes les parties et chiffre tout le trafic. Bien que le système TLS n’empêche pas l’écoute clandestine, la personne malveillante ne peut pas lire le trafic si le chiffrement est rompu.

Le protocole TURN est utilisé à des fins multimédias en temps réel. Le protocole TURN n’exige pas le chiffrement du trafic et les informations qu’il envoie sont protégées par l’intégrité du message. Bien qu’il soit ouvert à l’écoute clandestine, les informations qu’il envoie, c’est-à-dire les adresses IP et le port, peuvent être extraites directement en regardant les adresses source et de destination des paquets. Le service Teams s’assure que les données sont valides par la vérification de l’intégrité du message en utilisant la clé dérivée de quelques éléments comprenant un mot de passe TURN, qui n'est jamais envoyé en clair. SRTP est utilisé pour le trafic multimédia et est également chiffré.

### <a name="identity-spoofing-ip-address-spoofing"></a>Usurpation d’identité (usurpation d’adresse IP)

L’usurpation d’adresse se produit lorsque l’utilisateur malveillant identifie, puis utilise l’adresse IP d’un composant réseau, d’un ordinateur ou d’un composant réseau sans être autorisé à le faire. Une attaque réussie permet à l’agresseur de fonctionner comme si l’utilisateur malveillant était l’entité identifiée normalement par l’adresse IP.

TLS authentifie toutes les parties et chiffre tout le trafic. L’utilisation de TLS empêche les agresseurs d’effectuer l’usurpation d’adresse IP sur une connexion spécifique (par exemple, des connexions Mutual TLS). Une personne malveillante peut toujours usurper l’adresse du serveur DNS (Domain Name System). Comme l’authentification est assurée à l’aide de certificats dans Teams, un intrus n’aurait pas de certificat valide nécessaire pour usurper l’identité d’une des parties dans la communication.

### <a name="man-in-the-middle-attack"></a>Attaque par intercepteur

Une attaque de l’intercepteur se produit lorsqu’une personne malveillante redirige les communications entre deux utilisateurs via son propre ordinateur, à l’insu des deux participants. L’intrus peut surveiller et lire le trafic avant de l’acheminer vers le destinataire concerné. Chacun des utilisateurs envoie et reçoit du trafic vers/de l’intrus, alors qu’il pense communiquer avec l’utilisateur concerné uniquement. Ce scénario peut se produire si un utilisateur malveillant peut modifier Active Directory Domain Services pour ajouter son serveur en tant que serveur approuvé ou modifier la configuration DNS pour que les clients se connectent via la personne malveillante lorsqu’elle arrive sur le serveur.

Les attaques d’homme-intermédiaire sur le trafic multimédia entre deux points de terminaison qui participent dans l’audio, la vidéo et le partage d’applications dans Teams sont évitées en utilisant SRTP pour chiffrer le flux de données multimédia. Les clés cryptographiques sont négociées entre les deux points de terminaison sur un protocole de signalisation exclusif (protocole Teams Call Signaling) qui utilise le canal UDP/TCP chiffré TLS 1.2 et AES-256 (en mode GCM).

### <a name="real-time-transport-protocol-rtp-replay-attack"></a>Attaque par relecture en temps réel du protocole RTP

Une attaque par relecture se produit lorsqu’une transmission multimédia valide entre deux correspondants est interceptée, puis retransmise à des fins malveillantes. Teams utilise le protocole SRTP avec un protocole de signalisation sécurisé qui protège les transmissions contre les attaques par relecture en permettant au destinataire de conserver un index des paquets RTP déjà reçus et de comparer chaque nouveau paquet avec les paquets déjà répertoriés dans l’index.

### <a name="spim"></a>SPIM

Il s’agit de messages instantanés commerciaux non sollicités ou de demandes d’abonnement de présence, tels que le courrier indésirable, mais sous forme de message instantané. Bien qu’il ne soit pas de lui-même une compromission du réseau, il est pour le moins gênant, peut réduire la disponibilité et la production des ressources et peut conduire à une compromission du réseau. Par exemple, les utilisateurs s'envoyant des messages instantanés indésirables lors de l’envoi de demandes. Les utilisateurs peuvent se bloquer pour empêcher l’attaque par l’envoi de messages instantanés indésirables, mais avec la fédération, si un acteur malveillant établit une attaque par message instantanée indésirable coordonnée, elle peut être difficile à surmonter sauf si vous désactivez la fédération du partenaire.

### <a name="viruses-and-worms"></a>Virus et vers

Un virus est une unité de code dont l’objectif est de reproduire d’autres unités de code similaires. Pour fonctionner, un virus a besoin d’un hôte, par exemple un fichier, un e-mail ou un programme. Tel qu’un virus, un vers est une unité de code qui reproduit d’autres unités de code similaires, mais qui à la différence d’un virus n’a pas besoin d’hôte. Les virus et les vers apparaissent principalement lors des transferts de fichiers entre clients ou lorsque des URL sont envoyées par d’autres utilisateurs. Si vous avez un virus sur votre ordinateur, il peut, par exemple, utiliser votre identité et envoyer des messages instantanés en votre nom. Les meilleures pratiques standard de sécurité client, telles que la recherche périodique de virus, peuvent atténuer ce problème.

## <a name="security-framework-for-teams"></a>Infrastructure de sécurité pour Teams

Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent une infrastructure de sécurité pour Microsoft Teams.

Les principaux éléments sont les suivants :

- Azure Active Directory (Azure AD) fournit un unique référentiel back-end fiable pour les comptes d’utilisateurs. Les informations de profil utilisateur sont stockées dans Azure AD via les actions de Microsoft Graph.
  - Plusieurs jetons peuvent être émis que vous pouvez voir si vous suivez votre trafic réseau. Y compris les jetons Skype que vous pouvez voir dans les traces tout en consultant le trafic audio et les conversations.
- TLS (Transport Layer Security) et Mutual TLS (MTLS) qui chiffre le trafic de messages instantanés et active l’authentification de point de terminaison. Les flux de données audio, vidéo et de partage d’applications point à point sont chiffrés et l’intégrité est vérifiée à l’aide du protocole SRTP (Secure Real-Time Transport Protocol). Vous pouvez également voir le trafic OAuth dans votre trace, en particulier autour des autorisations de négociation, lorsque vous basculez entre les onglets dans Teams, par exemple, pour passer d’une publication à une autre. Pour obtenir un exemple de flux OAuth pour les onglets, [consultez ce document](/microsoftteams/platform/tabs/how-to/authentication/auth-flow-tab).
- Les équipes utilisent des protocoles standard pour l’authentification des utilisateurs, autant que possible.

Les sections suivantes décrivent certaines de ces technologies de base.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure Active Directory sert de service d’annuaire pour Microsoft 365 et Office 365. Il stocke toutes les affectations de stratégie et les informations de l’annuaire utilisateur.

#### <a name="certificate-revocation-list-crl-distribution-points"></a>Points de distribution de liste de révocation de certificats (CRL)

Le trafic Microsoft 365 et Office 365 a lieu sur les canaux chiffrés TLS/HTTPs, ce qui signifie que les certificats sont utilisés pour le chiffrement de tout le trafic. Teams exige que tous les certificats de serveur contiennent un ou plusieurs points de distribution de CRL. Les points de distribution de CRL sont des emplacements à partir desquels les listes de révocation de certificats peuvent être téléchargés afin de vérifier que le certificat n’a pas été révoqué depuis l’émission du certificat et qu’il est toujours dans la période de validité. Un point de distribution CRL est indiqué dans les propriétés du certificat sous forme d’URL et il s’agit d’une adresse HTTP sécurisée. Le service Teams vérifie la liste de révocation de certificats avec chaque authentification de certificat.

#### <a name="enhanced-key-usage"></a>Utilisation avancée de la clé :

Tous les composants du service Teams requièrent que tous les certificats de serveur prennent en charge l’Utilisation améliorée de la clé améliorée (EKU) pour l’authentification du serveur. La configuration du champ de l’EKU pour l’authentification du serveur signifie que le certificat est valide pour l’authentification des serveurs. Cette EKU est essentielle pour MTLS.

### <a name="tls-and-mtls-for-teams"></a>TLS et MTLS pour les équipes

Les protocoles TLS et MTLS fournissent des communications chiffrées et une authentification de point de terminaison sur Internet. Teams utilise ces deux protocoles pour créer le réseau des serveurs approuvés et vérifier que toutes les communications sont chiffrées sur ce réseau. Toutes les communications entre les serveurs se produisent sur MTLS. Toute communication SIP restante ou héritée entre le client et le serveur se produit sur TLS.

TLS permet aux utilisateurs, par le biais de leur logiciel client, d'authentifier les serveurs Teams auxquels ils se connectent. Lors d'une connexion TLS, le client demande un certificat valide au serveur. Pour être valide, le certificat doit avoir été émis par une autorité de certification (CA) à laquelle le client fait également confiance et le nom DNS du serveur doit correspondre au nom DNS du certificat. Si le certificat est valide, le client utilise la clé publique du certificat pour chiffrer les clés de chiffrement symétrique à utiliser pour la communication, de sorte que seul le propriétaire initial du certificat peut utiliser sa clé privée pour déchiffrer le contenu de la communication. La connexion qui en résulte est de confiance et, à partir de ce moment, elle n'est pas contestée par d'autres serveurs ou clients de confiance.

Les connexions de serveur à serveur reposent sur le protocole TLS (MTLS) mutuel pour l’authentification mutuelle. Sur une connexion MTLS, le serveur à l’origine d’un message et le serveur le recevant échangent des certificats à partir d’une autorité de certification mutuellement approuvée. Les certificats prouvent l’identité d’un serveur à un autre. Cette procédure est suivie dans le service Teams.

TLS et MTLS permettent d'éviter à la fois l'écoute clandestine et les attaques de type homme du milieu.Dans une attaque de type homme du milieu , l'attaquant redirige les communications entre deux entités du réseau via son ordinateur, à l'insu des deux parties.TLS et la spécification des serveurs de confiance de Teams atténuent le risque d'une attaque de type homme du milieu en partie sur la couche application en utilisant un cryptage coordonné à l'aide de la cryptographie à clé publique entre les deux points d'extrémité.Pour décrypter la communication, un attaquant devrait disposer d'un certificat valide et fiable, accompagné de la clé privée correspondante et émis au nom du service auquel le client s'adresse.

Les données Teams sont chiffrées pendant le transit et au repos dans des centres de données Microsoft. Microsoft utilise des technologies standard du secteur d’activité, telles que TLS et SRTP, pour chiffrer toutes les données en transit entre les appareils des utilisateurs et les centres de données Microsoft, et entre les centres de données Microsoft. Les données en transit incluent les messages, les fichiers, les réunions et d’autres contenus. Les données d’entreprise sont également chiffrées au repos dans les centres de données Microsoft de sorte que les organisations peuvent déchiffrer le contenu si nécessaire afin de respecter leurs obligations en matière de sécurité et de conformité via des méthodes telles que eDiscovery. Pour plus d’informations sur le chiffrement dans Microsoft 365, voir [Chiffrement dans Microsoft 365](/microsoft-365/compliance/encryption)

### <a name="encryption-in-teams"></a>Chiffrement dans Teams

Il existe plusieurs couches de chiffrement au travail au sein de Microsoft 365. Le chiffrement dans Teams fonctionne avec le reste du chiffrement Microsoft 365 pour protéger le contenu de votre organisation. Cet article décrit les technologies de chiffrement spécifiques à Teams. Pour une vue d’ensemble du chiffrement dans Microsoft 365, voir [Chiffrement dans Microsoft 365](/microsoft-365/compliance/encryption).

#### <a name="traffic-encryption"></a>Chiffrement du trafic

L’ensemble du trafic serveur à serveur nécessite MTLS, que le trafic soit limité au réseau interne ou franchit la limite du réseau interne. Ce tableau résume les protocoles utilisés par les équipes.

|**Type de trafic**|**Encrypté par**|
|:-----|:-----|
|Serveur à serveur|MTLS|
|Client au serveur, par exemple, la messagerie instantanée et la présence|TLS|
|Flux multimédias, par exemple, le partage audio et vidéo de médias|TLS|
|Partage de fichiers audio et vidéo|SRTP/TLS|
|Signalisation|TLS|
|Chiffrement amélioré client à client (par exemple, les appels de chiffrement de bout en bout)|SRTP/DTLS|
|||

Teams utilise TLS et MTLS pour encrypter les messages instantanés.

#### <a name="media-encryption"></a>Chiffrement multimédia

Les flux d’appels dans Teams sont basés sur l’offre [Protocole SDP RFC 4566](https://tools.ietf.org/html/rfc4566) et le modèle de réponse sur HTTPS. Une fois que l’appelant accepte un appel entrant, l’appelant et l’appelé conviennent des paramètres de la session.

Le trafic de médias est chiffré par et circule entre l’appelant et l’appelé à l’aide du protocole Secure RTP (SRTP), un profil du protocole RTP (Real-time Transport Protocol) qui fournit une confidentialité, une authentification et une protection contre les attaques par relecture vers le trafic RTP. Le SRTP utilise une clé de session générée par un générateur de nombres aléatoires sécurisé et échangé à l’aide du canal TLS de signalisation. Dans la plupart des cas, le trafic multimédia client à client est négocié via la signalisation de la connexion client au serveur et chiffré à l’aide du SRTP lorsque vous passez directement d’un client à un autre.

Dans les flux d’appels normaux, la négociation de la clé de chiffrement intervient sur le canal de signalisation d’appel. Dans un appel chiffré de bout en bout, le flux de signalisation est identique à un appel Teams individuel. Toutefois, Teams utilise DTLS pour dériver une clé de chiffrement basée sur des certificats générés sur les deux points de terminaison du client. Étant donné que DTLS dérive la clé en fonction des certificats client, la clé est opaque pour Microsoft. Une fois que les deux clients s’accordent sur la clé, les médias commencent à circuler à l’aide de cette clé de chiffrement négociée par DTLS sur le SRTP.

Pour vous protéger contre une attaque par intercepteur entre l’appelant et l’appelé, Teams dérive un code de sécurité à 20 chiffres des empreintes numériques SHA-256 des certificats d’appel du point de terminaison de l’appelant et de l’appelé. L’appelant et l’appelé peuvent valider les codes de sécurité à 20 chiffres en les lisant entre eux pour voir s’ils correspondent. Si les codes ne correspondent pas, la connexion entre l’appelant et l’appelé a été interceptée par une attaque par intercepteur. Si l’appel a été compromis, les utilisateurs peuvent mettre fin à l’appel manuellement.

Teams utilise un jeton basé sur les informations d’identification pour sécuriser l’accès aux relais multimédias à la main. Les relais de contenu échangent le jeton via un canal sécurisé TLS.

#### <a name="federal-information-processing-standard-fips"></a>Norme FIPS (Federal Information Processing Standard)

Teams utilise des algorithmes compatibles FIPS pour les échanges de clés de chiffrement. Pour plus d’informations sur l’implémentation de la norme FIPS, consultez la [Publication 140-2 de la norme FIPS (Federal Information Processing Standard)](/microsoft-365/compliance/offering-fips-140-2).

### <a name="user-and-client-authentication"></a>Authentification utilisateur et client

Un utilisateur approuvé est un utilisateur dont les informations d’identification ont été authentifiées par Azure AD dans Microsoft 365 et Office 365.

L'authentification consiste à fournir les informations d'identification de l'utilisateur à un serveur ou un service de confiance. Teams utilise les protocoles d'authentification suivants, en fonction du statut et de l'emplacement de l'utilisateur.

- **L’authentification moderne (AM)** est l’implémentation Microsoft d’OAUTH 2.0 pour la communication client à serveur. Elle active les fonctionnalités de sécurité telles que l’authentification multifacteur et l’accès conditionnel. Pour utiliser l’authentification moderne, le client en ligne et les clients doivent avoir l’autorisation pour celle-ci. Les clients Teams sur PC et appareils mobiles, ainsi que le client web [prennent tous en charge l’authentification moderne](./sign-in-teams.md).

> [!NOTE]
> Pour plus d’informations sur l’authentification Azure AD et les méthodes d’autorisation, les sections Introduction et « Principes de base de l’authentification dans Azure AD » de cet article vous seront utiles.

L’authentification des équipes est effectuée via Azure AD et OAuth. Le processus d’authentification peut être simplifié pour :

- Connexion de l’utilisateur > émission de jeton > la prochaine demande utilise le jeton émis.

Les demandes du client au serveur sont authentifiées et autorisées par Azure AD en utilisant OAuth. Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés et passent par le même processus que les utilisateurs natifs. Toutefois, des restrictions complémentaires peuvent être mises en place par les administrateurs.

Pour l’authentification multimédias, les protocoles de glace et de tournage utilisent également la stimulation Digest, comme décrit dans l’IETF TURN RFC.

### <a name="windows-powershell-and-team-management-tools"></a>Windows PowerShell et outils de gestion Teams

Dans Teams, les administrateurs informatiques peuvent gérer leur service via le centre d'administration Microsoft 365 ou en utilisant Tenant Remote PowerShell (TRPS). Les administrateurs Tenant utilisent Modern Authentication pour s'authentifier auprès de TRPS.

### <a name="configuring-access-to-teams-at-your-internet-boundary"></a>Configuration de l’accès Teams dans les limites de votre Internet

Pour que Teams fonctionne correctement, par exemple, pour que les utilisateurs puissent participer à des réunions, les clients doivent configurer leur accès Internet de sorte que le trafic UDP et TCP sortant vers les services dans le cloud Teams soit autorisé. Pour plus d’informations, consultez [URL et plages d’adresses IP Office 365](/office365/enterprise/urls-and-ip-address-ranges).

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 et TCP 443

Les ports UDP 3478-3481 et TCP 443 sont utilisés par les clients pour demander un service pour les visuels audio. Un client utilise ces deux ports pour allouer les ports UDP et TCP respectivement pour activer ces flux multimédias. Les flux de médias sur ces ports sont protégés par une clé qui est échangée via un canal de signalisation sécurisé TLS.

### <a name="federation-safeguards-for-teams"></a>Protections de la fédération pour Teams

La Fédération offre à votre organisation la possibilité de communiquer avec d’autres organisations afin de partager la messagerie instantanée et la présence. La Fédération de Teams est activée par défaut. Toutefois, les administrateurs des locataires ont la possibilité de contrôler la fédération via le Centre d'administration Microsoft 365.

## <a name="addressing-threats-to-teams-meetings"></a>Répondre aux menaces pour les réunions Teams

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

Teams offre aux utilisateurs d’entreprise la possibilité de créer et de participer à des réunions en temps réel. Les utilisateurs d’entreprise peuvent également inviter des utilisateurs externes n’ayant pas de compte Azure AD, Microsoft 365 ou Office 365 à participer à ces réunions. Les utilisateurs qui sont employés par des partenaires externes avec une identité sécurisée et authentifiée peuvent également participer à des réunions et, s’ils sont promus, ils peuvent agir en tant que présentateurs. Les utilisateurs anonymes ne peuvent pas créer ou participer à une réunion en tant que présentateur, mais ils peuvent être promus présentateurs après leur participation.

Pour que les utilisateurs anonymes puissent participer aux réunions Teams, le paramètre réunions des participants dans le centre d’administration teams doit être activé.

> [!NOTE]
> Le terme *utilisateurs anonymes* indique que les utilisateurs qui ne sont pas authentifiés auprès du locataire des organisations. Dans ce contexte, tous les utilisateurs externes sont considérés comme anonymes. Les utilisateurs authentifiés incluent les utilisateurs clients et les utilisateurs invités du locataire.

L’activation des utilisateurs externes pour la participation à des réunions Teams peut être utile, mais implique quelques risques pour la sécurité. Pour prendre en compte ces risques, Teams utilise les protections suivantes :

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

- **Utilisateurs qui appartiennent au client**. Ces utilisateurs ont des informations d’identification dans Azure Active Directory pour le client.

    *Membres de mon organisation* : ces utilisateurs ont une information d’identification dans Azure Active Directory pour le client. *Membres de mon organisation* inclut les comptes invités invités.

    *Utilisateurs distants* : ces utilisateurs se rejoignent en dehors du réseau de l’entreprise. Ce sont, par exemple, des employés qui travaillent à domicile ou en déplacement, ou d’autres personnes, comme les employés de fournisseurs de confiance, qui ont reçu des informations d’identification d’entreprise pour leurs conditions d’utilisation du service. Les utilisateurs distants peuvent créer et participer à des réunions et se comporter comme présentateurs.

- **Utilisateurs qui n’appartiennent pas au client**. Ces utilisateurs n’ont pas d’informations d’identification dans Azure AD pour le client.

    *Les utilisateurs fédérés* les utilisateurs fédérés ont des informations d’identification valides avec les partenaires fédérés et sont donc traités comme authentifiés par Teams, mais restent externe pour le client organisateur de la réunion. Les utilisateurs fédérés peuvent participer à des réunions et être promus aux présentateurs une fois qu’ils ont rejoint la réunion, mais ils ne peuvent pas créer de réunions dans les entreprises avec lesquelles ils sont fédérés.

    *Les utilisateurs anonymes*-les utilisateurs anonymes n’ont pas d’identité Active Directory et ne sont pas fédérés avec le client.

De nombreuses réunions impliquent des utilisateurs externes. Ces mêmes clients veulent également être rassurés en ce qui concerne l’identité des utilisateurs externes avant de permettre à ces utilisateurs de participer à une réunion. La section suivante décrit comment les équipes limitent l’accès aux types d’utilisateurs qui ont été explicitement autorisés et nécessite que tous les types d’utilisateur présentent les *informations d’identification* lors de la saisie d’une réunion.

### <a name="participant-admittance"></a>Admission des participants

> [!CAUTION]
> Si vous ne souhaitez pas que les utilisateurs anonymes (utilisateurs que vous n’invitez pas explicitement) participent à une réunion, vous devez vous assurer que les **Utilisateurs anonymes peuvent participer à une réunion** est définie sur **Activé** pour la section de réunion du **Participant**.

Dans Teams, les utilisateurs anonymes peuvent être transférés vers une zone d’attente appelée salle d’attente. Les présentateurs peuvent ensuite *admettre* ces utilisateurs à la réunion ou les *rejeter*. Lorsque ces utilisateurs sont transférés vers la salle d’attente, le présentateur et les participants reçoivent une notification et les utilisateurs anonymes doivent patienter jusqu’à ce qu’ils soient acceptés ou rejetés, ou que leur connexion arrive à expiration.

Par défaut, les participants qui accèdent à partir du RTC accèdent directement à la réunion une fois qu’un utilisateur authentifié rejoint la réunion, mais cette option peut être modifiée pour forcer les participants à appeler la salle d’attente.

Les organisateurs de la réunion contrôlent si les participants peuvent rejoindre une réunion sans attendre dans la salle d’attente. Chaque réunion peut être configurée pour autoriser l’accès à l’aide de l’une des méthodes suivantes :

Les valeurs par défaut sont les suivantes :

- *Les membres de mon organisation* – toutes les personnes extérieures à l’organisation attendent dans la salle d’attente jusqu’à leur admission.
- *Les membres de mon organisation et les organisations approuvées* : les utilisateurs authentifiés et les utilisateurs externes provenant de domaines Teams et Skype Entreprise qui se trouvent dans la liste verte d’accès externe peuvent contourner la salle d’attente. Tous les autres utilisateurs attendent dans la salle d’attente jusqu’à leur admission.
- *Tout le monde* – tous les participants à la réunion ignorent la salle d’attente une fois qu’un utilisateur authentifié a rejoint la réunion.

### <a name="presenter-capabilities"></a>Fonctionnalités du présentateur

Les organisateurs de la réunion contrôlent si les participants peuvent présenter lors d’une réunion. Chaque réunion peut être définie de façon à limiter les présentateurs à l’une des options suivantes :

- *Les membres de mon organisation*-tous les utilisateurs clients, y compris les invités, peuvent présenter
- *Membres de mon organisation et organisations de confiance* : tous les utilisateurs clients, y compris les invités, peuvent présenter et les utilisateurs externes de domaines Teams et Skype Entreprise inclus dans la liste verte d’accès externe peuvent présenter.  
- *Tout le monde* – tous les participants à la réunion sont des présentateurs.

### <a name="modify-while-meeting-is-running"></a>Modification pendant le déroulement d’une réunion

Vous pouvez modifier les options de réunion pendant qu’une réunion est en cours. La modification, une fois enregistrée, est visible en quelques secondes lors de la tenue de la réunion. Elle affecte également toutes les occurrences futures de la réunion.

## <a name="related-topics"></a>Voir aussi

[12 premières tâches pour les équipes de sécurité qui prennent en charge le travail à domicile](/microsoft-365/security/top-security-tasks-for-remote-work)

[Centre de gestion de la confidentialité Microsoft](https://microsoft.com/trustcenter)

[Gérer les paramètres de réunion dans Microsoft Teams](./meeting-settings-in-teams.md)

[Optimiser la connectivité de Microsoft 365 ou Office 365 pour les utilisateurs à distance à l’aide de la segmentation de tunnel VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)

- [Implémentation de la segmentation de tunnel VPN](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

[Enregistrements de réunions dans Teams, emplacement de stockage de ces enregistrements et personnes autorisées à y accéder](./tmr-meeting-recording-change.md)
