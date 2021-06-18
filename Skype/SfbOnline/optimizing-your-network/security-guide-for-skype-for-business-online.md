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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Security
description: Guide de sécurité pour Skype Entreprise Online <add description>
ms.openlocfilehash: a430d2b6aa4f1992e8710c4a7105530b3dd9fc24
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505191"
---
# <a name="security-and-skype-for-business-online"></a>Sécurité et Skype Entreprise Online

Skype Entreprise Online (SfBO), dans le cadre des services Microsoft 365 et Office 365, suit toutes les meilleures pratiques et procédures en matière de sécurité, telles que la sécurité au niveau du service, la défense en profondeur, les contrôles client au sein du service, l’enchaînement de sécurité et les meilleures pratiques opérationnelles. Pour plus d’informations, consultez le Centre de confiance Microsoft ( https://microsoft.com/trustcenter) .

## <a name="trustworthy-by-design"></a>Confiance en conception
Skype for Business Online is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at https://www.microsoft.com/sdl/default.aspx. The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed. Multiple security-related improvements were built into the coding process and practices. Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product. Of course, it is impossible to design against all unknown security threats. No system can guarantee complete security. However, because product development embraced secure design principles from the start, Skype for Business Online incorporates industry standard security technologies as a fundamental part of its architecture. 

## <a name="trustworthy-by-default"></a>Fiable par défaut
Network communications in Skype for Business Online are encrypted by default. By requiring all servers to use certificates and by using OAUTH, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 256-bit Advanced Encryption Standard (AES) encryption, all Skype for Business Online data is protected on the network.

## <a name="how-sfbo-handles-common-security-threats"></a>Comment SFBO gère-t-il les menaces de sécurité courantes
Cette section identifie les menaces les plus courantes pour la sécurité du service SfBO et la manière dont Microsoft atténue chaque menace.

### <a name="compromised-key-attack"></a>Attaques par clé compromise
Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations secrètes. Deux clés sensibles sont en cours d’utilisation dans l’infrastructure de clé publique (PKI) et doivent être considérées comme étant la clé privée de chaque titulaire du certificat et la clé de session utilisée après un échange réussi d’identification et de clé de session par les partenaires en communication. Une attaque à clé compromis se produit lorsque l’pirate détermine la clé privée ou la clé de session. Lorsque l’utilisateur malveillant réussit à déterminer la clé, il peut utiliser cette clé pour déchiffrer les données chiffrées à l’insu de l’expéditeur.

Skype for Business Online uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections. The keys used for media encryptions are exchanged over TLS connections. 

### <a name="network-denial-of-service-attack"></a>Attaque par déni de service réseau
The denial-of-service attack occurs when the attacker prevents normal network use and function by valid users. By using a denial-of-service attack, the attacker can:
- envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;
- envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;
- masquer les signes d’attaque ;
- empêcher les utilisateurs d’accéder aux ressources réseau.

SfBO se limite à ces attaques en exécutant la protection réseau DDOS Azure et en limitation des demandes des clients à partir des mêmes points de terminaison, sous-réseaux et entités fédérées.

### <a name="eavesdropping"></a>Protection contre l’écoute
Une attaque par écoute peut se produire lorsqu’une personne malveillante parvient à accéder au chemin d’accès des données d’un réseau et qu’elle peut ainsi surveiller et lire le trafic. Cette attaque est également appelée reniflage (« sniffing ») ou surveillance (« snooping »). Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données. 

SfBO utilise un système TLS (MTLS) commun pour les communications serveur entre les clients dans Microsoft 365 ou Office 365 et TLS, ce qui rend cette attaque très difficile à impossible à atteindre au cours de la période pendant laquelle une conversation donnée pourrait être atteinte. TLS authentifier toutes les parties et chiffre tout le trafic. Cela n’empêche pas les eavesdropping, mais l’pirate ne peut pas lire le trafic tant que le chiffrement n’est pas rompu.

Le protocole TURN est utilisé à des fins multimédias en temps réel. Le protocole TURN n’a pas pour objectif de chiffrer le trafic et les informations qu’il envoie sont protégées par l’intégrité des messages. Bien qu’elles soient ouvertes à l’envoi, les informations qu’elles envoient (c’est-à-dire, les adresses IP et le port) peuvent être extraites directement en regardant simplement les adresses source et de destination des paquets. Le service SfBO garantit la validité des données en vérifiant l’intégrité du message à l’aide de la clé dérivée de quelques éléments, dont un mot de passe TURN, qui n’est jamais envoyé en texte clair. Le SRTP est utilisé pour le trafic de médias et est également chiffré.

### <a name="identity-spoofing-ip-address-spoofing"></a>Usurpation d’identité (usurpation d’adresse IP)
Spoofing occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so. A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address. Within the context of Microsoft Lync Server 2010, this situation comes into play only if an administrator has done both of the following:
- configuré des connexions qui prennent uniquement en charge le protocole TCP (Transmission Control Protocol), ce qui n’est pas recommandé car les communications TCP ne sont pas chiffrées ;
- marqué les adresses IP de ces connexions en tant qu’hôtes approuvés. 

This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic. Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections). But an attacker could still spoof the address of the DNS server that SfBO uses. However, because authentication in SfBO is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.

### <a name="man-in-the-middle-attack"></a>Attaque de l’intercepteur
A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users. The attacker can monitor and read the traffic before sending it on to the intended recipient. Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user. This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server. 

Une attaque de l’intercepteur peut également se produire avec le trafic multimédia entre deux clients, sauf que dans SfBO, les flux audio, vidéo et de partage d’applications point à point sont chiffrés avec SRTP à l’aide de clés cryptographiques négociées entre les homologues utilisant le protocole SIP (Session Initiation Protocol) sur TLS. 

### <a name="rtp-replay-attack"></a>Attaque par relecture RTP
A replay attack occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SfBO uses SRTP in conjunction with a secure signaling protocol that protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.

### <a name="spim"></a>SPIM
Le spim correspond à des messages instantanés commerciaux ou des demandes d’abonnement aux informations de présence non sollicités. S’il ne constitue pas à lui seul une menace envers le réseau, il peut néanmoins perturber les activités des utilisateurs et avoir un impact négatif sur la disponibilité des ressources et la production. Il représente donc un risque potentiel pour le réseau. Prenons le cas d’utilisateurs qui génèrent du spim en s’envoyant mutuellement des demandes. Un utilisateur peut en bloquer un autre pour ne plus recevoir de messages instantanés indésirables. Toutefois, dans le cas de la fédération, il peut s’avérer difficile de faire face à une attaque de spim coordonnée, à moins de désactiver la fédération pour le partenaire.

### <a name="viruses-and-worms"></a>Virus et vers
Un virus est une unité de code dont l’objectif est de reproduire des unités de code supplémentaires similaires. Pour fonctionner, un virus a besoin d’un hôte, tel qu’un fichier, une adresse e-mail ou un programme. Comme un virus, un vers est une unité de code qui est codée afin de reproduire des unités de code supplémentaires similaires, mais qui, contrairement à un virus, n’a pas besoin d’un hôte. Les virus et vers sont principalement mis en avant lors des transferts de fichiers entre clients ou lorsque des URL sont envoyées par d’autres utilisateurs. Si un virus se trouve sur votre ordinateur, il peut, par exemple, utiliser votre identité et envoyer des messages instantanés en votre nom. Les meilleures pratiques standard en matière de sécurité client, telles que l’analyse périodique des virus, peuvent réduire ce problème. 

## <a name="personally-identifiable-information"></a>Informations d’identification personnelle
SfBO has the potential to disclose information over a public network that might be able to be linked to an individual. The information types can be broken down to two specific categories:
- **Enhanced presence data**&nbsp;&nbsp;&nbsp;Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization. This data is not shared with users on a public IM network. Client policies and other client configuration may put some control with the system administrator. In the SfBO service, enhanced presence privacy mode can be configured for an individual user to prevent SfBO users not on the user’s Contacts list from seeing the user’s presence information. 
- **Mandatory data**&nbsp;&nbsp;&nbsp;Mandatory data is data that is required for the proper operation of the server or the client. This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling. The following tables list the data that is required for SfBO to operate.

***Tableau 1 - Données de présence enrichies***

<!--start table here -->


|                      |                                                                                            |   |
|:---------------------|:-------------------------------------------------------------------------------------------|:--|
| **Données**             | **Paramètres** **possibles**                                                                  |   |
| Données personnelles        | Nom, Titre, Société, Adresse de courrier, Fuseau horaire                                             |   |
| Numéros de téléphone    | Bureau, Mobile, Domicile                                                                         |   |
| Informations de calendrier | Informations de libre/occupé, avis d’urgence, détails de la réunion (à ceux qui ont accès à votre calendrier) |   |
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
- L’infrastructure de clés publiques utilise des certificats émis par des autorités de certification fiables pour authentifier les serveurs et assurer l’intégrité des données.
- Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted and integrity checked using Secure Real-Time Transport Protocol (SRTP).
- Protocoles standard d’authentification des utilisateurs, le cas échéant.

Les rubriques de cette section décrivent la manière dont chacun de ces éléments fondamentaux fonctionne pour améliorer la sécurité du service SfBO.
 
### <a name="azure-active-directory"></a>Azure Active Directory
Azure Active Directory fonctionne comme service d’annuaire pour Microsoft 365 et Office 365. Il stocke toutes les informations d’annuaire des utilisateurs et les affectations de stratégies. 

### <a name="public-key-infrastructure-for-sfbo"></a>Infrastructure à clé publique pour SFBO
SfBO service relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles. The Windows Server public key infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust. Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a Certificate Authority (CA) that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.

Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in. Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.

#### <a name="crl-distribution-points"></a>Points de distribution
SfBO nécessite que tous les certificats de serveur contiennent un ou plusieurs points de distribution de liste de révocation de certificats. Les points de distribution CRL sont des emplacements à partir des lesquels les révocation de certificats peuvent être téléchargés afin de vérifier que le certificat n’a pas été révoqué depuis l’émission du certificat et qu’il est toujours dans la période de validité. Un point de distribution CRL est indiqué dans les propriétés du certificat en tant qu’URL et sécurisé HTTP. Le service SfBO vérifie la CRL avec chaque authentification de certificat.

#### <a name="enhanced-key-usage"></a>Utilisation avancée de la clé :
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
Un utilisateur approuvé est un utilisateur dont les informations d’identification ont été authentifiées par AAD dans Microsoft 365 ou Office 365. 

Authentication is the provision of user credentials to a trusted server or service. SfBO uses the following authentication protocols, depending on the status and location of the user.
- **L’authentification** moderne est l’implémentation Microsoft d’OAUTH 2.0 pour les communications client à serveur. Il active les fonctionnalités de sécurité telles que l’authentification basée sur les certificats, l’authentification multifacteur et l’accès conditionnel. Pour utiliser ma, le client en ligne et les clients doivent être activés pour ma. Les locataires SfBO créés après mai 2017 ont la ma activée par défaut. Pour les locataires créés avant cette heure, suivez les instructions ci-après pour l’activer. Tous les clients suivants supportent ma : client Skype Entreprise 2015 ou 2016, Skype Entreprise pour Mac, client Lync 2013, téléphones IP 3PIP, iOS et Android. 
- **L’ID d’organisation** est utilisé lorsque l’authentification moderne n’est pas activée (ou non disponible).
- **Protocole Digest** pour utilisateurs anonymes. Les utilisateurs anonymes sont des utilisateurs externes qui ne disposent pas d’informations d’identification Active Directory reconnues mais qui ont été invités à une conférence sur site et qui possèdent une clé de conférence valide. L’authentification Digest n’est pas utilisée pour d’autres interactions clients.

L’authentification SfBO se compose de deux phases :
1. Une association de sécurité est établie entre le client et le serveur.
2. Le client et le serveur utilisent l’association de sécurité existante pour signer les messages qu’ils envoient et vérifier les messages qu’ils reçoivent. Les messages non authentifiés d’un client ne sont pas acceptés lorsque l’authentification est activée sur le serveur.

User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in SfBO.

Les utilisateurs disposant d’informations d’identification valides émises par un partenaire fédéré sont approuvés mais peuvent éventuellement subir des contraintes supplémentaires les empêchant de profiter de la gamme complète de privilèges accordés aux utilisateurs internes.

For media authentication, the ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC. For details, see [media traversal](#external-user-av-traffic-traversal).

Les certificats client permettent aux utilisateurs d’être authentifiés par SfBO. Au lieu de fournir un nom d’utilisateur et un mot de passe, les utilisateurs ont un certificat et une clé privée correspondant au certificat requis pour résoudre un problème cryptographique. 

### <a name="windows-powershell-and-sfbo-management-tools"></a>Outils de gestion Windows PowerShell et SfBO
Dans SfBO, les administrateurs informatiques peuvent gérer leur service via le portail d’administration D’O365 ou à l’aide du système de gestion des coûts (TRPS) du client distant. Les administrateurs de client utilisent l’authentification moderne pour s’authentifier au TRPS.

### <a name="configuring-access-to-sfbo-at-your-internet-boundary"></a>Configuration de l'accès à SfBO à votre frontière Internet
Pour que SfBO fonctionne correctement (utilisateurs autorisés à participer à des réunions, etc.), les clients doivent configurer leur accès à Internet de sorte que le trafic UDP et TCP sortant vers les services dans le cloud SfBO soit autorisé. Pour plus d’informations, voir ici : https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo 

### <a name="udp-3478-3481-and-tcp-443"></a>UDP 3478-3481 et TCP 443

Les ports UDP 3478-3481 et TCP 443 sont utilisés par les clients pour demander un service auprès du service Edge A/V. Un client utilise ces deux ports pour allouer respectivement des ports UDP et TCP au groupe distant. Pour accéder au service Edge A/V, le client doit d’abord avoir établi une session de signalisation SIP authentifiée auprès du bureau d’enregistrement SfBO pour obtenir des informations d’identification d’authentification du service A/V Edge. Ces valeurs sont envoyées dans le canal de signalisation protégé par le TLS et sont générées par l’ordinateur afin d’atténuer les risques d’attaque par dictionnaire. Les clients peuvent ensuite utiliser ces informations d’identification pour l’authentification de la digestibilité avec le service Edge A/V afin d’allouer des ports à utiliser dans une session multimédia. Une demande d’attribution initiale est envoyée par le client et un message 401 nonce/défi est envoyé par le service Edge A/V. Le client envoie un deuxième nom d’utilisateur contenant le nom d’utilisateur et un hMAC (Hash Message Authentication Code) avec le nom d’utilisateur et non un hachage. 

A sequence number mechanism is also in place to prevent replay attacks. The server calculates the expected HMAC based on its own knowledge of the user name and password and if the HMAC values match, the allocate procedure is carried out. Otherwise, the packet is dropped. This same HMAC mechanism is also applied to subsequent messages within this call session. The lifetime of this user name/password value is a maximum of eight hours at which time the client reacquires a new user name/password for subsequent calls.

### <a name="udptcp-5000059999"></a>UDP/TCP 50 000-59 999
TCP 50,000 outbound is used for SfBO, including for application and desktop sharing, file transfer. UDP/TCP 50,000-59,999 port ranges are used for media sessions with Microsoft Office Communications Server 2007 partners that require NAT/firewall traversal service from the A/V Edge service. Because the A/V Edge service is the sole process using these ports, the size of the port range does not indicate the potential surface of attack. Good security practice is to always minimize the total number of listening ports by not running unnecessary network services. If a network service is not running, it is not exploitable by a remote attacker and the surface of attack of the host computer is reduced. However, within a single service, reducing the number of ports does not provide the same benefit. The A/V Edge service software is no more exposed to attack with 10,000 ports open as it is with 10. The allocation of ports within this range is done randomly and ports not currently allocated do not listen for packets.

### <a name="external-user-av-traffic-traversal"></a>Traversée de trafic A/V des utilisateurs externes
Enabling external users and internal users to exchange media requires an Access Edge service to handle the SIP signaling that is necessary to set up and tear down a session. It also requires an A/V Edge service to act as a relay for the transfer of the media. The call sequence is illustrated in the following figure.


![Séquence d’appel pour rejoindre une réunion](media/sfbo-call-sequence-security.png) 

1. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.<p>L’utilisateur lance la procédure de jointage en cliquant sur l’URL de la réunion dans le courrier électronique, ce qui lance un processus de détection de client sur l’ordinateur de l’utilisateur. Si le client est détecté, ce client est lancé. Si elle n’est pas détectée, l’utilisateur est redirigé vers le client web.<p/>
2. Le client SfBO envoie une INVITATION SIP contenant les informations d’identification de l’utilisateur. Un utilisateur fédéré ou distant participe à une conférence à l’aide de ses informations d’identification d’entreprise. Pour un utilisateur fédéré, l’invitation SIP est tout d’abord envoyée à son serveur principal, qui authentifiera l’utilisateur et le fait parvenir au SfBO. Un utilisateur anonyme est requis pour transmettre l’authentification de la digestibilité.<p>SfBO authenticates the remote or anonymous user and notifies the client. As mentioned in step 2, federated users joining a conference are authenticated by their enterprise.<p/>

3. Le client envoie une demande d’informations pour ajouter l’utilisateur à la conférence A/V.

    Les conférences A/V envoient une réponse Ajouter un utilisateur contenant le jeton à présenter au service Edge de conférence A/V, entre autres informations.

    [Remarque]  Tout le trafic SIP précédent est passé par le service Edge Access.

    The client connects to the A/V Conference Server, which validates the token and proxies the request, which contains another authorization token, to the internal A/V Conferencing Server. The A/V Conferencing Server validates the Authorization Token, which it originally issued over the SIP channel, to further ensure that a valid user is joining the conference.

4. Entre le client et le serveur de conférence A/V, une connexion multimédia est négociation et configurée via le SRTP.
5. A user receives an email containing an invitation to join an SfBO meeting. The email contains a conference key and a HTTP-based URL linking to the conference. Both the key and the URL are unique for a particular meeting.

### <a name="federation-safeguards-for-sfbo"></a>Protections de la fédération pour SfBO
La fédération offre à votre organisation la possibilité de communiquer avec d’autres organisations pour partager la messagerie instantanée et les informations de présence. Dans la fédération SfBO, cette fonction est déjà optionnée par défaut. Toutefois, les administrateurs des clients ont la possibilité de contrôler ceci via le portail d’administration Microsoft 365 ou Office 365. En savoir plus.

## <a name="addressing-threats-to-sfbo-conferences"></a>Répondre aux menaces pesant sur les conférences SFBO

SfBO offre aux utilisateurs d’entreprise la possibilité de créer et de rejoindre des conférences web en temps réel. Les utilisateurs d’entreprise peuvent également inviter des utilisateurs externes qui n’ont pas de compte AAD, Microsoft 365 ou Office 365 à participer à ces réunions. Les utilisateurs qui sont salariés par des partenaires fédérés ayant une identité sécurisée et authentifiée peuvent également participer à des réunions et, s’ils sont promus pour le faire, agir en tant que présentateurs. Les utilisateurs anonymes ne peuvent pas créer ou rejoindre une réunion en tant que présentateur, mais peuvent être promus présentateurs après avoir rejoint la réunion.

Enabling external users to participate in SfBO meetings greatly increases the value of this feature, but it also entails some security risks. To address these risks, SfBO provides the following additional safeguards:
- Les rôles de participant déterminent les privilèges de contrôle de conférence.
- Les types de participants vous permettent de limiter l’accès à des réunions spécifiques.
- Les types de réunion définis déterminent quels types de participants peuvent participer.
- La programmation des conférences est réservée aux utilisateurs disposant d'un compte AAD et d’une licence SFBO.
- Anonymous, that is, unauthenticated, users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.

### <a name="participant-roles"></a>Rôles des participants
Les participants à la réunion se répartissent en trois groupes, chacun ayant ses propres privilèges et restrictions :
-  &nbsp; Organisateur &nbsp; Utilisateur qui crée une réunion, que ce soit improvisée ou en programmant. Un organisateur doit être un utilisateur d’entreprise authentifié et contrôler tous les aspects des utilisateurs finaux d’une réunion.
-  &nbsp; Présentateur &nbsp; Un utilisateur autorisé à présenter des informations lors d’une réunion, à l’aide de tout support multimédia pris en charge. Par définition, l’organisateur d’une réunion est également un présentateur et détermine qui d’autre peut être présentateur. Un organisateur peut prendre cette décision lorsqu’une réunion est prévue ou en cours.
-  &nbsp; Participant &nbsp; Utilisateur qui a été invité à participer à une réunion, mais qui n’est pas autorisé à agir en tant que présentateur.

Un présentateur peut également promouvoir un participant au rôle de présentateur pendant la réunion.

### <a name="participant-types"></a>Types de participants

Meeting participants are also categorized by location and credentials. You can use both of these characteristics to specify which users can have access to specific meetings. Users can be divided broadly into the following categories:
1.  **Utilisateurs appartenant au client** &nbsp; &nbsp; Ces utilisateurs ont des informations d’identification dans Azure Active Directory pour le client.<br/> a. *Inside corpnet* – These users are joining from inside the corporate network.<br/>b. *Remote users* – These users are joining from outside the corporate network. They can include employees who are working at home or on the road, and others, such as employees of trusted vendors, who have been granted enterprise credentials for their terms of service. Remote users can create and join conferences and act as presenters.
2.  **Utilisateurs n'appartenant pas au client** &nbsp;&nbsp; Ces utilisateurs n'ont pas d'informations d'identification dans Azure Active Directory pour le client.<br/>a. *Utilisateurs fédérés* : les utilisateurs fédérés possèdent des informations d’identification valides avec des partenaires fédérés et sont par conséquent traités comme authentifiés par SfBO. Les utilisateurs fédérés peuvent participer à des conférences et être promus comme présentateurs après avoir rejoint la réunion, mais ils ne peuvent pas créer de conférences dans les entreprises avec lesquelles ils sont fédérés.<br/>b. *Anonymous Users* - Anonymous users do not have an Active Directory identity and are not federated with the tenant. 

Customer data shows that many conferences involve external users. Those same customers also want reassurance about the identity of external users before allowing those users to join a conference. As the following section describes, SfBO limits meeting access to those user types that have been explicitly allowed and requires all user types to present appropriate credentials when entering a meeting.

### <a name="participant-admittance"></a>Admission des participants
In SfBO, anonymous users are transferred to a waiting area called the lobby. Presenters can then either admit these users to the meeting or reject them. These users are transferred to the lobby, the leader is notified, and the users then wait until a leader either accepts or rejects them or their connection times out. While in the lobby, the users hear music. 

Par défaut, les participants qui se connectent à partir du RTPC vont directement à la réunion, mais cette option peut être modifiée pour forcer les participants à entrer dans le salle d’attente.  
Meeting organizers control whether participants can join a meeting without waiting in the lobby. Each meeting can be set up to enable access using any one of the following methods:
- **Seul moi, l’organisateur de la réunion**&nbsp;&nbsp;Tout le monde sauf l’organisateur doit attendre dans la salle d’attente jusqu’à ce qu’à l’admission.
- **Les personnes que j’invite dans mon entreprise**&nbsp;&nbsp;Toute personne de votre entreprise peut participer directement à la réunion, même si elle n'est pas invitée.
- **Toute personne de mon organisation** &nbsp; &nbsp; Tous les utilisateurs de SfBO dans le client Microsoft 365 ou Office 365 peuvent participer à la réunion sans attendre dans la salle d’attente, même ceux qui ne sont pas dans la liste de distribution. Tous les autres utilisateurs, y compris les utilisateurs externes et anonymes, doivent patienter dans la salle d’attente jusqu’à leur admission.
- **Tout le monde** &nbsp; &nbsp; Toute personne (aucune restriction) qui a accès au lien de la réunion accède directement à la réunion. Lorsqu’une méthode quelconque, à l’exception de l’Organisateur (verrouillé uniquement) est spécifiée, l’organisateur de la réunion peut également spécifier les personnes qui se appellent par téléphone, sans passer par la salle d’salle d’accueil. 

### <a name="presenter-capabilities"></a>Fonctions du présentateur
Meeting organizers control whether participants can present during a meeting. Each meeting can be set up to limit presenters to any one of the following:
- **Organisateur uniquement** &nbsp; &nbsp; Seul l’organisateur de la réunion peut faire la présentation.
- **Personnes de mon entreprise** &nbsp; &nbsp; Tous les utilisateurs internes peuvent faire une présentation.
- **Tout le monde, y compris les personnes extérieures à ma société** &nbsp; &nbsp; Tous les personnes qui rejoignent la réunion (aucune restriction) peuvent faire une présentation.
- **Les personnes que je choisis**&nbsp;&nbsp;L’organisateur de la réunion précise quels utilisateurs peuvent présenter en les ajoutant à une liste de présentateurs.

## <a name="related-topics"></a>Sujets associés
[Centre de gestion de la confidentialité Microsoft](https://microsoft.com/trustcenter)

