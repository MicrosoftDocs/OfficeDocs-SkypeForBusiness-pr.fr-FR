---
title: Configurer le contournement de média avec un routage direct
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
ms.openlocfilehash: 459ebd80a175fbf2c213a016436a2bf130ae9982
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232693"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="382a5-103">Configurer le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="382a5-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="382a5-104">Avant de configurer le contournement de média avec le routage Direct, veillez à ce que vous avez lu [Plan pour le média de contournement de média avec le routage Direct](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="382a5-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="382a5-105">Pour activer le contournement de média, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="382a5-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="382a5-106">Assurez-vous que votre fournisseur de contrôleur de Session en périphérie (SBC) de choix prend en charge le contournement de média et fournit des instructions sur la configuration de contournement de média sur le contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="382a5-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="382a5-107">Reportez-vous à la page de certification pour en savoir plus sur SBC, qui le support celles contournement de média, et pour obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="382a5-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="382a5-108">Vous devez activer le contournement de média sur la jonction à l’aide de la commande suivante : **Set-CSOnlinePSTNGateway-Identity <sbc_FQDN> - MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="382a5-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="382a5-109">Assurez-vous que les ports requis sont ouverts.</span><span class="sxs-lookup"><span data-stu-id="382a5-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="382a5-110">Migration de jonctions non contourné vers jonctions prenant en charge contournement de média</span><span class="sxs-lookup"><span data-stu-id="382a5-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="382a5-111">Vous pouvez changer de tous les utilisateurs à la fois, ou vous pouvez implémenter une approche progressive (recommandé).</span><span class="sxs-lookup"><span data-stu-id="382a5-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="382a5-112">**Changer de tous les utilisateurs à la fois.**</span><span class="sxs-lookup"><span data-stu-id="382a5-112">**Switch all users at once.**</span></span> <span data-ttu-id="382a5-113">Si toutes les conditions sont remplies, vous pouvez activer le mode de contournement de média.</span><span class="sxs-lookup"><span data-stu-id="382a5-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="382a5-114">Toutefois, tous les utilisateurs de production bascule en même temps.</span><span class="sxs-lookup"><span data-stu-id="382a5-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="382a5-115">Étant donné que vous rencontriez certains problèmes à l’origine lorsque vous configurez des jonctions et des ports, votre expérience utilisateur de production peut être affectée.</span><span class="sxs-lookup"><span data-stu-id="382a5-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="382a5-116">Approche **en phase. (Recommandé)**.</span><span class="sxs-lookup"><span data-stu-id="382a5-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="382a5-117">Créer une nouvelle jonction pour le même SBC (avec un autre port), tester et modifier la stratégie de routage voix en ligne pour les utilisateurs afin de pointer vers la nouvelle jonction.</span><span class="sxs-lookup"><span data-stu-id="382a5-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="382a5-118">Il s’agit de l’approche recommandée car elle permet une transition plus fluide et l’expérience utilisateur sans interruption.</span><span class="sxs-lookup"><span data-stu-id="382a5-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="382a5-119">Cette approche nécessite la configuration du contrôleur SBC, un nouveau nom de domaine complet et la configuration du pare-feu.</span><span class="sxs-lookup"><span data-stu-id="382a5-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="382a5-120">Notez que vous devez vous assurer que votre certificat prend en charge les jonctions.</span><span class="sxs-lookup"><span data-stu-id="382a5-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="382a5-121">SAN, vous devez avoir deux noms (**sbc1.contoso.com** et **sbc2.contoso.com**) ou dispose d’un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="382a5-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migration de jonctions non contourné vers jonctions prenant en charge contournement de média)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="382a5-123">Pour obtenir des instructions sur la façon de configurer les jonctions et effectuer la migration, consultez la documentation de votre fournisseur SBC :</span><span class="sxs-lookup"><span data-stu-id="382a5-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- <span data-ttu-id="382a5-124">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="382a5-124">AudioCodes</span></span>
- <span data-ttu-id="382a5-125">Ruban</span><span class="sxs-lookup"><span data-stu-id="382a5-125">Ribbon</span></span>
- <span data-ttu-id="382a5-126">NOTE-Systems (AnyNode)</span><span class="sxs-lookup"><span data-stu-id="382a5-126">TE-Systems (AnyNode)</span></span>    

<span data-ttu-id="382a5-127">Pour obtenir la liste de contrôleurs de frontière de Session (SBC) certifié pour le routage Direct, voir [liste de Session Broder contrôleurs certifiés pour le routage Direct](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="382a5-127">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="382a5-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="382a5-128">See also</span></span>

[<span data-ttu-id="382a5-129">Planifier le contournement de média avec le routage Direct</span><span class="sxs-lookup"><span data-stu-id="382a5-129">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



