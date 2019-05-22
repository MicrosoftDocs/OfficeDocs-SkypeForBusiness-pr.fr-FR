---
title: Configurer l’audioconférence pour Skype entreprise
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Découvrez comment configurer des conférences rendez-vous ou audio pour les personnes de votre entreprise qui ont besoin d’utiliser un téléphone pour participer à des conférences téléphoniques. '
ms.openlocfilehash: fd259553794f0ed56d5e3a59752017b50478a97c
ms.sourcegitcommit: 2f8b9c7c8d20f2605d09cae4bbaeb10667f2ddea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/21/2019
ms.locfileid: "34329559"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="77d61-103">Configurer l’audioconférence pour Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="77d61-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="77d61-104">Parfois, les membres de votre organisation doivent utiliser un téléphone pour appeler une réunion.</span><span class="sxs-lookup"><span data-stu-id="77d61-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="77d61-105">Skype entreprise inclut la fonction de conférence rendez-vous pour cette situation uniquement.</span><span class="sxs-lookup"><span data-stu-id="77d61-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="77d61-106">Les personnes peuvent appeler des réunions Skype entreprise à l’aide d’un téléphone, au lieu d’utiliser l’application Skype entreprise sur un appareil mobile ou un PC.</span><span class="sxs-lookup"><span data-stu-id="77d61-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="77d61-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="77d61-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="77d61-109">Pour trouver les questions fréquemment posées à propos des audioconférences, consultez [Questions courantes concernant les audioconférences](/MicrosoftTeams/audio-conferencing-common-questions).</span><span class="sxs-lookup"><span data-stu-id="77d61-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="77d61-110">Étape 1 : Déterminez si les audioconférence sont disponibles dans votre pays/région</span><span class="sxs-lookup"><span data-stu-id="77d61-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="77d61-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="77d61-111"><a name="__top"> </a></span></span>

<span data-ttu-id="77d61-112">Allez à la page [Disponibilité des pays et des régions pour les audioconférences et les forfaits d’appel](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) et sélectionnez votre pays ou région pour obtenir des informations de disponibilité sur les audioconférences, ainsi que des informations sur le système téléphonique, les forfaits d’appel, les numéros payants et gratuits et les crédits de communications.</span><span class="sxs-lookup"><span data-stu-id="77d61-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="77d61-113">Étape 2 : Obtenir et attribuer des licences</span><span class="sxs-lookup"><span data-stu-id="77d61-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="77d61-114">Pour une audioconférence, vous avez besoin d’une licence pour chaque utilisateur qui établira des réunions.</span><span class="sxs-lookup"><span data-stu-id="77d61-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="77d61-115">Pour connaître les licences que vous devez acheter pour les conférences audio et leurs coûts, reportez-vous à la rubrique [licences de complément Skype entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="77d61-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="77d61-116">L’audioconférence est incluse dans les licences Office 365 entreprise E5 et en tant que composant additionnel.</span><span class="sxs-lookup"><span data-stu-id="77d61-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="77d61-117">Une fois que vous avez acheté les licences de conférence audio, vous devez les affecter aux personnes de votre organisation qui vont planifier ou animer des réunions.</span><span class="sxs-lookup"><span data-stu-id="77d61-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="77d61-118">Voir [affecter ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que vous avez achetées aux personnes de votre organisation qui vont planifier ou animer des réunions.</span><span class="sxs-lookup"><span data-stu-id="77d61-118">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="77d61-119">Nous vous recommandons également d’affecter des licences de crédits de communications (elles ne coûtent rien) aux mêmes personnes à qui vous avez attribué des licences à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="77d61-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="77d61-120">Pour savoir comment configurer les Crédits de communications, voir [Configurer les Crédits de communications pour votre entreprise](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="77d61-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="77d61-121">Vous pouvez également configurer [le service de conférence](/microsoftteams/audio-conferencing-pay-per-minute)rendez-vous en fonction du son.</span><span class="sxs-lookup"><span data-stu-id="77d61-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="77d61-122">Étape 3 : Obtenir les numéros de service pour vos ponts de conférence</span><span class="sxs-lookup"><span data-stu-id="77d61-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="77d61-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="77d61-123"></span></span>

<span data-ttu-id="77d61-124">Pour les audioconférences, vous ne pouvez pas utiliser les numéros de téléphone pour les utilisateurs ; vous devez leur obtenir des numéros de service.</span><span class="sxs-lookup"><span data-stu-id="77d61-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="77d61-125">Vous pouvez obtenir des numéros de service payants ou gratuits pour vos ponts de conférence.</span><span class="sxs-lookup"><span data-stu-id="77d61-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="77d61-126">Il existe trois façons d’obtenir des numéros de service payants et gratuits  :</span><span class="sxs-lookup"><span data-stu-id="77d61-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="77d61-127">**Utilisez le centre d’administration Skype entreprise**.</span><span class="sxs-lookup"><span data-stu-id="77d61-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="77d61-128">Dans certains pays ou régions, vous pouvez obtenir des numéros de service pour les ponts de conférences à l’aide du centre d’administration Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="77d61-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="77d61-129">Voir [réception des numéros de téléphone de service](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="77d61-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="77d61-130">**Transférez vos numéros de service existants**.</span><span class="sxs-lookup"><span data-stu-id="77d61-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="77d61-131">Pour porter ou transférer des numéros existants de votre fournisseur de services ou de l’opérateur de téléphonie actuel vers Office 365.</span><span class="sxs-lookup"><span data-stu-id="77d61-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="77d61-132">Vous pouvez consulter [Transfert des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) ou [Gestion des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization) pour plus d’informations pour vous aider à effectuer ces opérations.</span><span class="sxs-lookup"><span data-stu-id="77d61-132">You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="77d61-133">**Utiliser un formulaire de demande pour de nouveaux numéros**.</span><span class="sxs-lookup"><span data-stu-id="77d61-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="77d61-134">Parfois (en fonction de votre pays ou région) vous ne serez pas en mesure d’obtenir vos nouveaux numéros de service dans le centre d’administration de Skype entreprise ou vous aurez besoin de numéros de téléphone spécifiques ou d’indicatifs régionaux.</span><span class="sxs-lookup"><span data-stu-id="77d61-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="77d61-135">Dans ce cas, vous devez télécharger un formulaire et nous le renvoyer.</span><span class="sxs-lookup"><span data-stu-id="77d61-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="77d61-136">Pour plus d’informations, voir [Gestion des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="77d61-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="77d61-137">Étape 4 : Affecter un numéro de service pour le pont de conférence</span><span class="sxs-lookup"><span data-stu-id="77d61-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="77d61-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="77d61-138"></span></span>

<span data-ttu-id="77d61-139">Une fois que vous obtenez les numéros de téléphone payants et/ou gratuits pour votre pont de conférence, vous devez les affecter pour les invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="77d61-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="77d61-140">Affecter un nouveau numéro de téléphone à votre pont d’audioconférence :</span><span class="sxs-lookup"><span data-stu-id="77d61-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="77d61-141">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **à l’aide du centre d’administration Skype entreprise:**</span><span class="sxs-lookup"><span data-stu-id="77d61-141">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="77d61-142">Accédez au**portail**d'**administration** > \*\*\*\* > du centre > d' **administration Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="77d61-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="77d61-143">Sélectionnez les**numéros de téléphone** **vocaux** > .</span><span class="sxs-lookup"><span data-stu-id="77d61-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="77d61-144">Sélectionnez le numéro de téléphone et cliquez sur **affecter**.</span><span class="sxs-lookup"><span data-stu-id="77d61-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="77d61-145">Pour plus d’informations, consultez la rubrique [Modifier les numéros de téléphone sur votre pont d’audioconférence](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="77d61-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="77d61-146">Étape 5 : Définir les langues par défaut et alternatives pour un pont de conférence</span><span class="sxs-lookup"><span data-stu-id="77d61-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="77d61-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="77d61-147"></span></span>

<span data-ttu-id="77d61-148">Vous pouvez ensuite [définir des langues de standard automatique pour les conférences audio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que le standard automatique de conférence utilise pour appeler les appelants quand ils se connectent à un numéro de téléphone pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="77d61-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="77d61-149">![teams-logo-30x30. png](../images/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="77d61-149">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="77d61-150">Dans le tableau de bord, accédez à **meetings** > **Conference ponts**.</span><span class="sxs-lookup"><span data-stu-id="77d61-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="77d61-151">Sélectionnez le numéro de téléphone du pont de conférence, cliquez sur **modifier**, puis sélectionnez la langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="77d61-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="77d61-152">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **à l’aide du centre d’administration Skype entreprise**:</span><span class="sxs-lookup"><span data-stu-id="77d61-152">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="77d61-153">\*\*\*\* > Accédez au portail d’administration du centre > d' **administration Office 365\*\*\*\*équipes** > du**portail hérité**.</span><span class="sxs-lookup"><span data-stu-id="77d61-153">Go to the **Office 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="77d61-154">Sélectionnez **audioconférence** > **Microsoft Bridge**.</span><span class="sxs-lookup"><span data-stu-id="77d61-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="77d61-155">Sélectionnez le numéro de téléphone du pont de conférence, cliquez sur **définir les langues**, puis sélectionnez la langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="77d61-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="77d61-156">Étape 6 : Définir vos paramètres de pont de conférence</span><span class="sxs-lookup"><span data-stu-id="77d61-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="77d61-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="77d61-157"></span></span>
    
<span data-ttu-id="77d61-158">Après avoir configuré votre pont de conférence, vérifiez que les paramètres par défaut, tels que les notifications d’entrée/sortie et la longueur du code confidentiel sont ceux que vous souhaitez utiliser. Si ce n’est pas le cas, vous pouvez les modifier.</span><span class="sxs-lookup"><span data-stu-id="77d61-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="77d61-159">![teams-logo-30x30. png](../images/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="77d61-159">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="77d61-160">Dans le tableau de bord, accédez à **meetings** > **Conference ponts**.</span><span class="sxs-lookup"><span data-stu-id="77d61-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="77d61-161">Sélectionnez **paramètres du pont**.</span><span class="sxs-lookup"><span data-stu-id="77d61-161">Select **Bridge settings**.</span></span> <span data-ttu-id="77d61-162">Cela ouvrira le volet **Paramètres de pont**.</span><span class="sxs-lookup"><span data-stu-id="77d61-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="77d61-163">Pour plus d’informations, voir [Changement des paramètres de pont d’audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="77d61-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="77d61-164">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **à l’aide du centre d’administration Skype entreprise:**</span><span class="sxs-lookup"><span data-stu-id="77d61-164">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="77d61-165">Accédez au**portail**d'**administration** > \*\*\*\* > du centre > d' **administration Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="77d61-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="77d61-166">Sélectionnez \*\*\*\* > **paramètres du pont Microsoft**Conferencing.</span><span class="sxs-lookup"><span data-stu-id="77d61-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="77d61-167">Cela ouvrira la page **Paramètres de pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="77d61-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="77d61-168">Pour plus d’informations, voir [Changement des paramètres de pont d’audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="77d61-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="77d61-169">Étape 7: Attribuer des numéros de téléphone de connexion pour les utilisateurs qui animent des réunions</span><span class="sxs-lookup"><span data-stu-id="77d61-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="77d61-170">Après avoir créé un pont d’audioconférence, vous devez définir les numéros payants et gratuits de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="77d61-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="77d61-171">Vous devez effectuer cette opération pour toutes les personnes de votre entreprise qui animent ou qui planifient des réunions.</span><span class="sxs-lookup"><span data-stu-id="77d61-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="77d61-172">![teams-logo-30x30. png](../images/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**:</span><span class="sxs-lookup"><span data-stu-id="77d61-172">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="77d61-173">Dans le tableau de bord, cliquez sur **utilisateurs**, sélectionnez l’utilisateur dans la liste, puis sélectionnez **modifier**.</span><span class="sxs-lookup"><span data-stu-id="77d61-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="77d61-174">Sélectionnez **modifier** en regard de **audioconférence**, puis dans le volet **audioconférence** , sélectionnez un numéro dans les listes **numéro payant** et numéro **gratuit** .</span><span class="sxs-lookup"><span data-stu-id="77d61-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="77d61-175">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **à l’aide du centre d’administration Skype entreprise:**</span><span class="sxs-lookup"><span data-stu-id="77d61-175">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="77d61-176">Accédez au**portail**d'**équipe** > du centre > d' **administration 365 Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="77d61-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="77d61-177">Sélectionnez \*\*\*\* > **utilisateurs**de l’audioconférence, puis sélectionnez l’utilisateur dans la liste et cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="77d61-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="77d61-178">Si vous avez besoin de plus de détails, consultez [Sélectionner Microsoft en tant que fournisseur d’audioconférences](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="77d61-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="77d61-179">Étape 8 : Configuration des invitations aux réunions (facultatif)</span><span class="sxs-lookup"><span data-stu-id="77d61-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="77d61-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="77d61-180"></span></span>
 
<span data-ttu-id="77d61-181">Les numéros d’accès définis pour l’utilisateur sont automatiquement ajoutés aux invitations aux réunions envoyées aux participants à la réunion.</span><span class="sxs-lookup"><span data-stu-id="77d61-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="77d61-182">Vous pouvez cependant ajouter vos propres liens d’aide et légaux, un texte et une petite image de l’entreprise si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="77d61-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="77d61-183">Voir [personnaliser](../set-up-skype-for-business-online/customize-meeting-invitations.md)les invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="77d61-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="77d61-184">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="77d61-184">Related topics</span></span>

[<span data-ttu-id="77d61-185">Questions fréquentes à propos de l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="77d61-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="77d61-186">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="77d61-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="77d61-187">Numéros de téléphone pour l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="77d61-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="77d61-188">Définition des options pour les réunions en ligne et les téléconférences</span><span class="sxs-lookup"><span data-stu-id="77d61-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
