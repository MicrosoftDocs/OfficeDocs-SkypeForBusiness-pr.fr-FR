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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 'Apprenez à configurer des téléphones communs pour les couloirs, les zones de réception et les salles de conférence. '
ms.openlocfilehash: f678dba02506672be7176a75a355d606927d76d6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693909"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="df45d-103">Configurer la licence de téléphone de partie commune pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df45d-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="df45d-104">Les téléphones ordinaires ne prennent pas en charge la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="df45d-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="df45d-105">En règle générale, un téléphone commun est placé dans une zone telle que la salle d’attente ou une autre zone qui est disponible pour de nombreux utilisateurs pour passer un appel ; par exemple, une zone de réception, une salle d’attente ou un téléphone de conférence.</span><span class="sxs-lookup"><span data-stu-id="df45d-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="df45d-106">Les téléphones communs sont configurés en tant que périphériques plutôt qu’en tant qu’utilisateurs et peuvent se connecter automatiquement à un réseau.</span><span class="sxs-lookup"><span data-stu-id="df45d-106">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="df45d-107">Dans la procédure ci-dessous, nous allons vous aider à configurer un compte pour le système téléphonique afin de déployer des téléphones de zone commune pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="df45d-107">In the steps below, we’ll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="df45d-108">Pour une interface de salle de réunion plus complète, y compris l’audioconférence, envisagez d’acheter une licence de salle de réunion dédiée avec un appareil de salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="df45d-108">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="df45d-109">Tout d’abord, vous devez acheter une licence de téléphone pour les zones communes et vérifier que vous disposez d’un numéro de téléphone certifié.</span><span class="sxs-lookup"><span data-stu-id="df45d-109">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="df45d-110">Pour en savoir plus sur les téléphones certifiés, accédez à la zone [appareils Microsoft teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span><span class="sxs-lookup"><span data-stu-id="df45d-110">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="df45d-111">Étape 1 - Acheter les licences</span><span class="sxs-lookup"><span data-stu-id="df45d-111">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="df45d-112">Dans le centre d’administration Microsoft 365, accédez à**services d’achat** de **facturation** > , puis développez **autres plans**.</span><span class="sxs-lookup"><span data-stu-id="df45d-112">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Capture d’écran montrant la vignette téléphonique de zone commune](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="df45d-114">Sélectionnez l' > **option d’achat**de votre **téléphone courante**.</span><span class="sxs-lookup"><span data-stu-id="df45d-114">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="df45d-115">Dans la page validation, cliquez sur **acheter maintenant**.</span><span class="sxs-lookup"><span data-stu-id="df45d-115">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="df45d-116">Développez **abonnements de modules complémentaires** , puis cliquez sur pour acheter un plan d’appels.</span><span class="sxs-lookup"><span data-stu-id="df45d-116">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="df45d-117">Choisissez le forfait d' **appels nationaux** ou les offres d' **appels nationaux et internationaux**.</span><span class="sxs-lookup"><span data-stu-id="df45d-117">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="df45d-118">Vous n’avez pas besoin d’une licence de Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="df45d-118">You don't need a Phone System license.</span></span> <span data-ttu-id="df45d-119">Il est inclus dans la licence Téléphone de zone commune.</span><span class="sxs-lookup"><span data-stu-id="df45d-119">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="df45d-120">Pour plus d’informations sur les licences, voir [licences de complément Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="df45d-120">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="df45d-121">La licence de téléphone commune prend en charge les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="df45d-121">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="df45d-122">Téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="df45d-122">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="df45d-123">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="df45d-123">Skype for Business</span></span> |   <span data-ttu-id="df45d-124">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="df45d-124">&#x2714;</span></span> |
|<span data-ttu-id="df45d-125">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df45d-125">Microsoft Teams</span></span> |   <span data-ttu-id="df45d-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="df45d-126">&#x2714;</span></span> |
|<span data-ttu-id="df45d-127">Systèmes téléphoniques</span><span class="sxs-lookup"><span data-stu-id="df45d-127">Phone Systems</span></span> |    <span data-ttu-id="df45d-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="df45d-128">&#x2714;</span></span> |
|<span data-ttu-id="df45d-129">Audioconférence,</span><span class="sxs-lookup"><span data-stu-id="df45d-129">Audio Conferencing</span></span> |       <span data-ttu-id="df45d-130">&#x2718; &sup1 ;</span><span class="sxs-lookup"><span data-stu-id="df45d-130">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="df45d-131">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="df45d-131">Microsoft Intune</span></span> |        <span data-ttu-id="df45d-132">&#x2718; &sup2 ;</span><span class="sxs-lookup"><span data-stu-id="df45d-132">&#x2718; &sup2;</span></span> |
|<span data-ttu-id="df45d-133">Disponibilité dans le monde entier</span><span class="sxs-lookup"><span data-stu-id="df45d-133">Worldwide Availability</span></span> |    <span data-ttu-id="df45d-134">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="df45d-134">&#x2714;</span></span> |
|<span data-ttu-id="df45d-135">Disponibilité du canal</span><span class="sxs-lookup"><span data-stu-id="df45d-135">Channel Availability</span></span> |    <span data-ttu-id="df45d-136">AE, EAS, CSP, GCC, EES, Web direct</span><span class="sxs-lookup"><span data-stu-id="df45d-136">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="df45d-137">&sup1 ; Les téléphones ordinaires peuvent participer à des conférences audio par le biais d’un numéro de connexion fourni par l’organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="df45d-137">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="df45d-138">&sup2 ; Non disponible dans les nuages souverains</span><span class="sxs-lookup"><span data-stu-id="df45d-138">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="df45d-139">Étape 2 - Créer un nouveau compte utilisateur pour le téléphone et attribuer les licences</span><span class="sxs-lookup"><span data-stu-id="df45d-139">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="df45d-140">Dans le centre d’administration 365 de Microsoft, accédez à **utilisateurs** > **actifs utilisateurs** > **Ajouter un utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="df45d-140">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="df45d-141">Entrez un nom d’utilisateur tel que « main » pour le prénom et « réception » pour le second nom.</span><span class="sxs-lookup"><span data-stu-id="df45d-141">Enter a user name like “Main" for the first name and "Reception” for the second name.</span></span>

3. <span data-ttu-id="df45d-142">Entrez un nom d’affichage s’il n’en génère pas une de la façon suivante : « réception principale ».</span><span class="sxs-lookup"><span data-stu-id="df45d-142">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="df45d-143">Entrez un nom d’utilisateur (par exemple, « MainReception » ou « Mainlobby »).</span><span class="sxs-lookup"><span data-stu-id="df45d-143">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="df45d-144">Pour les téléphones portables courants, il est possible que vous deviez définir un mot de passe manuellement ou utiliser le même mot de passe pour tous les téléphones de votre zone commune.</span><span class="sxs-lookup"><span data-stu-id="df45d-144">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="df45d-145">Par ailleurs, vous pouvez penser à décocher la case **faire en sorte que l’utilisateur modifie son mot de passe lors de la première connexion** .</span><span class="sxs-lookup"><span data-stu-id="df45d-145">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="df45d-146">Attribuez les licences à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="df45d-146">Assign the licenses to the user.</span></span> <span data-ttu-id="df45d-147">Sur la même page, cliquez pour développer **Licences produit**.</span><span class="sxs-lookup"><span data-stu-id="df45d-147">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="df45d-148">Activez le téléphone courant et sélectionnez un **plan d’appels nationaux** ou un plan d' **appels nationaux et internationaux**.</span><span class="sxs-lookup"><span data-stu-id="df45d-148">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Capture d’écran montrant une attribution de licence](media/set-up-common-area-phone-image2.png)

<span data-ttu-id="df45d-150">Pour plus d’informations, reportez-vous à [Ajouter un utilisateur](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="df45d-150">For more information, see [Add a user](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="df45d-151">Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="df45d-151">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="df45d-152">Utilisez le centre d’administration teams pour attribuer un numéro à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="df45d-152">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="df45d-153">Dans le centre d’administration Teams, sélectionnez**numéros de téléphone** **vocaux** > .</span><span class="sxs-lookup"><span data-stu-id="df45d-153">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.  <span data-ttu-id="df45d-154">Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.</span><span class="sxs-lookup"><span data-stu-id="df45d-154">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="df45d-155">Dans la page **assigner** , dans la zone utilisateur vocal, tapez le nom de l’utilisateur qui utilisera le téléphone, puis sélectionnez l’utilisateur dans la liste déroulante **Sélectionner un utilisateur vocal** .</span><span class="sxs-lookup"><span data-stu-id="df45d-155">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="df45d-156">Ensuite, vous devez ajouter une adresse de secours.</span><span class="sxs-lookup"><span data-stu-id="df45d-156">Next, you need to add an emergency address.</span></span> <span data-ttu-id="df45d-157">Sélectionnez **Rechercher par ville**, **Rechercher par Description**ou **Rechercher par emplacement** dans la liste déroulante, puis entrez la ville, la description ou l’emplacement dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="df45d-157">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="df45d-158">Lorsque vous effectuez une recherche, recherchez sous **Sélectionner une adresse de secours** pour choisir celle qui vous convient.</span><span class="sxs-lookup"><span data-stu-id="df45d-158">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="df45d-159">Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="df45d-159">Click **Save** and your user should look like this:</span></span>

   ![Capture d’écran montrant une attribution de licence](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="df45d-161">Les utilisateurs ne s’afficheront que s’ils disposent d’une licence de système téléphonique appliquée.</span><span class="sxs-lookup"><span data-stu-id="df45d-161">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="df45d-162">Si vous venez d’attribuer, il faudra parfois attendre un moment pour que l’utilisateur apparaisse dans la liste.</span><span class="sxs-lookup"><span data-stu-id="df45d-162">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="df45d-163">Pour plus d’informations, reportez-vous à [la rubrique réception des numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="df45d-163">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="df45d-164">Vous pouvez également utiliser votre numéro de téléphone avec un autre opérateur et le transférer vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="df45d-164">You can also take your phone number that you have with another carrier and "port" or transfer it over to Office 365.</span></span> <span data-ttu-id="df45d-165">Voir [transférer des numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="df45d-165">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


