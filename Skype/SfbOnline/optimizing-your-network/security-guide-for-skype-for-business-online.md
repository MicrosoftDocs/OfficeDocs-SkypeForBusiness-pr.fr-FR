---
title: Guide de sécurité pour Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Security
description: Guide de sécurité pour Skype Entreprise Online <add description>
ms.openlocfilehash: 85084e3bc675aaadf190b2c486bfe3d6adcb684c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728439"
---
# <a name="security-and-skype-for-business-online"></a>Sécurité et Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype Entreprise Dans le cadre des services Microsoft 365 et Office 365, online (SfBO) suit toutes les meilleures pratiques et procédures en matière de sécurité, telles que la sécurité au niveau du service par le biais de la défense en profondeur, les contrôles client au sein du service, l’utilisation de la sécurité et les meilleures pratiques opérationnelles. Pour plus d’informations, consultez le Centre de confiance Microsoft ( https://microsoft.com/trustcenter) .

## <a name="trustworthy-by-design"></a>Confiance en conception
Skype Entreprise Online est conçu et développé dans le respect du Microsoft Trustworthy Computing Security Development Lifecycle (SDL), décrit à https://www.microsoft.com/sdl/default.aspx. Pour créer un système de communications unifiées plus sûr, la première étape a consisté à concevoir des modèles de menace, puis à tester chaque nouvelle fonctionnalité durant sa conception. Plusieurs améliorations liées à la sécurité ont été intégrées au processus et aux pratiques de codage. Au moment de la création, des outils détectent les dépassements de mémoire tampon et d’autres risques de sécurité potentiels avant l’archivage du code dans le produit final. Bien sûr, il est impossible de prévoir toutes les menaces de sécurités inconnues lors de la conception. Aucun système ne peut garantir une sécurité totale. Toutefois, étant donné que le développement de produits adopte des principes de conception sécurisés dès le début, Skype Entreprise Online intègre des technologies de sécurité standard dans le cadre de son architecture. 

## <a name="trustworthy-by-default"></a>Fiable par défaut
Les communications réseau dans Skype Entreprise Online sont chiffrées par défaut. Avec l’exigence que tous les serveurs utilisent des certificats et avec l'utilisation d'OAUTH, de TLS, du protocole SRTP (Secure Real-Time Transport Protocol) et d'autres techniques de chiffrement standard, notamment le chiffrement AES (Advanced Encryption Standard) 256 bits, toutes les données de Skype Entreprise Online sont protégées sur le réseau.

## <a name="how-sfbo-handles-common-security-threats"></a>Comment SFBO gère-t-il les menaces de sécurité courantes
Cette section identifie les menaces les plus courantes pour la sécurité du service SfBO et la manière dont Microsoft atténue chaque menace.

### <a name="compromised-key-attack"></a>Attaque par clé compromise
Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations confidentielles. Deux clés sensibles utilisées dans l’infrastructure à clé publique (PKI) doivent être prises en compte : la clé privée de chaque détenteur de certificat et la clé de session utilisée après une identification réussie et un échange de clés de session par les partenaires communicants. Une attaque par clé compromise se produit lorsqu’un intrus parvient à identifier la clé privée ou la clé de session. Lorsque l’intrus parvient à déterminer la clé, il s’en sert pour déchiffrer des données chiffrées, à l’insu de l’expéditeur des données.

Skype Entreprise Online utilise les fonctionnalités PKI du système d’exploitation Windows Server pour protéger les données clés utilisées pour le chiffrement des connexions TLS (Transport Layer Security). Les clés utilisées pour le chiffrement multimédia sont échangées via des connexions TLS. 

### <a name="network-denial-of-service-attack"></a>Attaque par déni de service réseau
L’attaque par déni de service se produit lorsque l’agresseur empêche l’utilisation normale du réseau et la fonctionnement par des utilisateurs valides. À l’aide d’une attaque par déni de service, l’agresseur peut :
- envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;
- envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;
- masquer les signes d’attaque ;
- empêcher les utilisateurs d’accéder aux ressources réseau.

SfBO se limite à ces attaques en exécutant la protection réseau DDOS Azure et en limitation des demandes des clients à partir des mêmes points de terminaison, sous-réseaux et entités fédérées.

### <a name="eavesdropping"></a>Protection contre l’écoute
Une attaque par écoute peut se produire lorsqu’une personne malveillante parvient à accéder au chemin d’accès des données d’un réseau et qu’elle peut ainsi surveiller et lire le trafic. Cette attaque est également appelée reniflage (« sniffing ») ou surveillance (« snooping »). Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données. 

SfBO utilise un système TLS (MTLS) commun pour les communications du serveur entre Microsoft 365 ou Office 365 et TLS entre clients et le service, ce qui rend cette attaque très difficile à obtenir pendant la période pendant laquelle une conversation donnée peut être atteinte. TLS authentifie toutes les parties et chiffre tout le trafic. Ceci n’empêche pas les attaques par écoute, mais l’intrus ne peut pas lire le trafic à moins que le chiffrement ne soit rompu.

Le protocole TURN est utilisé pour les médias en temps réel. Le protocole TURN n’impose pas de chiffrement du trafic et les informations qu’il envoie sont protégées par l’intégrité des messages. Bien qu’il soit ouvert à l’écoute électronique, les informations qu’il envoie (autrement dit les adresses IP et le port) peuvent être extraites directement en regardant simplement les adresses source et de destination des paquets. Le service SFBO s’assure que les données sont valides par la vérification de l’intégrité du message en utilisant la clé dérivée de quelques éléments comprenant un mot de passe TURN, qui n'est jamais envoyé en clair. SRTP est utilisé pour le trafic multimédia et est également chiffré.

### <a name="identity-spoofing-ip-address-spoofing"></a>Usurpation d’identité (usurpation d’adresse IP)
On parle d’usurpation d’identité lorsqu’une personne malveillante parvient à déterminer et à utiliser l’adresse IP d’un réseau, d’un ordinateur ou d’un composant réseau, sans y avoir été autorisée. Une attaque réussie permet à l’agresseur de fonctionner comme si l’utilisateur malveillant était l’entité identifiée normalement par l’adresse IP. Dans le contexte de Microsoft Lync Server 2010, cette situation n’est possible que si un administrateur a effectué les deux conditions suivantes :
- configuré des connexions qui prennent uniquement en charge le protocole TCP (Transmission Control Protocol), ce qui n’est pas recommandé car les communications TCP ne sont pas chiffrées ;
- marqué les adresses IP de ces connexions en tant qu’hôtes approuvés. 

Ce problème est moins grave pour les connexions TLS (Transport Layer Security), car TLS authentifie toutes les parties et chiffre le trafic. L’utilisation du protocole TLS empêche une personne malveillante d’usurper une adresse IP sur une connexion spécifique (par exemple, les connexions Mutual TLS). Mais un pirate informatique peut toujours usurper l’adresse du serveur DNS utilisé par SfBO. Toutefois, étant donné que l’authentification dans SfBO est effectuée avec des certificats, un pirate malveillant n’a pas de certificat valide requis pour usurper l’identité d’une des parties dans la communication.

### <a name="man-in-the-middle-attack"></a>Attaque de l’intercepteur (« man-in-the-middle »)
Une attaque de l’intercepteur se produit lorsqu’une personne malveillante redirige les communications entre deux utilisateurs via son propre ordinateur, à l’insu des deux participants. L’intrus peut surveiller et lire le trafic avant de l’acheminer vers le destinataire concerné. Chacun des utilisateurs envoie et reçoit du trafic vers/de l’intrus, alors qu’il pense communiquer avec l’utilisateur concerné uniquement. Cela peut se produire si une personne malveillante modifie les services de domaine Active Directory pour ajouter son serveur en tant que serveur approuvé, ou si elle modifie DNS (Domain Name System) pour faire en sorte que les clients se connectent au serveur via l’ordinateur de l’intrus à l’origine de l’attaque. 

Une attaque de l’intercepteur peut également se produire avec le trafic multimédia entre deux clients, sauf que dans SfBO, les flux audio, vidéo et de partage d’applications point à point sont chiffrés avec SRTP à l’aide de clés cryptographiques négociées entre les homologues utilisant le protocole SIP (Session Initiation Protocol) sur TLS. 

### <a name="rtp-replay-attack"></a>Attaque par relecture RTP
Une attaque par relecture se produit lorsqu’une transmission multimédia valide entre deux correspondants est interceptée, puis retransmise à des fins malveillantes. SfBO utilise le protocole SRTP conjointement avec un protocole de signalisation sécurisé qui protège les transmissions contre les attaques par relecture en permettant au destinataire de conserver un index des paquets RTP déjà reçus et de comparer chaque nouveau paquet avec ceux déjà répertoriés dans l’index.

### <a name="spim"></a>Spim
Le spim correspond à des messages instantanés commerciaux ou des demandes d’abonnement aux informations de présence non sollicités. S’il ne constitue pas à lui seul une menace envers le réseau, il peut néanmoins perturber les activités des utilisateurs et avoir un impact négatif sur la disponibilité des ressources et la production. Il représente donc un risque potentiel pour le réseau. Prenons le cas d’utilisateurs qui génèrent du spim en s’envoyant mutuellement des demandes. Un utilisateur peut en bloquer un autre pour ne plus recevoir de messages instantanés indésirables. Toutefois, dans le cas de la fédération, il peut s’avérer difficile de faire face à une attaque de spim coordonnée, à moins de désactiver la fédération pour le partenaire.

### <a name="viruses-and-worms"></a>Virus et vers
Un virus est une unité de code dont le but est de reproduire d'autres unités de code similaires. Pour fonctionner, un virus a besoin d'un hôte, tel qu'un fichier, un courriel ou un programme. Comme un virus, un ver est une unité de code qui est codée pour reproduire d'autres unités de code similaires, mais qui, contrairement à un virus, n'a pas besoin d'un hôte. Les virus et les vers apparaissent principalement lors des transferts de fichiers entre clients ou lorsque des URL sont envoyés par d'autres utilisateurs. Si un virus se trouve sur votre ordinateur, il peut, par exemple, utiliser votre identité et envoyer des messages instantanés en votre nom. Les meilleures pratiques standard en matière de sécurité des clients, telles que l'analyse périodique des virus, peuvent atténuer ce problème. 

## <a name="personally-identifiable-information"></a>Informations d’identification personnelle
SfBO peut divulguer des informations sur un réseau public qui peut être lié à une personne. Ces informations appartiennent à deux catégories :
- **Données de présence améliorées** &nbsp; &nbsp; &nbsp; Les données de présence améliorées sont des informations qu’un utilisateur peut choisir de partager ou non sur un lien vers un partenaire fédéré ou avec des contacts au sein d’une organisation. Elles ne sont pas partagées avec les utilisateurs d’un réseau public de messagerie instantanée. Selon les stratégies de groupe en vigueur et la configuration du client, l’administrateur système peut contrôler ces informations. Dans le service SfBO, le mode de confidentialité de présence amélioré peut être configuré pour un utilisateur individuel afin d’empêcher les utilisateurs de SfBO de ne pas voir les informations de présence de l’utilisateur dans la liste des contacts de l’utilisateur. 
- **Données obligatoires**&nbsp;&nbsp;&nbsp;Les données obligatoires sont les données requises pour que le serveur ou le client s’exécute correctement. Il s’agit d’informations nécessaires au niveau d’un serveur ou réseau à des fins de routage, de maintenance de l’état et de signalisation.
Les tableaux suivants répertorient les données nécessaires au fonctionnement de SFBO.

***Tableau 1 - Données de présence enrichies***

<!--start table here -->



| **Données**             | **Paramètres** **possibles**                                                                  |
|:---------------------|:-------------------------------------------------------------------------------------------|
| Données personnelles        | Nom, Titre, Société, Adresse de courrier, Fuseau horaire                                             |
| Numéros de téléphone    | Bureau, Mobile, Domicile                                                                         |
| Informations de calendrier | Informations de liberté, informations d’urgence et de réunion (à ceux qui ont accès à votre calendrier) |
| Statut de présence      | Absent(e), Disponible, Occupé(e), Ne pas déranger, Hors connexion                                             |
|                      |                                                                                            |

<!-- end of table -->

***Tableau 2 - Données obligatoires***

<!--start table here -->


| **Données**             | **Paramètres** **possibles**                                                                  |
|:---------------------|:-------------------------------------------------------------------------------------------|
| Adresse IP   | Adresse réelle de l’ordinateur ou adresse traduite via NAT                     |
| URI SIP      | <u>david.campbell@contoso.com</u>                               |
| Nom         | David Campbell (tel que défini dans les services de domaine Active Directory) |
|              |                                                                 |

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>Infrastructure de sécurité pour SfBO
Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité de Microsoft SfBO. Ces éléments sont les suivants :
- Azure Active Directory (AAD) fournit un référentiel unique de back-end de confiance pour les comptes d’utilisateurs. 
- L’infrastructure de clés publiques utilise des certificats émis par des autorités de certification fiables pour authentifier les serveurs et assurer l’intégrité des données.
- Le protocole de transport TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et MTLS (Mutual TLS) permettent l’authentification des points de terminaison et le chiffrement des messages instantanés. Les flux de données audio, vidéo et de partage d’applications point à point sont chiffrés et l’intégrité est vérifiée à l’aide du protocole SRTP (Secure Real-Time Transport Protocol).
- Protocoles standard d’authentification des utilisateurs, le cas échéant.

Les rubriques de cette section décrivent la manière dont chacun de ces éléments fondamentaux fonctionne pour améliorer la sécurité du service SfBO.
 
### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory sert de service d’annuaire pour Microsoft 365 et Office 365. Il stocke toutes les affectations de stratégie et les informations de l’annuaire utilisateur. 

### <a name="public-key-infrastructure-for-sfbo"></a>Infrastructure à clé publique pour SFBO
Le service SfBO s’appuie sur des certificats pour l’authentification du serveur et pour établir une chaîne de confiance entre les clients et les serveurs et entre les différents rôles des serveurs. L’infrastructure à clé publique (PKI) de Windows Server fournit l’infrastructure nécessaire à l’établissement et à la validation de cette chaîne de confiance.
Les certificats sont des ID numériques. Ils identifient un serveur par son nom et indiquent ses propriétés. Pour garantir la validité des informations d’un certificat, le certificat doit être émis par une autorité de certification fiable par des clients ou d’autres serveurs connectés au serveur. Si le serveur se connecte uniquement avec d’autres clients et serveurs sur un réseau privé, la CA peut être une CA d’entreprise. Si le serveur interagit avec des entités en dehors du réseau privé, une CA publique peut être requise.

Même si les informations du certificat sont valides, il doit exister un moyen de vérifier que le serveur présentant le certificat est en fait celui représenté par le certificat. C’est ici que le PKI de Windows entre en jeu.
Chaque certificat est lié à une clé publique. Le serveur nommé sur le certificat contient une clé privée correspondante que lui seul connaît. Un client ou serveur se connectant utilise la clé publique pour chiffrer une information aléatoire et l’envoie au serveur. Si le serveur déchiffre l’information et la retourne sous forme de texte simple, l’entité se connectant peut ainsi être sûre que le serveur contient la clé privée du certificat et qu’il s’agit donc du serveur nommé sur le certificat.

#### <a name="crl-distribution-points"></a>Points de distribution
SfBO nécessite que tous les certificats de serveur contiennent un ou plusieurs points de distribution de liste de révocation de certificats. Les points de distribution CRL (CDP) sont des emplacements à partir desquels les CRL peuvent être téléchargés en vue de vérifier que le certificat n’a pas été révoqué depuis son émission et qu’il est toujours dans sa période de validité. Un point de distribution CRL est indiqué dans les propriétés du certificat sous forme d’URL et il s’agit d’une adresse HTTP sécurisée. Le service SfBO vérifie la liste de révocation de certificats avec chaque authentification de certificat.

#### <a name="enhanced-key-usage"></a>Utilisation améliorée des clés
Toutes les composantes du service SfBO exigent que tous les certificats de serveur prennent en charge l’utilisation améliorée de la clé (EKU) aux fins de l’authentification du serveur. La configuration du champ EKU pour l’authentification du serveur signifie que le certificat est valide pour l’authentification des serveurs. Cette EKU est essentielle pour MTLS. 

### <a name="tls-and-mtls-for-sfbo"></a>TLS et MTLS pour SfBO
Les protocoles TLS et MTLS fournissent des communications chiffrées et une authentification de point de terminaison sur Internet. SfBO utilise ces deux protocoles pour créer le réseau des serveurs de confiance et s’assurer que toutes les communications sur ce réseau sont chiffrées. Toutes les communications SIP entre les serveurs interviennent sur MTLS. Les communications SIP du client au serveur interviennent sur TLS.

TLS permet aux utilisateurs, via leur logiciel client, d’authentifier les serveurs SfBO auxquels ils se connectent. Sur une connexion TLS, le client demande un certificat valide du serveur. Pour être valide, le certificat doit avoir été émis par une autorité de certification qui est également approuvée par le client et le nom DNS du serveur doit correspondre au nom DNS dans le certificat. Si le certificat est valide, le client utilise la clé publique du certificat pour chiffrer les clés de chiffrement symétriques à utiliser pour la communication, de sorte que seul le propriétaire d’origine du certificat peut utiliser sa clé privée pour déchiffrer le contenu de la communication. La connexion résultante est approuvée et à partir de ce point n’est pas contestée par d’autres serveurs ou clients approuvés. Dans ce contexte, le protocole SSL (Secure Sockets Layer) utilisé avec les services Web peut être associé au protocole TLS.

Les connexions de serveur à serveur reposent sur le protocole TLS (MTLS) mutuel pour l’authentification mutuelle. Sur une connexion MTLS, le serveur à l’origine d’un message et le serveur le recevant échangent des certificats à partir d’une autorité de certification mutuellement approuvée. Les certificats prouvent l’identité d’un serveur à un autre. Dans le service SfBO, cette procédure est adoptée.

TLS et MTLS permettent d’empêcher les attaques par écoute et les attaques d’intercepteur. Dans le cas d’une attaque d’intercepteur, l’attaquant réachemine les communications entre deux entités de réseau via l’ordinateur de l’attaquant sans que l’autre partie n’en ait connaissance. La spécification des serveurs fiables TLS et SfBO réduit le risque d’une attaque entre les hommes en milieu, partiellement sur la couche d’application, à l’aide d’un chiffrement de bout en bout coordonné à l’aide du chiffrement de clé publique entre les deux points de terminaison, et un pirate informatique doit avoir un certificat valide et approuvé avec la clé privée correspondante et émis au nom du service sur lequel le client communique pour déchiffrer la communication. 

### <a name="encryption-for-sfbo"></a>Chiffrement pour SFBO
SfBO utilise les technologie TLS et MTLS pour chiffrer les messages instantanés. Tout le trafic de serveur à serveur requiert MTLS, que le trafic soit confiné au réseau interne ou qu’il traverse le périmètre réseau interne.

Le tableau suivant résume le protocole utilisé par SfBO.

***Tableau 3 - Protection du trafic***

<!--start table here with header -->




|**Type de trafic**|**Protégé par**|
|:-----|:-----|
|Serveur à serveur|MTLS|
|Client à serveur|TLS|
|Messagerie instantanée et présence|TLS (si TLS est configuré)|
|Partage multimédia audio, vidéo et de bureau|SRTP|
|Partage du bureau (signalisation)|TLS|
|Conférence web|TLS|
|Téléchargement de contenu de réunion, téléchargement de carnet d’adresses, développement de groupe de distribution|HTTPS|
|||

<!-- end of table -->

#### <a name="media-encryption"></a>Chiffrement multimédia
Le trafic multimédia est chiffré à l'aide du protocole SRTP (Secure Real-time Transport Protocol), un profil du protocole RTP (Real-Time Transport Protocol) qui offre confidentialité, authentification et protection contre les attaques sur le trafic RTP. SRTP utilise une clé de session produite à l’aide d’un générateur de nombres aléatoires sécurisé et échangée en utilisant le canal TLS de signalisation. De plus, les données multimédias acheminées dans les deux directions entre le serveur de médiation et son tronçon suivant interne sont également chiffrées avec SRTP. 

SfBO génère un nom d’utilisateur/mot de passe pour un accès sécurisé aux relais de média sur TURN. Les relais de média échangent le nom d’utilisateur/mot de passe sur un canal SIP sécurisé par TLS.

#### <a name="fips"></a>FIPS
SFBO utilise des algorithmes qui sont conformes aux normes FIPS (Federal Information Processing Standard) pour les échanges de clés de chiffrement. 

### <a name="user-and-client-authentication"></a>Authentification utilisateur et client 
Un utilisateur approuvé est un utilisateur dont les informations d’identification ont été authentifiées par AAD dans Microsoft 365 ou Office 365. 

L’authentification consiste à fournir des informations d’identification d’utilisateur à un serveur approuvé ou service. SfBO utilise les protocoles d’authentification suivants, selon l’état et l’emplacement de l’utilisateur.
- **L’authentification moderne** est l’implémentation Microsoft d’OAUTH 2.0 pour la communication client à serveur. Il active les fonctionnalités de sécurité telles que l’authentification basée sur les certificats, l’authentification multifacteur et l’accès conditionnel. Pour utiliser l’authentification multifacteur, celle-ci doit être activée pour le client en ligne et les clients. L'authentification multifacteur est activée par défaut pour les clients de SDBO créés après mai 2017. Pour les clients créés avant cette date, suivez les instructions qui suivent pour l’activer. Les clients suivants prennent tous en charge l’authentification multifacteur : client Skype Entreprise 2015 ou 2016, Skype Entreprise sur Mac, client Lync 2013, téléphones IP 3PIP, iOS et Android. 
- **L’ID d’organisation** est utilisé lorsque l’authentification moderne n’est pas activée (ou non disponible).
- **Protocole Digest** pour utilisateurs anonymes. Les utilisateurs anonymes sont des utilisateurs externes qui ne disposent pas d’informations d’identification Active Directory reconnues mais qui ont été invités à une conférence sur site et qui possèdent une clé de conférence valide. L’authentification Digest n’est pas utilisée pour d’autres interactions clients.

L’authentification SfBO se compose de deux phases :
1. Une association de sécurité est établie entre le client et le serveur.
2. Le client et le serveur utilisent l’association de sécurité existante pour signer les messages qu’ils envoient et vérifier les messages qu’ils reçoivent. Les messages non authentifiés d’un client ne sont pas acceptés lorsque l’authentification est activée sur le serveur.

La confiance de l’utilisateur est associée à chaque message qui provient d’un utilisateur, et non à l’identité de l’utilisateur. Le serveur vérifie chaque message à la recherche d’informations d’identification d’utilisateur valides. Si les informations d’identification de l’utilisateur sont valides, le message n’est pas remis, non seulement par le premier serveur à le recevoir, mais par tous les autres serveurs de SfBO.

Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés mais peuvent éventuellement subir des contraintes supplémentaires les empêchant de profiter de la gamme complète de privilèges accordés aux utilisateurs internes.

Pour l’authentification multimédias, les protocoles de glace et de tournage utilisent également la stimulation Digest, comme décrit dans l’IETF TURN RFC. Pour plus d’informations, [consultez le travers multimédia.](#external-user-av-traffic-traversal)

Les certificats client permettent aux utilisateurs d’être authentifiés par SfBO. Au lieu de fournir un nom d’utilisateur et un mot de passe, les utilisateurs disposent d’un certificat et d’une clé privée correspondant au certificat requis pour résoudre un défi cryptographique. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Outils de gestion Windows PowerShell et SfBO
Dans SFBO, les administrateurs informatiques peuvent gérer leur service via le portail d’administration d’O365 ou en utilisant TRPS (Tenant Remote PowerShell). Les administrateurs de client utilisent l’authentification moderne pour s’authentifier auprès de TRPS.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>Configuration de l'accès à SfBO à votre frontière Internet
Pour que SfBO fonctionne correctement (utilisateurs autorisés à participer à des réunions, etc.), les clients doivent configurer leur accès à Internet de sorte que le trafic UDP et TCP sortant vers les services dans le cloud SfBO soit autorisé. Pour plus d’informations, voir ici : https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 et TCP 443

Les ports UDP 3478-3481 et TCP 443 sont utilisés par les clients pour demander un service auprès du service Edge A/V. Un client utilise ces deux ports pour allouer des ports UDP et TCP respectivement à la partie distante à laquelle se connecter. Pour accéder au service Edge A/V, le client doit d’abord avoir établi une session de signalisation SIP authentifiée auprès du bureau d’enregistrement SfBO pour obtenir des informations d’identification d’authentification du service A/V Edge. Ces valeurs sont envoyées à travers le canal de signalisation protégé par TLS et générées par ordinateur pour pallier les attaques par dictionnaire. Les clients peuvent ensuite utiliser ces informations d’identification pour l’authentification Digest avec le service Edge A/V afin d’allouer les ports à utiliser dans une session multimédia. Une requête d’allocation initiale est envoyée par le client et répond par un message de défi/nonce 401 provenant du service Edge A/V. Le client envoie une seconde allocation contenant le nom d’utilisateur et un hachage HMAC (Hash Message Authentication Code) du nom d’utilisateur et du nonce. 

Un mécanisme de numéro de séquence est également en place pour empêcher les attaques par rejeu. Le serveur calcule le HMAC attendu sur la base de sa connaissance du nom d’utilisateur et du mot de passe et si les valeurs HMAC concordent, la procédure d’allocation est exécutée. Sinon, le paquet est abandonné. Ce même mécanisme HMAC est également appliqué aux messages subséquents dans cette session d’appel. La durée de vie de cette valeur de nom d’utilisateur/mot de passe est de huit heures au maximum, au bout desquelles le client réacquiert un nouveau nom d’utilisateur/mot de passe pour les appels subséquents.

### <a name="udptcp-5000059999"></a>UDP/TCP 50 000-59 999
Le port TCP 50 000 sortant est utilisé pour SFBO, y compris pour le partage d’applications et de bureau ainsi que pour le transfert de fichiers. Les plages de ports UDP/TCP 50 000-59 999 sont utilisées pour les sessions multimédia avec les partenaires Microsoft Office Communications Server 2007 qui nécessitent un service de traversée NAT/de pare-feu à partir du service Edge A/V. Étant donné que le service Edge A/V est le seul processus utilisant ces ports, la taille de la plage de ports n’indique pas la surface d’attaque potentielle. Une bonne pratique de sécurité consiste toujours à minimiser le nombre total de ports d’écoute en n’exécutant pas de services réseau inutiles. Si un service réseau n’est pas exécuté, il n’est pas exploitable par une personne malveillante distante et la surface d’attaque de l’ordinateur hôte est réduite. Cependant, au sein d’un même service, la réduction du nombre de ports n’offre pas le même avantage. Le logiciel de service Edge A/V n’est pas plus exposé à une attaque qu’il y ait 10 000 ports ouverts ou 10. L’allocation des ports dans cette plage est effectuée de manière aléatoire et ceux non actuellement alloués n’écoutent pas les paquets.

### <a name="external-user-av-traffic-traversal"></a>Traversée de trafic A/V des utilisateurs externes
Pour permettre aux utilisateurs externes et aux utilisateurs internes d’échanger des médias, un service Edge d’accès doit gérer la signalisation SIP nécessaire pour configurer et détruire une session. Un service Edge A/V est également requis pour agir en tant que relais pour le transfert des médias. La séquence d’appel est illustrée dans la figure suivante.


![Séquence d’appels dans Participer à une réunion.](media/sfbo-call-sequence-security.png) 

1. Un utilisateur reçoit un e-mail contenant une invitation pour rejoindre une réunion SfBO. L’e-mail contient une clé de conférence et une URL au format HTTP établissant un lien vers la conférence. La clé et l’URL sont spécifiques à une réunion particulière.<p>L’utilisateur initie la procédure de participation en cliquant sur l’URL de la réunion dans l’e-mail qui lance le processus de détection du client sur la machine de l’utilisateur. Si le client est détecté, il est lancé. S’il n’est pas détecté, l’utilisateur est redirigé vers le client Web.<p/>
2. Le client SFBO envoie une INVITATION SIP contenant les informations d’identification de l’utilisateur. Un utilisateur fédéré ou distant participe à une conférence à l’aide de ses informations d’identification d’entreprise. Pour un utilisateur fédéré, l’INVITATION SIP est d'abord envoyée à son serveur d’origine, lequel authentifie l’utilisateur et transmet l’INVITATION à SFBO. Un utilisateur anonyme est requis pour réussir l’authentification digest.<p>SDBO authentifie l’utilisateur distant ou anonyme et notifie le client. Comme mentionné à l’étape 2, les utilisateurs fédérés qui rejoignent une conférence sont authentifiés par leur entreprise.<p/>

3. Le client envoie une demande d’informations pour ajouter l’utilisateur à la conférence A/V.

    Les conférences A/V envoient une réponse Ajouter un utilisateur contenant le jeton à présenter au service Edge de conférence A/V, entre autres informations.

    [Remarque]  Tout le trafic SIP précédent est passé par le service Edge Access.

    Le client se connecte au serveur de conférence A/V, qui valide le jeton et transfère par proxy la demande, qui contient un autre jeton d’autorisation au serveur de conférence A/V interne. Le serveur de conférence A/V valide le jeton d’autorisation, qu'il a émis initialement sur le canal SIP, afin de s’assurer qu’un utilisateur valide rejoint la conférence.

4. Entre le client et le serveur de conférence A/V, une connexion multimédia est négociation et configurée via le SRTP.
5. Un utilisateur reçoit un e-mail contenant une invitation pour rejoindre une réunion SfBO. L’e-mail contient une clé de conférence et une URL au format HTTP établissant un lien vers la conférence. La clé et l’URL sont spécifiques à une réunion particulière.

### <a name="federation-safeguards-for-sfbo"></a>Protections de la fédération pour SfBO
La fédération fournit à votre organisation la possibilité de communiquer avec d’autres organisations pour partager la messagerie instantanée et la présence. Dans SFBO, la fédération est activée par défaut. Toutefois, les administrateurs des locataires ont la possibilité de contrôler ceci via le portail Microsoft 365 ou Office 365 Admin client. En savoir plus.

## <a name="addressing-threats-to-sfbo-conferences"></a>Répondre aux menaces pesant sur les conférences SFBO

SFBO offre aux utilisateurs d’entreprise la possibilité de créer et de rejoindre des conférences Web en temps réel. Enterprise utilisateurs externes peuvent également inviter des utilisateurs externes qui n’ont pas de compte AAD, Microsoft 365 ou Office 365 à participer à ces réunions. Les utilisateurs qui sont employés par des partenaires fédérés avec une identité sécurisée et authentifiée peuvent également participer à des réunions et, s’ils sont promus, ils peuvent agir en tant que présentateurs. Les utilisateurs anonymes ne peuvent pas créer ou rejoindre à une réunion en tant que présentateur, mais ils peuvent être promus à ce rôle après l’avoir rejointe.

Permettre aux utilisateurs externes de participer aux réunions SFBO augmente considérablement la valeur de cette fonctionnalité, mais comporte également certains risques de sécurité. Pour répondre à ces risques, SFBO fournit les garanties supplémentaires suivantes :
- Les rôles de participant déterminent les privilèges de contrôle de conférence.
- Les types de participants vous permettent de limiter l’accès à des réunions spécifiques.
- Les types de réunion définis déterminent quels types de participants peuvent participer.
- La programmation des conférences est réservée aux utilisateurs disposant d'un compte AAD et d’une licence SFBO.
- Les utilisateurs anonymes, c’est-à-dire non authentifiés, qui souhaitent participer à une conférence téléphonique avec l’un des numéros d’accès à la conférence, sont invités à entrer l’ID de conférence. Les utilisateurs anonymes qui souhaitent participer à une conférence composent un des numéros d’accès à la conférence, puis sont invités à entrer l’ID de conférence. Le nom enregistré identifie les utilisateurs non authentifiés au sein de la conférence. Les utilisateurs anonymes ne sont pas admis à la conférence tant qu’au moins un organisateur ou utilisateur authentifié ne l’a pas rejointe. Aucun rôle prédéfini ne peut leur être attribué.

### <a name="participant-roles"></a>Rôles des participants
Les participants à la réunion se répartissent en trois groupes, chacun ayant ses propres privilèges et restrictions :
-  &nbsp; Organisateur &nbsp; Utilisateur qui crée une réunion, que ce soit improvisé ou en programmant. Un organisateur doit être un utilisateur d’entreprise authentifié et contrôler tous les aspects des utilisateurs finaux d’une réunion.
-  &nbsp; Présentateur &nbsp; Un utilisateur autorisé à présenter des informations lors d’une réunion, à l’aide de tout support multimédia pris en charge. Un organisateur de réunion est par définition également un présentateur et détermine qui d’autre peut être un présentateur. Il peut effectuer cette détermination lorsqu’une réunion est planifiée ou pendant son déroulement.
-  &nbsp; Participant &nbsp; Utilisateur qui a été invité à participer à une réunion, mais qui n’est pas autorisé à agir en tant que présentateur.

Un présentateur peut également promouvoir un participant au rôle de présentateur pendant la réunion.

### <a name="participant-types"></a>Types de participants

Les participants à la réunion sont également classés par localisation et informations d’identification. Vous pouvez utiliser ces deux caractéristiques pour préciser les utilisateurs pouvant avoir accès à des réunions spécifiques. Les utilisateurs peuvent être répartis globalement dans les catégories suivantes :
1.  **Utilisateurs appartenant au client** &nbsp; &nbsp; Ces utilisateurs ont des informations d’identification Azure Active Directory pour le client.<br/>
    a. *Inside corpnet* – These users are joining from inside the corporate network.<br/>b. *Utilisateurs distants* : ces utilisateurs se rejoignent en dehors du réseau de l’entreprise. Ce sont, par exemple, des employés qui travaillent à domicile ou en déplacement, ou d’autres personnes, comme les employés de fournisseurs de confiance, qui ont reçu des informations d’identification d’entreprise pour leurs conditions d’utilisation du service. Les utilisateurs distants peuvent créer et rejoindre des conférences et agir en tant que présentateurs.
2.  **Utilisateurs n'appartenant pas au client** &nbsp;&nbsp; Ces utilisateurs n'ont pas d'informations d'identification dans Azure Active Directory pour le client.<br/>a. *Utilisateurs fédérés* : les utilisateurs fédérés possèdent des informations d’identification valides auprès de partenaires fédérés et sont par conséquent traités comme authentifiés par SfBO. Les utilisateurs fédérés peuvent se joindre à des conférences et être promus au rôle de présentateur après avoir rejoint la réunion, mais ils ne peuvent pas créer de conférences dans les entreprises avec lesquelles ils sont fédérés.<br/>b. *Les utilisateurs anonymes*-les utilisateurs anonymes n’ont pas d’identité Active Directory et ne sont pas fédérés avec le client. 

Les données client indiquent que de nombreuses conférences impliquent des utilisateurs externes. Ces mêmes clients veulent également être rassurés en ce qui concerne l’identité des utilisateurs externes avant de permettre à ces utilisateurs de participer à une conférence. Comme le décrit la section suivante, SfBO limite l’accès aux réunions aux types d’utilisateurs qui ont été explicitement autorisés et exige que tous les types d’utilisateurs présentent des informations d’identification appropriées en entrant dans une réunion.

### <a name="participant-admittance"></a>Admission des participants
Dans SfBO, les utilisateurs anonymes sont transférés dans une zone appelée salle d’attente Les présentateurs peuvent ensuite admettre ces utilisateurs à la réunion ou les rejeter. Ces utilisateurs sont transférés dans la salle d’attente, le leader est averti, et les utilisateurs attendent alors qu’un leader les accepte ou les rejette ou que leur connexion expire. Pendant qu’ils sont dans la salle d’attente, les utilisateurs entendent de la musique. 

Par défaut, les participants qui se connectent à partir du RTPC vont directement à la réunion, mais cette option peut être modifiée pour forcer les participants à entrer dans le salle d’attente.  
Les organisateurs de la réunion contrôlent si les participants peuvent rejoindre une réunion sans attendre dans la salle d’attente. Chaque réunion peut être configurée pour autoriser l’accès à l’aide de l’une des méthodes suivantes :
- **Seul moi, l’organisateur de la réunion**&nbsp;&nbsp;Tout le monde sauf l’organisateur doit attendre dans la salle d’attente jusqu’à ce qu’à l’admission.
- **Les personnes que j’invite dans mon entreprise**&nbsp;&nbsp;Toute personne de votre entreprise peut participer directement à la réunion, même si elle n'est pas invitée.
- **Toute personne de mon organisation** &nbsp; &nbsp; Tous les utilisateurs du client SfBO dans le client Microsoft 365 ou Office 365 peuvent participer à la réunion sans attendre dans la salle d’attente, même s’ils ne font pas partie de la liste de distribution. Tous les autres, y compris tous les utilisateurs externes et anonymes, doivent attendre dans la salle d’attente jusqu'à ce qu’ils soient admis.
- **Tout le monde** &nbsp; &nbsp; Toute personne (aucune restriction) qui a accès au lien de la réunion accède directement à la réunion.
Lorsque l’une des méthodes est spécifiée, à l'exception d’« Organisateur uniquement » (rôle verrouillé), l’organisateur de la réunion peut également indiquer que les personnes qui appellent par téléphone ne passent pas par le lobby. 

### <a name="presenter-capabilities"></a>Fonctions du présentateur
Les organisateurs de la réunion contrôlent si les participants peuvent présenter lors d’une réunion. Chaque réunion peut être configurée pour limiter les présentateurs à l’une des entités suivantes :
- **Organisateur uniquement** &nbsp; &nbsp; Seul l’organisateur de la réunion peut faire la présentation.
- **Personnes de mon entreprise** &nbsp; &nbsp; Tous les utilisateurs internes peuvent faire une présentation.
- **Tout le monde, y compris les personnes extérieures à ma société** &nbsp; &nbsp; Tous les personnes qui rejoignent la réunion (aucune restriction) peuvent faire une présentation.
- **Les personnes que je choisis**&nbsp;&nbsp;L’organisateur de la réunion précise quels utilisateurs peuvent présenter en les ajoutant à une liste de présentateurs.

## <a name="related-topics"></a>Sujets associés
[Centre de gestion de la confidentialité Microsoft](https://microsoft.com/trustcenter)

