---
title: Configurer les numéros Microsoft 365 Business voix
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Découvrez comment configurer des numéros Microsoft 365 Business voix pour les utilisateurs et les services de votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130053"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="feef1-103">Étape 2 : configurer les numéros de téléphone d'entreprise</span><span class="sxs-lookup"><span data-stu-id="feef1-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="feef1-104">Avant de pouvoir configurer des utilisateurs ou des attendants automatiques dans votre organisation, vous devez obtenir des numéros de téléphone pour eux.</span><span class="sxs-lookup"><span data-stu-id="feef1-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="feef1-105">Il existe plusieurs types de numéros de téléphone. Toutefois, voici les deux types de numéros que vous devez ajouter à cette étape :</span><span class="sxs-lookup"><span data-stu-id="feef1-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="feef1-106">**Numéros de service** Ces numéros sont utilisés pour le support automatique, l'audioconférence et les files d'attente.</span><span class="sxs-lookup"><span data-stu-id="feef1-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="feef1-107">Ils peuvent être des numéros gratuits ou gratuits et peuvent gérer de grandes quantités d'appels en même temps.</span><span class="sxs-lookup"><span data-stu-id="feef1-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="feef1-108">Le numéro de téléphone de votre entreprise doit être un numéro de service, car il sera affecté à un agent automatique dans une étape ultérieure.</span><span class="sxs-lookup"><span data-stu-id="feef1-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="feef1-109">**Numéros d'abonné** Ces numéros sont utilisés pour les utilisateurs réguliers afin qu'ils peuvent effectuer et recevoir des appels téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="feef1-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="feef1-110">Même si vous voulez utiliser vos numéros de téléphone existants, vous devez créer et attribuer des numéros de téléphone temporaires à la ligne de téléphone principale de votre entreprise et à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="feef1-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="feef1-111">Vous pourrez remplacer ces numéros temporaires par vos numéros de téléphone existants dans une étape ultérieure.</span><span class="sxs-lookup"><span data-stu-id="feef1-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="feef1-112">Plusieurs heures peuvent être avant que vos nouveaux numéros de téléphone deviennent disponibles dans Teams.</span><span class="sxs-lookup"><span data-stu-id="feef1-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

## <a name="set-up-a-service-number"></a><span data-ttu-id="feef1-113">Configurer un numéro de service</span><span class="sxs-lookup"><span data-stu-id="feef1-113">Set up a service number</span></span>

<span data-ttu-id="feef1-114">Le numéro de service que vous définissez maintenant sera utilisé dans une étape ultérieure pour le numéro de téléphone principal de votre société.</span><span class="sxs-lookup"><span data-stu-id="feef1-114">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="feef1-115">Allez dans le Microsoft Teams d'administration.</span><span class="sxs-lookup"><span data-stu-id="feef1-115">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="feef1-116">Dans le groupe de navigation de gauche, cliquez  >  **sur Numéros Téléphone la** voix, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="feef1-116">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="feef1-117">Entrez un nom pour la commande et ajoutez une description.</span><span class="sxs-lookup"><span data-stu-id="feef1-117">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="feef1-118">Dans la page Emplacement et quantité, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="feef1-118">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="feef1-119">Sous **Pays ou région,** sélectionnez un pays ou une région.</span><span class="sxs-lookup"><span data-stu-id="feef1-119">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="feef1-120">Sous **Type de nombre,** sélectionnez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="feef1-120">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="feef1-121">**Service de service automatique (numéro de frais)** Numéro de téléphone normal, non gratuit.</span><span class="sxs-lookup"><span data-stu-id="feef1-121">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="feef1-122">Des frais de longue distance sont facturés à l'appelant.</span><span class="sxs-lookup"><span data-stu-id="feef1-122">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="feef1-123">**Attendant automatique (numéro gratuit)** Numéro de téléphone gratuit (États-Unis et Canada) ou téléphone gratuit (Royaume-Uni).</span><span class="sxs-lookup"><span data-stu-id="feef1-123">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="feef1-124">Les frais d'longue distance sont facturés à votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="feef1-124">Long distances fees are charged to your company.</span></span> <span data-ttu-id="feef1-125">Pour pouvoir sélectionner cette option, vous devez acheter des crédits de communication.</span><span class="sxs-lookup"><span data-stu-id="feef1-125">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="feef1-126">Pour plus d'informations, [voir Que dois-je](what-to-buy.md)acheter pour utiliser Microsoft 365 Business Voice ?</span><span class="sxs-lookup"><span data-stu-id="feef1-126">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="feef1-127">Sous **Quantité,** sélectionnez **1.**</span><span class="sxs-lookup"><span data-stu-id="feef1-127">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="feef1-128">Si vous recevez un message vous **n'avez** pas assez de licences pour demander davantage de licences de ce type, assurez-vous que vous avez acheté des licences Business Voice.</span><span class="sxs-lookup"><span data-stu-id="feef1-128">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="feef1-129">Pour plus d'informations, [voir Que dois-je](what-to-buy.md)acheter pour utiliser Microsoft 365 Business Voice ?</span><span class="sxs-lookup"><span data-stu-id="feef1-129">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="feef1-130">Sous **Emplacement,** tapez le nom de l'emplacement que vous avez créé à l'étape [Configurer les emplacements d'urgence.](set-up-emergency-locations.md)</span><span class="sxs-lookup"><span data-stu-id="feef1-130">Under **Location**, type the name of the location you created in the [Set up emergency locations](set-up-emergency-locations.md) step.</span></span>
    5. <span data-ttu-id="feef1-131">Sous **Code de la** zone, sélectionnez un code de zone, puis cliquez sur **Suivant** pour sélectionner vos numéros</span><span class="sxs-lookup"><span data-stu-id="feef1-131">Under **Area code**, select an area code, and then click **Next** to select your numbers</span></span>
5. <span data-ttu-id="feef1-132">Sélectionnez le nombre de votre choix.</span><span class="sxs-lookup"><span data-stu-id="feef1-132">Select the number you want.</span></span> <span data-ttu-id="feef1-133">Vous avez 10 minutes pour sélectionner votre numéro de téléphone et y placer votre commande.</span><span class="sxs-lookup"><span data-stu-id="feef1-133">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="feef1-134">Si cela prend plus de 10 minutes, le numéro de téléphone est renvoyé dans la réserve de numéros.</span><span class="sxs-lookup"><span data-stu-id="feef1-134">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="feef1-135">Lorsque vous êtes prêt à passer votre commande, **cliquez** sur Passer commande, puis **terminez**</span><span class="sxs-lookup"><span data-stu-id="feef1-135">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="feef1-136">Configurer des numéros de téléphone pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="feef1-136">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="feef1-137">Allez dans le Microsoft Teams d'administration.</span><span class="sxs-lookup"><span data-stu-id="feef1-137">Go to the Microsoft Teams Admin Center.</span></span>
2. <span data-ttu-id="feef1-138">Dans le groupe de navigation de gauche, cliquez  >  **sur Numéros Téléphone la** voix, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="feef1-138">In the left navigation, go to **Voice** > **Phone numbers**, and then click **Add**.</span></span>
3. <span data-ttu-id="feef1-139">Entrez un nom pour la commande et ajoutez une description.</span><span class="sxs-lookup"><span data-stu-id="feef1-139">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="feef1-140">Dans la page Emplacement et quantité, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="feef1-140">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="feef1-141">Sous **Pays ou région,** sélectionnez un pays ou une région.</span><span class="sxs-lookup"><span data-stu-id="feef1-141">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="feef1-142">Sous **Type de numéro,** **sélectionnez Utilisateur (abonné).**</span><span class="sxs-lookup"><span data-stu-id="feef1-142">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="feef1-143">Sous **Quantité,** entrez le nombre de nombres que vous souhaitez pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="feef1-143">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="feef1-144">Sous **Emplacement,** sélectionnez un emplacement.</span><span class="sxs-lookup"><span data-stu-id="feef1-144">Under **Location**, select a location.</span></span> <span data-ttu-id="feef1-145">Vous pouvez sélectionner l'emplacement d'urgence que vous avez ajouté à l'étape Configurer les emplacements d'urgence ou, si vous avez besoin de créer un emplacement pour un autre bureau ou un bureau à domicile, cliquer sur Ajouter un **emplacement.** [](set-up-emergency-locations.md)</span><span class="sxs-lookup"><span data-stu-id="feef1-145">You can select either the emergency location you added in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
    5. <span data-ttu-id="feef1-146">Sous **Code de la** zone, sélectionnez un code de zone, puis cliquez sur **Suivant** pour sélectionner vos numéros.</span><span class="sxs-lookup"><span data-stu-id="feef1-146">Under **Area code**, select an area code, and then click **Next** to select your numbers.</span></span>
5. <span data-ttu-id="feef1-147">Sélectionnez les nombres de votre choix.</span><span class="sxs-lookup"><span data-stu-id="feef1-147">Select the numbers you want.</span></span> <span data-ttu-id="feef1-148">Vous avez 10 minutes pour sélectionner vos numéros de téléphone et placer votre commande.</span><span class="sxs-lookup"><span data-stu-id="feef1-148">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="feef1-149">Si cela prend plus de 10 minutes, les numéros de téléphone sont renvoyés dans la réserve de numéros.</span><span class="sxs-lookup"><span data-stu-id="feef1-149">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="feef1-150">Lorsque vous êtes prêt à passer votre commande, cliquez **sur** Passer commande, puis sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="feef1-150">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="feef1-151">Étape suivante : attribuer des licences à Teams utilisateurs</span><span class="sxs-lookup"><span data-stu-id="feef1-151">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
