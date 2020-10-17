---
title: 'Lync Server 2013 : menaces de sécurité courantes lors de l’informatique moderne'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60197a65bb0362b1bbdcf3fee779ed503af00eb6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526131"
---
# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="ed594-102">Menaces de sécurité courantes lors de l’informatique moderne</span><span class="sxs-lookup"><span data-stu-id="ed594-102">Common security threats in modern day computing</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed594-103">_**Dernière modification de la rubrique :** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="ed594-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="ed594-104">Étant donné que Lync Server 2013 est un système de communication d’entreprise, vous devez être conscient des attaques de sécurité courantes susceptibles d’avoir une incidence sur son infrastructure et ses communications.</span><span class="sxs-lookup"><span data-stu-id="ed594-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="ed594-105">Attaque par clé compromise</span><span class="sxs-lookup"><span data-stu-id="ed594-105">Compromised-Key Attack</span></span>

<span data-ttu-id="ed594-106">Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations confidentielles.</span><span class="sxs-lookup"><span data-stu-id="ed594-106">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="ed594-107">Il existe deux clés sensibles utilisées dans l’infrastructure à clé publique (PKI) qui doivent être considérées comme suit :.</span><span class="sxs-lookup"><span data-stu-id="ed594-107">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="ed594-108">La clé privée que chaque détenteur de certificat a</span><span class="sxs-lookup"><span data-stu-id="ed594-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="ed594-109">La clé de session utilisée après l’identification et l’échange de clés de session réussies par les partenaires communicants.</span><span class="sxs-lookup"><span data-stu-id="ed594-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="ed594-110">Une attaque par clé compromise se produit lorsque l’intrus détermine la clé privée ou la clé de session.</span><span class="sxs-lookup"><span data-stu-id="ed594-110">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="ed594-111">Lorsque l’intrus parvient à déterminer la clé, il s’en sert pour déchiffrer des données chiffrées, à l’insu de l’expéditeur des données.</span><span class="sxs-lookup"><span data-stu-id="ed594-111">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="ed594-112">Lync Server 2013 utilise les fonctionnalités de l’infrastructure à clé publique dans le système d’exploitation Windows Server pour protéger les données clés utilisées pour le chiffrement des connexions TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="ed594-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="ed594-113">Les clés utilisées pour le chiffrement multimédia sont échangées via des connexions TLS.</span><span class="sxs-lookup"><span data-stu-id="ed594-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="ed594-114">Attaque réseau par déni de service</span><span class="sxs-lookup"><span data-stu-id="ed594-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="ed594-115">L' *attaque par déni de service* se produit lorsque l’agresseur empêche l’utilisation et la fonction réseau normales par les utilisateurs valides.</span><span class="sxs-lookup"><span data-stu-id="ed594-115">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="ed594-116">Cette opération est réalisée lorsque l’agresseur inonde le service de demandes légitimes qui inondent l’utilisation du service par des utilisateurs légitimes.</span><span class="sxs-lookup"><span data-stu-id="ed594-116">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="ed594-117">À l’aide d’une attaque par déni de service, l’agresseur peut effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed594-117">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="ed594-118">envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;</span><span class="sxs-lookup"><span data-stu-id="ed594-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="ed594-119">envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;</span><span class="sxs-lookup"><span data-stu-id="ed594-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="ed594-120">masquer les signes d’attaque ;</span><span class="sxs-lookup"><span data-stu-id="ed594-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="ed594-121">empêcher les utilisateurs d’accéder aux ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="ed594-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="ed594-122">Écoute clandestine (reniflage, espionnage)</span><span class="sxs-lookup"><span data-stu-id="ed594-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="ed594-123">Une *écoute clandestine* peut se produire lorsqu’un agresseur accède au chemin des données d’un réseau et qu’il a la possibilité de surveiller et de lire le trafic.</span><span class="sxs-lookup"><span data-stu-id="ed594-123">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="ed594-124">Il s’agit également de *reniflage* ou d' *espionnage*.</span><span class="sxs-lookup"><span data-stu-id="ed594-124">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="ed594-125">Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données.</span><span class="sxs-lookup"><span data-stu-id="ed594-125">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="ed594-126">Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données.</span><span class="sxs-lookup"><span data-stu-id="ed594-126">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="ed594-127">La recommandation et le paramétrage par défaut du trafic au sein de Microsoft Lync Server 2013 consiste à utiliser Mutual TLS (MTLS) entre les serveurs approuvés et TLS entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="ed594-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="ed594-128">Cette mesure de protection rendrait une attaque très difficile ou impossible à réaliser pendant la période pendant laquelle une conversation donnée a lieu.</span><span class="sxs-lookup"><span data-stu-id="ed594-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="ed594-129">TLS authentifie toutes les parties et chiffre tout le trafic.</span><span class="sxs-lookup"><span data-stu-id="ed594-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="ed594-130">Cela n’empêche pas les écoutes, mais l’agresseur ne peut pas lire le trafic, sauf si le chiffrement est rompu.</span><span class="sxs-lookup"><span data-stu-id="ed594-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="ed594-131">Le protocole Traversal NAT (TURN) de relais n’impose pas le chiffrement du trafic et les informations qu’il envoie sont protégées par l’intégrité des messages.</span><span class="sxs-lookup"><span data-stu-id="ed594-131">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="ed594-132">Bien qu’elle soit ouverte aux écoutes, les informations envoyées (c’est-à-dire, les adresses IP et le port) peuvent être extraites directement en examinant simplement les adresses source et de destination des paquets.</span><span class="sxs-lookup"><span data-stu-id="ed594-132">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="ed594-133">Le service Edge A/V garantit que les données sont valides en vérifiant l’intégrité des messages à l’aide de la clé dérivée de quelques éléments, y compris un mot de passe de retour, qui n’est jamais envoyé en texte clair.</span><span class="sxs-lookup"><span data-stu-id="ed594-133">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="ed594-134">Si le protocole SRTP (Secure Real Time Protocol) est utilisé, le trafic multimédia est également chiffré.</span><span class="sxs-lookup"><span data-stu-id="ed594-134">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="ed594-135">Usurpation d’identité (usurpation d’adresse IP)</span><span class="sxs-lookup"><span data-stu-id="ed594-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="ed594-136">L' *usurpation* se produit lorsque l’agresseur détermine et utilise une adresse IP d’un réseau, d’un ordinateur ou d’un composant réseau sans être autorisé à le faire.</span><span class="sxs-lookup"><span data-stu-id="ed594-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="ed594-137">Une attaque réussie permet à l’agresseur de fonctionner comme s’il s’agissait de l’entité normalement identifiée par l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="ed594-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="ed594-138">Dans le contexte de Microsoft Lync Server 2013, cette situation ne s’exécute que si un administrateur a réalisé les deux opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed594-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="ed594-139">Connexions configurées qui prennent uniquement en charge le protocole TCP (Transmission Control Protocol) (ce qui n’est pas recommandé, car les communications TCP ne sont pas chiffrées).</span><span class="sxs-lookup"><span data-stu-id="ed594-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="ed594-140">Marqué les adresses IP de ces connexions en tant qu’hôtes approuvés.</span><span class="sxs-lookup"><span data-stu-id="ed594-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="ed594-141">Il s’agit moins d’un problème pour les connexions TLS (Transport Layer Security), car TLS authentifie toutes les parties et chiffre tout le trafic.</span><span class="sxs-lookup"><span data-stu-id="ed594-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="ed594-142">L’utilisation de TLS empêche une personne malveillante d’effectuer une usurpation d’adresse IP sur une connexion spécifique (par exemple, les connexions Mutual TLS).</span><span class="sxs-lookup"><span data-stu-id="ed594-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="ed594-143">Toutefois, un agresseur peut toujours usurper l’adresse du serveur DNS utilisé par Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed594-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="ed594-144">Toutefois, étant donné que l’authentification dans Lync est effectuée avec des certificats, un agresseur ne dispose pas d’un certificat valide requis pour usurper l’une des parties dans la communication.</span><span class="sxs-lookup"><span data-stu-id="ed594-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="ed594-145">Attaque de l’intercepteur</span><span class="sxs-lookup"><span data-stu-id="ed594-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="ed594-146">Une attaque de l’intercepteur se produit lorsqu’un agresseur redirige la communication entre deux utilisateurs par le biais de l’ordinateur de l’agresseur sans avoir connaissance des deux utilisateurs communicants.</span><span class="sxs-lookup"><span data-stu-id="ed594-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="ed594-147">L’agresseur peut surveiller et lire le trafic avant de l’envoyer au destinataire concerné.</span><span class="sxs-lookup"><span data-stu-id="ed594-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="ed594-148">Chaque utilisateur de la communication envoie un trafic vers et reçoit le trafic de l’agresseur, tout en pensant qu’il communique uniquement avec l’utilisateur prévu.</span><span class="sxs-lookup"><span data-stu-id="ed594-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="ed594-149">Cela peut se produire si un agresseur peut modifier les services de domaine Active Directory pour ajouter son serveur en tant que serveur approuvé ou modifier le système DNS (Domain Name System) pour permettre aux clients de se connecter au serveur par l’intermédiaire de l’agresseur.</span><span class="sxs-lookup"><span data-stu-id="ed594-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="ed594-150">Une attaque de l’intercepteur peut également se produire avec le trafic multimédia entre deux clients.</span><span class="sxs-lookup"><span data-stu-id="ed594-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="ed594-151">Toutefois, dans Microsoft Lync Server 2013 point à point, la vidéo et le partage d’application, les flux sont chiffrés avec SRTP, à l’aide de clés de chiffrement négociées entre les homologues qui utilisent le protocole SIP (Session Initiation Protocol) sur TLS.</span><span class="sxs-lookup"><span data-stu-id="ed594-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="ed594-152">Les serveurs tels que la conversation de groupe utilisent le protocole HTTPs pour améliorer la sécurité du trafic Web.</span><span class="sxs-lookup"><span data-stu-id="ed594-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="ed594-153">Attaque par relecture RTP</span><span class="sxs-lookup"><span data-stu-id="ed594-153">RTP Replay Attack</span></span>

<span data-ttu-id="ed594-154">Une *attaque par relecture* se produit lorsqu’une transmission de média valide entre deux parties est interceptée et retransmise à des fins malveillantes.</span><span class="sxs-lookup"><span data-stu-id="ed594-154">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="ed594-155">Les SRTP utilisés dans le cadre d’un protocole de signalisation sécurisé protègent les transmissions des attaques de relecture en permettant au récepteur de maintenir un index des paquets RTP déjà reçus et de comparer chaque nouveau paquet à ceux figurant déjà dans l’index.</span><span class="sxs-lookup"><span data-stu-id="ed594-155">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="ed594-156">Désir</span><span class="sxs-lookup"><span data-stu-id="ed594-156">Spim</span></span>

<span data-ttu-id="ed594-157">*SPIM* désigne les messages instantanés commerciaux non sollicités ou les demandes d’abonnement de présence.</span><span class="sxs-lookup"><span data-stu-id="ed594-157">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="ed594-158">Bien qu’il ne soit pas en soi un compromis du réseau, il est ennuyeux au moins, peut réduire la disponibilité et la production des ressources, et peut entraîner une compromission du réseau.</span><span class="sxs-lookup"><span data-stu-id="ed594-158">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="ed594-159">Par exemple, les utilisateurs se spimmingent mutuellement en envoyant des demandes.</span><span class="sxs-lookup"><span data-stu-id="ed594-159">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="ed594-160">Les utilisateurs peuvent se bloquer pour éviter cela, mais avec la Fédération, si une attaque de spim coordonné est établie, il peut être difficile de la surmonter, sauf si vous désactivez la Fédération pour le partenaire.</span><span class="sxs-lookup"><span data-stu-id="ed594-160">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="ed594-161">Virus et vers</span><span class="sxs-lookup"><span data-stu-id="ed594-161">Viruses and Worms</span></span>

<span data-ttu-id="ed594-162">Un *virus* est une unité de code dont l’objectif est de reproduire des unités de code similaires supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="ed594-162">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="ed594-163">Pour fonctionner, un virus doit être hébergé dans un fichier, un message électronique ou un programme.</span><span class="sxs-lookup"><span data-stu-id="ed594-163">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="ed594-164">Un *ver* est une unité de code dont l’objectif est de reproduire des unités de code similaires, mais il n’a pas besoin d’un hôte.</span><span class="sxs-lookup"><span data-stu-id="ed594-164">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="ed594-165">Les virus et les vers apparaissent principalement lors du transfert de fichiers entre clients ou lorsque d’autres utilisateurs transmettent des URL.</span><span class="sxs-lookup"><span data-stu-id="ed594-165">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="ed594-166">Une fois qu’un virus se trouve sur votre ordinateur, il peut, par exemple, usurper votre identité et envoyer des messages instantanés en votre nom.</span><span class="sxs-lookup"><span data-stu-id="ed594-166">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="ed594-167">Informations d’identification personnelle</span><span class="sxs-lookup"><span data-stu-id="ed594-167">Personally Identifiable Information</span></span>

<span data-ttu-id="ed594-168">Microsoft Lync Server 2013 a le potentiel de divulguer des informations sur un réseau public qui pourrait être lié à un individu.</span><span class="sxs-lookup"><span data-stu-id="ed594-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="ed594-169">Les types d’informations peuvent être divisées en deux catégories spécifiques :</span><span class="sxs-lookup"><span data-stu-id="ed594-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="ed594-170">**Données de présence enrichies** Les données de présence enrichies sont des informations qu’un utilisateur peut choisir de partager ou non via un lien vers un partenaire fédéré ou avec des contacts au sein d’une organisation.</span><span class="sxs-lookup"><span data-stu-id="ed594-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="ed594-171">Ces données ne sont pas partagées avec les utilisateurs d’un réseau de messagerie instantanée public.</span><span class="sxs-lookup"><span data-stu-id="ed594-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="ed594-172">Les stratégies de client et les autres configurations de client peuvent mettre en place un contrôle auprès de l’administrateur système.</span><span class="sxs-lookup"><span data-stu-id="ed594-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="ed594-173">Dans Lync Server 2013, le mode de confidentialité améliorée de la présence peut être configuré pour un utilisateur individuel afin d’empêcher les utilisateurs de Lync ne figurant pas dans la liste des contacts de voir les informations de présence de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed594-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="ed594-174">Le mode de confidentialité de la présence enrichie n’empêche pas les utilisateurs de Microsoft Office Communicator 2007 et de Microsoft Office Communicator 2007 R2 de voir les informations de présence d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed594-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="ed594-175">Pour plus d’informations, voir [what’s New for clients in Lync server 2013](lync-server-2013-what-s-new-for-clients.md) dans la documentation de prise en main et [Configuring Enhanced presence Privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ed594-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ed594-176">**Données obligatoires** Des données obligatoires sont requises pour le bon fonctionnement du serveur ou du client et ne sont pas sous le contrôle de l’administration du client ou du système.</span><span class="sxs-lookup"><span data-stu-id="ed594-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="ed594-177">Il s’agit d’informations nécessaires au niveau d’un serveur ou d’un réseau à des fins de routage, d’état de maintenance et de signalisation.</span><span class="sxs-lookup"><span data-stu-id="ed594-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="ed594-178">Les tableaux suivants répertorient les données exposées sur un réseau public.</span><span class="sxs-lookup"><span data-stu-id="ed594-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="ed594-179">Données de présence enrichies</span><span class="sxs-lookup"><span data-stu-id="ed594-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed594-180">Données divulguées</span><span class="sxs-lookup"><span data-stu-id="ed594-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="ed594-181">Paramètres possibles</span><span class="sxs-lookup"><span data-stu-id="ed594-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed594-182">Données personnelles</span><span class="sxs-lookup"><span data-stu-id="ed594-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="ed594-183">Nom, titre, société, adresse de messagerie, fuseau horaire</span><span class="sxs-lookup"><span data-stu-id="ed594-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed594-184">Numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="ed594-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="ed594-185">Bureau, mobile, domicile</span><span class="sxs-lookup"><span data-stu-id="ed594-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed594-186">Informations de calendrier</span><span class="sxs-lookup"><span data-stu-id="ed594-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="ed594-187">Informations de disponibilité, de notification d’absence de ville, de détails de réunion (pour les personnes ayant accès à votre calendrier)</span><span class="sxs-lookup"><span data-stu-id="ed594-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed594-188">Statut de présence</span><span class="sxs-lookup"><span data-stu-id="ed594-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="ed594-189">Absent, disponible, occupé, ne pas déranger, hors connexion</span><span class="sxs-lookup"><span data-stu-id="ed594-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="ed594-190">Données obligatoires</span><span class="sxs-lookup"><span data-stu-id="ed594-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed594-191">Données divulguées</span><span class="sxs-lookup"><span data-stu-id="ed594-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="ed594-192">Exemple d’informations</span><span class="sxs-lookup"><span data-stu-id="ed594-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed594-193">Adresse IP</span><span class="sxs-lookup"><span data-stu-id="ed594-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="ed594-194">Adresse réelle de l’ordinateur ou de l’adresse de l’adresse de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="ed594-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed594-195">URI SIP</span><span class="sxs-lookup"><span data-stu-id="ed594-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="ed594-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ed594-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

