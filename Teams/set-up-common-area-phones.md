---
title: Configurer la licence zone Téléphone commun
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
description: 'Découvrez comment configurer les téléphones communs pour les centres d’accueil, les zones de réception et les salles de conférence '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117112"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="31f85-103">Configurer la licence de téléphone de partie commune pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="31f85-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="31f85-104">Les téléphones de la zone commune ne supportent pas la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="31f85-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="31f85-105">Un téléphone commun est généralement placé dans une zone telle qu’une salle d’accueil ou une autre zone accessible à de nombreuses personnes pour appeler. par exemple, une zone de réception, une salle d’accueil ou un téléphone de conférence.</span><span class="sxs-lookup"><span data-stu-id="31f85-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="31f85-106">Les téléphones de zone commune sont inscrits avec des comptes liés à une licence zone Téléphone commun.</span><span class="sxs-lookup"><span data-stu-id="31f85-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="31f85-107">La stratégie TeamsIPPhone doit également être définie de manière appropriée pour que le téléphone offre une expérience utilisateur commune.</span><span class="sxs-lookup"><span data-stu-id="31f85-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="31f85-108">Dans les étapes ci-dessous, nous allons vous aider à configurer un compte pour les utilisateurs Système téléphonique déployer des téléphones en zone commune pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="31f85-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="31f85-109">Pour une expérience de salle de réunion plus complète, y compris les audioconférences, envisagez d’acheter la licence de salle Salle de réunion dédiée avec un appareil de salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="31f85-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="31f85-110">Tout d’abord, vous devez acheter une licence zone Téléphone (CAP) et vous assurer que vous avez un téléphone certifié.</span><span class="sxs-lookup"><span data-stu-id="31f85-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="31f85-111">Pour rechercher et en savoir plus sur les téléphones certifiés, voir [Microsoft Teams appareils certifiés.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="31f85-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="31f85-112">Étape 1 - Acheter les licences</span><span class="sxs-lookup"><span data-stu-id="31f85-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="31f85-113">Dans le centre Microsoft 365 d’administration, allez aux services **d’achat** de  >   facturation, puis développez **Autres plans.**</span><span class="sxs-lookup"><span data-stu-id="31f85-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![Capture d’écran montrant la vignette Téléphone commun](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="31f85-115">Sélectionnez **Zone commune Téléphone** acheter  >  **maintenant.**</span><span class="sxs-lookup"><span data-stu-id="31f85-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="31f85-116">Dans la page De achat, cliquez sur **Acheter maintenant.**</span><span class="sxs-lookup"><span data-stu-id="31f85-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="31f85-117">Développez **les abonnements au** module extension, puis cliquez pour acheter un forfait d’appels.</span><span class="sxs-lookup"><span data-stu-id="31f85-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="31f85-118">Sélectionnez le **plan Appels nationaux ou** le plan Appels **nationaux et internationaux.**</span><span class="sxs-lookup"><span data-stu-id="31f85-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="31f85-119">Si vous utilisez un Téléphone Microsoft routage direct du système, vous n’avez pas besoin d’une licence de plan d’appels.</span><span class="sxs-lookup"><span data-stu-id="31f85-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="31f85-120">Vous n’avez pas besoin d’ajouter Système téléphonique licence.</span><span class="sxs-lookup"><span data-stu-id="31f85-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="31f85-121">Il est inclus dans la licence Téléphone de zone commune.</span><span class="sxs-lookup"><span data-stu-id="31f85-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="31f85-122">Pour plus d’informations sur les licences, voir [Microsoft Teams licences de module complémentaire.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="31f85-122">For more information on licenses, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="31f85-123">La licence Zone Téléphone prend en charge :</span><span class="sxs-lookup"><span data-stu-id="31f85-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="31f85-124">Téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="31f85-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="31f85-125">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="31f85-125">Skype for Business</span></span> |   <span data-ttu-id="31f85-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="31f85-126">&#x2714;</span></span> |
|<span data-ttu-id="31f85-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="31f85-127">Microsoft Teams</span></span> |   <span data-ttu-id="31f85-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="31f85-128">&#x2714;</span></span> |
|<span data-ttu-id="31f85-129">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="31f85-129">Phone System</span></span> |    <span data-ttu-id="31f85-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="31f85-130">&#x2714;</span></span> |
|<span data-ttu-id="31f85-131">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="31f85-131">Audio Conferencing</span></span> |       <span data-ttu-id="31f85-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="31f85-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="31f85-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="31f85-133">Microsoft Intune</span></span> |    <span data-ttu-id="31f85-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="31f85-134">&#x2718;</span></span> |
|<span data-ttu-id="31f85-135">Disponibilité mondiale</span><span class="sxs-lookup"><span data-stu-id="31f85-135">Worldwide Availability</span></span> |       <span data-ttu-id="31f85-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="31f85-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="31f85-137">Disponibilité des canaux</span><span class="sxs-lookup"><span data-stu-id="31f85-137">Channel Availability</span></span> |    <span data-ttu-id="31f85-138">EA, EAS, CSP, Cloud de la communauté du secteur public, EES, Web Direct</span><span class="sxs-lookup"><span data-stu-id="31f85-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="31f85-139">&sup1; Les téléphones de la zone commune peuvent participer à des audioconférences via un numéro d’accès fourni par l’organisateur de la réunion</span><span class="sxs-lookup"><span data-stu-id="31f85-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="31f85-140">&sup2; Non disponible dans des nuages souverains</span><span class="sxs-lookup"><span data-stu-id="31f85-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="31f85-141">Étape 2 - Créer un nouveau compte utilisateur pour le téléphone et attribuer les licences</span><span class="sxs-lookup"><span data-stu-id="31f85-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="31f85-142">Dans le centre Microsoft 365 d’administration, allez aux **utilisateurs**  >  **actifs pour** ajouter un  >  **utilisateur.**</span><span class="sxs-lookup"><span data-stu-id="31f85-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="31f85-143">Entrez un nom d’utilisateur tel que « Principal » pour le prénom et « Réception » pour le deuxième nom.</span><span class="sxs-lookup"><span data-stu-id="31f85-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="31f85-144">Entrez un nom d’affichage s’il ne prend pas en main un nom tel que « Réception principale ».</span><span class="sxs-lookup"><span data-stu-id="31f85-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="31f85-145">Entrez un nom d’utilisateur tel que « MainReception » ou « Mainlobby ».</span><span class="sxs-lookup"><span data-stu-id="31f85-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="31f85-146">Pour les téléphones de la zone commune, vous pouvez définir un mot de passe manuellement ou avoir le même mot de passe pour tous vos téléphones communs.</span><span class="sxs-lookup"><span data-stu-id="31f85-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="31f85-147">De plus, vous pouvez être plus à même d’effacer la case à cocher Faire en sorte que l’utilisateur change de mot de passe lors de **sa** première inscription.</span><span class="sxs-lookup"><span data-stu-id="31f85-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="31f85-148">Attribuez les licences à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31f85-148">Assign the licenses to the user.</span></span> <span data-ttu-id="31f85-149">Sur la même page, cliquez pour développer **Licences produit**.</span><span class="sxs-lookup"><span data-stu-id="31f85-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="31f85-150">Vous pouvez activer la zone Téléphone et choisir un **plan** d’appels nationaux ou un **plan d’appels nationaux et internationaux.**</span><span class="sxs-lookup"><span data-stu-id="31f85-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![Capture d’écran montrant l’attribution de licences](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="31f85-152">Si vous utilisez un Téléphone Microsoft routage direct du système, vous n’avez pas besoin d’affecter une licence de plan d’appels.</span><span class="sxs-lookup"><span data-stu-id="31f85-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="31f85-153">Pour plus d’informations, voir [Attribuer des licences aux utilisateurs.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="31f85-153">For more information, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="31f85-154">Étape 3 - Attribuer un numéro de téléphone au compte utilisateur du téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="31f85-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="31f85-155">Utilisez le Teams centre d’administration pour attribuer un numéro à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31f85-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="31f85-156">Dans le Teams d’administration, sélectionnez **Numéros**  >  **Téléphone voix.**</span><span class="sxs-lookup"><span data-stu-id="31f85-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="31f85-157">Sélectionnez un numéro dans la liste des numéros de téléphone et cliquez sur **Attribuer**.</span><span class="sxs-lookup"><span data-stu-id="31f85-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="31f85-158">Dans la **page** Affecter, dans la zone Utilisateur vocal, tapez le nom de l’utilisateur qui utilisera le téléphone, puis sélectionnez-le dans la liste de sélection d’un utilisateur vocal. </span><span class="sxs-lookup"><span data-stu-id="31f85-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="31f85-159">Vous devez ensuite ajouter une adresse de secours.</span><span class="sxs-lookup"><span data-stu-id="31f85-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="31f85-160">Sélectionnez Rechercher **par** ville,  Rechercher par **description** ou Rechercher par emplacement à partir de la liste drop-down, puis entrez la ville, la description ou le lieu dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="31f85-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="31f85-161">Une fois que vous avez recherché, regardez sous **Sélectionner l’adresse de** secours pour choisir celle qui vous est la plus proche.</span><span class="sxs-lookup"><span data-stu-id="31f85-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="31f85-162">Cliquez sur **Enregistrer** et votre utilisateur devrait ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="31f85-162">Click **Save** and your user should look like this:</span></span>

   ![Capture d’écran montrant l’attribution de licences](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="31f85-164">Les utilisateurs ne s’afficheront que s’ils ont Système téléphonique licence utilisateur.</span><span class="sxs-lookup"><span data-stu-id="31f85-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="31f85-165">Si vous venez d’attribuer, il faudra parfois attendre un moment pour que l’utilisateur apparaisse dans la liste.</span><span class="sxs-lookup"><span data-stu-id="31f85-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="31f85-166">Pour plus d’informations, voir [Obtention de numéros de téléphone pour vos utilisateurs.](getting-phone-numbers-for-your-users.md)</span><span class="sxs-lookup"><span data-stu-id="31f85-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="31f85-167">Vous pouvez également transférer votre numéro de téléphone avec un autre opérateur vers un autre opérateur ou le transférer vers un Microsoft 365 ou un Office 365.</span><span class="sxs-lookup"><span data-stu-id="31f85-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="31f85-168">Voir [Transférer des numéros de téléphone vers Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="31f85-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>