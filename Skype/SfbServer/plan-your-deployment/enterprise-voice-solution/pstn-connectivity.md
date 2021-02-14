---
title: Composants de connectivité PSTN dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Découvrez les passerelles PSTN et de la Voix Entreprise SIP dans Skype Entreprise Server.
ms.openlocfilehash: 6261b95906699777e62c025889d23e03d381f09d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813534"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="a7ac7-103">Composants de connectivité PSTN dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a7ac7-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="a7ac7-104">Découvrez les passerelles PSTN et de la Voix Entreprise SIP dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="a7ac7-p101">Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (PSTN) avec une qualité de service constante. En outre, la technologie sous-jacente doit être transparente pour les utilisateurs lorsqu’ils passent ou reçoivent des appels. De leur point de vue, un appel entre l’infrastructure Voix Entreprise et le RTC doit ressembler à toute autre session SIP.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-p101">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS). In addition, users should not be aware of the underlying technology when they place and receive calls. From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="a7ac7-108">Pour les connexions PSTN, vous pouvez déployer une connexion SIP ou une passerelle PSTN (avec un PBX, également appelé lien SIP direct, ou sans PBX).</span><span class="sxs-lookup"><span data-stu-id="a7ac7-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="a7ac7-109">Jonction SIP</span><span class="sxs-lookup"><span data-stu-id="a7ac7-109">SIP Trunking</span></span>

<span data-ttu-id="a7ac7-p102">Une alternative à l’utilisation des passerelles PSTN consiste à connecter votre solution Voix Entreprise au PSTN à l’aide d’une jonction SIP. La jonction SIP autorise les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="a7ac7-p102">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking. SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="a7ac7-112">Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou longue distance au format E.164 qui aboutit sur le réseau PSTN en tant que service du fournisseur de services correspondant.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="a7ac7-113">Chaque abonné PSTN peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing (DID)) associé à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="a7ac7-114">L’utilisation de cette solution de déploiement requiert un fournisseur de services de jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="a7ac7-115">Passerelles PSTN</span><span class="sxs-lookup"><span data-stu-id="a7ac7-115">PSTN gateways</span></span>

<span data-ttu-id="a7ac7-116">Les passerelles PSTN sont des périphériques tiers qui traduisent la signalisation et le trafic multimédia entre l’infrastructure Voix Entreprise et un PSTN ou un PBX.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="a7ac7-117">Les passerelles PSTN fonctionnent avec le serveur de médiation pour présenter un appel PSTN ou PBX à un client Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="a7ac7-118">Le serveur de médiation présente également des appels de clients Voix Entreprise à la passerelle PSTN pour le routage vers le PSTN ou le PBX.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="a7ac7-119">Pour obtenir la liste des partenaires qui travaillent avec Microsoft pour fournir des appareils qui fonctionnent avec Skype Entreprise Server, consultez le site [Web Microsoft Unified Communications Partners.](https://go.microsoft.com/fwlink/p/?linkId=202836)</span><span class="sxs-lookup"><span data-stu-id="a7ac7-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="a7ac7-120">Autocommutateurs privés (PBX, Private branch exchange)</span><span class="sxs-lookup"><span data-stu-id="a7ac7-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="a7ac7-121">Si vous avez une infrastructure vocale existante qui utilise un pbX (private branch exchange), vous pouvez utiliser votre PBX avec Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="a7ac7-122">Les scénarios d’intégration Voix Entreprise-PBX pris en charge sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="a7ac7-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="a7ac7-123">IP-PBX qui prend en charge le contournement de média, avec un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="a7ac7-124">IP-PBX qui requiert une passerelle PSTN autonome.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="a7ac7-125">PBX TDM (multiplexage temporel), avec une passerelle PSTN autonome.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a7ac7-126">Le contournement de média n’interagit pas avec chaque passerelle PSTN, système IP-PBX et contrôleur de session en périphérie (SBC).</span><span class="sxs-lookup"><span data-stu-id="a7ac7-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="a7ac7-127">Microsoft a testé un ensemble de passerelles PSTN et de SCS avec des partenaires certifiés et a effectué des tests avec cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="a7ac7-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="a7ac7-128">Le contournement de média est pris en charge uniquement avec les produits et versions répertoriés dans le programme d’interopérabilité d’ouverture des communications unifiées [- Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span><span class="sxs-lookup"><span data-stu-id="a7ac7-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="a7ac7-129">Pour plus d’informations sur les partenaires qui proposent des solutions Voix Entreprise, consultez le site [Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="a7ac7-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="a7ac7-130">Pour plus d’informations sur les partenaires qui proposent Voix Entreprise solutions matérielles, y compris les passerelles PSTN, consultez le site [Web Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="a7ac7-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

