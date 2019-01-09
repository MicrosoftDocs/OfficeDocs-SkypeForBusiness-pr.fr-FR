---
title: Migration des périphériques Lync salle système vers le système de salle Skype version 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Lisez cette rubrique pour savoir comment migrer des périphériques de système de salle de Lync pour utiliser le système de salle Skype v2 logiciel.
ms.openlocfilehash: b2d748a37e7e060e19d0708b6979f9254af13682
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772902"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="adc88-103">Migrer les appareils Lync salle système (KR) au système de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="adc88-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="adc88-104">Les appareils Lync salle système (KR) avec le logiciel système Version 1 (v1 SRS) Skype salle a atteint la [fin de la prise en charge sur le 9 octobre 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span><span class="sxs-lookup"><span data-stu-id="adc88-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="adc88-105">Cela signifie que logiciel v1 de systèmes de salle Skype n’est plus aura les mises à jour ou les correctifs plus.</span><span class="sxs-lookup"><span data-stu-id="adc88-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="adc88-106">Il est conseillé aux utilisateurs avec des périphériques de système de salle Lync l’utilisation du système de salle Skype v1 logiciel pour mettre à niveau leurs périphériques au système de salle Skype version 2 (v2 SRS).</span><span class="sxs-lookup"><span data-stu-id="adc88-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="adc88-107">Logiciel système Version 2 (v2 SRS) Skype salle fonctionne avec Microsoft Teams outre Skype pour les services Business Server et en ligne pour les réunions et les appeler sur tous les périphériques de SRS v2 pris en charge.</span><span class="sxs-lookup"><span data-stu-id="adc88-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="adc88-108">Votre de périphériques existant **peut** continuer à fonctionner après la fin d’un système de salle de Skype v1 prennent en charge.</span><span class="sxs-lookup"><span data-stu-id="adc88-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="adc88-109">Toutefois, si ce logiciel accède à un bogue doit Microsoft publie un correctif logiciel, il ne sera pas être pris en charge.</span><span class="sxs-lookup"><span data-stu-id="adc88-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="adc88-110">V1 SRS utilise TLS 1.0 / 1.1 qui sera déconseillé dans les futures par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="adc88-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in future.</span></span> <span data-ttu-id="adc88-111">Pour plus d’informations sur [la préparation pour TLS 1.0/1.1 désapprobation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="adc88-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="adc88-112">Skype salle système V2 consiste à ajouter la prise en charge pour TLS 1.2 et continueront de fonctionner après le 31 octobre 2018.</span><span class="sxs-lookup"><span data-stu-id="adc88-112">Skype Room System V2 is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="adc88-113">Skype pour les entreprises sur les clients de site ne désactivez pas TLS 1.0/1.1 jusqu'à ce que Skype salle système V2 annouces prise en charge pour TLS 1.2 indépendamment des instructions générales sur désapprobation TLS 1.0/1.1.</span><span class="sxs-lookup"><span data-stu-id="adc88-113">Skype for Business on premise customers should not disable TLS 1.0/1.1 until Skype Room System V2 annouces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="adc88-114">Les périphériques sont affectés ?</span><span class="sxs-lookup"><span data-stu-id="adc88-114">Which devices are affected?</span></span>
<span data-ttu-id="adc88-115">Voici la liste des périphériques qui sont affectées par cette modification :</span><span class="sxs-lookup"><span data-stu-id="adc88-115">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="adc88-116">Systèmes de salle actives</span><span class="sxs-lookup"><span data-stu-id="adc88-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="adc88-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="adc88-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="adc88-118">CX8000 de Polycom</span><span class="sxs-lookup"><span data-stu-id="adc88-118">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="adc88-119">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="adc88-119">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="adc88-120">Options de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="adc88-120">Upgrade options</span></span>
<span data-ttu-id="adc88-121">Il existe plusieurs options de mise à niveau des systèmes de salle de Lync pour la nouvelle génération de systèmes de salle Skype (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="adc88-121">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="adc88-122">Programme de reprise de matériel Crestron</span><span class="sxs-lookup"><span data-stu-id="adc88-122">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="adc88-123">Crestron fournira une mise à niveau pour le [système SR Crestron](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) ou l’équivalent pour tous les clients Non-Crestron Lync salle système.</span><span class="sxs-lookup"><span data-stu-id="adc88-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="adc88-124">Afficher les détails de ce programme [ici](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, --> [messagerie](mailto:lrsupgrade@crestron.com) prise en charge Crestron LRS.</span><span class="sxs-lookup"><span data-stu-id="adc88-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-upgrade-to-srs-v2"></a><span data-ttu-id="adc88-125">Mise à niveau Crestron RL2 SRS V2</span><span class="sxs-lookup"><span data-stu-id="adc88-125">Crestron RL2 upgrade to SRS V2</span></span>
<span data-ttu-id="adc88-126">Les clients existants Crestron RL2 (également appelé Crestron RL200) pouvant vous procurer un kit de mise à niveau pour mettre à niveau en cours RL2 à l’aide de RL3 un pour un coût minimal par périphérique.</span><span class="sxs-lookup"><span data-stu-id="adc88-126">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="adc88-127">Afficher les détails de ce programme [ici](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span><span class="sxs-lookup"><span data-stu-id="adc88-127">See details of this program [here](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span> 


### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="adc88-128">Mise à niveau des systèmes de salle Active</span><span class="sxs-lookup"><span data-stu-id="adc88-128">SMART Room Systems upgrade</span></span> 
<span data-ttu-id="adc88-129">Pour les clients KR actives, en dehors du programme de reprise Crestron matériel, Microsoft et à puce fonctionnent également à fournir une solution de mise à niveau vers le système de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="adc88-129">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="adc88-130">Cette mise à niveau sera fournie par actives Technologies Inc. Veuillez consulter plus d’informations sur cette [ici](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span><span class="sxs-lookup"><span data-stu-id="adc88-130">This upgrade will be provided by SMART Technologies Inc. Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a><span data-ttu-id="adc88-131">Comment procéder ?</span><span class="sxs-lookup"><span data-stu-id="adc88-131">What should you do?</span></span>
<span data-ttu-id="adc88-132">Nous vous recommandons de que vous envisagez de mettre à jour des périphériques Lync salle système pour systèmes de salle Skype v2 avant désapprobation TLS 1.0/1.1 à l’aide des options de mise à niveau mentionnées ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="adc88-132">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="adc88-133">En outre, vous pouvez également envisager de remplacement de périphériques existants avec de nouveaux périphériques certifiés pour SRS v2.</span><span class="sxs-lookup"><span data-stu-id="adc88-133">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="adc88-134">Pour plus d’informations, consultez [équipements de salle](https://aka.ms/roomdevices) et également jeter un œil à [v2 Skype salle requise](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="adc88-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="adc88-135">Fonctionnalité tactile et le tableau blanc n’est pas encore pris en charge dans le système de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="adc88-135">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="adc88-136">Prise en charge tactile et tableau blanc se trouve dans la file d’attente pour le système de salle Skype v2 et est ajouté dans CY2019 H1.</span><span class="sxs-lookup"><span data-stu-id="adc88-136">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>

> [!NOTE]
> <span data-ttu-id="adc88-137">Logiciel Skype salle système V2 n’autorise pas actuellement protocole TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="adc88-137">Skype Room System V2 software currently does not support TLS 1.2 protocol.</span></span> <span data-ttu-id="adc88-138">Prise en charge TLS 1.2 est en cours de traitement et sera exécuté avant désapprobation TLS 1.0/1.1.</span><span class="sxs-lookup"><span data-stu-id="adc88-138">TLS 1.2 support is being worked on and will be completed before TLS 1.0/1.1 deprecation.</span></span> <span data-ttu-id="adc88-139">Clients upgradging à SRS v2 ne s’affiche pas n’importe quel impact de désapprobation TLS 1.0/1.1 sur les appareils de salle version la plus récente de SRS v2 application en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="adc88-139">Customers upgradging to SRS v2 will not see any impact of TLS 1.0/1.1 deprecation on Room devices running latest version of SRS v2 app.</span></span> <span data-ttu-id="adc88-140">Skype pour les entreprises sur les clients de site ne désactivez pas TLS 1.0/1.1 jusqu'à ce que la prise en charge annouces Skype salle système V2 pour TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="adc88-140">Skype for Business on premise customers should not disable TLS 1.0/1.1 until Skype Room System V2 annouces support for TLS 1.2.</span></span> 
