---
title: Planifier la connectivité PSTN dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Planifiez la connectivité PSTN dans voix entreprise dans Skype entreprise Server.
ms.openlocfilehash: 12c18ba0be3f01651fb72ff325d7e51566da86ae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802544"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="aa73b-103">Planifier la connectivité PSTN dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="aa73b-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="aa73b-104">Planifiez la connectivité PSTN dans voix entreprise dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="aa73b-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="aa73b-105">Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (RTC) avec une qualité de service constante.</span><span class="sxs-lookup"><span data-stu-id="aa73b-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="aa73b-106">Les utilisateurs qui passent et reçoivent des appels ne doivent pas être informés de la technologie sous-jacente : du point de vue de l’utilisateur, un appel entre l’infrastructure voix entreprise et le RTC devrait paraître un appel téléphonique.</span><span class="sxs-lookup"><span data-stu-id="aa73b-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="aa73b-107">Skype entreprise Server fournit une connectivité PSTN fiable et évolutive en utilisant les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="aa73b-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="aa73b-108">Les **jonctions SIP** vers un fournisseur de services de téléphonie Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="aa73b-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="aa73b-109">Les **connexions SIP directes** à une passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="aa73b-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="aa73b-110">Les **connexions SIP directes** à un système PBX</span><span class="sxs-lookup"><span data-stu-id="aa73b-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="aa73b-p102">Selon la taille, la couverture géographique et l’infrastructure vocale existante, une entreprise peut utiliser une ou deux des options, voire les trois, à divers emplacements. Pour plus d’informations sur ces options, consultez les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="aa73b-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="aa73b-113">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="aa73b-113">In this section</span></span>

- [<span data-ttu-id="aa73b-114">Trunking SIP dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="aa73b-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="aa73b-115">Connexions SIP directes dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="aa73b-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="aa73b-116">M :N Trunk dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="aa73b-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="aa73b-117">Règles de traduction dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="aa73b-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="aa73b-118">Planifier le routage des communications sortantes dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="aa73b-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

