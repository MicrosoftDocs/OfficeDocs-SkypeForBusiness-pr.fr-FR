---
title: Composants de connectivité PSTN dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: En savoir plus sur l’acheminement SIP et des passerelles PSTN pour Enterprise Voice sur Skype pour Business Server.
ms.openlocfilehash: 06c4b79d07b776b4f5820f67ab86ac958db32686
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876999"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="a946f-103">Composants de connectivité PSTN dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="a946f-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="a946f-104">En savoir plus sur l’acheminement SIP et des passerelles PSTN pour Enterprise Voice sur Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="a946f-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="a946f-105">Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (RTC) avec une qualité de service constante.</span><span class="sxs-lookup"><span data-stu-id="a946f-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="a946f-106">En outre, la technologie sous-jacente doit être transparente pour les utilisateurs lorsqu’ils passent ou reçoivent des appels.</span><span class="sxs-lookup"><span data-stu-id="a946f-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="a946f-107">Point de vue de l’utilisateur, d’un appel entre l’infrastructure Enterprise Voice et le réseau RTC doit ressembler à toute autre session SIP.</span><span class="sxs-lookup"><span data-stu-id="a946f-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="a946f-108">Pour les connexions RTC, vous pouvez déployer une jonction SIP ou une passerelle RTC (avec un PBX, également appelé lien SIP direct, ou sans PBX).</span><span class="sxs-lookup"><span data-stu-id="a946f-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="a946f-109">Jonction SIP</span><span class="sxs-lookup"><span data-stu-id="a946f-109">SIP Trunking</span></span>

<span data-ttu-id="a946f-110">Comme alternative à l’utilisation de passerelles PSTN, vous pouvez connecter votre solution Enterprise Voice au RTC à l’aide de l’acheminement SIP.</span><span class="sxs-lookup"><span data-stu-id="a946f-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="a946f-111">La jonction SIP autorise les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="a946f-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="a946f-112">Un utilisateur d’entreprise, qu’il se trouve à l’intérieur ou à l’extérieur des limites du pare-feu de l’entreprise, peut passer un appel local ou longue distance au format E.164 qui aboutit sur le réseau RTC en tant que service du fournisseur de services correspondant.</span><span class="sxs-lookup"><span data-stu-id="a946f-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="a946f-113">Chaque abonné RTC peut contacter un utilisateur d’entreprise à l’intérieur ou à l’extérieur des limites du pare-feu en composant un numéro SDA (sélection directe à l’arrivée, Direct Inward Dialing [DID]) associé à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a946f-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="a946f-114">L’utilisation de cette solution de déploiement requiert un fournisseur de services de jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="a946f-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="a946f-115">Passerelles RTC</span><span class="sxs-lookup"><span data-stu-id="a946f-115">PSTN gateways</span></span>

<span data-ttu-id="a946f-116">Passerelles PSTN sont des périphériques tiers qui traduisent la signalisation et les médias entre l’infrastructure Enterprise Voice et un réseau RTC ou un PBX.</span><span class="sxs-lookup"><span data-stu-id="a946f-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="a946f-117">Passerelles PSTN fonctionnent avec le serveur de médiation pour présenter un appel RTC ou PBX à un client Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a946f-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="a946f-118">Le serveur de médiation présente également les appels de clients Enterprise Voice vers la passerelle PSTN pour le routage vers le RTC ou un PBX.</span><span class="sxs-lookup"><span data-stu-id="a946f-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="a946f-119">Pour obtenir la liste des partenaires qui travaillent avec Microsoft pour fournir des périphériques fonctionnant avec Skype pour Business Server, consultez [le site Web partenaires des Communications unifiées de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="a946f-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="a946f-120">Autocommutateurs privés (PBX, Private branch exchange)</span><span class="sxs-lookup"><span data-stu-id="a946f-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="a946f-121">Si vous disposez d’une infrastructure vocale existante qui utilise un autocommutateur privé (PBX), vous pouvez utiliser votre système PBX avec Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a946f-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="a946f-122">Les scénarios d’intégration voix entreprise-PBX pris en charge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a946f-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="a946f-123">IP-PBX qui prend en charge le contournement de média, avec un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a946f-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="a946f-124">IP-PBX qui requiert une passerelle RTC autonome.</span><span class="sxs-lookup"><span data-stu-id="a946f-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="a946f-125">PBX TDM (multiplexage temporel), avec une passerelle RTC autonome.</span><span class="sxs-lookup"><span data-stu-id="a946f-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a946f-126">La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et SBC.</span><span class="sxs-lookup"><span data-stu-id="a946f-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="a946f-127">Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="a946f-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="a946f-128">Le contournement de média est pris en charge uniquement avec les produits et les versions répertoriés au [Unified Communications programme Open Interoperability - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span><span class="sxs-lookup"><span data-stu-id="a946f-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="a946f-129">Pour plus d’informations sur les partenaires qui proposent des solutions voix entreprise, consultez le [site Web des partenaires des Communications unifiées de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="a946f-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="a946f-130">Pour plus d’informations sur les partenaires qui proposent des solutions matérielles de voix entreprise, notamment des passerelles PSTN, consultez le [site Web des partenaires des Communications unifiées de Microsoft](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="a946f-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

