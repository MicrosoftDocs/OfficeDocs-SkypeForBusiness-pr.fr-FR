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
ms.openlocfilehash: 89cb3764e30fa0bf4fcfa9d6a18d29ca69786cef
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910036"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a><span data-ttu-id="948ca-103">Étape 2 : configurer les numéros de téléphone d’entreprise</span><span class="sxs-lookup"><span data-stu-id="948ca-103">Step 2: Set up Business Voice phone numbers</span></span>

<span data-ttu-id="948ca-104">Avant de pouvoir configurer des utilisateurs ou des attendants automatiques dans votre organisation, vous devez obtenir des numéros de téléphone pour eux.</span><span class="sxs-lookup"><span data-stu-id="948ca-104">Before you can set up users or auto attendants in your organization, you need to get phone numbers for them.</span></span> <span data-ttu-id="948ca-105">Il existe plusieurs types de numéros de téléphone. Toutefois, voici les deux types de numéros que vous devez ajouter à cette étape :</span><span class="sxs-lookup"><span data-stu-id="948ca-105">There are several different types of phone numbers, however the following are the two types of numbers that you need to add in this step:</span></span>

- <span data-ttu-id="948ca-106">**Numéros de service** Ces numéros sont utilisés pour le support automatique, l’audioconférence et les files d’attente.</span><span class="sxs-lookup"><span data-stu-id="948ca-106">**Service numbers** These numbers are used for auto attendants, audio conferencing, and call queues.</span></span> <span data-ttu-id="948ca-107">Ils peuvent être des numéros gratuits ou gratuits et peuvent gérer de grandes quantités d’appels en même temps.</span><span class="sxs-lookup"><span data-stu-id="948ca-107">They can be toll or toll-free numbers and can handle large amounts of calls at the same time.</span></span> <span data-ttu-id="948ca-108">Le numéro de téléphone de votre entreprise doit être un numéro de service, car il sera affecté à un agent automatique dans une étape ultérieure.</span><span class="sxs-lookup"><span data-stu-id="948ca-108">Your company phone number needs to be a service number because it'll be assigned to an auto attendant in a later step.</span></span>
- <span data-ttu-id="948ca-109">**Numéros d’abonné** Ces numéros sont utilisés pour les utilisateurs réguliers afin qu’ils peuvent effectuer et recevoir des appels téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="948ca-109">**Subscriber numbers** These numbers are used for regular users so they can make and receive phone calls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="948ca-110">Même si vous voulez utiliser vos numéros de téléphone existants, vous devez créer et attribuer des numéros de téléphone temporaires à la ligne de téléphone principale de votre entreprise et à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="948ca-110">Even if you want to use your existing phone numbers, you need to create and assign temporary phone numbers to your company's main phone line and your users.</span></span> <span data-ttu-id="948ca-111">Vous pourrez remplacer ces numéros temporaires par vos numéros de téléphone existants dans une étape ultérieure.</span><span class="sxs-lookup"><span data-stu-id="948ca-111">You'll be able to replace these temporary numbers with your existing phone numbers in a later step.</span></span>

> [!NOTE]
> <span data-ttu-id="948ca-112">Plusieurs heures peuvent être avant que vos nouveaux numéros de téléphone deviennent disponibles dans Teams.</span><span class="sxs-lookup"><span data-stu-id="948ca-112">It may take several hours for your new phone numbers to become available in Teams.</span></span>

<span data-ttu-id="948ca-113">La vidéo suivante vous montre comment effectuer ces étapes dans le Centre d’administration Teams’administration.</span><span class="sxs-lookup"><span data-stu-id="948ca-113">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWENzQ]

## <a name="set-up-a-service-number"></a><span data-ttu-id="948ca-114">Configurer un numéro de service</span><span class="sxs-lookup"><span data-stu-id="948ca-114">Set up a service number</span></span>

<span data-ttu-id="948ca-115">Le numéro de service que vous définissez maintenant sera utilisé dans une étape ultérieure pour le numéro de téléphone principal de votre société.</span><span class="sxs-lookup"><span data-stu-id="948ca-115">The service number you set up now will be used in a later step for your company's main phone number.</span></span>

1. <span data-ttu-id="948ca-116">Ouvrez le Microsoft Teams d’administration et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="948ca-116">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="948ca-117">Dans le groupe de navigation de gauche, cliquez <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">   >  **sur Numéros Téléphone**</a>la voix, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="948ca-117">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="948ca-118">Entrez un nom pour la commande et ajoutez une description.</span><span class="sxs-lookup"><span data-stu-id="948ca-118">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="948ca-119">Dans la page Emplacement et quantité, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="948ca-119">On the Location and quantity page, do the following:</span></span>
    1. <span data-ttu-id="948ca-120">Sous **Pays ou région,** sélectionnez un pays ou une région.</span><span class="sxs-lookup"><span data-stu-id="948ca-120">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="948ca-121">Sous **Type de nombre,** sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="948ca-121">Under **Number type**, select one of the following options:</span></span>

        - <span data-ttu-id="948ca-122">**Service de service automatique (numéro de frais)** Numéro de téléphone normal, non gratuit.</span><span class="sxs-lookup"><span data-stu-id="948ca-122">**Auto attendant (Toll)** Regular, non-toll-free, phone number.</span></span> <span data-ttu-id="948ca-123">Les frais de distance longue sont facturés à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="948ca-123">Long distance fees are charged to the caller.</span></span>
        - <span data-ttu-id="948ca-124">**Service de service automatique (gratuit)** Numéro de téléphone gratuit (États-Unis et Canada) ou téléphone gratuit (Royaume-Uni).</span><span class="sxs-lookup"><span data-stu-id="948ca-124">**Auto attendant (Toll Free)** Toll-free (US and Canada) or freephone (UK) phone number.</span></span> <span data-ttu-id="948ca-125">Les frais d’longue distance sont facturés à votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="948ca-125">Long distances fees are charged to your company.</span></span> <span data-ttu-id="948ca-126">Pour pouvoir sélectionner cette option, vous devez acheter des crédits de communication.</span><span class="sxs-lookup"><span data-stu-id="948ca-126">Before you can select this option, you need to purchase Communication Credits.</span></span> <span data-ttu-id="948ca-127">Pour plus d’informations, [voir Que dois-je](what-to-buy.md)acheter pour utiliser Microsoft 365 Business Voice ?</span><span class="sxs-lookup"><span data-stu-id="948ca-127">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>

    3. <span data-ttu-id="948ca-128">Sous **Quantité,** sélectionnez **1.**</span><span class="sxs-lookup"><span data-stu-id="948ca-128">Under **Quantity**, select **1**.</span></span>
        > [!NOTE]
        > <span data-ttu-id="948ca-129">Si vous recevez un message vous **n’avez** pas assez de licences pour demander davantage de licences de ce type, assurez-vous que vous avez acheté des licences Business Voice.</span><span class="sxs-lookup"><span data-stu-id="948ca-129">If you get the message **You don't have enough licenses to request more numbers of this type**, make sure you've purchased Business Voice licenses.</span></span> <span data-ttu-id="948ca-130">Pour plus d’informations, [voir Que dois-je](what-to-buy.md)acheter pour utiliser Microsoft 365 Business Voice ?</span><span class="sxs-lookup"><span data-stu-id="948ca-130">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
    4. <span data-ttu-id="948ca-131">Choisissez Emplacement **ou** **Code** de la zone, selon que vous souhaitez rechercher des numéros de téléphone en utilisant la ville d’un lieu ou si vous souhaitez rechercher des numéros dans un code de zone spécifique.</span><span class="sxs-lookup"><span data-stu-id="948ca-131">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="948ca-132">Si vous sélectionnez **Emplacement**:</span><span class="sxs-lookup"><span data-stu-id="948ca-132">If you select **Location**:</span></span>

        1. <span data-ttu-id="948ca-133">Tapez la ville dans laquelle se [](set-up-emergency-locations.md) trouve votre adresse de secours à l’étape Configurer les emplacements d’urgence, ou si vous avez besoin de créer un nouvel emplacement pour un autre bureau ou un bureau à domicile, cliquez sur Ajouter un **emplacement.**</span><span class="sxs-lookup"><span data-stu-id="948ca-133">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="948ca-134">Sous **Code de la** zone, sélectionnez un code de zone, puis **sélectionnez Suivant** pour réserver votre numéro.</span><span class="sxs-lookup"><span data-stu-id="948ca-134">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="948ca-135">Si vous sélectionnez **l’code de** zone, tapez l’code de la zone dans le cas d’une recherche, puis sélectionnez **Suivant** pour réserver votre numéro.</span><span class="sxs-lookup"><span data-stu-id="948ca-135">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>

5. <span data-ttu-id="948ca-136">Sélectionnez le nombre de votre choix.</span><span class="sxs-lookup"><span data-stu-id="948ca-136">Select the number you want.</span></span> <span data-ttu-id="948ca-137">Vous avez 10 minutes pour sélectionner votre numéro de téléphone et y placer votre commande.</span><span class="sxs-lookup"><span data-stu-id="948ca-137">You have 10 minutes to select your phone number and place your order.</span></span> <span data-ttu-id="948ca-138">Si cela prend plus de 10 minutes, le numéro de téléphone est renvoyé vers le pool de numéros.</span><span class="sxs-lookup"><span data-stu-id="948ca-138">If you take more than 10 minutes, the phone number will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="948ca-139">Lorsque vous êtes prêt à passer votre commande, **cliquez** sur Passer commande, puis **terminez**</span><span class="sxs-lookup"><span data-stu-id="948ca-139">When you're ready to place your order, click **Place order**, and then **Finish**</span></span>

## <a name="set-up-phone-numbers-for-your-users"></a><span data-ttu-id="948ca-140">Configurer des numéros de téléphone pour vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="948ca-140">Set up phone numbers for your users</span></span>

1. <span data-ttu-id="948ca-141">Ouvrez le Microsoft Teams d’administration et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="948ca-141">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="948ca-142">Dans le groupe de navigation de gauche, cliquez <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">   >  **sur Numéros Téléphone**</a>la voix, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="948ca-142">In the left navigation, go to <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Voice** > **Phone numbers**</a>, and then click **Add**.</span></span>
3. <span data-ttu-id="948ca-143">Entrez un nom pour la commande et ajoutez une description.</span><span class="sxs-lookup"><span data-stu-id="948ca-143">Enter a name for the order and add a description.</span></span>
4. <span data-ttu-id="948ca-144">Dans la page Emplacement et quantité, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="948ca-144">On the Location and quantity page, do the following:</span></span>

    1. <span data-ttu-id="948ca-145">Sous **Pays ou région,** sélectionnez un pays ou une région.</span><span class="sxs-lookup"><span data-stu-id="948ca-145">Under **Country or region**, select a country or region.</span></span>
    2. <span data-ttu-id="948ca-146">Sous **Type de numéro,** **sélectionnez Utilisateur (abonné).**</span><span class="sxs-lookup"><span data-stu-id="948ca-146">Under **Number type**, select **User (subscriber)**.</span></span>
    3. <span data-ttu-id="948ca-147">Sous **Quantité,** entrez le nombre de nombres que vous souhaitez pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="948ca-147">Under **Quantity**, enter the number of numbers that you want for your organization.</span></span>
    4. <span data-ttu-id="948ca-148">Choisissez Emplacement **ou** **Code** de la zone, selon que vous souhaitez rechercher des numéros de téléphone en utilisant la ville d’un lieu ou si vous souhaitez rechercher des numéros dans un code de zone spécifique.</span><span class="sxs-lookup"><span data-stu-id="948ca-148">Choose either **Location** or **Area code**, depending on whether you want to search for phone numbers using a location's city, or if you want to search for numbers in a specific area code.</span></span>
    5. <span data-ttu-id="948ca-149">Si vous sélectionnez **Emplacement**:</span><span class="sxs-lookup"><span data-stu-id="948ca-149">If you select **Location**:</span></span>

        1. <span data-ttu-id="948ca-150">Tapez la ville dans laquelle se [](set-up-emergency-locations.md) trouve votre adresse de secours à l’étape Configurer les emplacements d’urgence, ou si vous avez besoin de créer un nouvel emplacement pour un autre bureau ou un bureau à domicile, cliquez sur Ajouter un **emplacement.**</span><span class="sxs-lookup"><span data-stu-id="948ca-150">Type the city in which your emergency address is located in the [Set up emergency locations](set-up-emergency-locations.md) step, or if you need to create a new location for another office or a home office, click **Add a location**.</span></span>
        2. <span data-ttu-id="948ca-151">Sous **Code de la** zone, sélectionnez un code de zone, puis **sélectionnez Suivant** pour réserver votre numéro.</span><span class="sxs-lookup"><span data-stu-id="948ca-151">Under **Area code**, select an area code, and then select **Next** to reserve your number.</span></span>

    6. <span data-ttu-id="948ca-152">Si vous sélectionnez **l’code de** zone, tapez l’code de la zone dans le cas d’une recherche, puis sélectionnez **Suivant** pour réserver votre numéro.</span><span class="sxs-lookup"><span data-stu-id="948ca-152">If you select **Area code**, type the area code you want to search, and then select **Next** to reserve your number.</span></span>
5. <span data-ttu-id="948ca-153">Sélectionnez les nombres de votre choix.</span><span class="sxs-lookup"><span data-stu-id="948ca-153">Select the numbers you want.</span></span> <span data-ttu-id="948ca-154">Vous avez 10 minutes pour sélectionner vos numéros de téléphone et placer votre commande.</span><span class="sxs-lookup"><span data-stu-id="948ca-154">You have 10 minutes to select your phone numbers and place your order.</span></span> <span data-ttu-id="948ca-155">Si cela prend plus de 10 minutes, les numéros de téléphone sont renvoyés dans la réserve de numéros.</span><span class="sxs-lookup"><span data-stu-id="948ca-155">If you take more than 10 minutes, the phone numbers will be returned to the pool of numbers.</span></span>
6. <span data-ttu-id="948ca-156">Lorsque vous êtes prêt à passer votre commande, cliquez **sur** Passer commande, puis sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="948ca-156">When you're ready to place your order, click **Place order**, and then **Finish**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="948ca-157">Étape suivante : attribuer des licences à Teams utilisateurs</span><span class="sxs-lookup"><span data-stu-id="948ca-157">Next step: Assign licenses to Teams users</span></span>](set-up-licenses.md)
