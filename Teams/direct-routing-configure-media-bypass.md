---
title: Configurer le contournement de média avec un routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment configurer la dérivation média avec le routage direct du système téléphonique pour Microsoft Teams en changeant tous les utilisateurs en une fois ou en implémentant une approche progressive (recommandé).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416894"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="fd948-103">Configurer le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="fd948-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="fd948-104">Avant de configurer la dérivation média avec le routage direct, veillez à lire le plan de dérivation [média avec le routage direct.](direct-routing-plan-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="fd948-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="fd948-105">Pour activer la dérivation média, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="fd948-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="fd948-106">Assurez-vous que le fournisseur de votre choix de contrôleur de session en bordure (SBC) prend en charge la dérivation média et fournit des instructions sur la configuration de la dérivation sur le SBC.</span><span class="sxs-lookup"><span data-stu-id="fd948-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="fd948-107">Reportez-vous à la page de certification pour en savoir plus sur les SBCs, lesquels supportent la dérivation média, et pour obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="fd948-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="fd948-108">Vous devez activer la dérivation média sur la ligne à l’aide de la commande suivante : **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true.**</span><span class="sxs-lookup"><span data-stu-id="fd948-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="fd948-109">Assurez-vous que les ports requis sont ouverts.</span><span class="sxs-lookup"><span data-stu-id="fd948-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="fd948-110">Migrer des ligne sans contournement vers des ligne activées par dérivation</span><span class="sxs-lookup"><span data-stu-id="fd948-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="fd948-111">Vous pouvez changer tous les utilisateurs en une fois ou implémenter une approche progressive (recommandé).</span><span class="sxs-lookup"><span data-stu-id="fd948-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="fd948-112">**Basculez tous les utilisateurs en une fois.**</span><span class="sxs-lookup"><span data-stu-id="fd948-112">**Switch all users at once.**</span></span> <span data-ttu-id="fd948-113">Si toutes les conditions sont remplies, vous pouvez activer le mode contournement.</span><span class="sxs-lookup"><span data-stu-id="fd948-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="fd948-114">Toutefois, tous vos utilisateurs de production seront basculés en même temps.</span><span class="sxs-lookup"><span data-stu-id="fd948-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="fd948-115">Comme vous risquez de faire face à des problèmes initialement lors de la configuration de ports et de ligne, votre expérience utilisateur en production peut être affectée.</span><span class="sxs-lookup"><span data-stu-id="fd948-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="fd948-116">**Approche progressive. (Recommandé).**</span><span class="sxs-lookup"><span data-stu-id="fd948-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="fd948-117">Créez une ligne pour le même port SBC (avec un autre port), testez-la et modifiez la stratégie de routage voix en ligne pour que les utilisateurs pointent vers la nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="fd948-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="fd948-118">Il s’agit de l’approche recommandée, car elle permet une transition plus fluide et une expérience utilisateur ininterrompue.</span><span class="sxs-lookup"><span data-stu-id="fd948-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="fd948-119">Cette approche nécessite la configuration du SBC, d’un nouveau nom de nom de domaine complet (FQDN) et de la configuration du pare-feu.</span><span class="sxs-lookup"><span data-stu-id="fd948-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="fd948-120">Notez que vous devez vous assurer que votre certificat prend en charge les deux ligne.</span><span class="sxs-lookup"><span data-stu-id="fd948-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="fd948-121">En san san, vous devez avoir deux noms **(sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="fd948-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migrer des ligne sans contournement vers des ligne activées par dérivation)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="fd948-123">Pour obtenir des instructions sur la configuration des ligne et l’étape de migration, consultez la documentation de votre fournisseur SBC :</span><span class="sxs-lookup"><span data-stu-id="fd948-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="fd948-124">Documentation sur le déploiement de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="fd948-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="fd948-125">Documentation sur le déploiement d’Oracle</span><span class="sxs-lookup"><span data-stu-id="fd948-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="fd948-126">Documentation de déploiement de Communications du ruban</span><span class="sxs-lookup"><span data-stu-id="fd948-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="fd948-127">Documentation sur le déploiement des systèmes TE (anynode)</span><span class="sxs-lookup"><span data-stu-id="fd948-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="fd948-128">Pour obtenir la liste des contrôleurs de session en bordure certifiés pour le routage direct, consultez la liste des contrôleurs de session Broder certifiés pour le [routage direct.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="fd948-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="fd948-129">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="fd948-129">Related topics</span></span>

[<span data-ttu-id="fd948-130">Planifier la dérivation média avec le routage direct</span><span class="sxs-lookup"><span data-stu-id="fd948-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



