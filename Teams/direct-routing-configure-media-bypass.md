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
description: Pour plus d’informations sur la configuration du contournement multimédia avec le routage direct du système téléphonique, lisez cette rubrique.
ms.openlocfilehash: 2931194783e2055c468ec2d7ad1286b9fe1940ae
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572233"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="e6d53-103">Configurer le contournement de média avec un routage direct</span><span class="sxs-lookup"><span data-stu-id="e6d53-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="e6d53-104">Avant de configurer la dérivation de médias avec le routage direct, assurez-vous d’avoir un [plan de lecture pour la dérivation de média avec le routage direct](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="e6d53-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="e6d53-105">Pour activer le contournement du contenu multimédia, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="e6d53-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="e6d53-106">Assurez-vous que le fournisseur de votre contrôleur de bordure de session (SBC) prend en charge la méthode de contournement du contenu multimédia et fournit des instructions sur la configuration du contournement sur la SBC.</span><span class="sxs-lookup"><span data-stu-id="e6d53-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="e6d53-107">Reportez-vous à la page de certification pour en savoir plus sur les éléments SBCs, qui prennent en charge la contournement du support technique et des instructions.</span><span class="sxs-lookup"><span data-stu-id="e6d53-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="e6d53-108">Vous devez activer la dérivation multimédia sur le Trunk en utilisant la commande suivante : **Set-CSOnlinePSTNGateway-identity <sbc_FQDN>-MediaBypass $true**.</span><span class="sxs-lookup"><span data-stu-id="e6d53-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="e6d53-109">Vérifiez que les ports requis sont ouverts.</span><span class="sxs-lookup"><span data-stu-id="e6d53-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="e6d53-110">Migrer entre des Trunks non ignorés et des Trunks compatibles avec bypass</span><span class="sxs-lookup"><span data-stu-id="e6d53-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="e6d53-111">Vous pouvez basculer tous les utilisateurs à la fois ou vous pouvez implémenter une approche échelonnée (recommandé).</span><span class="sxs-lookup"><span data-stu-id="e6d53-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="e6d53-112">**Basculer tous les utilisateurs en même temps.**</span><span class="sxs-lookup"><span data-stu-id="e6d53-112">**Switch all users at once.**</span></span> <span data-ttu-id="e6d53-113">Si toutes les conditions sont remplies, vous pouvez activer le mode contournement.</span><span class="sxs-lookup"><span data-stu-id="e6d53-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="e6d53-114">Toutefois, tous vos utilisateurs de production seront basculés en même temps.</span><span class="sxs-lookup"><span data-stu-id="e6d53-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="e6d53-115">Comme il se peut que vous rencontriez des problèmes au départ lorsque vous configurez des Trunks et des ports, il est possible que l’interface utilisateur de production soit affectée.</span><span class="sxs-lookup"><span data-stu-id="e6d53-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="e6d53-116">**Approche progressive. (Recommandé)**.</span><span class="sxs-lookup"><span data-stu-id="e6d53-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="e6d53-117">Créez une nouvelle Trunk pour la même SBC (avec un port différent), testez-la, puis modifiez la stratégie de routage de la voix en ligne pour les utilisateurs afin qu’ils pointent vers le nouveau Trunk.</span><span class="sxs-lookup"><span data-stu-id="e6d53-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="e6d53-118">Il s’agit de l’approche recommandée, car elle permet une transition plus fluide et une utilisation ininterrompue des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e6d53-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="e6d53-119">Cette approche nécessite une configuration de SBC, un nouveau nom de domaine complet et une configuration du pare-feu.</span><span class="sxs-lookup"><span data-stu-id="e6d53-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="e6d53-120">Remarque vous devrez vous assurer que votre certificat prend en charge les deux Trunks.</span><span class="sxs-lookup"><span data-stu-id="e6d53-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="e6d53-121">Dans SAN, vous devez avoir deux noms (**sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.</span><span class="sxs-lookup"><span data-stu-id="e6d53-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Migrer entre des Trunks non ignorés et des Trunks compatibles avec le contournement du réseau.](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="e6d53-123">Pour obtenir des instructions sur la façon de configurer les Trunks et de procéder à la migration, consultez la documentation de votre fournisseur de SBC :</span><span class="sxs-lookup"><span data-stu-id="e6d53-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="e6d53-124">Documentation de déploiement AudioCodes</span><span class="sxs-lookup"><span data-stu-id="e6d53-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="e6d53-125">Documentation relative au déploiement d’Oracle</span><span class="sxs-lookup"><span data-stu-id="e6d53-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="e6d53-126">Documentation sur le déploiement des communications du ruban</span><span class="sxs-lookup"><span data-stu-id="e6d53-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="e6d53-127">Documentation sur le déploiement de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="e6d53-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="e6d53-128">Pour obtenir la liste des contrôleurs de frontière de session (SBCs) certifiés pour le routage direct, voir [liste des contrôleurs de session des bordures certifiés pour le routage direct](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="e6d53-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="e6d53-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6d53-129">See also</span></span>

[<span data-ttu-id="e6d53-130">Envisager une dérivation de média avec le routage direct</span><span class="sxs-lookup"><span data-stu-id="e6d53-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



