---
title: 'Lync Server 2013 : composants de connectivité PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63b5534b817477ea42dbefd5244c974fc70881f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a><span data-ttu-id="d92ac-102">Composants de connectivité PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d92ac-102">PSTN connectivity components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d92ac-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="d92ac-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d92ac-104">Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (RTC) avec une qualité de service constante.</span><span class="sxs-lookup"><span data-stu-id="d92ac-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="d92ac-105">En outre, la technologie sous-jacente doit être transparente pour les utilisateurs lorsqu’ils passent ou reçoivent des appels.</span><span class="sxs-lookup"><span data-stu-id="d92ac-105">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="d92ac-106">Du point de vue de l’utilisateur, un appel entre l’infrastructure voix entreprise et le RTC devrait paraître une seule et même session SIP.</span><span class="sxs-lookup"><span data-stu-id="d92ac-106">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>

<span data-ttu-id="d92ac-107">Pour les connexions RTC, vous pouvez déployer une jonction SIP ou une passerelle RTC (avec un PBX, également appelé lien SIP direct, ou sans PBX).</span><span class="sxs-lookup"><span data-stu-id="d92ac-107">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>

<div>

## <a name="sip-trunking"></a><span data-ttu-id="d92ac-108">Jonction SIP</span><span class="sxs-lookup"><span data-stu-id="d92ac-108">SIP Trunking</span></span>

<span data-ttu-id="d92ac-109">À la place des passerelles RTC, vous pouvez connecter votre solution vocale d’entreprise au RTC en utilisant le trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="d92ac-109">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="d92ac-110">La jonction SIP autorise les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="d92ac-110">SIP trunking enables the following scenarios:</span></span>

  - <span data-ttu-id="d92ac-111">Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou longue distance au format E.164 qui aboutit sur le réseau RTC en tant que service du fournisseur de services correspondant.</span><span class="sxs-lookup"><span data-stu-id="d92ac-111">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="d92ac-112">Chaque abonné RTC peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing [DID]) associé à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d92ac-112">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>

<span data-ttu-id="d92ac-113">L’utilisation de cette solution de déploiement requiert un fournisseur de services de jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="d92ac-113">The use of this deployment solution requires a SIP trunking service provider.</span></span>

</div>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="d92ac-114">Passerelles RTC</span><span class="sxs-lookup"><span data-stu-id="d92ac-114">PSTN gateways</span></span>

<span data-ttu-id="d92ac-115">Les passerelles RTC sont des appareils tiers qui convertissent le signalement et le contenu multimédia entre l’infrastructure voix entreprise et un réseau PBX ou PSTN.</span><span class="sxs-lookup"><span data-stu-id="d92ac-115">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="d92ac-116">Les passerelles RTC fonctionnent avec le serveur de médiation pour présenter un appel PSTN ou PBX à un client voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="d92ac-116">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="d92ac-117">Le serveur de médiation présente également des appels de clients voix entreprise vers la passerelle RTC pour le routage vers le RTC ou le PBX.</span><span class="sxs-lookup"><span data-stu-id="d92ac-117">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="d92ac-118">Pour obtenir la liste des partenaires qui travaillent avec Microsoft pour fournir des appareils compatibles avec Lync Server, voir le site Web Microsoft Unified [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)communications Partners à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="d92ac-118">For a list of partners who work with Microsoft to provide devices that work with Lync Server, see the Microsoft Unified Communications Partners website at [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

<div>

## <a name="private-branch-exchanges"></a><span data-ttu-id="d92ac-119">Autocommutateurs privés (PBX, Private branch exchange)</span><span class="sxs-lookup"><span data-stu-id="d92ac-119">Private Branch Exchanges</span></span>

<span data-ttu-id="d92ac-120">Si vous disposez d’une infrastructure vocale existante qui utilise un système PBX (Private Branch Exchange), vous pouvez utiliser votre système PBX avec Lync Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d92ac-120">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Lync Server Enterprise Voice.</span></span>

<span data-ttu-id="d92ac-121">Les scénarios d’intégration PBX voix entreprise pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="d92ac-121">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>

  - <span data-ttu-id="d92ac-122">IP-PBX prenant en charge la dérivation multimédia, avec un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="d92ac-122">IP-PBX that supports media bypass, with a Mediation Server.</span></span>

  - <span data-ttu-id="d92ac-123">IP-PBX qui requiert une passerelle RTC autonome.</span><span class="sxs-lookup"><span data-stu-id="d92ac-123">IP-PBX that requires a stand-alone PSTN gateway.</span></span>

  - <span data-ttu-id="d92ac-124">PBX TDM (multiplexage temporel), avec une passerelle RTC autonome.</span><span class="sxs-lookup"><span data-stu-id="d92ac-124">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d92ac-125">La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC.</span><span class="sxs-lookup"><span data-stu-id="d92ac-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="d92ac-126">Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="d92ac-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="d92ac-127">La dérivation de média est uniquement prise en charge avec les produits et les versions indiqués sur le programme d’interopérabilité d’ouverture de communications unifiées-Lync Server à <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span><span class="sxs-lookup"><span data-stu-id="d92ac-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="d92ac-128">Pour plus d’informations sur les partenaires proposant des solutions voix entreprise, consultez le site Web Microsoft [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)Unified Communications Partners à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="d92ac-128">For details about partners who offer Enterprise Voice solutions, see the Microsoft Unified Communications Partners website at [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

<span data-ttu-id="d92ac-129">Pour plus d’informations sur les partenaires qui proposent des solutions matérielles voix entreprise, notamment les passerelles RTC, consultez [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)le site Web Microsoft Unified Communications Partners.</span><span class="sxs-lookup"><span data-stu-id="d92ac-129">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the Microsoft Unified Communications Partners website [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

