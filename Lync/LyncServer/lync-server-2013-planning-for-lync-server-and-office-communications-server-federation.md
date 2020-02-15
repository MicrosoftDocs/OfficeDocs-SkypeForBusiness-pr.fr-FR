---
title: Planification de la Fédération de Lync Server et Office Communications Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22c94254921e3aa1cde8d93998f8fe5bf122ac92
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="35236-102">Planification de la Fédération entre Lync Server 2013 et Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="35236-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35236-103">_**Dernière modification de la rubrique :** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="35236-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="35236-104">La Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server prend en charge les communications entre homologues et plusieurs parties.</span><span class="sxs-lookup"><span data-stu-id="35236-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="35236-105">Les communications d’égal à égal peuvent devenir des conversions à plusieurs utilisateurs, ce qui permet d’organiser des réunions ad hoc.</span><span class="sxs-lookup"><span data-stu-id="35236-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="35236-106">Des réunions (conférences web ou conférences audiovisuelles) peuvent être programmées pour inclure des contacts de votre organisation, ainsi que des contacts des partenaires avec lesquels vous appliquez la fédération.</span><span class="sxs-lookup"><span data-stu-id="35236-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="35236-107">La Fédération s’est d’abord affichée dans Microsoft Office Live Communications Server 2005 et prend en charge un type de Fédération directe.</span><span class="sxs-lookup"><span data-stu-id="35236-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="35236-108">La Fédération directe exigeait que vous connaissiez le domaine SIP (Session Initiation Protocol) du partenaire de Fédération et le nom de domaine complet (FQDN) du serveur Edge du partenaire.</span><span class="sxs-lookup"><span data-stu-id="35236-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="35236-109">Live Communications Server 2005 avec SP1 a introduit des types de Fédération supplémentaires, dont tous les enregistrements SRV DNS (Domain Name System) requis doivent être publiés par le partenaire fédéré pour localiser leur serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="35236-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="35236-110">Cette version utilisait la terminologie suivante :</span><span class="sxs-lookup"><span data-stu-id="35236-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="35236-111">*Ouvrir la Fédération étendue*: accepter tout nom de domaine SIP et utiliser DNS SRV pour localiser le serveur Edge partenaire</span><span class="sxs-lookup"><span data-stu-id="35236-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="35236-112">*Fédération étendue*: configurez le nom de domaine SIP du partenaire en tant que partenaire de Fédération pour votre organisation et utilisez DNS SRV pour rechercher le serveur Edge partenaire.</span><span class="sxs-lookup"><span data-stu-id="35236-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="35236-113">*Fédération directe*: configurez le nom de domaine SIP du partenaire et le nom de domaine complet (FQDN) du serveur Edge du partenaire.</span><span class="sxs-lookup"><span data-stu-id="35236-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="35236-114">*Liste verte du serveur*: accepter n’importe quel domaine, utiliser DNS SRV pour rechercher le serveur Edge d’un fournisseur d’hébergement ou d’un fournisseur de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="35236-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="35236-115">Microsoft Office Communications Server 2007 a introduit un nom mis à jour pour les types de Fédération afin de mieux définir ce que chaque type de Fédération a réellement accompli :</span><span class="sxs-lookup"><span data-stu-id="35236-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="35236-116">La fédération étendue ouverte a été remplacée par le *domaine partenaire découvert*.</span><span class="sxs-lookup"><span data-stu-id="35236-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="35236-117">La fédération étendue a été remplacée par le *domaine partenaire autorisé*.</span><span class="sxs-lookup"><span data-stu-id="35236-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="35236-118">La fédération directe a été remplacée par le *serveur partenaire autorisé*.</span><span class="sxs-lookup"><span data-stu-id="35236-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="35236-119">La liste verte du serveur a été remplacée par le *fournisseur d’hébergement* et le *fournisseur public de messagerie instantanée*.</span><span class="sxs-lookup"><span data-stu-id="35236-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="35236-120">Microsoft Lync Server 2010 a introduit une définition plus étroite du fournisseur d’hébergement conformément à Microsoft Lync Online 2010 et à Microsoft Office 365 et l’a également soumise à la même liste autorisée définie par le type de Fédération de domaine partenaire autorisé.</span><span class="sxs-lookup"><span data-stu-id="35236-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="35236-121">L’activation de la Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server utilise les serveurs Edge et les proxys inverses pour appliquer les règles et les domaines partenaires que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="35236-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="35236-122">Du point de vue de la planification, la Fédération avec d’autres Lync Server, Office Communications Server requiert les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="35236-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="35236-123">activation de la fédération dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="35236-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="35236-124">Pour plus d’informations, reportez-vous à la rubrique relative au déploiement Configuration de la [Fédération SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="35236-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="35236-125">détermination de vos conditions pour la découverte des domaines fédérés :</span><span class="sxs-lookup"><span data-stu-id="35236-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="35236-126">Pour la configuration manuelle de la Fédération, vous devez disposer du nom de domaine complet (FQDN) du serveur Edge et du nom de domaine du partenaire, ou du nom de domaine en ligne, qui est entré dans le panneau de configuration Lync Server, **Fédération et accès externe**, **domaines fédérés SIP**.</span><span class="sxs-lookup"><span data-stu-id="35236-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="35236-127">Créez une **nouvelle** stratégie ou **modifiez** une stratégie existante pour autoriser ou bloquer les domaines par nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="35236-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="35236-128">La configuration manuelle du serveur Edge d’un partenaire de Fédération est susceptible d’échouer si le partenaire modifie l’adresse IP de son serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="35236-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="35236-129">Pour les <STRONG>nouveaux domaines fédérés SIP</STRONG>, vous devez fournir le <STRONG>nom de domaine (ou FQDN)</STRONG> pour Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="35236-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="35236-130">Pour Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server, vous devez également fournir un <STRONG>service Edge d’accès (FQDN)</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="35236-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="35236-131">Pour la Fédération des partenaires découverts, où les partenaires peuvent découvrir votre serveur Edge, vous créez un enregistrement SRV dans \_votre DNS externe-sipfederationtls. \_TCP.contoso.com – qui pointe vers le port 5061 et l’enregistrement d’hôte (A) de votre serveur Edge</span><span class="sxs-lookup"><span data-stu-id="35236-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="35236-132">Si vous prenez en charge les clients mobiles Microsoft Lync sur Windows Phone ou Apple iPhone, iPad ou d’autres appareils Apple et que vous utilisez le service de notification par transmission ou de notification, vous devez planifier _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="35236-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="35236-133">&lt;Enregistrements SRV&gt; de domaine SIP pour chaque domaine SIP que vous avez des clients mobiles Lync.</span><span class="sxs-lookup"><span data-stu-id="35236-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="35236-134">Android et Nokia Symbian Lync mobile n’utilisent pas la notification de transmission et ne sont pas soumis à cette exigence.</span><span class="sxs-lookup"><span data-stu-id="35236-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="35236-135">configuration des stratégies d’accès des utilisateurs externes pour la prise en charge des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="35236-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="35236-136">ouverture des ports de pare-feu pour le protocole SIP (Session Initiation Protocol), les conférences web et audiovisuelles pour prendre en charge la fédération ou les contacts que vous activez.</span><span class="sxs-lookup"><span data-stu-id="35236-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="35236-137">Pour plus d’informations, reportez-vous à la rubrique : [determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="35236-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="35236-138">Les informations suivantes vous aideront à définir les exigences en matière de certificat, de port/protocole et de DNS pour la Fédération avec Microsoft Lync Server 2013 et Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="35236-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="35236-139">La planification des certificats, des exigences de pare-feu et de port/protocole et des exigences DNS est généralement un processus direct si vous avez planifié ou déployé vos serveurs Edge Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35236-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="35236-140">Étant donné que la Fédération est une fonctionnalité supplémentaire qui utilise le serveur Edge existant, les exigences de planification sont généralement satisfaites par la planification et le déploiement du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="35236-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="35236-141">Vous devez utiliser les tableaux suivants pour déterminer si vos conditions sont satisfaites et apporter des modifications au port/protocole et au DNS le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="35236-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="35236-142">Si vous disposez d’un pool de serveurs Edge et que vous vous fédérer avec des partenaires Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser l’équilibrage de charge DNS ou des programmes d’équilibrage de la charge matérielle sur les côtés internes et externes des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="35236-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="35236-143">Si vous vous fédérer avec Office Communications Server 2007 ou Office Communications Server 2007 R2, l’équilibrage de la charge matérielle fournira une prise en charge du basculement en cas de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="35236-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="35236-144">Office Communications Server 2007 et Office Communications Server 2007 R2 ne prennent pas en charge l’équilibrage de la charge DNS.</span><span class="sxs-lookup"><span data-stu-id="35236-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="35236-145">Les serveurs Edge partenaires vont établir une communication avec le premier serveur Edge de votre pool qui répond.</span><span class="sxs-lookup"><span data-stu-id="35236-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="35236-146">En cas de défaillance du serveur Edge, la communication ne bascule pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="35236-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="35236-147">Les certificats requis sont généralement satisfaits via la planification des certificats pour le serveur Edge choisi ou le plan de serveur Edge mis en pool.</span><span class="sxs-lookup"><span data-stu-id="35236-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="35236-148">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="35236-148">In This Section</span></span>

  - [<span data-ttu-id="35236-149">Résumé des certificats-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35236-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="35236-150">Résumé des ports-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35236-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="35236-151">Résumé des enregistrements DNS-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35236-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35236-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35236-152">See Also</span></span>


[<span data-ttu-id="35236-153">Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35236-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="35236-154">Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35236-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="35236-155">Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35236-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="35236-156">Déterminer les exigences DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35236-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="35236-157">Gérer la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35236-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="35236-158">Gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35236-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="35236-159">Gestion des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35236-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

