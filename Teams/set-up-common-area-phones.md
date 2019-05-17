---
title: Configurer la licence de téléphone de partie commune pour Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Découvrez comment configurer des téléphones en zone commune pour les salles d’attente, les zones de réception et les salles de conférence '
ms.openlocfilehash: 66f84cb1ce768cc86a7c31a6ac345f0fcc135726
ms.sourcegitcommit: d4b007b88469a820595ecdcf2a90854ecefe2809
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2019
ms.locfileid: "34108746"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="05d77-103">Configurer la licence de téléphone de partie commune pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="05d77-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="05d77-104">Téléphones de partie commune ne prennent pas en charge de la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="05d77-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="05d77-105">Un téléphone en zone commune est généralement placé dans une zone comme une salle d’attente ou une autre zone qui est disponible à plusieurs personnes pour émettre un appel ; par exemple, une réception zone, salle d’attente ou une conférence téléphonique.</span><span class="sxs-lookup"><span data-stu-id="05d77-105">A common area phone is typically placed in an area like a lobby or another area which is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="05d77-106">Téléphones de partie commune sont configurés en tant que périphériques plutôt que des utilisateurs et peuvent vous connecter automatiquement à un réseau.</span><span class="sxs-lookup"><span data-stu-id="05d77-106">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="05d77-107">Dans les étapes suivantes, nous allons vous aider à configurer un compte de système téléphonique déployer les téléphones en zone commune pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="05d77-107">In the steps below, we’ll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="05d77-108">Pour une salle de réunion plus complète optimal, y compris les services d’audioconférence, envisager d’acquérir la licence de salle de réunion dédiée à une réunion périphérique.</span><span class="sxs-lookup"><span data-stu-id="05d77-108">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="05d77-109">Premières choses que vous devez faire est achat une licence de téléphone de zone commune (CAP) et assurez-vous que vous disposez d’un téléphone certifié.</span><span class="sxs-lookup"><span data-stu-id="05d77-109">The first things you need to do are purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="05d77-110">Pour rechercher et en savoir plus sur les téléphones certifiés, accédez aux [périphériques équipes Microsoft](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span><span class="sxs-lookup"><span data-stu-id="05d77-110">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="05d77-111">Étape 1 - Acheter les licences</span><span class="sxs-lookup"><span data-stu-id="05d77-111">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="05d77-112">Dans le centre d’administration Microsoft 365, accédez à la **facturation** > **services d’achat** , puis développez **autres plans**.</span><span class="sxs-lookup"><span data-stu-id="05d77-112">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Capture d’écran indiquant la vignette de téléphone en zone commune](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="05d77-114">Sélectionnez le **téléphone en zone commune** > **Acheter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="05d77-114">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="05d77-115">Sur la page de **validation** , cliquez sur **Acheter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="05d77-115">On the **Checkout** page click **Buy now**.</span></span>

4. <span data-ttu-id="05d77-116">**Les abonnements de module complémentaire** , puis cliquez sur pour acheter un Plan de l’appel.</span><span class="sxs-lookup"><span data-stu-id="05d77-116">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="05d77-117">Choisissez **l’intérieur de l’appel de Plan** ou **appel nationale et International planifier**.</span><span class="sxs-lookup"><span data-stu-id="05d77-117">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="05d77-118">Vous n’avez pas besoin d’une licence de Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="05d77-118">You don't need a Phone System license.</span></span> <span data-ttu-id="05d77-119">Il est inclus dans la licence Téléphone de zone commune.</span><span class="sxs-lookup"><span data-stu-id="05d77-119">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="05d77-120">Pour plus d’informations sur les licences, voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="05d77-120">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="05d77-121">Étape 2 - Créer un nouveau compte utilisateur pour le téléphone et attribuer les licences</span><span class="sxs-lookup"><span data-stu-id="05d77-121">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="05d77-122">Dans le centre d’administration Microsoft 365, accédez aux **utilisateurs** > **utilisateurs actifs** > **Ajouter un utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="05d77-122">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="05d77-123">Entrez un nom d’utilisateur comme « Main » pour le prénom et le « Réception » pour le nom du deuxième.</span><span class="sxs-lookup"><span data-stu-id="05d77-123">Enter a user name like “Main" for the first name and "Reception” for the second name.</span></span>

3. <span data-ttu-id="05d77-124">Entrez un nom d’affichage si elle n’est pas générer automatiquement comme « Réception principal. »</span><span class="sxs-lookup"><span data-stu-id="05d77-124">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="05d77-125">Entrez un nom d’utilisateur comme « MainReception » ou « Mainlobby ».</span><span class="sxs-lookup"><span data-stu-id="05d77-125">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="05d77-126">Pour les téléphones de partie commune, vous souhaitez définir un mot de passe manuellement ou ont le même mot de passe pour tous vos téléphones en zone commune.</span><span class="sxs-lookup"><span data-stu-id="05d77-126">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="05d77-127">En outre, pensez à la case à cocher **faire de cet utilisateur de modifier leur mot de passe lorsqu’ils se connectent tout d’abord** .</span><span class="sxs-lookup"><span data-stu-id="05d77-127">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="05d77-128">Attribuer des licences à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="05d77-128">Assign the licenses to the user.</span></span> <span data-ttu-id="05d77-129">Sur la même page, cliquez pour développer **Licences produit**.</span><span class="sxs-lookup"><span data-stu-id="05d77-129">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="05d77-130">Activer le téléphone en zone commune et choisissez un **Intérieur appelant planifier** ou un **national et International appelant planifier**.</span><span class="sxs-lookup"><span data-stu-id="05d77-130">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Capture d’écran montrant affectation](media/set-up-common-area-phone-image2.png)

<span data-ttu-id="05d77-132">Pour plus d’informations, voir [Ajouter un utilisateur](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="05d77-132">For more information, see [Add a user](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="05d77-133">Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="05d77-133">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="05d77-134">Utilisez le Skype entreprise centre d’administration pour affecter un numéro à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="05d77-134">Use the Skype for Business admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="05d77-135">Dans le centre d’administration Microsoft 365, sélectionnez **centre Admin** > **& équipes Skype** > **portail hérité**.</span><span class="sxs-lookup"><span data-stu-id="05d77-135">In the Microsoft 365 admin center, select **Admin centers** > **Teams & Skype** > **Legacy portal**.</span></span>

2. <span data-ttu-id="05d77-136">Dans Skype entreprise centre d’administration, sélectionnez **voix** > **numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="05d77-136">In the Skype for Business admin center, select **Voice** > **Phone numbers**.</span></span>

3.  <span data-ttu-id="05d77-137">Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.</span><span class="sxs-lookup"><span data-stu-id="05d77-137">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="05d77-138">Dans la page **affecter** , dans la boîte vocale de l’utilisateur, tapez le nom de l’utilisateur qui utilisera le téléphone, puis sélectionnez l’utilisateur dans la liste déroulante **Sélectionner un utilisateur de voix** .</span><span class="sxs-lookup"><span data-stu-id="05d77-138">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="05d77-139">Pendant que vous êtes là, vous devrez ajouter une adresse d’urgence.</span><span class="sxs-lookup"><span data-stu-id="05d77-139">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="05d77-140">Choisissez **Rechercher par ville**, **recherche par description**ou **Rechercher par emplacement** dans la liste déroulante, puis entrez la ville, description ou l’emplacement dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="05d77-140">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="05d77-141">Une fois que vous recherchez, regardez sous **Sélectionnez une adresse d’urgence** à choisir celle de droite pour vous.</span><span class="sxs-lookup"><span data-stu-id="05d77-141">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="05d77-142">Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="05d77-142">Click **Save** and your user should look like this:</span></span>

   ![Capture d’écran montrant affectation](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="05d77-144">Les utilisateurs seront affichent uniquement s’ils disposent d’une licence de système téléphonique appliquée.</span><span class="sxs-lookup"><span data-stu-id="05d77-144">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="05d77-145">Si vous venez d’attribuer, il faudra parfois attendre un moment pour que l’utilisateur apparaisse dans la liste.</span><span class="sxs-lookup"><span data-stu-id="05d77-145">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="05d77-146">Pour plus d’informations, voir [mise en route des numéros de téléphone pour vos utilisateurs](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span><span class="sxs-lookup"><span data-stu-id="05d77-146">For more information, see [Getting phone numbers for your users](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="05d77-147">Vous pouvez également effectuer votre numéro de téléphone que vous avez avec un autre transporteur et « port » ou transférez vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="05d77-147">You can also take your phone number that you have with another carrier and "port" or transfer it over to Office 365.</span></span> <span data-ttu-id="05d77-148">Consultez [transfert des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="05d77-148">See [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


