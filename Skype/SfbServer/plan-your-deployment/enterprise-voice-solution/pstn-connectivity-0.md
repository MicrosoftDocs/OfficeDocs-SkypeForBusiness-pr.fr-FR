---
title: Planifier la connectivité PSTN dans Skype Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Planifier la connectivité PSTN dans Enterprise Voice dans Skype Business Server.
ms.openlocfilehash: ed8b4d29dd6d2fdfc3592fba4236f4a99b9ee05d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003870"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="e784a-103">Planifier la connectivité PSTN dans Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="e784a-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="e784a-104">Planifier la connectivité PSTN dans Enterprise Voice dans Skype Business Server.</span><span class="sxs-lookup"><span data-stu-id="e784a-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="e784a-105">Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (RTC) avec une qualité de service constante.</span><span class="sxs-lookup"><span data-stu-id="e784a-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="e784a-106">Les utilisateurs qui émettre et recevoir des appels ne doivent pas être conscient de la technologie sous-jacente : point de vue de l’utilisateur, d’un appel entre l’infrastructure Enterprise Voice et le réseau RTC doit ressembler à tout autre appel téléphonique.</span><span class="sxs-lookup"><span data-stu-id="e784a-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="e784a-107">Skype pour Business Server offre une connectivité PSTN fiable et évolutive à l’aide des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e784a-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="e784a-108">Les **jonctions SIP** vers un fournisseur de services de téléphonie Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="e784a-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="e784a-109">Les **connexions SIP directes** à une passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="e784a-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="e784a-110">Les **connexions SIP directes** à un système PBX</span><span class="sxs-lookup"><span data-stu-id="e784a-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="e784a-p102">Selon la taille, la couverture géographique et l’infrastructure vocale existante, une entreprise peut utiliser une ou deux des options, voire les trois, à divers emplacements. Pour plus d’informations sur ces options, consultez les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="e784a-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="e784a-113">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="e784a-113">In this section</span></span>

- [<span data-ttu-id="e784a-114">Jonction SIP dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e784a-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="e784a-115">Connexions SIP directes dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e784a-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="e784a-116">Jonction m : n dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e784a-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="e784a-117">Règles de traduction dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e784a-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="e784a-118">Planifier le routage des communications vocales sortantes dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e784a-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

