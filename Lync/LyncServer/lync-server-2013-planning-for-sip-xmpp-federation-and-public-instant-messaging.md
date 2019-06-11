---
title: Planification pour les conversations SIP, XMPP et la messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88aa8c6f3f2f11b303a7e25eed96d5f0d7243cb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="5d5ef-102">Planification de la Fédération SIP, de XMPP et de la messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5ef-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d5ef-103">_**Dernière modification de la rubrique:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="5d5ef-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="5d5ef-104">Les serveurs Edge peuvent être configurés pour autoriser vos utilisateurs internes et externes à accéder à des contacts au niveau des organisations ou services partenaires.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="5d5ef-105">Les fédérations, au fur et à mesure qu’elles sont connues, peuvent fournir tout ou partie des éléments suivants aux contacts de votre organisation dans le cadre de la Fédération de partenaire ou des contacts de la Fédération du partenaire au vôtre:</span><span class="sxs-lookup"><span data-stu-id="5d5ef-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="5d5ef-106">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="5d5ef-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="5d5ef-107">Collaboration et conférences, par exemple: conférences Web</span><span class="sxs-lookup"><span data-stu-id="5d5ef-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="5d5ef-108">Audioconférence, visioconférence ou les deux</span><span class="sxs-lookup"><span data-stu-id="5d5ef-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="5d5ef-109">Dans certains cas, la communication, par exemple, la messagerie instantanée et la présence d’un contact Microsoft Lync Server 2013 et d’un protocole de messagerie extensible (XMPP), est pair à pair uniquement: vous ne pouvez prendre en charge que vous et le contact fédéré. partenaire.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="5d5ef-110">Dans d’autres cas, comme un serveur Lync, Lync Server 2010 vers Lync Server 2013 Federation, plusieurs participants peuvent être invités à rejoindre la conversation.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="5d5ef-111">Fédération Lync Server et Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="5d5ef-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="5d5ef-112">La Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server prend en charge les communications d’égal à égal et à plusieurs parties.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="5d5ef-113">Les conversations d’égal à égal peuvent être transmises à des conversations à plusieurs participants, ce qui permet de participer à des réunions ad hoc.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="5d5ef-114">Réunions (conférences Web ou conférences audiovisuelles) il est possible d’inclure les contacts au sein de votre organisation ainsi que les contacts des partenaires avec lesquels vous vous fédérer.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="5d5ef-115">La Fédération s’est d’abord affichée dans Microsoft Office Live Communications Server 2005 et prend en charge un type de Fédération unique.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="5d5ef-116">La Fédération directe nécessite que vous connaissiez le domaine SIP (Session Initiation Protocol) du partenaire de Fédération ainsi que le nom de domaine complet (FQDN) du serveur Edge du partenaire.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="5d5ef-117">Live Communications Server 2005 avec SP1 a introduit des types de Fédération supplémentaires, tous les enregistrements SRV du système de noms de domaine (DNS) requis pour la publication du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="5d5ef-118">La terminologie de cette version était la suivante:</span><span class="sxs-lookup"><span data-stu-id="5d5ef-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="5d5ef-119">*Ouvrir la Fédération avancée*: accepter un nom de domaine SIP et utiliser DNS SRV pour localiser le serveur Edge du partenaire</span><span class="sxs-lookup"><span data-stu-id="5d5ef-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="5d5ef-120">*Fédération améliorée*: configurez le nom de domaine SIP du partenaire en tant que partenaire de Fédération pour votre organisation et utilisez DNS SRV pour trouver le serveur Edge du partenaire.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="5d5ef-121">*Fédération directe*: configuration du nom de domaine SIP du partenaire et du nom de domaine complet (FQDN) du serveur Edge du partenaire</span><span class="sxs-lookup"><span data-stu-id="5d5ef-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="5d5ef-122">*Liste verte du serveur*: accepter les domaines, utiliser DNS SRV pour trouver le serveur de périphérie d’un fournisseur d’hébergement ou un fournisseur de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="5d5ef-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="5d5ef-123">Microsoft Office Communications Server 2007 a introduit un nom mis à jour pour les types de Fédération pour mieux définir ce que chaque type de Fédération a réellement accompli:</span><span class="sxs-lookup"><span data-stu-id="5d5ef-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="5d5ef-124">Ouvrir la Fédération avancée a été connu sous le nom de *domaine partenaire détecté*</span><span class="sxs-lookup"><span data-stu-id="5d5ef-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="5d5ef-125">La Fédération améliorée a été connue sous le nom de *domaine partenaire autorisé*</span><span class="sxs-lookup"><span data-stu-id="5d5ef-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="5d5ef-126">La Fédération directe s’est appelée *serveur partenaire autorisé*</span><span class="sxs-lookup"><span data-stu-id="5d5ef-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="5d5ef-127">La liste verte du serveur est devenue désignée comme *fournisseur d’hébergement* et *fournisseur de messagerie instantanée publique*</span><span class="sxs-lookup"><span data-stu-id="5d5ef-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="5d5ef-128">Microsoft Lync Server 2010 a introduit une définition plus restreinte du fournisseur d’hébergement conformément à Microsoft Lync Online 2010 et Microsoft Office 365, et il a également été soumis à la même liste autorisée définie par le type de Fédération de domaine autorisé.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="5d5ef-129">L’activation de la Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server fait appel aux serveurs Edge et aux proxys inverses pour appliquer les règles et domaines de partenaires autorisés que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="5d5ef-130">Du point de vue de la planification, la Fédération avec un autre serveur Lync Server et Office Communications Server nécessite les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="5d5ef-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="5d5ef-131">Activez la Fédération dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="5d5ef-132">Pour plus d’informations, reportez-vous à la rubrique déploiement Configuration de la Fédération [SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="5d5ef-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="5d5ef-133">Déterminez la configuration requise pour la découverte de domaines fédérés:</span><span class="sxs-lookup"><span data-stu-id="5d5ef-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="5d5ef-134">Pour la configuration manuelle de la Fédération, vous devez disposer du nom de domaine complet (FQDN) du serveur Edge du partenaire et du nom de domaine ou du nom de domaine en ligne, qui est entré dans le panneau de configuration de Lync Server, la **Fédération et l’accès externe**, **SIP Domaines fédérés**.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="5d5ef-135">Créez une \*\*\*\* stratégie ou **Modifiez** une stratégie existante pour autoriser ou bloquer des domaines en utilisant un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="5d5ef-136">La configuration manuelle du serveur Edge d’un partenaire de Fédération est susceptible de ne pas pouvoir échouer en cas de changement d’adresse IP de son serveur Edge par le partenaire.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="5d5ef-137">Pour les <STRONG>nouveaux domaines fédérés SIP</STRONG>, vous devez indiquer le <STRONG>nom de domaine (ou le nom de domaine complet (FQDN)</STRONG> de Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="5d5ef-138">Pour Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server vous devez également fournir un <STRONG>service Edge d’accès (FQDN)</STRONG></span><span class="sxs-lookup"><span data-stu-id="5d5ef-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="5d5ef-139">Pour la Fédération de partenaires découverte, où les partenaires peuvent découvrir votre serveur Edge, vous devez créer un enregistrement SRV dans \_votre DNS externe-sipfederationtls. \_TCP.contoso.com: qui pointe vers le port 5061 et l’hôte (A) du serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="5d5ef-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="5d5ef-140">Si vous prenez en charge des clients mobiles Microsoft Lync sur un appareil Windows Phone ou un Apple iPhone, iPad ou d’autres appareils Apple et que vous utilisez le service de notifications de transmission ou le service de notifications d’émission, vous devez planifier _sipfederationtls. _ TCP.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="5d5ef-141">&lt;Enregistrements SRV&gt; du domaine SIP pour chaque domaine SIP que vous avez des clients mobiles Lync.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="5d5ef-142">Android et Nokia Symbian Lync mobile n’utilisent pas de notifications de transmission et ne sont pas soumis à cette obligation.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="5d5ef-143">Configurer des stratégies d’accès des utilisateurs externes pour prendre en charge des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="5d5ef-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="5d5ef-144">Ouvrez les ports de pare-feu pour le protocole SIP (Session Initiation Protocol), la conférence Web et l’audio/visuel pour accepter la ou les personnes que vous activez.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="5d5ef-145">Pour plus d’informations, reportez-vous à: [identification des exigences de port et de pare-feu externes pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5d5ef-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="5d5ef-146">Les informations suivantes vous permettront de définir le certificat, le port/protocole et les exigences DNS pour la Fédération avec Microsoft Lync Server 2013 et Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="5d5ef-147">La planification des certificats, de la configuration requise pour le pare-feu et du port/protocole et des exigences DNS est généralement un processus direct de transfert si vous avez planifié ou déployé vos serveurs Microsoft Lync Server 2013 Edge.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="5d5ef-148">Dans la mesure où la Fédération est une fonctionnalité supplémentaire qui utilise le serveur de périphérie existant, les exigences de planification sont généralement satisfaites par la planification et le déploiement de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="5d5ef-149">Vous devez utiliser les tableaux suivants pour vérifier que vos exigences sont remplies et apporter des modifications au port/protocole et au DNS en conséquence.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5d5ef-150">Si vous avez un pool de serveurs Edge et que vous effectuez une Fédération avec Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser l’équilibrage de charge DNS ou les équilibreurs de charge matérielle sur les côtés internes et externes des serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="5d5ef-151">Si vous vous fédérationz avec Office Communications Server 2007 ou Office Communications Server 2007 R2, l’équilibrage de charge matérielle fournira une prise en charge du basculement en cas de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="5d5ef-152">Office Communications Server 2007 et Office Communications Server 2007 R2 ne prennent pas en charge l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="5d5ef-153">Les serveurs Edge du partenaire établiront une communication avec le premier serveur Edge de votre pool qui répond.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="5d5ef-154">Si ce serveur Edge tombe en panne, la communication ne bascule pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="5d5ef-155">Les exigences en matière de certificats sont généralement satisfaites par le cadre de la planification de certificats pour le serveur Edge ou le plan de serveur Edge sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="5d5ef-156">Connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="5d5ef-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="5d5ef-157">La connectivité de messagerie instantanée publique est une classe de Fédération et est configurée pour permettre à vos utilisateurs de Lync Server 2013 internes et externes d’ajouter des contacts à partir de l’un des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="5d5ef-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="5d5ef-158">Contacts Messenger</span><span class="sxs-lookup"><span data-stu-id="5d5ef-158">Messenger contacts</span></span>

  - <span data-ttu-id="5d5ef-159">Yahoo!\!</span><span class="sxs-lookup"><span data-stu-id="5d5ef-159">Yahoo\!</span></span> <span data-ttu-id="5d5ef-160">contacts</span><span class="sxs-lookup"><span data-stu-id="5d5ef-160">contacts</span></span>

  - <span data-ttu-id="5d5ef-161">Contacts AOL (America Online)</span><span class="sxs-lookup"><span data-stu-id="5d5ef-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="5d5ef-162">À compter du 1er septembre 2012, la licence de l’abonnement à l’utilisateur de la connectivité PIC (Public IM Connectivity) de Microsoft Lync n’est plus disponible pour l’achat de contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="5d5ef-163">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5d5ef-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="5d5ef-164">Messenger jusqu’à la date d’arrêt du service (la date exacte doit toujours être décidée, mais pas avant le 2013 juin).</span><span class="sxs-lookup"><span data-stu-id="5d5ef-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="5d5ef-165">La fonction USL (PIC) est une licence d’abonnement par utilisateur et par mois requise pour la Fédération de Lync Server ou d’Office Communications Server avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="5d5ef-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="5d5ef-166">Messenger.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-166">Messenger.</span></span> <span data-ttu-id="5d5ef-167">La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, qui n’est pas renouvelé.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="5d5ef-168">Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="5d5ef-169">La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="5d5ef-170">Skype Federation sera ajouté à cette liste, ce qui permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes par messagerie instantanée et vocale.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="5d5ef-171">Cette classe de Fédération exige les considérations en matière de planification suivantes:</span><span class="sxs-lookup"><span data-stu-id="5d5ef-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="5d5ef-172">Les utilisateurs de Windows Live Messenger peuvent utiliser la communication audio et vidéo d’égal à égal avec les utilisateurs de Lync Server 2013, en plus de la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="5d5ef-173">Vos serveurs Edge doivent répondre à des exigences de port et de protocole spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="5d5ef-174">Pour plus d’informations, reportez-vous à [la rubrique déterminer la configuration requise 2013 pour le pare-feu A](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5d5ef-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="5d5ef-175">Le service de messagerie instantanée Yahoo n’est soumis à aucune configuration unique, autre que celles généralement utilisées dans le cadre de la planification et du déploiement du serveur de périphérie standard qui fournit la Fédération.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="5d5ef-176">America Online nécessite que votre certificat de serveur Edge attribué au service Edge d’accès possède une utilisation améliorée de la clé par le client.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="5d5ef-177">Fédération des protocoles de messagerie extensible et de présence</span><span class="sxs-lookup"><span data-stu-id="5d5ef-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="5d5ef-178">Les versions précédentes de Lync Server et d’Office Communications Server ont fourni une passerelle XMPP (extensible Messaging and Presence Protocol) qui pouvait être déployée en tant que rôle de serveur distinct pour permettre la Fédération avec des déploiements de XMPP.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="5d5ef-179">Dans Microsoft Lync Server 2013, la fonctionnalité XMPP peut être déployée en tant que fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="5d5ef-180">La fonctionnalité XMPP est installée en deux parties: un proxy XMPP qui s’exécute sur le serveur Edge et la passerelle XMPP qui s’exécute sur les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="5d5ef-181">Le déploiement et la configuration de XMPP sont abordés dans le déploiement d’un [accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) que vous envisagez de prendre en charge XMPP au sein de votre organisation en définissant des règles de port et de protocole sur votre pare-feu, la configuration des certificats et l’ajout de DNS registres.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="5d5ef-182">Les rubriques suivantes de cette section résument les informations dont vous avez besoin pour planifier la Fédération XMPP pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5d5ef-p120">La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-p120">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5d5ef-185">La Fédération XMPP n’est pas prise en charge pour les utilisateurs hébergés sur des appareils de succursales survivables.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="5d5ef-186">Cela s’applique aussi bien aux informations de présence qu’à l’échange de messages INSTANTANÉs.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="5d5ef-187">Les rubriques suivantes contiennent des recommandations pour la définition de certificats, de ports de pare-feu et d’entrées DNS pour les types de scénarios de Fédération pris en charge.</span><span class="sxs-lookup"><span data-stu-id="5d5ef-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="5d5ef-188">Résumé du certificat-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5ef-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="5d5ef-189">Résumé de port-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5ef-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="5d5ef-190">Résumé DNS-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5ef-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5d5ef-191">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d5ef-191">See Also</span></span>


[<span data-ttu-id="5d5ef-192">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5ef-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="5d5ef-193">Scénarios d’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5ef-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="5d5ef-194">Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5ef-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="5d5ef-195">Détermination de la configuration requise pour DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5ef-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="5d5ef-196">Gestion de la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5ef-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="5d5ef-197">Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5ef-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="5d5ef-198">Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5ef-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

