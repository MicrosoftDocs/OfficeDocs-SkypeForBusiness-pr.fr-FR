---
title: Planification de Lync Server et de la Fédération du serveur Office Communications Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c683092b61d278d380ad68cef86795d496498fbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="e23e0-102">Planification de Lync Server 2013 et de la Fédération Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="e23e0-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e23e0-103">_**Dernière modification de la rubrique:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="e23e0-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="e23e0-104">La Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server prend en charge les communications d’égal à égal et à plusieurs parties.</span><span class="sxs-lookup"><span data-stu-id="e23e0-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="e23e0-105">Les conversations d’égal à égal peuvent être transmises à des conversations à plusieurs participants, ce qui permet de participer à des réunions ad hoc.</span><span class="sxs-lookup"><span data-stu-id="e23e0-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="e23e0-106">Réunions (conférences Web ou conférences audiovisuelles) il est possible d’inclure les contacts au sein de votre organisation ainsi que les contacts des partenaires avec lesquels vous vous fédérer.</span><span class="sxs-lookup"><span data-stu-id="e23e0-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="e23e0-107">La Fédération s’est d’abord affichée dans Microsoft Office Live Communications Server 2005 et prend en charge un type de Fédération unique.</span><span class="sxs-lookup"><span data-stu-id="e23e0-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="e23e0-108">La Fédération directe nécessite que vous connaissiez le domaine SIP (Session Initiation Protocol) du partenaire de Fédération ainsi que le nom de domaine complet (FQDN) du serveur Edge du partenaire.</span><span class="sxs-lookup"><span data-stu-id="e23e0-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="e23e0-109">Live Communications Server 2005 avec SP1 a introduit des types de Fédération supplémentaires, tous les enregistrements SRV du système de noms de domaine (DNS) requis pour la publication du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="e23e0-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="e23e0-110">La terminologie de cette version était la suivante:</span><span class="sxs-lookup"><span data-stu-id="e23e0-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="e23e0-111">*Ouvrir la Fédération avancée*: accepter un nom de domaine SIP et utiliser DNS SRV pour localiser le serveur Edge du partenaire</span><span class="sxs-lookup"><span data-stu-id="e23e0-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="e23e0-112">*Fédération améliorée*: configurez le nom de domaine SIP du partenaire en tant que partenaire de Fédération pour votre organisation et utilisez DNS SRV pour trouver le serveur Edge du partenaire.</span><span class="sxs-lookup"><span data-stu-id="e23e0-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="e23e0-113">*Fédération directe*: configuration du nom de domaine SIP du partenaire et du nom de domaine complet (FQDN) du serveur Edge du partenaire</span><span class="sxs-lookup"><span data-stu-id="e23e0-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="e23e0-114">*Liste verte du serveur*: accepter les domaines, utiliser DNS SRV pour trouver le serveur de périphérie d’un fournisseur d’hébergement ou un fournisseur de connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="e23e0-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="e23e0-115">Microsoft Office Communications Server 2007 a introduit un nom mis à jour pour les types de Fédération pour mieux définir ce que chaque type de Fédération a réellement accompli:</span><span class="sxs-lookup"><span data-stu-id="e23e0-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="e23e0-116">Ouvrir la Fédération avancée a été connu sous le nom de *domaine partenaire détecté*</span><span class="sxs-lookup"><span data-stu-id="e23e0-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="e23e0-117">La Fédération améliorée a été connue sous le nom de *domaine partenaire autorisé*</span><span class="sxs-lookup"><span data-stu-id="e23e0-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="e23e0-118">La Fédération directe s’est appelée *serveur partenaire autorisé*</span><span class="sxs-lookup"><span data-stu-id="e23e0-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="e23e0-119">La liste verte du serveur est devenue désignée comme *fournisseur d’hébergement* et *fournisseur de messagerie instantanée publique*</span><span class="sxs-lookup"><span data-stu-id="e23e0-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="e23e0-120">Microsoft Lync Server 2010 a introduit une définition plus restreinte du fournisseur d’hébergement conformément à Microsoft Lync Online 2010 et Microsoft Office 365, et il a également été soumis à la même liste autorisée définie par le type de Fédération de domaine autorisé.</span><span class="sxs-lookup"><span data-stu-id="e23e0-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="e23e0-121">L’activation de la Fédération entre Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server fait appel aux serveurs Edge et aux proxys inverses pour appliquer les règles et domaines de partenaires autorisés que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="e23e0-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="e23e0-122">Du point de vue de la planification, la Fédération avec un autre serveur Lync Server et Office Communications Server nécessite les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="e23e0-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="e23e0-123">Activez la Fédération dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="e23e0-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="e23e0-124">Pour plus d’informations, reportez-vous à la rubrique déploiement Configuration de la Fédération [SIP, de la Fédération XMPP et de la messagerie instantanée publique dans Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="e23e0-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="e23e0-125">Déterminez la configuration requise pour la découverte de domaines fédérés:</span><span class="sxs-lookup"><span data-stu-id="e23e0-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="e23e0-126">Pour la configuration manuelle de la Fédération, vous devez disposer du nom de domaine complet (FQDN) du serveur Edge du partenaire et du nom de domaine ou du nom de domaine en ligne, qui est entré dans le panneau de configuration de Lync Server, la **Fédération et l’accès externe**, **SIP Domaines fédérés**.</span><span class="sxs-lookup"><span data-stu-id="e23e0-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="e23e0-127">Créez une \*\*\*\* stratégie ou **Modifiez** une stratégie existante pour autoriser ou bloquer des domaines en utilisant un nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="e23e0-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="e23e0-128">La configuration manuelle du serveur Edge d’un partenaire de Fédération est susceptible de ne pas pouvoir échouer en cas de changement d’adresse IP de son serveur Edge par le partenaire.</span><span class="sxs-lookup"><span data-stu-id="e23e0-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="e23e0-129">Pour les <STRONG>nouveaux domaines fédérés SIP</STRONG>, vous devez indiquer le <STRONG>nom de domaine (ou le nom de domaine complet (FQDN)</STRONG> de Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="e23e0-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="e23e0-130">Pour Microsoft Lync Server 2013, Lync Server 2010 et Office Communications Server vous devez également fournir un <STRONG>service Edge d’accès (FQDN)</STRONG></span><span class="sxs-lookup"><span data-stu-id="e23e0-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="e23e0-131">Pour la Fédération de partenaires découverte, où les partenaires peuvent découvrir votre serveur Edge, vous devez créer un enregistrement SRV dans \_votre DNS externe-sipfederationtls. \_TCP.contoso.com: qui pointe vers le port 5061 et l’hôte (A) du serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="e23e0-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="e23e0-132">Si vous prenez en charge des clients mobiles Microsoft Lync sur un appareil Windows Phone ou un Apple iPhone, iPad ou d’autres appareils Apple et que vous utilisez le service de notifications de transmission ou le service de notifications d’émission, vous devez planifier _sipfederationtls. _ TCP.</span><span class="sxs-lookup"><span data-stu-id="e23e0-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="e23e0-133">&lt;Enregistrements SRV&gt; du domaine SIP pour chaque domaine SIP que vous avez des clients mobiles Lync.</span><span class="sxs-lookup"><span data-stu-id="e23e0-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="e23e0-134">Android et Nokia Symbian Lync mobile n’utilisent pas de notifications de transmission et ne sont pas soumis à cette obligation.</span><span class="sxs-lookup"><span data-stu-id="e23e0-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="e23e0-135">Configurer des stratégies d’accès des utilisateurs externes pour prendre en charge des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="e23e0-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="e23e0-136">Ouvrez les ports de pare-feu pour le protocole SIP (Session Initiation Protocol), la conférence Web et l’audio/visuel pour accepter la ou les personnes que vous activez.</span><span class="sxs-lookup"><span data-stu-id="e23e0-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="e23e0-137">Pour plus d’informations, reportez-vous à: [identification des exigences de port et de pare-feu externes pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="e23e0-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="e23e0-138">Les informations suivantes vous permettront de définir le certificat, le port/protocole et les exigences DNS pour la Fédération avec Microsoft Lync Server 2013 et Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e23e0-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="e23e0-139">La planification des certificats, de la configuration requise pour le pare-feu et du port/protocole et des exigences DNS est généralement un processus direct de transfert si vous avez planifié ou déployé vos serveurs Microsoft Lync Server 2013 Edge.</span><span class="sxs-lookup"><span data-stu-id="e23e0-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="e23e0-140">Dans la mesure où la Fédération est une fonctionnalité supplémentaire qui utilise le serveur de périphérie existant, les exigences de planification sont généralement satisfaites par la planification et le déploiement de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="e23e0-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="e23e0-141">Vous devez utiliser les tableaux suivants pour vérifier que vos exigences sont remplies et apporter des modifications au port/protocole et au DNS en conséquence.</span><span class="sxs-lookup"><span data-stu-id="e23e0-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e23e0-142">Si vous avez un pool de serveurs Edge et que vous effectuez une Fédération avec Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser l’équilibrage de charge DNS ou les équilibreurs de charge matérielle sur les côtés internes et externes des serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="e23e0-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="e23e0-143">Si vous vous fédérationz avec Office Communications Server 2007 ou Office Communications Server 2007 R2, l’équilibrage de charge matérielle fournira une prise en charge du basculement en cas de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="e23e0-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="e23e0-144">Office Communications Server 2007 et Office Communications Server 2007 R2 ne prennent pas en charge l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="e23e0-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="e23e0-145">Les serveurs Edge du partenaire établiront une communication avec le premier serveur Edge de votre pool qui répond.</span><span class="sxs-lookup"><span data-stu-id="e23e0-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="e23e0-146">Si ce serveur Edge tombe en panne, la communication ne bascule pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="e23e0-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="e23e0-147">Les exigences en matière de certificats sont généralement satisfaites par le cadre de la planification de certificats pour le serveur Edge ou le plan de serveur Edge sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e23e0-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e23e0-148">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e23e0-148">In This Section</span></span>

  - [<span data-ttu-id="e23e0-149">Résumé du certificat-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e23e0-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="e23e0-150">Résumé de port-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e23e0-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="e23e0-151">Résumé DNS-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e23e0-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e23e0-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e23e0-152">See Also</span></span>


[<span data-ttu-id="e23e0-153">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e23e0-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="e23e0-154">Scénarios d’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e23e0-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="e23e0-155">Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e23e0-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="e23e0-156">Détermination de la configuration requise pour DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e23e0-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="e23e0-157">Gestion de la configuration du serveur Edge d’accès pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e23e0-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="e23e0-158">Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e23e0-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="e23e0-159">Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e23e0-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

