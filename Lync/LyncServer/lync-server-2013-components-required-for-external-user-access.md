---
title: 'Lync Server 2013 : composants requis pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e225f63da97ea48d98a5a2540a6b35a9c63c08f2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="ef3b8-102">Composants requis pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef3b8-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef3b8-103">_**Dernière modification de la rubrique :** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="ef3b8-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="ef3b8-104">La plupart des composants Edge sont déployés dans un réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="ef3b8-105">Les deux composants suivants forment la topologie de périphérie du réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="ef3b8-106">Sauf indication contraire, les composants font partie des [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) et se trouvent dans le réseau de périmètre.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="ef3b8-107">Ces composants de périphérie sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="ef3b8-107">Edge components include the following:</span></span>

  - <span data-ttu-id="ef3b8-108">Serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="ef3b8-108">Edge Servers</span></span>

  - <span data-ttu-id="ef3b8-109">Proxys inverses</span><span class="sxs-lookup"><span data-stu-id="ef3b8-109">Reverse proxies</span></span>

  - <span data-ttu-id="ef3b8-110">Pare-feu</span><span class="sxs-lookup"><span data-stu-id="ef3b8-110">Firewalls</span></span>

  - <span data-ttu-id="ef3b8-111">Directeurs (facultatifs et logiquement situés sur le réseau interne)</span><span class="sxs-lookup"><span data-stu-id="ef3b8-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="ef3b8-112">Équilibrage de la charge pour les topologies Edge mises à l’échelle (avec charge DNS équilibrée ou un programme d’équilibrage de la charge matérielle)</span><span class="sxs-lookup"><span data-stu-id="ef3b8-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ef3b8-p102">L’utilisation de l’équilibrage de la charge DNS sur une interface et de l’équilibrage de la charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser soit l’équilibrage de la charge matérielle, soit l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="ef3b8-115">Serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="ef3b8-115">Edge Servers</span></span>

<span data-ttu-id="ef3b8-116">Les serveurs Edge envoient et reçoivent le trafic réseau pour les services offerts par les utilisateurs externes par le déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="ef3b8-117">Il exécute les services suivants :</span><span class="sxs-lookup"><span data-stu-id="ef3b8-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="ef3b8-118">**Service Edge d’accès**   le service Edge d’accès fournit un point de connexion unique et approuvé pour le trafic SIP (Session Initiation Protocol) entrant et sortant.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="ef3b8-119">**Service Edge de conférence Web**   le service Edge de conférence Web permet aux utilisateurs externes de rejoindre des réunions hébergées sur votre déploiement interne de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="ef3b8-120">**Service Edge a/v**   le service Edge a/v rend l’audio, la vidéo, le partage d’application et le transfert de fichiers accessibles aux utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="ef3b8-121">Vos utilisateurs peuvent ajouter de l’audio et de la vidéo à des réunions qui incluent des participants externes et ils peuvent communiquer à l’aide de l’audio et/ou de la vidéo directement avec un utilisateur externe dans les sessions de point à point.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="ef3b8-122">Le service Edge A/V fournit également une prise en charge pour le partage du Bureau et le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="ef3b8-123">**Service proxy XMPP**   le service proxy XMPP accepte et envoie les messages XMPP (extensible Messaging and Presence Protocol) vers et depuis les partenaires fédérés XMPP configurés.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="ef3b8-124">Les utilisateurs externes autorisés peuvent accéder aux serveurs Edge afin de se connecter à votre déploiement interne de Lync Server 2013, mais les serveurs Edge ne permettent pas d’autres accès au réseau interne.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef3b8-125">Les serveurs Edge sont déployés pour fournir des connexions pour les clients Lync activés et d’autres serveurs Microsoft Edge (comme dans les scénarios de Fédération).</span><span class="sxs-lookup"><span data-stu-id="ef3b8-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="ef3b8-126">Ils ne sont pas conçus pour autoriser les connexions d’autres types de client d’extrémité ou de serveur.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="ef3b8-127">Le serveur de passerelle XMPP peut être déployé pour autoriser les connexions avec les partenaires XMPP configurés.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="ef3b8-128">Le serveur Edge et la passerelle XMPP peuvent uniquement prendre en charge les connexions d’extrémité à partir de ces types de client et de fédération.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="ef3b8-129">Proxy inverse</span><span class="sxs-lookup"><span data-stu-id="ef3b8-129">Reverse Proxy</span></span>

<span data-ttu-id="ef3b8-130">Le proxy inverse est requis pour les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ef3b8-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="ef3b8-131">permettre aux utilisateurs de participer à des réunions ou à des conférences à distance via des URL simples ;</span><span class="sxs-lookup"><span data-stu-id="ef3b8-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="ef3b8-132">permettre aux utilisateurs externes de télécharger le contenu de réunions ;</span><span class="sxs-lookup"><span data-stu-id="ef3b8-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="ef3b8-133">permettre aux utilisateurs externes de développer des groupes de distribution ;</span><span class="sxs-lookup"><span data-stu-id="ef3b8-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="ef3b8-134">permettre à l’utilisateur d’obtenir un certificat utilisateur pour l’authentification basée sur un certificat client ;</span><span class="sxs-lookup"><span data-stu-id="ef3b8-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="ef3b8-135">permettre aux utilisateurs distants de télécharger des fichiers à partir du serveur de carnet d’adresses ou soumettre des requêtes au service de requête web du carnet d’adresses ;</span><span class="sxs-lookup"><span data-stu-id="ef3b8-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="ef3b8-136">permettre aux utilisateurs distants d’obtenir des mises à jour de logiciels clients et de périphériques ;</span><span class="sxs-lookup"><span data-stu-id="ef3b8-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="ef3b8-137">permettre aux appareils mobiles de découvrir automatiquement les serveurs frontaux qui proposent des services de mobilité ;</span><span class="sxs-lookup"><span data-stu-id="ef3b8-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="ef3b8-138">permettre d’envoyer des notifications push aux appareils mobiles depuis les services de notification push Office 365 ou Apple.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="ef3b8-139">Pour plus d’informations sur les proxys inverses et sur les exigences auxquelles doivent répondre les proxys inverses, voir les détails relatifs à la [Configuration requise pour le proxy inverse dans Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="ef3b8-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef3b8-140">Les utilisateurs externes n’ont pas besoin d’une connexion de réseau privé virtuel (VPN) à votre organisation afin de participer aux communications à l’aide de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="ef3b8-141">Si vous avez implémenté la technologie VPN dans votre organisation et que vos utilisateurs utilisent le VPN pour Lync, le trafic multimédia (par exemple, la vidéoconférence) peut être compromis.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="ef3b8-142">Vous devez envisager de permettre au trafic multimédia de se connecter directement au service Edge AV et de contourner le VPN.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="ef3b8-143">Pour plus d’informations, reportez-vous à l’article du blog NextHop, « activation de médias <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>Lync pour contourner un tunnel VPN », à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="ef3b8-144">-</span><span class="sxs-lookup"><span data-stu-id="ef3b8-144">Firewall</span></span>

<span data-ttu-id="ef3b8-145">Vous pouvez déployer votre topologie de périmètre avec un seul pare-feu externe ou un pare-feu interne et un pare-feu externe.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="ef3b8-146">Les architectures de scénario incluent deux pare-feu.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="ef3b8-147">Il est recommandé d’utiliser deux pare-feu pour garantir le routage strict d’un côté du réseau à l’autre et protéger votre déploiement interne derrière deux niveaux de pare-feu.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="ef3b8-148">48000b</span><span class="sxs-lookup"><span data-stu-id="ef3b8-148">Director</span></span>

<span data-ttu-id="ef3b8-149">Un directeur est un rôle serveur distinct et facultatif dans Lync Server 2013 qui n’utilise pas de compte d’utilisateur personnel, ou fournit des services de présence ou de conférence.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="ef3b8-150">Il sert de serveur de tronçon suivant interne vers lequel un serveur Edge achemine le trafic SIP entrant destiné aux serveurs internes.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="ef3b8-151">Le directeur authentifie les demandes entrantes et les redirige vers le serveur ou le pool d’accueil de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="ef3b8-152">En préauthentifiant le directeur, vous pouvez supprimer des demandes de comptes d’utilisateurs qui ne sont pas répertoriés dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="ef3b8-153">Un directeur aide à isoler les serveurs Standard Edition et les serveurs frontaux dans les pools frontaux Enterprise Edition du trafic malveillant, tels que les attaques par déni de service (DoS).</span><span class="sxs-lookup"><span data-stu-id="ef3b8-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="ef3b8-154">Si le réseau est inondé avec du trafic externe non valide lors d’une attaque de ce type, le trafic se termine au niveau du directeur.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="ef3b8-155">Pour plus d’informations sur l’utilisation des directeurs, reportez-vous à [la rubrique Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="ef3b8-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ef3b8-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef3b8-156">See Also</span></span>


[<span data-ttu-id="ef3b8-157">Configuration requise pour le programme d’équilibrage de la charge matérielle pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef3b8-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

