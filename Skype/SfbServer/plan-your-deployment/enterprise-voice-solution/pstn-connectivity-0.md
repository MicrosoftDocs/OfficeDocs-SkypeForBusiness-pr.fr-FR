---
title: Planifier la connectivité PSTN dans Skype Entreprise Server
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
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Planifiez la connectivité PSTN dans Voix Entreprise dans Skype Entreprise Server.
ms.openlocfilehash: 492f4e2cc71644cb1e9957f407a549cce5dbc31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813564"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="9d4a9-103">Planifier la connectivité PSTN dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9d4a9-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="9d4a9-104">Planifiez la connectivité PSTN dans Voix Entreprise dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="9d4a9-105">Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (PSTN) avec une qualité de service constante.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="9d4a9-106">Les utilisateurs qui passent et reçoivent des appels ne doivent pas connaître la technologie sous-jacente : du point de vue de l’utilisateur, un appel entre l’infrastructure Voix Entreprise et le réseau téléphonique (PSTN) doit se faire comme un simple appel téléphonique.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="9d4a9-107">Skype Entreprise Server offre une connectivité PSTN fiable et évolutive à l’aide des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d4a9-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="9d4a9-108">**Des trunks SIP vers** un fournisseur de services de téléphonie Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="9d4a9-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="9d4a9-109">**Connexions SIP directes** à une passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="9d4a9-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="9d4a9-110">**Connexions SIP directes** à un PBX</span><span class="sxs-lookup"><span data-stu-id="9d4a9-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="9d4a9-111">En fonction de sa taille, de sa couverture géographique et de son infrastructure vocale existante, une entreprise peut utiliser une, deux ou même les trois options à différents emplacements.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span> <span data-ttu-id="9d4a9-112">Pour plus d’informations sur ces options, voir les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="9d4a9-112">For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="9d4a9-113">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="9d4a9-113">In this section</span></span>

- [<span data-ttu-id="9d4a9-114">Une trunking SIP dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9d4a9-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="9d4a9-115">Connexions SIP directes dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9d4a9-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="9d4a9-116">M:N trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9d4a9-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="9d4a9-117">Règles de traduction dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9d4a9-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="9d4a9-118">Planifier le routage des voix sortantes dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9d4a9-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

