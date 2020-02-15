---
title: 'Lync Server 2013 : modifier les paramètres de configuration de jonction SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8c61fac4c310eff24f14c31e67554934f3d7f67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="3f530-102">Modifier les paramètres de configuration de jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f530-102">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f530-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="3f530-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="3f530-p101">Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="3f530-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="3f530-106">L’activation ou non du contournement de média sur les jonctions.</span><span class="sxs-lookup"><span data-stu-id="3f530-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="3f530-107">Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="3f530-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="3f530-108">L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.</span><span class="sxs-lookup"><span data-stu-id="3f530-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="3f530-109">Lorsque vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de jonction SIP (Session Initiation Protocol) est créée.</span><span class="sxs-lookup"><span data-stu-id="3f530-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="3f530-110">En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).</span><span class="sxs-lookup"><span data-stu-id="3f530-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="3f530-111">Ces collections peuvent être modifiées ultérieurement à l’aide du panneau de configuration Lync Server ou de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f530-111">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="3f530-112">Lorsque vous modifiez les paramètres de configuration de jonction SIP à l’aide du panneau de configuration Lync Server, les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="3f530-112">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f530-113">Paramètre de l’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="3f530-113">UI Setting</span></span></th>
<th><span data-ttu-id="3f530-114">Paramètre PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f530-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="3f530-115">Description</span><span class="sxs-lookup"><span data-stu-id="3f530-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f530-116">Nom</span><span class="sxs-lookup"><span data-stu-id="3f530-116">Name</span></span></p></td>
<td><p><span data-ttu-id="3f530-117">Identité</span><span class="sxs-lookup"><span data-stu-id="3f530-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="3f530-p103">Identificateur unique de la collection. Cette propriété est en lecture seule ; vous ne pouvez pas changer l’identité d’une collection de paramètres de configuration de jonctions.</span><span class="sxs-lookup"><span data-stu-id="3f530-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f530-120">Description</span><span class="sxs-lookup"><span data-stu-id="3f530-120">Description</span></span></p></td>
<td><p><span data-ttu-id="3f530-121">Description</span><span class="sxs-lookup"><span data-stu-id="3f530-121">Description</span></span></p></td>
<td><p><span data-ttu-id="3f530-122">Permet aux administrateurs de stocker des informations supplémentaires sur les paramètres (par exemple, l’objectif de la configuration des jonctions).</span><span class="sxs-lookup"><span data-stu-id="3f530-122">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f530-123">Nombre maximal de boîtes de dialogue préliminaires prises en charge</span><span class="sxs-lookup"><span data-stu-id="3f530-123">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="3f530-124">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="3f530-124">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="3f530-125">Nombre maximal de réponses dirigées qu’une passerelle PSTN, un système IP-PBX ou un contrôleur de session en périphérie du côté fournisseur de services peut recevoir à une invitation qui est envoyée au serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="3f530-125">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f530-126">Niveau de prise en charge du chiffrement</span><span class="sxs-lookup"><span data-stu-id="3f530-126">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="3f530-127">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="3f530-127">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="3f530-128">Indique le niveau de prise en charge de la protection du trafic multimédia entre le serveur de médiation et la passerelle PSTN, le système IP-PBX ou le contrôleur de session en périphérie du côté fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="3f530-128">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="3f530-129">Dans les cas de déviation du trafic multimédia, cette valeur doit être compatible avec le paramètre EncryptionLevel de la configuration multimédia.</span><span class="sxs-lookup"><span data-stu-id="3f530-129">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="3f530-130">La configuration du média est définie à l’aide des cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> et <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="3f530-130">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="3f530-131">Les valeurs autorisées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3f530-131">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f530-132">Requis : le chiffrement SRTP doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="3f530-132">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="3f530-133">Facultatif : le chiffrement SRTP sera utilisé si la passerelle le prend en charge.</span><span class="sxs-lookup"><span data-stu-id="3f530-133">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="3f530-134">Non pris en charge : le chiffrement SRTP n’est pas pris en charge et ne sera donc pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="3f530-134">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="3f530-p105">SRTPMode est utilisé uniquement si la passerelle est configurée en vue d’un recours au protocole de transport TLS (Transport Layer Security). Si la passerelle est configurée avec le protocole de transport TCP, SRTPMode est défini en interne sur NotSupported.</span><span class="sxs-lookup"><span data-stu-id="3f530-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f530-137">Prise en charge de la référence</span><span class="sxs-lookup"><span data-stu-id="3f530-137">Refer support</span></span></p></td>
<td><p><span data-ttu-id="3f530-138">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="3f530-138">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="3f530-139">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="3f530-139">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="3f530-140">Si défini sur <strong>Activer la référence d’appel vers la passerelle</strong>, indique que la jonction prend en charge la réception des demandes REFER à partir du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="3f530-140">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="3f530-141">Si défini sur <strong>Activer la référence avec un contrôle d’appel tiers</strong>, indique que le protocole 3pcc peut être utilisé pour permettre aux appels transférés de contourner le site hébergé.</span><span class="sxs-lookup"><span data-stu-id="3f530-141">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="3f530-142">3PCC est également appelé contrôle &quot;tiers&quot; et se produit lorsqu’un tiers est utilisé pour connecter une paire d’appelants (par exemple, un opérateur passant un appel de la personne a à la personne B).</span><span class="sxs-lookup"><span data-stu-id="3f530-142">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f530-143">Activer le contournement de média</span><span class="sxs-lookup"><span data-stu-id="3f530-143">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="3f530-144">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="3f530-144">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="3f530-p107">Indique si le contournement de média est activé pour cette jonction. Le contournement de média peut être activé uniquement si <strong>Traitement multimédia centralisé</strong> est également activé.</span><span class="sxs-lookup"><span data-stu-id="3f530-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f530-147">Traitement multimédia centralisé</span><span class="sxs-lookup"><span data-stu-id="3f530-147">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="3f530-148">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="3f530-148">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="3f530-p108">Indique si une terminaison multimédia connue existe (par exemple, une passerelle PSTN où la terminaison multimédia possède la même adresse IP que la terminaison de signalisation).</span><span class="sxs-lookup"><span data-stu-id="3f530-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f530-151">Activer l’accrochage RTP</span><span class="sxs-lookup"><span data-stu-id="3f530-151">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="3f530-152">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="3f530-152">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="3f530-p109">Indique si les jonctions SIP prennent en charge l’accrochage RTP. L’accrochage RTP est une technologie qui permet la connectivité RTP/RTCP via un appareil ou un pare-feu NAT (traduction d’adresses réseau).</span><span class="sxs-lookup"><span data-stu-id="3f530-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f530-155">Activer l’historique du transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="3f530-155">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="3f530-156">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="3f530-156">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="3f530-157">Indique si les informations d’historique d’appel sont transférées via la jonction.</span><span class="sxs-lookup"><span data-stu-id="3f530-157">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f530-158">Activer les données de transfert P-Asserted-Identity</span><span class="sxs-lookup"><span data-stu-id="3f530-158">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="3f530-159">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="3f530-159">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="3f530-p110">Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel. L’en-tête PAI permet de vérifier l’identité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="3f530-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f530-162">Activer le minuteur de basculement de routage de trafic sortant</span><span class="sxs-lookup"><span data-stu-id="3f530-162">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="3f530-163">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="3f530-163">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="3f530-p111">Indique si les appels sortants auxquels la passerelle ne répond pas dans les 10 secondes seront acheminés vers la jonction suivante disponible ; s’il n’existe aucune jonction supplémentaire, l’appel est automatiquement abandonné. Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.</span><span class="sxs-lookup"><span data-stu-id="3f530-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f530-166">Utilisations PSTN associées</span><span class="sxs-lookup"><span data-stu-id="3f530-166">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="3f530-167">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="3f530-167">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="3f530-168">Collection d’utilisations PSTN assignées à la jonction.</span><span class="sxs-lookup"><span data-stu-id="3f530-168">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f530-169">Numéro traduit à tester</span><span class="sxs-lookup"><span data-stu-id="3f530-169">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="3f530-170">N/A</span><span class="sxs-lookup"><span data-stu-id="3f530-170">N/A</span></span></p></td>
<td><p><span data-ttu-id="3f530-171">Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des paramètres de configuration des jonctions.</span><span class="sxs-lookup"><span data-stu-id="3f530-171">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f530-172">Règles de traduction associées</span><span class="sxs-lookup"><span data-stu-id="3f530-172">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="3f530-173">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="3f530-173">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="3f530-174">Collection de règles de traduction de numéros de téléphone qui s’appliquent aux appels gérés par le routage sortant (appels acheminés vers les destinations PBX ou PSTN).</span><span class="sxs-lookup"><span data-stu-id="3f530-174">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f530-175">Règles de traduction du numéro appelé</span><span class="sxs-lookup"><span data-stu-id="3f530-175">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="3f530-176">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="3f530-176">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="3f530-177">Collection de règles de traduction de numéro d’appel sortant assignées à la jonction.</span><span class="sxs-lookup"><span data-stu-id="3f530-177">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f530-178">Numéro de téléphone à tester</span><span class="sxs-lookup"><span data-stu-id="3f530-178">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="3f530-179">N/A</span><span class="sxs-lookup"><span data-stu-id="3f530-179">N/A</span></span></p></td>
<td><p><span data-ttu-id="3f530-180">Numéro de téléphone pouvant être utilisé pour effectuer un test ad hoc des règles de traduction.</span><span class="sxs-lookup"><span data-stu-id="3f530-180">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f530-181">Numéro appelant</span><span class="sxs-lookup"><span data-stu-id="3f530-181">Calling number</span></span></p></td>
<td><p><span data-ttu-id="3f530-182">N/A</span><span class="sxs-lookup"><span data-stu-id="3f530-182">N/A</span></span></p></td>
<td><p><span data-ttu-id="3f530-183">Indique que le numéro de téléphone à tester est celui de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="3f530-183">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f530-184">Numéro appelé</span><span class="sxs-lookup"><span data-stu-id="3f530-184">Called number</span></span></p></td>
<td><p><span data-ttu-id="3f530-185">N/A</span><span class="sxs-lookup"><span data-stu-id="3f530-185">N/A</span></span></p></td>
<td><p><span data-ttu-id="3f530-186">Indique que le numéro de téléphone à tester est celui de la personne appelée.</span><span class="sxs-lookup"><span data-stu-id="3f530-186">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="3f530-187">Les applets de commande Lync Server applet cstrunkconfiguration prennent en charge les propriétés supplémentaires qui ne figurent pas dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f530-187">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="3f530-188">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-applet cstrunkconfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="3f530-188">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="3f530-189">Pour modifier les paramètres de configuration de jonction SIP à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="3f530-189">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3f530-190">Dans le panneau de configuration Lync Server, cliquez sur **routage des communications vocales**, puis sur Configuration de la **jonction**.</span><span class="sxs-lookup"><span data-stu-id="3f530-190">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="3f530-p113">Sous l’onglet **Configuration de la jonction**, double-cliquez sur les paramètres de configuration de la jonction à modifier. Notez que vous ne pouvez modifier qu’une collection de paramètres à la fois. Si vous voulez apporter les mêmes modifications à plusieurs collections, utilisez Windows PowerShell à la place.</span><span class="sxs-lookup"><span data-stu-id="3f530-p113">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified. Note that you can only edit one collection of settings at a time. If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="3f530-194">Dans la boîte de dialogue **modifier la configuration** de la jonction, effectuez les sélections appropriées, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f530-194">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="3f530-p114">La propriété **État** de la collection est mise à jour et présente la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="3f530-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="3f530-197">Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f530-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="3f530-198">Dans la boîte de dialogue **Panneau de configuration Microsoft Lync Server 2013**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f530-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

