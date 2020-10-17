---
title: Planification de SIP, de la Fédération XMPP et de la messagerie instantanée publique
description: Planification de SIP, de la Fédération XMPP et de la messagerie instantanée publique.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c28c9c75310c884ea00117be2458384d408daae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564060"
---
# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="887b2-103">Planification de SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887b2-103">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="887b2-104">_**Dernière modification de la rubrique :** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="887b2-104">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="887b2-105">Les serveurs Edge peuvent être configurés pour permettre à vos utilisateurs internes et externes d’accéder aux contacts au niveau des organisations ou des services partenaires.</span><span class="sxs-lookup"><span data-stu-id="887b2-105">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="887b2-106">Ces accords partenaires, que l’on appelle « fédérations », peuvent fournir tout ou partie des fonctionnalités suivantes entre les contacts de votre organisation et ceux de la fédération partenaire :</span><span class="sxs-lookup"><span data-stu-id="887b2-106">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="887b2-107">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="887b2-107">Instant messaging and presence</span></span>

  - <span data-ttu-id="887b2-108">Collaboration et conférence (par exemple, conférence web)</span><span class="sxs-lookup"><span data-stu-id="887b2-108">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="887b2-109">Audioconférence, vidéoconférence ou les deux</span><span class="sxs-lookup"><span data-stu-id="887b2-109">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="887b2-110">Dans certains cas, la communication, par exemple, la messagerie instantanée et la présence entre un contact Microsoft Lync Server 2013 et un contact XMPP (extensible Messaging and Presence Protocol), est à l’égal à homologue : ne prenez en charge que vous et le contact du partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="887b2-110">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="887b2-111">Dans d’autres cas, tels qu’un Lync Server, Lync Server 2010 à la Fédération Lync Server 2013, plusieurs participants peuvent être invités à participer à la conversation.</span><span class="sxs-lookup"><span data-stu-id="887b2-111">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="887b2-112">Fédération Lync Server et Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="887b2-112">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="887b2-113">La Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server prend en charge les communications entre homologues et plusieurs parties.</span><span class="sxs-lookup"><span data-stu-id="887b2-113">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="887b2-114">Les communications d’égal à égal peuvent devenir des conversions à plusieurs utilisateurs, ce qui permet d’organiser des réunions ad hoc.</span><span class="sxs-lookup"><span data-stu-id="887b2-114">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="887b2-115">Des réunions (conférences web ou conférences audiovisuelles) peuvent être programmées pour inclure des contacts de votre organisation, ainsi que des contacts des partenaires avec lesquels vous appliquez la fédération.</span><span class="sxs-lookup"><span data-stu-id="887b2-115">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="887b2-116">La Fédération s’est d’abord affichée dans Microsoft Office Live Communications Server 2005 et prend en charge un type de Fédération directe.</span><span class="sxs-lookup"><span data-stu-id="887b2-116">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="887b2-117">La Fédération directe exigeait que vous connaissiez le domaine SIP (Session Initiation Protocol) du partenaire de Fédération et le nom de domaine complet (FQDN) du serveur Edge du partenaire.</span><span class="sxs-lookup"><span data-stu-id="887b2-117">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="887b2-118">Live Communications Server 2005 avec SP1 a introduit des types de Fédération supplémentaires, dont tous les enregistrements SRV DNS (Domain Name System) requis doivent être publiés par le partenaire fédéré pour localiser leur serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="887b2-118">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="887b2-119">Cette version utilisait la terminologie suivante :</span><span class="sxs-lookup"><span data-stu-id="887b2-119">The terminology for that release was:</span></span>

  - <span data-ttu-id="887b2-120">*Ouvrir la Fédération étendue*: accepter tout nom de domaine SIP et utiliser DNS SRV pour localiser le serveur Edge partenaire</span><span class="sxs-lookup"><span data-stu-id="887b2-120">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="887b2-121">*Fédération étendue*: configurez le nom de domaine SIP du partenaire en tant que partenaire de Fédération pour votre organisation et utilisez DNS SRV pour rechercher le serveur Edge partenaire.</span><span class="sxs-lookup"><span data-stu-id="887b2-121">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="887b2-122">*Fédération directe*: configurez le nom de domaine SIP du partenaire et le nom de domaine complet (FQDN) du serveur Edge du partenaire.</span><span class="sxs-lookup"><span data-stu-id="887b2-122">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="887b2-123">*Liste verte du serveur*: accepter n’importe quel domaine, utiliser DNS SRV pour rechercher le serveur Edge d’un fournisseur d’hébergement ou d’un fournisseur de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="887b2-123">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="887b2-124">Microsoft Office Communications Server 2007 a introduit un nom mis à jour pour les types de Fédération afin de mieux définir ce que chaque type de Fédération a réellement accompli :</span><span class="sxs-lookup"><span data-stu-id="887b2-124">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="887b2-125">La fédération étendue ouverte a été remplacée par le *domaine partenaire découvert*.</span><span class="sxs-lookup"><span data-stu-id="887b2-125">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="887b2-126">La fédération étendue a été remplacée par le *domaine partenaire autorisé*.</span><span class="sxs-lookup"><span data-stu-id="887b2-126">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="887b2-127">La fédération directe a été remplacée par le *serveur partenaire autorisé*.</span><span class="sxs-lookup"><span data-stu-id="887b2-127">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="887b2-128">La liste verte du serveur a été remplacée par le *fournisseur d’hébergement* et le *fournisseur public de messagerie instantanée*.</span><span class="sxs-lookup"><span data-stu-id="887b2-128">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="887b2-129">Microsoft Lync Server 2010 a introduit une définition plus étroite du fournisseur d’hébergement conformément à Microsoft Lync Online 2010 et à Microsoft Office 365 et l’a également soumise à la même liste autorisée définie par le type de Fédération de domaine partenaire autorisé.</span><span class="sxs-lookup"><span data-stu-id="887b2-129">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="887b2-130">L’activation de la Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server utilise les serveurs Edge et les proxys inverses pour appliquer les règles et les domaines partenaires que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="887b2-130">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="887b2-131">Du point de vue de la planification, la Fédération avec d’autres Lync Server, Office Communications Server requiert les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="887b2-131">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="887b2-132">activation de la fédération dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="887b2-132">Enable federation in Topology Builder.</span></span> <span data-ttu-id="887b2-133">Pour plus d’informations, reportez-vous à la rubrique relative au déploiement Configuration de la [Fédération SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="887b2-133">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="887b2-134">détermination de vos conditions pour la découverte des domaines fédérés :</span><span class="sxs-lookup"><span data-stu-id="887b2-134">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="887b2-135">Pour la configuration manuelle de la Fédération, vous devez disposer du nom de domaine complet (FQDN) du serveur Edge et du nom de domaine du partenaire, ou du nom de domaine en ligne, qui est entré dans le panneau de configuration Lync Server, **Fédération et accès externe**, **domaines fédérés SIP**.</span><span class="sxs-lookup"><span data-stu-id="887b2-135">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="887b2-136">Créez une **nouvelle** stratégie ou **modifiez** une stratégie existante pour autoriser ou bloquer les domaines par nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="887b2-136">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="887b2-137">La configuration manuelle du serveur Edge d’un partenaire de Fédération est susceptible d’échouer si le partenaire modifie l’adresse IP de son serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="887b2-137">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="887b2-138">Pour les <STRONG>nouveaux domaines fédérés SIP</STRONG>, vous devez fournir le <STRONG>nom de domaine (ou FQDN)</STRONG> pour Microsoft Lync Online et microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="887b2-138">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online and Microsoft 365 or Office 365.</span></span> <span data-ttu-id="887b2-139">Pour Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server, vous devez également fournir un <STRONG>service Edge d’accès (FQDN)</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="887b2-139">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="887b2-140">Pour la Fédération des partenaires découverts, où les partenaires peuvent découvrir votre serveur Edge, vous créez un enregistrement SRV dans votre DNS externe- \_ sipfederationtls. \_ tcp.contoso.com – qui pointe vers le port 5061 et l’enregistrement d’hôte (A) de votre serveur Edge</span><span class="sxs-lookup"><span data-stu-id="887b2-140">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="887b2-141">Si vous prenez en charge les clients mobiles Microsoft Lync sur Windows Phone ou Apple iPhone, iPad ou d’autres appareils Apple et que vous utilisez le service de notification par transmission ou de notification, vous devez planifier _sipfederationtls. _ TCP.</span><span class="sxs-lookup"><span data-stu-id="887b2-141">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="887b2-142">&lt;&gt;Enregistrements SRV de domaine SIP pour chaque domaine SIP que vous avez des clients mobiles Lync.</span><span class="sxs-lookup"><span data-stu-id="887b2-142">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="887b2-143">Android et Nokia Symbian Lync mobile n’utilisent pas la notification de transmission et ne sont pas soumis à cette exigence.</span><span class="sxs-lookup"><span data-stu-id="887b2-143">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="887b2-144">configuration des stratégies d’accès des utilisateurs externes pour la prise en charge des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="887b2-144">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="887b2-145">ouverture des ports de pare-feu pour le protocole SIP (Session Initiation Protocol), les conférences web et audiovisuelles pour prendre en charge la fédération ou les contacts que vous activez.</span><span class="sxs-lookup"><span data-stu-id="887b2-145">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="887b2-146">Pour plus d’informations, reportez-vous à la rubrique : [determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="887b2-146">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="887b2-147">Les informations suivantes vous aideront à définir les exigences en matière de certificat, de port/protocole et de DNS pour la Fédération avec Microsoft Lync Server 2013 et Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="887b2-147">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="887b2-148">La planification des certificats, des exigences de pare-feu et de port/protocole et des exigences DNS est généralement un processus direct si vous avez planifié ou déployé vos serveurs Edge Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="887b2-148">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="887b2-149">Étant donné que la Fédération est une fonctionnalité supplémentaire qui utilise le serveur Edge existant, les exigences de planification sont généralement satisfaites par la planification et le déploiement du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="887b2-149">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="887b2-150">Vous devez utiliser les tableaux suivants pour déterminer si vos conditions sont satisfaites et apporter des modifications au port/protocole et au DNS le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="887b2-150">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="887b2-151">Si vous disposez d’un pool de serveurs Edge et que vous vous fédérer avec des partenaires Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser l’équilibrage de charge DNS ou des programmes d’équilibrage de la charge matérielle sur les côtés internes et externes des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="887b2-151">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="887b2-152">Si vous vous fédérer avec Office Communications Server 2007 ou Office Communications Server 2007 R2, l’équilibrage de la charge matérielle fournira une prise en charge du basculement en cas de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="887b2-152">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="887b2-153">Office Communications Server 2007 et Office Communications Server 2007 R2 ne prennent pas en charge l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="887b2-153">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="887b2-154">Les serveurs Edge partenaires vont établir une communication avec le premier serveur Edge de votre pool qui répond.</span><span class="sxs-lookup"><span data-stu-id="887b2-154">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="887b2-155">En cas de défaillance du serveur Edge, la communication ne bascule pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="887b2-155">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="887b2-156">Les certificats requis sont généralement satisfaits via la planification des certificats pour le serveur Edge choisi ou le plan de serveur Edge mis en pool.</span><span class="sxs-lookup"><span data-stu-id="887b2-156">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="887b2-157">Connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="887b2-157">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="887b2-158">La connectivité de messagerie instantanée publique est une classe de Fédération et est configurée pour permettre à vos utilisateurs de Lync Server 2013 internes et externes d’ajouter des contacts à partir de l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="887b2-158">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="887b2-159">Contacts Messenger</span><span class="sxs-lookup"><span data-stu-id="887b2-159">Messenger contacts</span></span>

  - <span data-ttu-id="887b2-160">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="887b2-160">Yahoo\!</span></span> <span data-ttu-id="887b2-161">contacts</span><span class="sxs-lookup"><span data-stu-id="887b2-161">contacts</span></span>

  - <span data-ttu-id="887b2-162">Contacts AOL (America Online)</span><span class="sxs-lookup"><span data-stu-id="887b2-162">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="887b2-163">À partir du 2012 1er septembre, la licence d’abonnement aux utilisateurs de la connectivité PIC de Microsoft Lync public (PIC) n’est plus disponible pour l’achat de contrats de nouvelle ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="887b2-163">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="887b2-164">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="887b2-164">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="887b2-165">Messenger jusqu’à la date d’arrêt du service (la date exacte doit toujours être fixée, mais pas avant le 2013 juin).</span><span class="sxs-lookup"><span data-stu-id="887b2-165">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="887b2-166">La fonction USL PIC est une licence d’abonnement mensuel, mensuelle, nécessaire pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="887b2-166">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="887b2-167">Messenger.</span><span class="sxs-lookup"><span data-stu-id="887b2-167">Messenger.</span></span> <span data-ttu-id="887b2-168">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent qui n’est pas renouvelé.</span><span class="sxs-lookup"><span data-stu-id="887b2-168">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="887b2-169">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="887b2-169">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="887b2-170">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="887b2-170">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="887b2-171">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes via la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="887b2-171">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="887b2-172">Cette classe de fédération nécessite les considérations de planification suivantes :</span><span class="sxs-lookup"><span data-stu-id="887b2-172">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="887b2-173">Les utilisateurs de Windows Live Messenger peuvent utiliser la communication audio/vidéo d’égal à égal avec les utilisateurs de Lync Server 2013, en plus de la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="887b2-173">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="887b2-174">Vos serveurs Edge doivent répondre à des exigences spécifiques en matière de port et de protocole.</span><span class="sxs-lookup"><span data-stu-id="887b2-174">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="887b2-175">Pour plus d’informations, reportez-vous à [la rubrique determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="887b2-175">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="887b2-176">La messagerie instantanée Yahoo n’a pas de configuration spécifique, à l’exception de celles généralement utilisées dans la planification et le déploiement du serveur Edge standard qui fournit la Fédération.</span><span class="sxs-lookup"><span data-stu-id="887b2-176">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="887b2-177">Pour America Online, le certificat de serveur Edge attribué au service Edge d’accès a une utilisation améliorée de la clé (EKU) par le client.</span><span class="sxs-lookup"><span data-stu-id="887b2-177">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="887b2-178">Fédération XMPP (extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="887b2-178">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="887b2-179">Les versions précédentes de Lync Server et Office Communications Server ont fourni une passerelle XMPP (extensible Messaging and Presence Protocol) qui pourrait être déployée en tant que rôle serveur distinct afin d’autoriser la Fédération avec des déploiements XMPP.</span><span class="sxs-lookup"><span data-stu-id="887b2-179">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="887b2-180">Dans Microsoft Lync Server 2013, la fonctionnalité XMPP peut être déployée sous la forme d’une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="887b2-180">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="887b2-181">La fonctionnalité XMPP est installée en deux parties : un proxy XMPP qui s’exécute sur le serveur Edge et la passerelle XMPP qui s’exécute sur les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="887b2-181">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="887b2-182">Le déploiement et la configuration de XMPP sont abordés dans le déploiement de l' [accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) vous prévoyez de prendre en charge XMPP dans votre organisation en définissant des règles de port et de protocole sur votre pare-feu, la configuration des certificats et l’ajout d’enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="887b2-182">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="887b2-183">Les rubriques suivantes de cette section résument les informations dont vous aurez besoin pour planifier la Fédération XMPP pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="887b2-183">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="887b2-p120">La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.</span><span class="sxs-lookup"><span data-stu-id="887b2-p120">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="887b2-186">La Fédération XMPP n’est pas prise en charge pour les utilisateurs hébergés sur les Survivable Branch Appliances.</span><span class="sxs-lookup"><span data-stu-id="887b2-186">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="887b2-187">Cela s’applique à la fois aux informations de présence et à l’échange de messages INSTANTANÉs.</span><span class="sxs-lookup"><span data-stu-id="887b2-187">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="887b2-188">Les rubriques suivantes contiennent des conseils pour définir des certificats, des ports de pare-feu et des entrées DNS pour les types de scénarios de Fédération pris en charge.</span><span class="sxs-lookup"><span data-stu-id="887b2-188">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="887b2-189">Résumé des certificats-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887b2-189">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="887b2-190">Résumé des ports-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887b2-190">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="887b2-191">Résumé des enregistrements DNS-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887b2-191">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="887b2-192">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="887b2-192">See Also</span></span>


[<span data-ttu-id="887b2-193">Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887b2-193">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="887b2-194">Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887b2-194">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="887b2-195">Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887b2-195">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="887b2-196">Déterminer les exigences DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887b2-196">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="887b2-197">Gérer la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887b2-197">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="887b2-198">Gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887b2-198">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="887b2-199">Gestion des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="887b2-199">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

