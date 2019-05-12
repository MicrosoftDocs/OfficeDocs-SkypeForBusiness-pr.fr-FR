---
title: Planifier la connectivité PSTN dans Skype Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Planifier la connectivité PSTN dans Enterprise Voice dans Skype Business Server.
ms.openlocfilehash: aa3449746c539e7b7bf8fe5332fa4313f80fa555
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913569"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="8e9d4-103">Planifier la connectivité PSTN dans Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="8e9d4-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="8e9d4-104">Planifier la connectivité PSTN dans Enterprise Voice dans Skype Business Server.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="8e9d4-105">Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (RTC) avec une qualité de service constante.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="8e9d4-106">Les utilisateurs qui émettre et recevoir des appels ne doivent pas être conscient de la technologie sous-jacente : point de vue de l’utilisateur, d’un appel entre l’infrastructure Enterprise Voice et le réseau RTC doit ressembler à tout autre appel téléphonique.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="8e9d4-107">Skype pour Business Server offre une connectivité PSTN fiable et évolutive à l’aide des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="8e9d4-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="8e9d4-108">Les **jonctions SIP** vers un fournisseur de services de téléphonie Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="8e9d4-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="8e9d4-109">Les **connexions SIP directes** à une passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="8e9d4-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="8e9d4-110">Les **connexions SIP directes** à un système PBX</span><span class="sxs-lookup"><span data-stu-id="8e9d4-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="8e9d4-p102">Selon la taille, la couverture géographique et l’infrastructure vocale existante, une entreprise peut utiliser une ou deux des options, voire les trois, à divers emplacements. Pour plus d’informations sur ces options, consultez les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8e9d4-113">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="8e9d4-113">In this section</span></span>

- [<span data-ttu-id="8e9d4-114">Jonction SIP dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="8e9d4-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="8e9d4-115">Connexions SIP directes dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="8e9d4-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="8e9d4-116">Jonction m : n dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="8e9d4-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="8e9d4-117">Règles de traduction dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="8e9d4-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="8e9d4-118">Planifier le routage des communications vocales sortantes dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="8e9d4-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

