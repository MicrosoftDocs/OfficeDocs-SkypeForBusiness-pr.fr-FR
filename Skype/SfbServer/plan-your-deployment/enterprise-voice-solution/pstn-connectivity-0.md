---
title: Planification de la connectivité PSTN dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
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
ms.openlocfilehash: 228391049988c2eb886c0cb4e7caccce6f55ff3b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server-2015"></a><span data-ttu-id="0e65b-103">Planification de la connectivité PSTN dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e65b-103">Plan for PSTN connectivity in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0e65b-104">Planifier la connectivité PSTN dans Enterprise Voice dans Skype Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e65b-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="0e65b-105">Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (RTC) avec une qualité de service constante.</span><span class="sxs-lookup"><span data-stu-id="0e65b-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="0e65b-106">Les utilisateurs qui émettre et recevoir des appels ne doivent pas être conscient de la technologie sous-jacente : point de vue de l’utilisateur, d’un appel entre l’infrastructure Enterprise Voice et le réseau RTC doit ressembler à tout autre appel téléphonique.</span><span class="sxs-lookup"><span data-stu-id="0e65b-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="0e65b-107">Skype pour Business Server offre une connectivité PSTN fiable et évolutive à l’aide des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="0e65b-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="0e65b-108">Les **jonctions SIP** vers un fournisseur de services de téléphonie Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="0e65b-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="0e65b-109">Les **connexions SIP directes** à une passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="0e65b-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="0e65b-110">Les **connexions SIP directes** à un système PBX</span><span class="sxs-lookup"><span data-stu-id="0e65b-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="0e65b-p102">Selon la taille, la couverture géographique et l’infrastructure vocale existante, une entreprise peut utiliser une ou deux des options, voire les trois, à divers emplacements. Pour plus d’informations sur ces options, consultez les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="0e65b-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0e65b-113">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="0e65b-113">In this section</span></span>

- [<span data-ttu-id="0e65b-114">Jonction SIP dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e65b-114">SIP trunking in Skype for Business Server 2015</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="0e65b-115">Connexions SIP directes dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e65b-115">Direct SIP connections in Skype for Business Server 2015</span></span>](direct-sip.md)
    
- [<span data-ttu-id="0e65b-116">Jonction m : n dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e65b-116">M:N trunk in Skype for Business Server 2015</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="0e65b-117">Règles de traduction dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e65b-117">Translation rules in Skype for Business Server 2015</span></span>](translation-rules.md)
    
- [<span data-ttu-id="0e65b-118">Planifier le routage des communications vocales sortantes dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e65b-118">Plan for outbound voice routing in Skype for Business Server 2015</span></span>](outbound-voice-routing.md)
    

