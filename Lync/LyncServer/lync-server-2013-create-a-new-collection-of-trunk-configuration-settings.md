---
title: 'Lync Server 2013 : créer une collection de paramètres de configuration de jonction'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7d019bfe7bb1dbb1322281a50f393decc8e5cc3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507461"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e1a84-102">Créer une collection de paramètres de configuration de jonction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1a84-102">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1a84-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e1a84-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e1a84-p101">Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="e1a84-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="e1a84-106">L’activation ou non du contournement de média sur les jonctions.</span><span class="sxs-lookup"><span data-stu-id="e1a84-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="e1a84-107">Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="e1a84-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="e1a84-108">L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.</span><span class="sxs-lookup"><span data-stu-id="e1a84-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="e1a84-109">Lorsque vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de jonction SIP (Session Initiation Protocol) est créée.</span><span class="sxs-lookup"><span data-stu-id="e1a84-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="e1a84-110">En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).</span><span class="sxs-lookup"><span data-stu-id="e1a84-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="e1a84-111">Lors de la création de paramètres de configuration de jonction SIP à l’aide du panneau de configuration Lync Server, les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="e1a84-111">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1a84-112">Paramètre de l’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e1a84-112">UI Setting</span></span></th>
<th><span data-ttu-id="e1a84-113">Paramètre PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1a84-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="e1a84-114">Description</span><span class="sxs-lookup"><span data-stu-id="e1a84-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1a84-115">Nom</span><span class="sxs-lookup"><span data-stu-id="e1a84-115">Name</span></span></p></td>
<td><p><span data-ttu-id="e1a84-116">Identité</span><span class="sxs-lookup"><span data-stu-id="e1a84-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="e1a84-p103">Identificateur unique de la collection. Cette propriété est en lecture seule ; vous ne pouvez pas changer l’identité d’une collection de paramètres de configuration de jonctions.</span><span class="sxs-lookup"><span data-stu-id="e1a84-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a84-119">Description</span><span class="sxs-lookup"><span data-stu-id="e1a84-119">Description</span></span></p></td>
<td><p><span data-ttu-id="e1a84-120">Description</span><span class="sxs-lookup"><span data-stu-id="e1a84-120">Description</span></span></p></td>
<td><p><span data-ttu-id="e1a84-121">Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).</span><span class="sxs-lookup"><span data-stu-id="e1a84-121">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1a84-122">Nombre maximal de boîtes de dialogue préliminaires prises en charge</span><span class="sxs-lookup"><span data-stu-id="e1a84-122">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="e1a84-123">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="e1a84-123">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="e1a84-124">Nombre maximal de réponses dirigées qu’une passerelle PSTN, un système IP-PBX ou un contrôleur de session en périphérie du côté fournisseur de services peut recevoir à une invitation qui est envoyée au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="e1a84-124">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a84-125">Niveau de prise en charge du chiffrement</span><span class="sxs-lookup"><span data-stu-id="e1a84-125">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="e1a84-126">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="e1a84-126">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="e1a84-127">Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle PSTN, le système IP-PBX ou le contrôleur de session en périphérie du côté fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="e1a84-127">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="e1a84-128">Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia.</span><span class="sxs-lookup"><span data-stu-id="e1a84-128">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="e1a84-129">La configuration du média est définie à l’aide des cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> et <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="e1a84-129">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="e1a84-130">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e1a84-130">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e1a84-131">Requis : le chiffrement SRTP doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="e1a84-131">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="e1a84-132">Facultatif : le chiffrement SRTP sera utilisé si la passerelle le prend en charge.</span><span class="sxs-lookup"><span data-stu-id="e1a84-132">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="e1a84-133">Non pris en charge : le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="e1a84-133">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="e1a84-p105">SRTPMode est utilisé uniquement si la passerelle est configurée en vue d’un recours au protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.</span><span class="sxs-lookup"><span data-stu-id="e1a84-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1a84-136">Prise en charge de la référence</span><span class="sxs-lookup"><span data-stu-id="e1a84-136">Refer support</span></span></p></td>
<td><p><span data-ttu-id="e1a84-137">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="e1a84-137">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="e1a84-138">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="e1a84-138">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="e1a84-139">Si défini sur <strong>Activer la référence d’appel vers la passerelle</strong>, indique que la jonction prend en charge la réception des demandes REFER à partir du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="e1a84-139">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="e1a84-140">Si défini sur <strong>Activer la référence avec un contrôle d’appel tiers</strong>, indique que le protocole 3pcc peut être utilisé pour permettre aux appels transférés de contourner le site hébergé.</span><span class="sxs-lookup"><span data-stu-id="e1a84-140">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="e1a84-141">3PCC est également appelé &quot; contrôle tiers &quot; et se produit lorsqu’un tiers est utilisé pour connecter une paire d’appelants (par exemple, un opérateur passant un appel de la personne a à la personne B).</span><span class="sxs-lookup"><span data-stu-id="e1a84-141">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a84-142">Activer le contournement de média</span><span class="sxs-lookup"><span data-stu-id="e1a84-142">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="e1a84-143">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="e1a84-143">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="e1a84-p107">Indique si le contournement de média est activé pour cette jonction. Le contournement de média peut être activé uniquement si <strong>Traitement multimédia centralisé</strong> est également activé.</span><span class="sxs-lookup"><span data-stu-id="e1a84-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1a84-146">Traitement multimédia centralisé</span><span class="sxs-lookup"><span data-stu-id="e1a84-146">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="e1a84-147">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="e1a84-147">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="e1a84-p108">Indique si une terminaison multimédia connue existe (par exemple, une passerelle PSTN où la terminaison multimédia possède la même adresse IP que la terminaison de signalisation).</span><span class="sxs-lookup"><span data-stu-id="e1a84-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a84-150">Activer l’accrochage RTP</span><span class="sxs-lookup"><span data-stu-id="e1a84-150">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="e1a84-151">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="e1a84-151">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="e1a84-p109">Indique si les jonctions SIP prennent en charge l’accrochage RTP. L’accrochage RTP est une technologie qui permet la connectivité RTP/RTCP via un appareil ou un pare-feu NAT (traduction d’adresses réseau).</span><span class="sxs-lookup"><span data-stu-id="e1a84-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1a84-154">Activer l’historique du transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="e1a84-154">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="e1a84-155">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="e1a84-155">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="e1a84-156">Indique si les informations d’historique d’appel sont transférées via la jonction.</span><span class="sxs-lookup"><span data-stu-id="e1a84-156">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a84-157">Activer les données de transfert P-Asserted-Identity</span><span class="sxs-lookup"><span data-stu-id="e1a84-157">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="e1a84-158">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="e1a84-158">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="e1a84-p110">Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e1a84-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1a84-161">Activer le minuteur de basculement de routage de trafic sortant</span><span class="sxs-lookup"><span data-stu-id="e1a84-161">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="e1a84-162">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="e1a84-162">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="e1a84-p111">Indique si les appels sortants auxquels la passerelle ne répond pas dans les 10 secondes seront acheminés vers la jonction suivante disponible ; s’il n’existe aucune jonction supplémentaire, l’appel est automatiquement abandonné. Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.</span><span class="sxs-lookup"><span data-stu-id="e1a84-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a84-165">Utilisations PSTN associées</span><span class="sxs-lookup"><span data-stu-id="e1a84-165">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="e1a84-166">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="e1a84-166">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="e1a84-167">Collection d’utilisations PSTN assignées à la jonction.</span><span class="sxs-lookup"><span data-stu-id="e1a84-167">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1a84-168">Numéro traduit à tester</span><span class="sxs-lookup"><span data-stu-id="e1a84-168">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="e1a84-169">N/A</span><span class="sxs-lookup"><span data-stu-id="e1a84-169">N/A</span></span></p></td>
<td><p><span data-ttu-id="e1a84-170">Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des paramètres de configuration des jonctions.</span><span class="sxs-lookup"><span data-stu-id="e1a84-170">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a84-171">Règles de traduction associées</span><span class="sxs-lookup"><span data-stu-id="e1a84-171">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="e1a84-172">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="e1a84-172">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="e1a84-173">Collection de règles de traduction de numéros de téléphone qui s’appliquent aux appels gérés par le routage sortant (appels acheminés vers les destinations PBX ou PSTN).</span><span class="sxs-lookup"><span data-stu-id="e1a84-173">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1a84-174">Règles de traduction du numéro appelé</span><span class="sxs-lookup"><span data-stu-id="e1a84-174">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="e1a84-175">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="e1a84-175">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="e1a84-176">Collection de règles de traduction de numéro d’appel sortant assignées à la jonction.</span><span class="sxs-lookup"><span data-stu-id="e1a84-176">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a84-177">Numéro de téléphone à tester</span><span class="sxs-lookup"><span data-stu-id="e1a84-177">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="e1a84-178">N/A</span><span class="sxs-lookup"><span data-stu-id="e1a84-178">N/A</span></span></p></td>
<td><p><span data-ttu-id="e1a84-179">Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des règles de traduction.</span><span class="sxs-lookup"><span data-stu-id="e1a84-179">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1a84-180">Numéro appelant</span><span class="sxs-lookup"><span data-stu-id="e1a84-180">Calling number</span></span></p></td>
<td><p><span data-ttu-id="e1a84-181">N/A</span><span class="sxs-lookup"><span data-stu-id="e1a84-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="e1a84-182">Indique que le numéro de téléphone à tester est celui de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="e1a84-182">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1a84-183">Numéro appelé</span><span class="sxs-lookup"><span data-stu-id="e1a84-183">Called number</span></span></p></td>
<td><p><span data-ttu-id="e1a84-184">N/A</span><span class="sxs-lookup"><span data-stu-id="e1a84-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="e1a84-185">Indique que le numéro de téléphone à tester est celui de la personne appelée.</span><span class="sxs-lookup"><span data-stu-id="e1a84-185">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e1a84-186">Les applets de commande Lync Server applet cstrunkconfiguration prennent en charge les propriétés supplémentaires qui ne figurent pas dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e1a84-186">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="e1a84-187">Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-applet cstrunkconfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="e1a84-187">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="e1a84-188">Pour créer de nouveaux paramètres de configuration de jonction à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="e1a84-188">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e1a84-189">Dans le panneau de configuration Lync Server, cliquez sur **routage des communications vocales**, puis sur Configuration de la **jonction**.</span><span class="sxs-lookup"><span data-stu-id="e1a84-189">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="e1a84-190">Sous l’onglet **Configuration de la jonction**, cliquez sur **Nouveau**, puis cliquez sur **Jonction de site** pour créer les paramètres au niveau de l’étendue Site, ou cliquez sur **Jonction de pool** pour créer les paramètres au niveau de l’étendue Service.</span><span class="sxs-lookup"><span data-stu-id="e1a84-190">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="e1a84-p113">Dans la boîte de dialogue **Sélectionner un site** ou **Sélectionner un service** (la boîte de dialogue qui s’affiche change selon que vous créez des paramètres au niveau de l’étendue Site ou au niveau de l’étendue Service), sélectionnez l’emplacement des nouveaux paramètres de configuration, puis cliquez sur **OK**. Si la boîte de dialogue est vide, cela signifie que vous ne pouvez pas créer de paramètres supplémentaires. Par exemple, si la boîte de dialogue **Sélectionner un site** est vide, cela signifie qu’une collection de sites de configuration de jonctions a déjà été affectée à l’ensemble de vos sites et que chaque site (chaque service) ne peut héberger qu’une seule collection de ce type. Dans ce cas, vous pouvez soit supprimer la collection existante et créer une autre collection, soit modifier simplement la collection existante.</span><span class="sxs-lookup"><span data-stu-id="e1a84-p113">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**. If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection. In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="e1a84-194">Dans la boîte de dialogue **Nouvelle configuration de jonction**, effectuez les sélections appropriées, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1a84-194">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="e1a84-p114">La propriété **État** de la collection aura la valeur **Non validé**. Pour valider les modifications et pour supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="e1a84-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="e1a84-197">Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1a84-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="e1a84-198">Dans la boîte de dialogue **Panneau de configuration Microsoft Lync Server 2013**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1a84-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

