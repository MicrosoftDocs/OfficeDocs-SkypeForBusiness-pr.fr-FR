---
title: Configurer l’audioconférence pour Microsoft teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Découvrez comment configurer des conférences rendez-vous ou audio pour les personnes de votre entreprise qui ont besoin d’utiliser un téléphone pour participer à des conférences téléphoniques. '
ms.openlocfilehash: 5bf9a4ba1928bd8532a0f97fcb899745ffb65d13
ms.sourcegitcommit: 3197f3ffca2b2315be9fd0c702ccc8c87383c893
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2019
ms.locfileid: "35062418"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="e68af-103">Configurer l’audioconférence pour Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e68af-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="e68af-104">Parfois, les membres de votre organisation doivent utiliser un téléphone pour appeler une réunion.</span><span class="sxs-lookup"><span data-stu-id="e68af-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="e68af-105">Microsoft teams inclut la fonction de conférence rendez-vous pour cette situation.</span><span class="sxs-lookup"><span data-stu-id="e68af-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="e68af-106">Les personnes peuvent appeler des réunions teams à l’aide d’un téléphone, au lieu d’utiliser l’application teams sur un appareil mobile ou un PC.</span><span class="sxs-lookup"><span data-stu-id="e68af-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="e68af-107">Il vous suffit de configurer la fonctionnalité de conférence audio pour les utilisateurs qui comptent planifier ou organiser des réunions.</span><span class="sxs-lookup"><span data-stu-id="e68af-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="e68af-108">Les participants à la réunion qui se connectent n’ont pas besoin de licence ou de configuration particulière.</span><span class="sxs-lookup"><span data-stu-id="e68af-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="e68af-109">Pour trouver les questions fréquemment posées à propos des audioconférences, consultez [Questions courantes concernant les audioconférences](audio-conferencing-common-questions.md).</span><span class="sxs-lookup"><span data-stu-id="e68af-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="e68af-110">Étape 1 : Déterminez si les audioconférence sont disponibles dans votre pays/région</span><span class="sxs-lookup"><span data-stu-id="e68af-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="e68af-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e68af-111"></span></span>

<span data-ttu-id="e68af-112">Allez à la page [Disponibilité des pays et des régions pour les audioconférences et les forfaits d’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) et sélectionnez votre pays ou région pour obtenir des informations de disponibilité sur les audioconférences, ainsi que des informations sur le système téléphonique, les forfaits d’appel, les numéros payants et gratuits et les crédits de communications.</span><span class="sxs-lookup"><span data-stu-id="e68af-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="e68af-113">Étape 2 : Obtenir et attribuer des licences</span><span class="sxs-lookup"><span data-stu-id="e68af-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="e68af-114">Pour une audioconférence, vous avez besoin d’une licence pour chaque utilisateur qui établira des réunions.</span><span class="sxs-lookup"><span data-stu-id="e68af-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="e68af-115">Pour connaître les licences que vous devez acheter pour l’audioconférence et leurs coûts, voir [licences de module complémentaire Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e68af-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="e68af-116">L’audioconférence est incluse dans les licences Office 365 entreprise E5 et en tant que composant additionnel.</span><span class="sxs-lookup"><span data-stu-id="e68af-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="e68af-117">Une fois que vous avez acheté les licences de conférence audio, vous devez les affecter aux personnes de votre organisation qui vont planifier ou animer des réunions.</span><span class="sxs-lookup"><span data-stu-id="e68af-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="e68af-118">Voir [attribuer des licences aux utilisateurs dans Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que vous avez acheté aux personnes de votre organisation qui vont planifier ou animer des réunions.</span><span class="sxs-lookup"><span data-stu-id="e68af-118">See [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="e68af-119">Nous vous recommandons également d’affecter des licences de crédits de communications (elles ne coûtent rien) aux mêmes personnes à qui vous avez attribué des licences à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="e68af-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="e68af-120">Pour savoir comment configurer les Crédits de communications, voir [Configurer les Crédits de communications pour votre entreprise](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e68af-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="e68af-121">Vous pouvez également configurer [le service de conférence](audio-conferencing-pay-per-minute.md)rendez-vous en fonction du son.</span><span class="sxs-lookup"><span data-stu-id="e68af-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="e68af-122">Étape 3 : Obtenir les numéros de service pour vos ponts de conférence</span><span class="sxs-lookup"><span data-stu-id="e68af-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="e68af-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e68af-123"></span></span>

<span data-ttu-id="e68af-124">Pour les audioconférences, vous ne pouvez pas utiliser les numéros de téléphone pour les utilisateurs ; vous devez leur obtenir des numéros de service.</span><span class="sxs-lookup"><span data-stu-id="e68af-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="e68af-125">Vous pouvez obtenir des numéros de service payants ou gratuits pour vos ponts de conférence.</span><span class="sxs-lookup"><span data-stu-id="e68af-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="e68af-126">Il existe trois façons d’obtenir des numéros de service payants et gratuits  :</span><span class="sxs-lookup"><span data-stu-id="e68af-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="e68af-127">**Utiliser le centre d’administration Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="e68af-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="e68af-128">Dans certains pays ou régions, vous pouvez obtenir des numéros de service pour vos ponts de conférence à l’aide du centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e68af-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="e68af-129">Voir [réception des numéros de téléphone de service](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="e68af-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="e68af-130">**Transférez vos numéros de service existants**.</span><span class="sxs-lookup"><span data-stu-id="e68af-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="e68af-131">Pour porter ou transférer des numéros existants de votre fournisseur de services ou de l’opérateur de téléphonie actuel vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="e68af-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="e68af-132">Vous pouvez consulter [Transfert des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md) ou [Gestion des numéros de téléphone pour votre entreprise](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) pour plus d’informations pour vous aider à effectuer ces opérations.</span><span class="sxs-lookup"><span data-stu-id="e68af-132">You can see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="e68af-133">**Utiliser un formulaire de demande pour de nouveaux numéros**.</span><span class="sxs-lookup"><span data-stu-id="e68af-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="e68af-134">Parfois (en fonction de votre pays ou région) vous ne serez pas en mesure d’obtenir vos nouveaux numéros de service à l’aide du centre d’administration Microsoft teams ou vous aurez besoin de numéros de téléphone spécifiques ou d’indicatifs régionaux.</span><span class="sxs-lookup"><span data-stu-id="e68af-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="e68af-135">Dans ce cas, vous devez télécharger un formulaire et nous le renvoyer.</span><span class="sxs-lookup"><span data-stu-id="e68af-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="e68af-136">Pour plus d’informations, voir [Gestion des numéros de téléphone pour votre entreprise](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="e68af-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="e68af-137">Étape 4 : Affecter un numéro de service pour le pont de conférence</span><span class="sxs-lookup"><span data-stu-id="e68af-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="e68af-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e68af-138"></span></span>

<span data-ttu-id="e68af-139">Une fois que vous obtenez les numéros de téléphone payants et/ou gratuits pour votre pont de conférence, vous devez les affecter pour les invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="e68af-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="e68af-140">Pour attribuer un nouveau numéro de téléphone à votre pont de conférence audio, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="e68af-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="e68af-141">![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise à l' **aide du centre d’administration Skype entreprise:**</span><span class="sxs-lookup"><span data-stu-id="e68af-141">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="e68af-142">Accédez au**portail**d'**administration** > \*\*\*\* > du centre > d' **administration Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="e68af-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="e68af-143">Sélectionnez les**numéros de téléphone** **vocaux** > .</span><span class="sxs-lookup"><span data-stu-id="e68af-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="e68af-144">Sélectionnez le numéro de téléphone et cliquez sur **affecter**.</span><span class="sxs-lookup"><span data-stu-id="e68af-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="e68af-145">Pour plus d’informations, reportez-vous à [la rubrique Modification des numéros de téléphone de votre pont de conférence audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="e68af-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="e68af-146">Étape 5 : Définir les langues par défaut et alternatives pour un pont de conférence</span><span class="sxs-lookup"><span data-stu-id="e68af-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="e68af-147"><a name="__top"></a> Ensuite, vous pouvez [définir des langues de standard automatique pour les conférences audio dans Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que le standard automatique de conférence utilise pour appeler les appelants quand ils se connectent à un numéro de téléphone pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="e68af-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="e68af-148">![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams **à l’aide du centre d’administration Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="e68af-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="e68af-149">Dans le tableau de bord, accédez à **meetings** > **Conference ponts**.</span><span class="sxs-lookup"><span data-stu-id="e68af-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="e68af-150">Sélectionnez le numéro de téléphone du pont de conférence, cliquez sur **modifier**, puis sélectionnez la langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="e68af-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="e68af-151">Étape 6 : Définir vos paramètres de pont de conférence</span><span class="sxs-lookup"><span data-stu-id="e68af-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="e68af-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e68af-152"></span></span>
    
<span data-ttu-id="e68af-153">Après avoir configuré votre pont de conférence, vérifiez que les paramètres par défaut, tels que les notifications d’entrée/sortie et la longueur du code confidentiel sont ceux que vous souhaitez utiliser. Si ce n’est pas le cas, vous pouvez les modifier.</span><span class="sxs-lookup"><span data-stu-id="e68af-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="e68af-154">![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams **à l’aide du centre d’administration Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="e68af-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="e68af-155">Dans le tableau de bord, accédez à **meetings** > **Conference ponts**.</span><span class="sxs-lookup"><span data-stu-id="e68af-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="e68af-156">Sélectionnez **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="e68af-156">Select **Bridge settings**.</span></span> <span data-ttu-id="e68af-157">Cela ouvrira le volet **Paramètres de pont**.</span><span class="sxs-lookup"><span data-stu-id="e68af-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="e68af-158">Pour plus d’informations, voir [Changement des paramètres de pont d’audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="e68af-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="e68af-159">Étape 7: Attribuer des numéros de téléphone de connexion pour les utilisateurs qui animent des réunions</span><span class="sxs-lookup"><span data-stu-id="e68af-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="e68af-160">Après avoir créé un pont d’audioconférence, vous devez définir les numéros payants et gratuits de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e68af-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="e68af-161">Vous devez effectuer cette opération pour toutes les personnes de votre entreprise qui animent ou qui planifient des réunions.</span><span class="sxs-lookup"><span data-stu-id="e68af-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="e68af-162">![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams **à l’aide du centre d’administration Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="e68af-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="e68af-163">Dans le tableau de bord, cliquez sur **utilisateurs**, sélectionnez l’utilisateur dans la liste, puis sélectionnez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="e68af-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="e68af-164">Sélectionnez **modifier** en regard de **audioconférence**, puis dans le volet **audioconférence** , sélectionnez un numéro dans les listes **numéro payant** et numéro **gratuit** .</span><span class="sxs-lookup"><span data-stu-id="e68af-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="e68af-165">Si vous avez besoin de plus de détails, consultez [Sélectionner Microsoft en tant que fournisseur d’audioconférences](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="e68af-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="e68af-166">Étape 8 : Configuration des invitations aux réunions (facultatif)</span><span class="sxs-lookup"><span data-stu-id="e68af-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="e68af-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e68af-167"></span></span>
 
<span data-ttu-id="e68af-168">Les numéros d’accès définis pour l’utilisateur sont automatiquement ajoutés aux invitations aux réunions envoyées aux participants à la réunion.</span><span class="sxs-lookup"><span data-stu-id="e68af-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="e68af-169">Vous pouvez cependant ajouter vos propres liens d’aide et légaux, un texte et une petite image de l’entreprise si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="e68af-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="e68af-170">Voir [personnaliser](meeting-settings-in-teams.md#customize-meeting-invitations)les invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="e68af-170">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="e68af-171">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="e68af-171">Related topics</span></span>

[<span data-ttu-id="e68af-172">Questions fréquentes à propos de l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="e68af-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="e68af-173">Numéros de téléphone pour l’audioconférence dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e68af-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="e68af-174">Définition des options pour les réunions en ligne et les téléconférences</span><span class="sxs-lookup"><span data-stu-id="e68af-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
