---
title: Configurer le contournement de média avec le routage Direct
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lisez cette rubrique pour savoir comment configurer le contournement de média avec le routage d’un système téléphonique Direct.
ms.openlocfilehash: 405f71fd0a1e0ea3e8fec6ee1061786c93fabf1b
ms.sourcegitcommit: 260635a24b282fbdf4a4aeffdb0f4f9be5407ec6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30631042"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="54c72-103">Configurer le contournement de média avec le routage Direct</span><span class="sxs-lookup"><span data-stu-id="54c72-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="54c72-104">Avant de configurer le contournement de média avec le routage Direct, veillez à ce que vous avez lu [Plan pour le média de contournement de média avec le routage Direct](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="54c72-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="54c72-105">Pour activer le contournement de média, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="54c72-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="54c72-106">Assurez-vous que votre fournisseur de contrôleur de Session en périphérie (SBC) de choix prend en charge le contournement de média et fournit des instructions sur la configuration de contournement de média sur le contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="54c72-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="54c72-107">Reportez-vous à la page de certification pour en savoir plus sur SBC, qui le support celles contournement de média, et pour obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="54c72-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="54c72-108">Vous devez activer le contournement de média sur la jonction à l’aide de la commande suivante : **Set-CSOnlinePSTNGateway-Identity <sbc_FQDN> - MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="54c72-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="54c72-109">Assurez-vous que les ports requis sont ouverts.</span><span class="sxs-lookup"><span data-stu-id="54c72-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="54c72-110">Migration de jonctions non contourné vers jonctions prenant en charge contournement de média</span><span class="sxs-lookup"><span data-stu-id="54c72-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="54c72-111">Vous pouvez changer de tous les utilisateurs à la fois, ou vous pouvez implémenter une approche progressive (recommandé).</span><span class="sxs-lookup"><span data-stu-id="54c72-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="54c72-112">**Changer de tous les utilisateurs à la fois.**</span><span class="sxs-lookup"><span data-stu-id="54c72-112">**Switch all users at once.**</span></span> <span data-ttu-id="54c72-113">Si toutes les conditions sont remplies, vous pouvez activer le mode de contournement de média.</span><span class="sxs-lookup"><span data-stu-id="54c72-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="54c72-114">Toutefois, tous les utilisateurs de production bascule en même temps.</span><span class="sxs-lookup"><span data-stu-id="54c72-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="54c72-115">Étant donné que vous rencontriez certains problèmes à l’origine lorsque vous configurez des jonctions et des ports, votre expérience utilisateur de production peut être affectée.</span><span class="sxs-lookup"><span data-stu-id="54c72-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="54c72-116">Approche **en phase. (Recommandé)**.</span><span class="sxs-lookup"><span data-stu-id="54c72-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="54c72-117">Créer une nouvelle jonction pour le même SBC (avec un autre port), tester et modifier la stratégie de routage voix en ligne pour les utilisateurs afin de pointer vers la nouvelle jonction.</span><span class="sxs-lookup"><span data-stu-id="54c72-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="54c72-118">Il s’agit de l’approche recommandée car elle permet une transition plus fluide et l’expérience utilisateur sans interruption.</span><span class="sxs-lookup"><span data-stu-id="54c72-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="54c72-119">Cette approche nécessite la configuration du contrôleur SBC, un nouveau nom de domaine complet et la configuration du pare-feu.</span><span class="sxs-lookup"><span data-stu-id="54c72-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="54c72-120">Notez que vous devez vous assurer que votre certificat prend en charge les jonctions.</span><span class="sxs-lookup"><span data-stu-id="54c72-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="54c72-121">SAN, vous devez avoir deux noms (**sbc1.contoso.com** et **sbc2.contoso.com**) ou dispose d’un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="54c72-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migration de jonctions non contourné vers jonctions prenant en charge contournement de média)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="54c72-123">Pour obtenir des instructions sur la façon de configurer les jonctions et effectuer la migration, consultez la documentation de votre fournisseur SBC :</span><span class="sxs-lookup"><span data-stu-id="54c72-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- <span data-ttu-id="54c72-124">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="54c72-124">AudioCodes</span></span>
- <span data-ttu-id="54c72-125">Ruban</span><span class="sxs-lookup"><span data-stu-id="54c72-125">Ribbon</span></span>
- <span data-ttu-id="54c72-126">NOTE-Systems (AnyNode)</span><span class="sxs-lookup"><span data-stu-id="54c72-126">TE-Systems (AnyNode)</span></span>    

<span data-ttu-id="54c72-127">Au moment de cette annonce, les SBCs suivantes sont entièrement testées et certifiées pour fonctionner avec le contournement de média :</span><span class="sxs-lookup"><span data-stu-id="54c72-127">At the moment of this announcement, the following SBCs are fully tested and certified to work with media bypass:</span></span>

- <span data-ttu-id="54c72-128">AudioCodes 9000 V7.20A.204.222, AudioCodes M800B-SBC / V7.20A.250.003</span><span class="sxs-lookup"><span data-stu-id="54c72-128">AudioCodes 9000 V7.20A.204.222, AudioCodes M800B-SBC/ V7.20A.250.003</span></span>

-   <span data-ttu-id="54c72-129">Ruban</span><span class="sxs-lookup"><span data-stu-id="54c72-129">Ribbon</span></span>
    - <span data-ttu-id="54c72-130">5210 v06.02.xx-xxx</span><span class="sxs-lookup"><span data-stu-id="54c72-130">5210 v06.02.xx-xxx</span></span> 
    - <span data-ttu-id="54c72-131">5400, v06.02.xx-xxx</span><span class="sxs-lookup"><span data-stu-id="54c72-131">5400, v06.02.xx-xxx</span></span>
    - <span data-ttu-id="54c72-132">5110, v06.02.xx-xxx</span><span class="sxs-lookup"><span data-stu-id="54c72-132">5110, v06.02.xx-xxx</span></span>

-   <span data-ttu-id="54c72-133">Système de note AnyNode v 3.16.2</span><span class="sxs-lookup"><span data-stu-id="54c72-133">TE-System AnyNode v 3.16.2</span></span> 


## <a name="see-also"></a><span data-ttu-id="54c72-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54c72-134">See also</span></span>

[<span data-ttu-id="54c72-135">Planifier le contournement de média avec le routage Direct</span><span class="sxs-lookup"><span data-stu-id="54c72-135">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



