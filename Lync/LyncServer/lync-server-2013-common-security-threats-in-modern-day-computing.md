---
title: 'Lync Server 2013: menaces de sécurité courantes au sein de l’informatique moderne'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2446ee0755f4544f17f6c04c6059d70576a466f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="c036d-102">Menaces fréquentes pour la sécurité dans l’informatique moderne</span><span class="sxs-lookup"><span data-stu-id="c036d-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c036d-103">_**Dernière modification de la rubrique:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="c036d-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="c036d-104">Dans la mesure où Lync Server 2013 est un système de communication d’entreprise, vous devez tenir compte des attaques courantes de sécurité qui pourraient affecter son infrastructure et ses communications.</span><span class="sxs-lookup"><span data-stu-id="c036d-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="c036d-105">Attaque par clé compromise</span><span class="sxs-lookup"><span data-stu-id="c036d-105">Compromised-Key Attack</span></span>

<span data-ttu-id="c036d-p101">Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations confidentielles. Deux clés de l’infrastructure à clé publique (PKI) sont particulièrement sensibles :</span><span class="sxs-lookup"><span data-stu-id="c036d-p101">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information. There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="c036d-108">la clé privée que possède chaque détenteur de certificat ;</span><span class="sxs-lookup"><span data-stu-id="c036d-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="c036d-109">la clé de session, utilisée après l’identification et l’échange de clé de session entre les partenaires communiquant entre eux.</span><span class="sxs-lookup"><span data-stu-id="c036d-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="c036d-p102">Une attaque par clé compromise se produit lorsqu’un intrus parvient à identifier la clé privée ou la clé de session. Lorsque l’intrus parvient à déterminer la clé, il s’en sert pour déchiffrer des données chiffrées, à l’insu de l’expéditeur des données.</span><span class="sxs-lookup"><span data-stu-id="c036d-p102">A compromised-key attack occurs when the attacker determines the private key or the session key. When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="c036d-112">Lync Server 2013 utilise les fonctionnalités de PKI dans le système d’exploitation Windows Server pour protéger les données clés utilisées pour le chiffrement des connexions TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="c036d-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="c036d-113">Les clés utilisées pour le chiffrement multimédia sont échangées via des connexions TLS.</span><span class="sxs-lookup"><span data-stu-id="c036d-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="c036d-114">Attaque réseau par déni de service</span><span class="sxs-lookup"><span data-stu-id="c036d-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="c036d-p104">Une *attaque par déni de service* se produit lorsqu’une personne malveillante empêche des utilisateurs valides de travailler et d’utiliser le réseau normalement. Pour ce faire, elle inonde le service avec des demandes légitimes qui submergent l’utilisation du service par les utilisateurs légitimes. Lors d’une attaque de ce type, la personne malveillante peut :</span><span class="sxs-lookup"><span data-stu-id="c036d-p104">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users. This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users. By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="c036d-118">envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;</span><span class="sxs-lookup"><span data-stu-id="c036d-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="c036d-119">envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;</span><span class="sxs-lookup"><span data-stu-id="c036d-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="c036d-120">masquer les signes d’attaque ;</span><span class="sxs-lookup"><span data-stu-id="c036d-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="c036d-121">empêcher les utilisateurs d’accéder aux ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="c036d-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="c036d-122">Attaque par écoute (Eavesdropping)</span><span class="sxs-lookup"><span data-stu-id="c036d-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="c036d-p105">Une *attaque par écoute* peut se produire lorsqu’une personne malveillante parvient à accéder au chemin d’accès des données d’un réseau et qu’elle peut ainsi surveiller et lire le trafic. Cette attaque est également appelée *reniflage* (« sniffing ») ou *surveillance* (« snooping »). Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données.</span><span class="sxs-lookup"><span data-stu-id="c036d-p105">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic. This is also called *sniffing* or *snooping*. If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path. An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="c036d-127">Par défaut, le paramétrage du trafic au sein de Microsoft Lync Server 2013 consiste à utiliser Mutual TLS (MTLS) entre les serveurs de confiance et TLS du client vers le serveur.</span><span class="sxs-lookup"><span data-stu-id="c036d-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="c036d-128">Cette mesure de protection rend ce type d’attaque difficile, voire impossible, durant le laps de temps pendant lequel une conversation donnée peut être attaquée.</span><span class="sxs-lookup"><span data-stu-id="c036d-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="c036d-129">Le protocole TLS authentifie toutes les parties et chiffre le trafic.</span><span class="sxs-lookup"><span data-stu-id="c036d-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="c036d-130">Ceci n’empêche pas les attaques par écoute, mais l’intrus ne peut pas lire le trafic à moins que le chiffrement ne soit rompu.</span><span class="sxs-lookup"><span data-stu-id="c036d-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="c036d-p107">Le protocole TURN (Traversal Using Relay NAT) n’exige pas que le trafic soit chiffré. Les informations acheminées sont protégées par l’intégrité des messages. Bien qu’elles puissent faire l’objet d’une attaque par écoute, les informations acheminées (autrement dit, les adresses IP et le port) peuvent être extraites directement, en observant simplement les adresses source et de destination des paquets. Le service Edge A/V s’assure que les données sont valides en vérifiant l’intégrité du message à l’aide d’une clé dérivée de plusieurs éléments, dont un mot de passe TURN, qui n’est jamais transmise en texte en clair. Si le protocole SRTP (Secure Real Time Protocol) est utilisé, le trafic multimédia est également chiffré.</span><span class="sxs-lookup"><span data-stu-id="c036d-p107">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity. Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets. The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text. If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="c036d-135">Usurpation d’identité (usurpation d’adresse IP)</span><span class="sxs-lookup"><span data-stu-id="c036d-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="c036d-136">On parle d’*usurpation d’identité* lorsqu’une personne malveillante parvient à déterminer et à utiliser l’adresse IP d’un réseau, d’un ordinateur ou d’un composant réseau, sans y avoir été autorisée.</span><span class="sxs-lookup"><span data-stu-id="c036d-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="c036d-137">Si l’attaque réussit, l’intrus peut opérer comme s’il était l’utilisateur habituellement identifié par l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="c036d-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="c036d-138">Dans le cadre de Microsoft Lync Server 2013, cette situation ne s’exécute que si un administrateur a réalisé les deux opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="c036d-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="c036d-139">configuré des connexions qui prennent uniquement en charge le protocole TCP (Transmission Control Protocol), ce qui n’est pas recommandé car les communications TCP ne sont pas chiffrées ;</span><span class="sxs-lookup"><span data-stu-id="c036d-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="c036d-140">marqué les adresses IP de ces connexions en tant qu’hôtes approuvés.</span><span class="sxs-lookup"><span data-stu-id="c036d-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="c036d-141">Ce problème est moins grave pour les connexions TLS (Transport Layer Security), car TLS authentifie toutes les parties et chiffre le trafic.</span><span class="sxs-lookup"><span data-stu-id="c036d-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="c036d-142">L’utilisation du protocole TLS empêche une personne malveillante d’usurper une adresse IP sur une connexion spécifique (par exemple, les connexions Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="c036d-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="c036d-143">En revanche, une personne malveillante pourrait toujours usurper l’adresse du serveur DNS utilisé par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c036d-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="c036d-144">Toutefois, dans la mesure où l’authentification dans Lync est effectuée avec des certificats, l’attaquant ne dispose pas d’un certificat valide requis pour usurper une des parties de la communication.</span><span class="sxs-lookup"><span data-stu-id="c036d-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="c036d-145">Attaque de l’intercepteur (« man-in-the-middle »)</span><span class="sxs-lookup"><span data-stu-id="c036d-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="c036d-146">Une attaque de l’intercepteur se produit lorsqu’une personne malveillante redirige les communications entre deux utilisateurs via son propre ordinateur, à l’insu des deux participants.</span><span class="sxs-lookup"><span data-stu-id="c036d-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="c036d-147">L’intrus peut surveiller et lire le trafic avant de l’acheminer vers le destinataire concerné.</span><span class="sxs-lookup"><span data-stu-id="c036d-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="c036d-148">Chacun des utilisateurs envoie et reçoit du trafic vers/de l’intrus, alors qu’il pense communiquer avec l’utilisateur concerné uniquement.</span><span class="sxs-lookup"><span data-stu-id="c036d-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="c036d-149">Cela peut se produire si une personne malveillante modifie les services de domaine Active Directory pour ajouter son serveur en tant que serveur approuvé, ou si elle modifie DNS (Domain Name System) pour faire en sorte que les clients se connectent au serveur via l’ordinateur de l’intrus à l’origine de l’attaque.</span><span class="sxs-lookup"><span data-stu-id="c036d-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="c036d-150">Une attaque de l’intercepteur peut également affecter le trafic multimédia entre deux clients.</span><span class="sxs-lookup"><span data-stu-id="c036d-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="c036d-151">Néanmoins, dans Microsoft Lync Server 2013, les flux audio et vidéo, et le partage d’applications, les flux sont chiffrés avec SRTP, à l’aide de clés de chiffrement négociées entre les homologues utilisant le protocole SIP (Session Initiation Protocol) sur TLS.</span><span class="sxs-lookup"><span data-stu-id="c036d-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="c036d-152">Les serveurs tels que le serveur de conversation de groupe utilisent le protocole HTTPS pour sécuriser le trafic.</span><span class="sxs-lookup"><span data-stu-id="c036d-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="c036d-153">Attaque par relecture RTP</span><span class="sxs-lookup"><span data-stu-id="c036d-153">RTP Replay Attack</span></span>

<span data-ttu-id="c036d-p111">Une *attaque par relecture* se produit lorsqu’une transmission multimédia valide entre deux correspondants est interceptée, puis retransmise à des fins malveillantes. L’utilisation de SRTP avec un protocole de signalisation sécurisé protège les transmissions contre les attaques par relecture. En effet, le destinataire est alors en mesure d’établir un index des paquets RTP déjà reçus et de comparer chaque nouveau paquet à ceux répertoriés dans l’index.</span><span class="sxs-lookup"><span data-stu-id="c036d-p111">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="c036d-156">Messages instantanés indésirables (Spim)</span><span class="sxs-lookup"><span data-stu-id="c036d-156">Spim</span></span>

<span data-ttu-id="c036d-p112">Le *spim* correspond à des messages instantanés commerciaux ou des demandes d’abonnement aux informations de présence non sollicités. S’il ne constitue pas à lui seul une menace envers le réseau, il peut néanmoins perturber les activités des utilisateurs et avoir un impact négatif sur la disponibilité des ressources et la production. Il représente donc un risque potentiel pour le réseau. Prenons le cas d’utilisateurs qui génèrent du spim en s’envoyant mutuellement des demandes. Un utilisateur peut en bloquer un autre pour ne plus recevoir de messages instantanés indésirables. Toutefois, dans le cas de la fédération, il peut s’avérer difficile de faire face à une attaque de spim coordonnée, à moins de désactiver la fédération pour le partenaire.</span><span class="sxs-lookup"><span data-stu-id="c036d-p112">*Spim* is unsolicited commercial instant messages or presence subscription requests. While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network. An example of this is users spimming each other by sending requests. Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="c036d-161">Virus et vers</span><span class="sxs-lookup"><span data-stu-id="c036d-161">Viruses and Worms</span></span>

<span data-ttu-id="c036d-p113">Un *virus* est une unité de code dont le seul rôle consiste à reproduire d’autres unités de code similaires. Pour fonctionner, un virus doit être hébergé dans un fichier, un courrier électronique ou un programme. Un *ver* est une unité de code programmée pour reproduire d’autres unités de code similaires. Toutefois, il n’est pas nécessaire qu’il soit hébergé. Les virus et les vers apparaissent principalement lors du transfert de fichiers entre clients ou lorsque d’autres utilisateurs transmettent des URL. Une fois qu’un virus se trouve sur votre ordinateur, il peut, par exemple, usurper votre identité et envoyer des messages instantanés à votre nom.</span><span class="sxs-lookup"><span data-stu-id="c036d-p113">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units. To work, a virus needs a host, such as a file, email, or program. A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host. Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users. If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="c036d-167">Informations d’identification personnelle</span><span class="sxs-lookup"><span data-stu-id="c036d-167">Personally Identifiable Information</span></span>

<span data-ttu-id="c036d-168">Microsoft Lync Server 2013 est en mesure de divulguer des informations sur un réseau public qui peuvent être liées à une personne.</span><span class="sxs-lookup"><span data-stu-id="c036d-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="c036d-169">Ces informations appartiennent à deux catégories :</span><span class="sxs-lookup"><span data-stu-id="c036d-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="c036d-170">**Données de présence améliorées** Les données de présence améliorées sont des informations que les utilisateurs peuvent choisir de partager ou de ne pas partager sur un lien vers un partenaire fédéré ou avec des contacts au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="c036d-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="c036d-171">Elles ne sont pas partagées avec les utilisateurs d’un réseau public de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="c036d-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="c036d-172">Selon les stratégies de groupe en vigueur et la configuration du client, l’administrateur système peut contrôler ces informations.</span><span class="sxs-lookup"><span data-stu-id="c036d-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="c036d-173">Dans Lync Server 2013, le mode de confidentialité Enhanced presence peut être configuré pour un utilisateur individuel afin d’empêcher les utilisateurs de Lync d’avoir à voir les informations de présence de l’utilisateur dans la liste des contacts de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c036d-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="c036d-174">Le mode de confidentialité de présence enrichie n’empêche pas les utilisateurs de Microsoft Office Communicator 2007 et Microsoft Office Communicator 2007 R2 de voir les informations de présence d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c036d-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="c036d-175">Pour plus d’informations, reportez-vous aux [nouveautés pour les clients dans Lync server 2013](lync-server-2013-what-s-new-for-clients.md) dans la documentation de mise en route et [configuration du mode de confidentialité de présence avancée dans Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c036d-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="c036d-176">**Données obligatoires** Des données obligatoires sont nécessaires pour le bon fonctionnement du serveur ou du client et ne sont pas sous le contrôle de l’administration du client ou du système.</span><span class="sxs-lookup"><span data-stu-id="c036d-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="c036d-177">Il s’agit d’informations nécessaires au niveau du serveur ou du réseau aux fins de routage, de maintenance de l’État et de signalisation.</span><span class="sxs-lookup"><span data-stu-id="c036d-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="c036d-178">Les tableaux suivants répertorient les données exposées sur un réseau public.</span><span class="sxs-lookup"><span data-stu-id="c036d-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="c036d-179">Données de présence enrichie</span><span class="sxs-lookup"><span data-stu-id="c036d-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c036d-180">Données divulguées</span><span class="sxs-lookup"><span data-stu-id="c036d-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="c036d-181">Paramètres possibles</span><span class="sxs-lookup"><span data-stu-id="c036d-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c036d-182">Données personnelles</span><span class="sxs-lookup"><span data-stu-id="c036d-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="c036d-183">Nom, Fonction, Société, Adresse électronique, Fuseau horaire</span><span class="sxs-lookup"><span data-stu-id="c036d-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c036d-184">Numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="c036d-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="c036d-185">Bureau, Mobile, Domicile</span><span class="sxs-lookup"><span data-stu-id="c036d-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c036d-186">Informations de calendrier</span><span class="sxs-lookup"><span data-stu-id="c036d-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="c036d-187">Libre/Occupé(e), notification d’absence du bureau, détails de réunion (pour les personnes ayant accès à votre calendrier)</span><span class="sxs-lookup"><span data-stu-id="c036d-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c036d-188">Statut de présence</span><span class="sxs-lookup"><span data-stu-id="c036d-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="c036d-189">Absent(e), Disponible, Occupé(e), Ne pas déranger, Hors connexion</span><span class="sxs-lookup"><span data-stu-id="c036d-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="c036d-190">Données obligatoires</span><span class="sxs-lookup"><span data-stu-id="c036d-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c036d-191">Données divulguées</span><span class="sxs-lookup"><span data-stu-id="c036d-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="c036d-192">Exemples d’informations</span><span class="sxs-lookup"><span data-stu-id="c036d-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c036d-193">Adresse IP</span><span class="sxs-lookup"><span data-stu-id="c036d-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="c036d-194">Adresse réelle de l’ordinateur ou adresse traduite via NAT</span><span class="sxs-lookup"><span data-stu-id="c036d-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c036d-195">URI SIP</span><span class="sxs-lookup"><span data-stu-id="c036d-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="c036d-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c036d-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

