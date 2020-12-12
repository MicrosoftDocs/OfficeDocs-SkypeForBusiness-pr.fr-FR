---
title: Migrer des appareils de système de salle Lync vers des salles Microsoft teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Consultez cette rubrique pour découvrir comment migrer des appareils de système de salle Lync pour utiliser le logiciel de salle Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662619"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="bb66a-103">Migration de périphériques LRS (Lync Room System) vers des salles Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="bb66a-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="bb66a-104">Les appareils LRS (Lync Room System) avec le logiciel Skype Room System version 1 (SRS v1) ont atteint la [fin de la prise en charge le 9 octobre 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span><span class="sxs-lookup"><span data-stu-id="bb66a-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="bb66a-105">Cela signifie que Skype Room Systems v1 ne recevra plus de mises à jour de produit ou de correctifs.</span><span class="sxs-lookup"><span data-stu-id="bb66a-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="bb66a-106">Les clients disposant d’appareils de salle Lync utilisant Skype Room v1 sont invités à mettre à niveau leurs appareils vers les salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb66a-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="bb66a-107">Le logiciel de salle Microsoft teams fonctionne avec Microsoft teams en plus de Skype entreprise Server et services en ligne pour les réunions et les appels sur tous les appareils Microsoft teams compatibles pris en charge.</span><span class="sxs-lookup"><span data-stu-id="bb66a-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="bb66a-108">Vos **appareils existants** continuent à fonctionner après la fin de la prise en charge des logiciels de la version v1 du système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="bb66a-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="bb66a-109">Toutefois, si ce logiciel rencontre un bogue logiciel qui nécessite Microsoft pour publier un correctif, il ne sera pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="bb66a-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="bb66a-110">SRS v1 utilise TLS 1.0/1,1 qui sera déconseillé par Microsoft dans le futur.</span><span class="sxs-lookup"><span data-stu-id="bb66a-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="bb66a-111">Vous pouvez en savoir plus sur la [préparation de la désapprobation TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="bb66a-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="bb66a-112">Quels appareils sont concernés ?</span><span class="sxs-lookup"><span data-stu-id="bb66a-112">Which devices are affected?</span></span>

<span data-ttu-id="bb66a-113">Voici la liste des appareils concernés par ce changement :</span><span class="sxs-lookup"><span data-stu-id="bb66a-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="bb66a-114">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="bb66a-114">Crestron RL</span></span>
- [<span data-ttu-id="bb66a-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="bb66a-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="bb66a-116">Systèmes de salle intelligente</span><span class="sxs-lookup"><span data-stu-id="bb66a-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="bb66a-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="bb66a-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="bb66a-118">Options de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="bb66a-118">Upgrade options</span></span>

<span data-ttu-id="bb66a-119">Plusieurs options s’offrent à vous pour effectuer la mise à niveau de systèmes de salle Lync vers la nouvelle génération de salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb66a-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="bb66a-120">Programme d’échange de matériel Crestron</span><span class="sxs-lookup"><span data-stu-id="bb66a-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="bb66a-121">Crestron fournira une mise à niveau vers le [système Crestron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) ou équivalent pour tous les clients de systèmes de salle non Crestron (par exemple, intelligent ou Polycom LRS).</span><span class="sxs-lookup"><span data-stu-id="bb66a-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="bb66a-122">Consultez les détails de ce programme [ici](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou</span><span class="sxs-lookup"><span data-stu-id="bb66a-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="bb66a-123">[courrier électronique](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span><span class="sxs-lookup"><span data-stu-id="bb66a-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="bb66a-124">Crestron RL2 mise à niveau vers les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="bb66a-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="bb66a-125">Les clients Crestron RL2 (également désignés sous le nom de Crestron RL200) peuvent acquérir un kit de mise à niveau pour mettre à niveau le RL2 actuel vers RL3 en utilisant un coût minimal par appareil.</span><span class="sxs-lookup"><span data-stu-id="bb66a-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="bb66a-126">Pour plus d’informations sur ce programme, voir [ici](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span><span class="sxs-lookup"><span data-stu-id="bb66a-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="bb66a-127">Mise à niveau des systèmes de salle intelligente</span><span class="sxs-lookup"><span data-stu-id="bb66a-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="bb66a-128">Pour les clients intelligents de LRS, à l’exception du programme d’échange de matériel Crestron, intelligent consiste également à proposer une solution de mise à niveau vers Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb66a-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="bb66a-129">Cette mise à niveau sera fournie par SMART Technologies Inc. au client en vertu du support technique.</span><span class="sxs-lookup"><span data-stu-id="bb66a-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="bb66a-130">Veuillez en savoir plus à [ce propos.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)</span><span class="sxs-lookup"><span data-stu-id="bb66a-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="bb66a-131">Que faire ?</span><span class="sxs-lookup"><span data-stu-id="bb66a-131">What should you do?</span></span>

<span data-ttu-id="bb66a-132">Nous vous conseillons de planifier la mise à jour des périphériques du système de salle Lync vers les salles de votre application avant TLS 1.0/1.1 à l’aide des options de mise à niveau mentionnées ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="bb66a-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="bb66a-133">Par ailleurs, vous pouvez également envisager de remplacer des appareils existants par de nouveaux appareils certifiés pour les salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb66a-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="bb66a-134">Pour plus d’informations, consultez la section [périphériques de salle](https://aka.ms/roomdevices) et prenez en revue la [Configuration requise pour Microsoft teams](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="bb66a-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="bb66a-135">Le logiciel de salles de Microsoft teams prend en charge le protocole TLS 1,2 au 14 décembre 2018 avec la version 4.0.64.0.</span><span class="sxs-lookup"><span data-stu-id="bb66a-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="bb66a-136">Pour les clients sur site, l’activation de la communication via TLS 1,2 pour les salles Microsoft teams nécessite Skype entreprise Server 2015 cumulative Update 9 (CU9) ou Skype entreprise Server 2019 cumulative update 1 (CU1).</span><span class="sxs-lookup"><span data-stu-id="bb66a-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="bb66a-137">Le changement ne devrait pas affecter les clients de Skype entreprise Online, car les modifications apportées au client sont conformes et en amont.</span><span class="sxs-lookup"><span data-stu-id="bb66a-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
