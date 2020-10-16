---
title: Configuration de la licence de téléphone commune
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Apprenez à configurer des téléphones communs pour les couloirs, les zones de réception et les salles de conférence. '
ms.openlocfilehash: f940ea7c14ad55c8cd3842e9830eb82da0d8867f
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476709"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="13c1d-103">Configurer la licence de téléphone de partie commune pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13c1d-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="13c1d-104">Les téléphones ordinaires ne prennent pas en charge la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="13c1d-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="13c1d-105">En règle générale, un téléphone commun est placé dans une zone telle que la salle d’attente ou une autre zone qui est disponible pour de nombreux utilisateurs pour passer un appel ; par exemple, une zone de réception, une salle d’attente ou un téléphone de conférence.</span><span class="sxs-lookup"><span data-stu-id="13c1d-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="13c1d-106">Les téléphones de surface commune sont connectés avec des comptes liés à une licence de téléphone commune.</span><span class="sxs-lookup"><span data-stu-id="13c1d-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="13c1d-107">La stratégie TeamsIPPhone doit également être correctement définie pour que le téléphone dispose d’une interface utilisateur commune.</span><span class="sxs-lookup"><span data-stu-id="13c1d-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="13c1d-108">Dans la procédure ci-dessous, nous allons vous aider à configurer un compte pour le système téléphonique afin de déployer des téléphones de zone commune pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="13c1d-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="13c1d-109">Pour une interface de salle de réunion plus complète, y compris l’audioconférence, envisagez d’acheter une licence de salle de réunion dédiée avec un appareil de salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="13c1d-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="13c1d-110">Tout d’abord, vous devez acheter une licence de téléphone pour les zones communes et vérifier que vous disposez d’un numéro de téléphone certifié.</span><span class="sxs-lookup"><span data-stu-id="13c1d-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="13c1d-111">Pour en savoir plus sur les téléphones certifiés, accédez à la zone [appareils Microsoft teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span><span class="sxs-lookup"><span data-stu-id="13c1d-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="13c1d-112">Étape 1 - Acheter les licences</span><span class="sxs-lookup"><span data-stu-id="13c1d-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="13c1d-113">Dans le centre d’administration Microsoft 365, accédez **Billing**à  >  **services d’achat** de facturation, puis développez **autres plans**.</span><span class="sxs-lookup"><span data-stu-id="13c1d-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Capture d’écran montrant la vignette téléphonique de zone commune](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="13c1d-115">Sélectionnez l’option d’achat de votre **téléphone courante**  >  **Buy now**.</span><span class="sxs-lookup"><span data-stu-id="13c1d-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="13c1d-116">Dans la page validation, cliquez sur **acheter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="13c1d-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="13c1d-117">Développez **abonnements de modules complémentaires** , puis cliquez sur pour acheter un plan d’appels.</span><span class="sxs-lookup"><span data-stu-id="13c1d-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="13c1d-118">Choisissez le forfait d' **appels nationaux** ou les offres d' **appels nationaux et internationaux**.</span><span class="sxs-lookup"><span data-stu-id="13c1d-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="13c1d-119">Si vous utilisez le routage direct du système Microsoft Phone, vous n’avez pas besoin d’une licence de plan d’appel.</span><span class="sxs-lookup"><span data-stu-id="13c1d-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="13c1d-120">Vous n’avez pas besoin d’ajouter une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="13c1d-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="13c1d-121">Il est inclus dans la licence Téléphone de zone commune.</span><span class="sxs-lookup"><span data-stu-id="13c1d-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="13c1d-122">Pour plus d’informations sur les licences, voir [licences de complément Microsoft teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="13c1d-122">For more information on licenses, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="13c1d-123">La licence de téléphone commune prend en charge les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="13c1d-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="13c1d-124">Téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="13c1d-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="13c1d-125">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="13c1d-125">Skype for Business</span></span> |   <span data-ttu-id="13c1d-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="13c1d-126">&#x2714;</span></span> |
|<span data-ttu-id="13c1d-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13c1d-127">Microsoft Teams</span></span> |   <span data-ttu-id="13c1d-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="13c1d-128">&#x2714;</span></span> |
|<span data-ttu-id="13c1d-129">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="13c1d-129">Phone System</span></span> |    <span data-ttu-id="13c1d-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="13c1d-130">&#x2714;</span></span> |
|<span data-ttu-id="13c1d-131">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="13c1d-131">Audio Conferencing</span></span> |       <span data-ttu-id="13c1d-132">&#x2718; &sup1 ;</span><span class="sxs-lookup"><span data-stu-id="13c1d-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="13c1d-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="13c1d-133">Microsoft Intune</span></span> |    <span data-ttu-id="13c1d-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="13c1d-134">&#x2718;</span></span> |
|<span data-ttu-id="13c1d-135">Disponibilité dans le monde entier</span><span class="sxs-lookup"><span data-stu-id="13c1d-135">Worldwide Availability</span></span> |       <span data-ttu-id="13c1d-136">&#x2718; &sup2 ;</span><span class="sxs-lookup"><span data-stu-id="13c1d-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="13c1d-137">Disponibilité du canal</span><span class="sxs-lookup"><span data-stu-id="13c1d-137">Channel Availability</span></span> |    <span data-ttu-id="13c1d-138">AE, EAS, CSP, GCC, EES, Web direct</span><span class="sxs-lookup"><span data-stu-id="13c1d-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="13c1d-139">&sup1 ; Les téléphones ordinaires peuvent participer à des conférences audio par le biais d’un numéro de connexion fourni par l’organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="13c1d-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="13c1d-140">&sup2 ; Non disponible dans les nuages souverains</span><span class="sxs-lookup"><span data-stu-id="13c1d-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="13c1d-141">Étape 2 - Créer un nouveau compte utilisateur pour le téléphone et attribuer les licences</span><span class="sxs-lookup"><span data-stu-id="13c1d-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="13c1d-142">Dans le centre d’administration 365 de Microsoft, accédez à **utilisateurs**  >  **actifs utilisateurs**  >  **Ajouter un utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="13c1d-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="13c1d-143">Entrez un nom d’utilisateur tel que « main » pour le prénom et « réception » pour le second nom.</span><span class="sxs-lookup"><span data-stu-id="13c1d-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="13c1d-144">Entrez un nom d’affichage s’il n’en génère pas une de la façon suivante : « réception principale ».</span><span class="sxs-lookup"><span data-stu-id="13c1d-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="13c1d-145">Entrez un nom d’utilisateur (par exemple, « MainReception » ou « Mainlobby »).</span><span class="sxs-lookup"><span data-stu-id="13c1d-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="13c1d-146">Pour les téléphones portables courants, il est possible que vous deviez définir un mot de passe manuellement ou utiliser le même mot de passe pour tous les téléphones de votre zone commune.</span><span class="sxs-lookup"><span data-stu-id="13c1d-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="13c1d-147">Par ailleurs, vous pouvez penser à décocher la case **faire en sorte que l’utilisateur modifie son mot de passe lors de la première connexion** .</span><span class="sxs-lookup"><span data-stu-id="13c1d-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="13c1d-148">Attribuez les licences à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="13c1d-148">Assign the licenses to the user.</span></span> <span data-ttu-id="13c1d-149">Sur la même page, cliquez pour développer **Licences produit**.</span><span class="sxs-lookup"><span data-stu-id="13c1d-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="13c1d-150">Activez le téléphone courant et sélectionnez un **plan d’appels nationaux** ou un plan d' **appels nationaux et internationaux**.</span><span class="sxs-lookup"><span data-stu-id="13c1d-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Capture d’écran montrant une attribution de licence](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="13c1d-152">Si vous utilisez le routage direct du système Microsoft Phone, il est inutile d’affecter une licence de plan d’appel.</span><span class="sxs-lookup"><span data-stu-id="13c1d-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="13c1d-153">Pour plus d’informations, voir [attribuer des licences à des utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="13c1d-153">For more information, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="13c1d-154">Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="13c1d-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="13c1d-155">Utilisez le centre d’administration teams pour attribuer un numéro à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="13c1d-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="13c1d-156">Dans le centre d’administration teams **Voice**, sélectionnez  >  **numéros de téléphone**vocaux.</span><span class="sxs-lookup"><span data-stu-id="13c1d-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="13c1d-157">Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.</span><span class="sxs-lookup"><span data-stu-id="13c1d-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="13c1d-158">Dans la page **assigner** , dans la zone utilisateur vocal, tapez le nom de l’utilisateur qui utilisera le téléphone, puis sélectionnez l’utilisateur dans la liste déroulante **Sélectionner un utilisateur vocal** .</span><span class="sxs-lookup"><span data-stu-id="13c1d-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="13c1d-159">Ensuite, vous devez ajouter une adresse de secours.</span><span class="sxs-lookup"><span data-stu-id="13c1d-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="13c1d-160">Sélectionnez **Rechercher par ville**, **Rechercher par Description**ou **Rechercher par emplacement** dans la liste déroulante, puis entrez la ville, la description ou l’emplacement dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="13c1d-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="13c1d-161">Lorsque vous effectuez une recherche, recherchez sous **Sélectionner une adresse de secours** pour choisir celle qui vous convient.</span><span class="sxs-lookup"><span data-stu-id="13c1d-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="13c1d-162">Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="13c1d-162">Click **Save** and your user should look like this:</span></span>

   ![Capture d’écran montrant une attribution de licence](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="13c1d-164">Les utilisateurs ne s’afficheront que s’ils disposent d’une licence de système téléphonique appliquée.</span><span class="sxs-lookup"><span data-stu-id="13c1d-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="13c1d-165">Si vous venez d’attribuer, il faudra parfois attendre un moment pour que l’utilisateur apparaisse dans la liste.</span><span class="sxs-lookup"><span data-stu-id="13c1d-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="13c1d-166">Pour plus d’informations, reportez-vous à [la rubrique réception des numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="13c1d-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="13c1d-167">Vous pouvez également utiliser votre numéro de téléphone avec un autre opérateur et « port », ou le transférer sur Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="13c1d-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="13c1d-168">Voir [transférer des numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="13c1d-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
