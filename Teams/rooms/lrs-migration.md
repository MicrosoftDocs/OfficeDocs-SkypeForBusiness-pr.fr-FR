---
title: Migrer des appareils Lync Room System vers Salles Microsoft Teams
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
description: Lisez cette rubrique pour découvrir comment migrer des appareils Lync Room System pour utiliser le Salles Microsoft Teams logiciel.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7e850b5f5f0f210abf7defc2e53cc510c5c0b0c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117522"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="816c1-103">Migrer des appareils Lync Room System (LRS) vers Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="816c1-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="816c1-104">Le support des appareils Lync Room System (LRS) avec le logiciel Skype Room System version 1 (SRS v1) a pris fin le 9 octobre [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)</span><span class="sxs-lookup"><span data-stu-id="816c1-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="816c1-105">Cela signifie que Skype Room Systems v1 ne recevra plus de mises à jour de produit ou de correctifs.</span><span class="sxs-lookup"><span data-stu-id="816c1-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="816c1-106">Les clients disposant d’appareils de salle Lync utilisant Skype Room v1 sont invités à mettre à niveau leurs appareils vers les salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="816c1-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="816c1-107">Salles Microsoft Teams logiciel fonctionne avec Microsoft Teams en plus des services Skype Entreprise Server online pour les réunions et les appels sur tous Salles Microsoft Teams appareils pris en charge.</span><span class="sxs-lookup"><span data-stu-id="816c1-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="816c1-108">Vos appareils existants **peuvent continuer à** fonctionner après la fin de Skype prise en charge du logiciel Room System v1.</span><span class="sxs-lookup"><span data-stu-id="816c1-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="816c1-109">Toutefois, si ce logiciel se produit après un bogue logiciel qui nécessite la publication d’un correctif par Microsoft, il ne sera pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="816c1-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="816c1-110">SRS v1 utilise TLS 1.0/1.1 que Microsoft utilisera à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="816c1-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="816c1-111">Vous pouvez en savoir plus sur la préparation de la retrait de [TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)</span><span class="sxs-lookup"><span data-stu-id="816c1-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="816c1-112">Quels appareils sont concernés ?</span><span class="sxs-lookup"><span data-stu-id="816c1-112">Which devices are affected?</span></span>

<span data-ttu-id="816c1-113">Voici la liste des appareils concernés par ce changement :</span><span class="sxs-lookup"><span data-stu-id="816c1-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="816c1-114">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="816c1-114">Crestron RL</span></span>
- [<span data-ttu-id="816c1-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="816c1-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="816c1-116">Systèmes de salle intelligente</span><span class="sxs-lookup"><span data-stu-id="816c1-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="816c1-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="816c1-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="816c1-118">Options de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="816c1-118">Upgrade options</span></span>

<span data-ttu-id="816c1-119">Plusieurs options s’offrent à vous pour mettre à niveau les systèmes de salle Lync vers la nouvelle génération de Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="816c1-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="816c1-120">Hardware Trade-in program (Matériel de pointe)</span><span class="sxs-lookup"><span data-stu-id="816c1-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="816c1-121">Crestron proposera une mise à niveau du système [SR de Crestron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) ou un équivalent pour tous les clients Non-Crestron Lync Room System (par exemple, Smart ou Polycom LRS).</span><span class="sxs-lookup"><span data-stu-id="816c1-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="816c1-122">Consultez les détails de ce [programme ici ou](https://support.crestron.com/app/answers/answer_view/a_id/1000220)</span><span class="sxs-lookup"><span data-stu-id="816c1-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="816c1-123">[e-mail](mailto:lrsupgrade@crestron.com) Prise en charge de Crestron LRS.</span><span class="sxs-lookup"><span data-stu-id="816c1-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="816c1-124">Upgrade to Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="816c1-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="816c1-125">Les clients existants de Crestron RL2 (également appelés RL200) peuvent acquérir un kit de mise à niveau pour mettre à niveau la version actuelle de RL2 vers RL3 à l’aide d’un coût minimal par appareil.</span><span class="sxs-lookup"><span data-stu-id="816c1-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="816c1-126">Consultez les détails de ce [programme ici.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)</span><span class="sxs-lookup"><span data-stu-id="816c1-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="816c1-127">Mise à niveau des systèmes de salle SMART Room</span><span class="sxs-lookup"><span data-stu-id="816c1-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="816c1-128">Pour les clients SMART LRS, à l’exception du programme de cérité du matériel de Crestron, SMART travaille également à la fourniture d’une solution pour la mise à niveau vers Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="816c1-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="816c1-129">Cette mise à niveau sera fournie par SMART Technologies Inc. au client sous support technique.</span><span class="sxs-lookup"><span data-stu-id="816c1-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="816c1-130">Consultez plus d’informations à ce [sujet ici.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)</span><span class="sxs-lookup"><span data-stu-id="816c1-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="816c1-131">Que devez-vous faire ?</span><span class="sxs-lookup"><span data-stu-id="816c1-131">What should you do?</span></span>

<span data-ttu-id="816c1-132">Nous vous recommandons de planifier la mise à jour des appareils Lync Room System Salles Microsoft Teams avant la dés déconseillation de TLS 1.0/1.1 à l’aide des options de mise à niveau mentionnées ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="816c1-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="816c1-133">En outre, vous pouvez également envisager de remplacer les appareils existants par de nouveaux appareils certifiés Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="816c1-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="816c1-134">Pour [plus d’informations,](https://aka.ms/roomdevices) consultez les appareils De salle et consultez [la Salles Microsoft Teams requise.](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)</span><span class="sxs-lookup"><span data-stu-id="816c1-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="816c1-135">Salles Microsoft Teams prend en charge le protocole TLS 1.2 à partir du 14 décembre 2018 avec la version d’application 4.0.64.0.</span><span class="sxs-lookup"><span data-stu-id="816c1-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="816c1-136">Pour les clients locaux, l’activation de la communication sur TLS 1.2 pour Salles Microsoft Teams nécessite la mise à jour cumulative Skype Entreprise Server 9 (CU9) ou la mise à jour cumulative Skype Entreprise Server 2019 1 (CU1).</span><span class="sxs-lookup"><span data-stu-id="816c1-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="816c1-137">La modification ne doit pas affecter Skype Entreprise online, car les modifications apportées aux clients sont conformes en conformité avec l’avant et l’arrière.</span><span class="sxs-lookup"><span data-stu-id="816c1-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>