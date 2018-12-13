---
title: Guide de sécurité pour Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: ''
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Security
description: Guide de sécurité pour Skype Entreprise Online <add description>
ms.openlocfilehash: a47ec19c0469e47644f7c3a7e86a6aa71cf730d6
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240947"
---
# <a name="security-and-skype-for-business-online"></a>Sécurité et Skype pour les entreprises en ligne

Skype for Business Online (SfBO), as part of the Office 365 service, follows all the security best practices and procedures such as service-level security through defense-in-depth, customer controls within the service, security hardening and operational best practices. Pour plus de détails, veuillez consulter la Gestion de la confidentialité Office 365 (https://products.office.com/en-us/business/office-365-trust-center-security).

## <a name="trustworthy-by-design"></a>Fiable par conception
Skype for Business Online is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at https://www.microsoft.com/en-us/sdl/default.aspx. The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed. Multiple security-related improvements were built into the coding process and practices. Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product. Of course, it is impossible to design against all unknown security threats. No system can guarantee complete security. However, because product development embraced secure design principles from the start, Skype for Business Online incorporates industry standard security technologies as a fundamental part of its architecture. 

## <a name="trustworthy-by-default"></a>Fiable par défaut
Network communications in Skype for Business Online are encrypted by default. By requiring all servers to use certificates and by using OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 256-bit Advanced Encryption Standard (AES) encryption, all Skype for Business Online data is protected on the network.

## <a name="how-sfbo-handles-common-security-threats"></a>Comment SFBO gère-t-il les menaces de sécurité courantes
Cette section identifie les plus courantes contre les menaces pour la sécurité du SfBO Service et la façon dont Microsoft atténue chacune d’elles.

### <a name="compromised-key-attack"></a>Attaque par clé compromise
Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations confidentielles. Deux clés sensibles utilisées dans l’infrastructure à clé publique (PKI) doivent être prises en compte : la clé privée de chaque détenteur de certificat et la clé de session utilisée après une identification réussie et un échange de clés de session par les partenaires communicants. Une attaque par clé compromise se produit lorsqu’un intrus parvient à identifier la clé privée ou la clé de session. Lorsque l’intrus parvient à déterminer la clé, il s’en sert pour déchiffrer des données chiffrées, à l’insu de l’expéditeur des données.

Skype for Business Online uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections. The keys used for media encryptions are exchanged over TLS connections. 

### <a name="network-denial-of-service-attack"></a>Attaque réseau par déni de service
The denial-of-service attack occurs when the attacker prevents normal network use and function by valid users. By using a denial-of-service attack, the attacker can:
- envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;
- envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;
- masquer les signes d’attaque ;
- empêcher les utilisateurs d’accéder aux ressources réseau.

SfBO atténue les attaques en exécutant la protection du réseau par déni Azure et par la limitation de requêtes client à partir des mêmes points de terminaison, sous-réseaux, les entités fédérées.

### <a name="eavesdropping"></a>Protection contre l’écoute
Eavesdropping can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic. This is also called sniffing or snooping. If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path. An example is an attack performed by controlling a router on the data path. 

SfBO uses mutual TLS (MTLS) for server communications within O365 and TLS from clients to the service, rendering this attack very difficult to impossible to achieve within the time period in which a given conversation could be attacked. TLS authenticates all parties and encrypts all traffic. This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.

Le protocole TURN est utilisé pour les médias en temps réel. Le protocole TURN n’impose pas de chiffrement du trafic et les informations qu’il envoie sont protégées par l’intégrité des messages. Bien qu’il soit ouvert à l’écoute électronique, les informations qu’il envoie (autrement dit les adresses IP et le port) peuvent être extraites directement en regardant simplement les adresses source et de destination des paquets. Le service SFBO s’assure que les données sont valides par la vérification de l’intégrité du message en utilisant la clé dérivée de quelques éléments comprenant un mot de passe TURN, qui n'est jamais envoyé en clair. SRTP est utilisé pour le trafic multimédia et est également chiffré.

### <a name="identity-spoofing-ip-address-spoofing"></a>Usurpation d’identité (usurpation d’adresse IP)
Spoofing occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so. A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address. Within the context of Microsoft Lync Server 2010, this situation comes into play only if an administrator has done both of the following:
- configuré des connexions qui prennent uniquement en charge le protocole TCP (Transmission Control Protocol), ce qui n’est pas recommandé car les communications TCP ne sont pas chiffrées ;
- marqué les adresses IP de ces connexions en tant qu’hôtes approuvés. 

This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic. Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections). But an attacker could still spoof the address of the DNS server that SfBO uses. However, because authentication in SfBO is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.

### <a name="man-in-the-middle-attack"></a>Attaque de l’intercepteur (« man-in-the-middle »)
A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users. The attacker can monitor and read the traffic before sending it on to the intended recipient. Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user. This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server. 

Une attaque de l’intercepteur peut également se produire avec le trafic multimédia entre deux clients, sauf que dans SfBO, les flux audio, vidéo et de partage d’applications point à point sont chiffrés avec SRTP à l’aide de clés cryptographiques négociées entre les homologues utilisant le protocole SIP (Session Initiation Protocol) sur TLS. 

### <a name="rtp-replay-attack"></a>Attaque par relecture RTP
A replay attack occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SfBO uses SRTP in conjunction with a secure signaling protocol that protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.

### <a name="spim"></a>Messages instantanés indésirables (Spim)
Spim is unsolicited commercial instant messages or presence subscription requests. While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network. An example of this is users spimming each other by sending requests. Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.

### <a name="viruses-and-worms"></a>Virus et vers
Un virus est une unité de code ayant pour finalité la reproduction d’unités de code similaires supplémentaires. Pour fonctionner, un virus a besoin d’un hôte, par exemple un fichier, un e-mail ou un programme. Comme un virus, un ver est une unité de code codée pour reproduire des unités de code similaires, mais contrairement à un virus, il n’a pas besoin d’hôte. Les virus et les vers apparaissent principalement lors des transferts de fichiers entre clients ou lorsque des URL sont envoyées par d’autres utilisateurs. Si vous avez un virus sur votre ordinateur, il peut, par exemple, utiliser votre identité et envoyer des messages instantanés en votre nom. Les meilleures pratiques standard de sécurité client, telles que la recherche périodique de virus, peuvent atténuer ce problème. 

## <a name="personally-identifiable-information"></a>Informations d’identification personnelle
SfBO has the potential to disclose information over a public network that might be able to be linked to an individual. The information types can be broken down to two specific categories:
- **Enhanced presence data**&nbsp;&nbsp;&nbsp;Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization. This data is not shared with users on a public IM network. Client policies and other client configuration may put some control with the system administrator. In the SfBO service, enhanced presence privacy mode can be configured for an individual user to prevent SfBO users not on the user’s Contacts list from seeing the user’s presence information. 
- **Mandatory data**&nbsp;&nbsp;&nbsp;Mandatory data is data that is required for the proper operation of the server or the client. This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling. The following tables list the data that is required for SfBO to operate.

***Tableau 1 - Données de présence enrichies***

<!--start table here -->


|                      |                                                                                            |   |
|:---------------------|:-------------------------------------------------------------------------------------------|:--|
| **Données**             | **Paramètres** **possibles**                                                                  |   |
| Données personnelles        | Nom, fonction, société, adresse électronique, fuseau horaire                                             |   |
| Numéros de téléphone    | Bureau, Mobile, Domicile                                                                         |   |
| Informations de calendrier | Avis de disponibilité, Out-of-town, détails de réunion (pour les personnes ayant accès à votre calendrier) |   |
| Statut de présence      | Absent(e), Disponible, Occupé(e), Ne pas déranger, Hors connexion                                             |   |
|                      |                                                                                            |   |

<!-- end of table -->

***Tableau 2 - Données obligatoires***

<!--start table here -->


|              |                                                                 |   |
|:-------------|:----------------------------------------------------------------|:--|
| **Catégorie** | **Paramètres possibles**                                           |   |
| Adresse IP   | Adresse réelle de l’ordinateur ou adresse traduite via NAT                     |   |
| URI SIP      | <u>david.campbell@contoso.com</u>                               |   |
| Nom         | David Campbell (tel que défini dans les services de domaine Active Directory) |   |
|              |                                                                 |   |

<!-- end of table -->

## <a name="security-framework-for-sfbo"></a>Infrastructure de sécurité pour SfBO
This section provides an overview of the fundamental elements that form the security framework for Microsoft SfBO. These elements are as follows:
- Azure Active Directory (AAD) fournit un référentiel unique de back-end de confiance pour les comptes d’utilisateurs. 
- Infrastructure à clé publique (PKI) utilise les certificats émis par des autorités de certification de confiance (CA) pour authentifier les serveurs et garantir l’intégrité des données.
- Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted and integrity checked using Secure Real-Time Transport Protocol (SRTP).
- Protocoles standard d’authentification des utilisateurs, le cas échéant.

Les rubriques de cette section décrivent comment chacun de ces éléments fondamentaux pour améliorer la sécurité du service SfBO.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory functions as the directory service for O365. It stores all user directory information and policy assignments. 

### <a name="public-key-infrastructure-for-sfbo"></a>Infrastructure à clé publique pour SFBO
SfBO service relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles. The Windows Server public key infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust. Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a Certificate Authority (CA) that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.

Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in. Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.

#### <a name="crl-distribution-points"></a>Points de distribution de liste de révocation de certificats
SfBO requiert tous les certificats de serveur pour contenir un ou plusieurs points de distribution de liste de révocation de certificats (CRL). Les points de distribution CRL (CDP) sont des emplacements à partir desquels les CRL peuvent être téléchargés en vue de vérifier que le certificat n’a pas été révoqué depuis son émission et qu’il est toujours dans sa période de validité. Un point de distribution est indiqué dans les propriétés du certificat sous forme d’URL et HTTP sécurisée. Le service SfBO vérifie la liste de révocation de certificats avec chaque authentification de certificat.

#### <a name="enhanced-key-usage"></a>Utilisation améliorée de la clé
All components of the SfBO service require all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication. Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers. This EKU is essential for MTLS. 

### <a name="tls-and-mtls-for-sfbo"></a>TLS et MTLS pour SfBO
TLS and MTLS protocols provide encrypted communications and endpoint authentication on the Internet. SfBO uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted. All SIP communications between servers occur over MTLS. SIP communications from client to server occur over TLS.

TLS enables users, through their client software, to authenticate the SfBO servers to which they connect. On a TLS connection, the client requests a valid certificate from the server. To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate. If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication. The resulting connection is trusted and from that point is not challenged by other trusted servers or clients. Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.

Server-to-server connections rely on mutual TLS (MTLS) for mutual authentication. On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA. The certificates prove the identity of each server to the other. In the SfBO service, this procedure is followed.

TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks. In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party. TLS and SfBO’s specification of trusted servers mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication. 

### <a name="encryption-for-sfbo"></a>Chiffrement pour SFBO
SfBO uses TLS and MTLS to encrypt instant messages. All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.

Le tableau suivant résume le protocole utilisé par SfBO.

***Tableau 3 - Protection du trafic***

<!--start table here with header -->


|||
|:-----|:-----|
|**Type de trafic**|**Protégé par**|
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
Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic. SRTP uses a session key generated by using a secure random number generator and exchanged using the signaling TLS channel. In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP. 

SfBO generates username/passwords for secure access to media relays over TURN. Media relays exchange the username/password over a TLS-secured SIP channel.

#### <a name="fips"></a>FIPS
SFBO utilise des algorithmes qui sont conformes aux normes FIPS (Federal Information Processing Standard) pour les échanges de clés de chiffrement. 

### <a name="user-and-client-authentication"></a>Authentification utilisateur et client 
Un utilisateur approuvé est un dont les informations d’identification ont été authentifiées par DAS dans O365. 

Authentication is the provision of user credentials to a trusted server or service. SfBO uses the following authentication protocols, depending on the status and location of the user.
- **L’authentification moderne** est l’implémentation Microsoft d’OAUTH 2.0 pour la communication client à serveur. Elle permet des fonctions de sécurité telles que l’authentification basée sur le certificat, l’authentification multifacteur d’O365 et l’accès conditionnel d’O365. Pour utiliser l’authentification multifacteur, celle-ci doit être activée pour le client en ligne et les clients. L'authentification multifacteur est activée par défaut pour les clients de SDBO créés après mai 2017. Pour les clients créés avant cette date, suivez les instructions qui suivent pour l’activer. Les clients suivants prennent tous en charge l’authentification multifacteur : client Skype Entreprise 2015 ou 2016, Skype Entreprise sur Mac, client Lync 2013, téléphones IP 3PIP, iOS et Android. 
- **ID d’organisation** est utilisé lorsque l’authentification modernes n’est pas activé (ou n’est pas disponible).
- **Protocole Digest** pour utilisateurs anonymes. Les utilisateurs anonymes sont des utilisateurs externes qui ne disposent pas d’informations d’identification Active Directory reconnues mais qui ont été invités à une conférence sur site et qui possèdent une clé de conférence valide. L’authentification Digest n’est pas utilisée pour d’autres interactions clients.

Authentification SfBO se compose de deux phases :
1. Une association de sécurité est établie entre le client et le serveur.
2. Le client et le serveur utilisent l’association de sécurité existante pour signer les messages qu’ils envoient et vérifier les messages qu’ils reçoivent. Les messages non authentifiés d’un client ne sont pas acceptés lorsque l’authentification est activée sur le serveur.

User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in SfBO.

Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés mais peuvent éventuellement subir des contraintes supplémentaires les empêchant de profiter de la gamme complète de privilèges accordés aux utilisateurs internes.

For media authentication, the ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC. For details, see [media traversal](#external-user-av-traffic-traversal).

Les certificats clients permettent également aux utilisateurs d’être authentifiés par SfBO. Au lieu d’un nom d’utilisateur et le mot de passe, les utilisateurs ont un certificat et la clé privée correspondant au certificat est requis pour résoudre un défi de chiffrement. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Outils de gestion Windows PowerShell et SfBO
Dans SFBO, les administrateurs informatiques peuvent gérer leur service via le portail d’administration d’O365 ou en utilisant TRPS (Tenant Remote PowerShell). Les administrateurs de clients utilisent l’authentification moderne pour s’authentifier auprès de TRPS.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>Configuration de l'accès à SfBO à votre frontière Internet
Pour SfBO fonctionne correctement (les utilisateurs peuvent participer à des réunions, etc.), les clients devoir configurer leur accès à internet afin que le trafic UDP et TCP sortant pour les services dans le SfBO cloud est autorisée. Pour plus d’informations, voir ici :https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 et TCP 443

Les ports TCP 443 UDP 3478-3481 sont utilisés par les clients à des demandes de service a / V Edge service. Un client utilise ces deux ports pour allouer UDP et les ports TCP respectivement pour l’utilisateur distant pour se connecter à. Pour accéder aux A / service Edge de V, le client doit au préalable avoir établi un signalisation SIP authentifiée pour SfBO serveurs d’inscriptions permettant d’obtenir une session / V Edge service informations d’identification d’authentification. Ces valeurs sont acheminées via le canal de signalisation protégé par TLS et sont générées par ordinateur pour atténuer les attaques par dictionnaire. Clients pouvant ensuite utiliser ces informations d’identification pour l’authentification digest avec A / V Edge service allouer les ports pour une utilisation dans une session multimédia. Une demande initiale est envoyée à partir du client et envoie un message stimulation/valeur à usage unique 401 a / V Edge service. Le client envoie une seconde allouer contenant le nom d’utilisateur et un hachage HMAC Message Authentication Code () de hachage du nom d’utilisateur et valeur à usage unique. 

A sequence number mechanism is also in place to prevent replay attacks. The server calculates the expected HMAC based on its own knowledge of the user name and password and if the HMAC values match, the allocate procedure is carried out. Otherwise, the packet is dropped. This same HMAC mechanism is also applied to subsequent messages within this call session. The lifetime of this user name/password value is a maximum of eight hours at which time the client reacquires a new user name/password for subsequent calls.

### <a name="udptcp-5000059999"></a>UDP/TCP 50 000 À 59 999
TCP 50,000 outbound is used for SfBO, including for application and desktop sharing, file transfer. UDP/TCP 50,000-59,999 port ranges are used for media sessions with Microsoft Office Communications Server 2007 partners that require NAT/firewall traversal service from the A/V Edge service. Because the A/V Edge service is the sole process using these ports, the size of the port range does not indicate the potential surface of attack. Good security practice is to always minimize the total number of listening ports by not running unnecessary network services. If a network service is not running, it is not exploitable by a remote attacker and the surface of attack of the host computer is reduced. However, within a single service, reducing the number of ports does not provide the same benefit. The A/V Edge service software is no more exposed to attack with 10,000 ports open as it is with 10. The allocation of ports within this range is done randomly and ports not currently allocated do not listen for packets.

### <a name="external-user-av-traffic-traversal"></a>Traversée de trafic A/V des utilisateurs externes
Enabling external users and internal users to exchange media requires an Access Edge service to handle the SIP signaling that is necessary to set up and tear down a session. It also requires an A/V Edge service to act as a relay for the transfer of the media. The call sequence is illustrated in the following figure.


![Séquence d’appel pour rejoindre une réunion](media/sfbo-call-sequence-security.png) 

1. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.<p>L’utilisateur initie la procédure de participation en cliquant sur l’URL de la réunion dans l’e-mail qui lance le processus de détection du client sur la machine de l’utilisateur. Si le client est détecté, il est lancé. S’il n’est pas détecté, l’utilisateur est redirigé vers le client Web.<p/>
2. Le client SFBO envoie une INVITATION SIP contenant les informations d’identification de l’utilisateur. Un utilisateur fédéré ou distant joint à une conférence à l’aide de leurs informations d’identification de l’entreprise. Pour un utilisateur fédéré, l’INVITATION SIP est d'abord envoyée à son serveur d’origine, lequel authentifie l’utilisateur et transmet l’INVITATION à SFBO. Un utilisateur anonyme est requis pour réussir l’authentification digest.<p>SfBO authenticates the remote or anonymous user and notifies the client. As mentioned in step 2, federated users joining a conference are authenticated by their enterprise.<p/>

3. Le client envoie une demande d’informations pour ajouter l’utilisateur à la conférence A/V.

    A / vidéoconférences envoie une réponse d’ajouter un utilisateur qui contient le jeton à présenter a / V serveur Edge de conférence de service parmi d’autres informations.

    [Note]  Tout le trafic SIP antérieur transitait via le service Edge d’accès.

    The client connects to the A/V Conference Server, which validates the token and proxies the request, which contains another authorization token, to the internal A/V Conferencing Server. The A/V Conferencing Server validates the Authorization Token, which it originally issued over the SIP channel, to further ensure that a valid user is joining the conference.

4. Entre le client et A / V Conferencing Server, une connexion media est négocié et le programme d’installation sur SRTP.
5. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.

### <a name="federation-safeguards-for-sfbo"></a>Protections de la fédération pour SFBO
La fédération fournit à votre organisation la possibilité de communiquer avec d’autres organisations pour partager la messagerie instantanée et la présence. Dans SFBO, la fédération est activée par défaut. Cependant, les administrateurs de clients ont la possibilité de contrôler cela à travers le portail d’administration d’O365. En savoir plus.

## <a name="addressing-threats-to-sfbo-conferences"></a>Répondre aux menaces pesant sur les conférences SFBO

SfBO provides the capability for enterprise users to create and join real-time Web conferences. Enterprise users can also invite external users who do not have an AAD/O365 account to participate in these meetings. Users who are employed by federated partners with a secure and authenticated identity can also join meetings and, if promoted to do so, can act as presenters. Anonymous users cannot create or join a meeting as a presenter, but they can be promoted to presenter after they join.

Enabling external users to participate in SfBO meetings greatly increases the value of this feature, but it also entails some security risks. To address these risks, SfBO provides the following additional safeguards:
- Les rôles de participant déterminent les privilèges de contrôle de conférence.
- Les types de participants vous permettent de limiter l’accès à des réunions spécifiques.
- Les types de réunion définis déterminent quels types de participants peuvent participer.
- La programmation des conférences est réservée aux utilisateurs disposant d'un compte AAD et d’une licence SFBO.
- Anonymous, that is, unauthenticated, users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.

### <a name="participant-roles"></a>Rôles des participants
Les participants à la réunion se répartissent en trois groupes, chacun ayant ses propres privilèges et restrictions :
- **Bibliothèque multimédia** &nbsp; &nbsp;L’utilisateur qui crée une réunion, ou non planifiée ou improvisée. Un organisateur doit correspondre à un utilisateur d’entreprise authentifiés et contrôler tous les aspects de l’utilisateur final d’une réunion.
- **Présentateur** &nbsp; &nbsp;Un utilisateur qui est autorisé à présenter des informations à une réunion, à l’aide de supports est pris en charge. Un organisateur de réunion est par définition également un présentateur et détermine qui d’autre peut être un présentateur. Il peut effectuer cette détermination lorsqu’une réunion est planifiée ou pendant son déroulement.
- **Participant** &nbsp; &nbsp;Un utilisateur qui a été invité à participer à une réunion, mais qui n’est pas autorisé à agir en tant que présentateur.

Un présentateur peut également promouvoir un participant au rôle de présentateur pendant la réunion.

### <a name="participant-types"></a>Types de participants

Meeting participants are also categorized by location and credentials. You can use both of these characteristics to specify which users can have access to specific meetings. Users can be divided broadly into the following categories:
1.  **Utilisateurs qui appartiennent au client** &nbsp; &nbsp;Ces utilisateurs ont une information d’identification dans Azure Active Directory pour le client.<br/> a. *Inside corpnet* – These users are joining from inside the corporate network.<br/>b. *Remote users* – These users are joining from outside the corporate network. They can include employees who are working at home or on the road, and others, such as employees of trusted vendors, who have been granted enterprise credentials for their terms of service. Remote users can create and join conferences and act as presenters.
2.  **Utilisateurs n'appartenant pas au client** &nbsp;&nbsp; Ces utilisateurs n'ont pas d'informations d'identification dans Azure Active Directory pour le client.<br/>les *Utilisateurs fédérés* a - utilisateurs fédérés possèdent des informations d’identification valides avec les partenaires fédérés et sont par conséquent considérés comme étant authentifiés par SfBO. Les utilisateurs fédérés peuvent participer à des conférences et être désignés présentateurs après s’être joints à la réunion, mais ils ne peuvent pas créer de conférences dans les entreprises à laquelle ils sont fédérés.<br/>b. *Anonymous Users* - Anonymous users do not have an Active Directory identity and are not federated with the tenant. 

Customer data shows that many conferences involve external users. Those same customers also want reassurance about the identity of external users before allowing those users to join a conference. As the following section describes, SfBO limits meeting access to those user types that have been explicitly allowed and requires all user types to present appropriate credentials when entering a meeting.

### <a name="participant-admittance"></a>Admission des participants
In SfBO, anonymous users are transferred to a waiting area called the lobby. Presenters can then either admit these users to the meeting or reject them. These users are transferred to the lobby, the leader is notified, and the users then wait until a leader either accepts or rejects them or their connection times out. While in the lobby, the users hear music. 

Par défaut, les participants qui se connectent à partir du RTPC vont directement à la réunion, mais cette option peut être modifiée pour forcer les participants à entrer dans le salle d’attente.  
Meeting organizers control whether participants can join a meeting without waiting in the lobby. Each meeting can be set up to enable access using any one of the following methods:
- **Seul moi, l’organisateur de la réunion**&nbsp;&nbsp;Tout le monde sauf l’organisateur doit attendre dans la salle d’attente jusqu’à ce qu’à l’admission.
- **Les personnes que j’invite dans mon entreprise**&nbsp;&nbsp;Toute personne de votre entreprise peut participer directement à la réunion, même si elle n'est pas invitée.
- **Anyone from my organization**&nbsp;&nbsp;All SfBO users in the O365 tenant can join the meeting without waiting in the lobby, even if those who are not on the distribution list. All others, including all external and anonymous users, must wait in the lobby until admitted.
- **Tout le monde**&nbsp;&nbsp;tout le monde (aucune restriction) qui a accès à un lien de la réunion pourra directement à la réunion.
Lorsque l’une des méthodes est spécifiée, à l'exception d’« Organisateur uniquement » (rôle verrouillé), l’organisateur de la réunion peut également indiquer que les personnes qui appellent par téléphone ne passent pas par le lobby. 

### <a name="presenter-capabilities"></a>Fonctions du présentateur
Meeting organizers control whether participants can present during a meeting. Each meeting can be set up to limit presenters to any one of the following:
- **Organisateur uniquement**&nbsp;&nbsp;uniquement l’organisateur de la réunion peut faire une présentation.
- **Personnes de mon entreprise**&nbsp;&nbsp;tous les utilisateurs internes peuvent faire une présentation.
- **Tout le monde, y compris les personnes extérieures à mon entreprise**&nbsp;&nbsp;tout le monde (aucune restriction) qui rejoint la réunion peut faire une présentation.
- **Les personnes que je choisis**&nbsp;&nbsp;L’organisateur de la réunion précise quels utilisateurs peuvent présenter en les ajoutant à une liste de présentateurs.

## <a name="related-topics"></a>Rubriques connexes
[Centre de gestion de la protection des données d’Office 365](https://products.office.com/en-us/business/office-365-trust-center-security)

