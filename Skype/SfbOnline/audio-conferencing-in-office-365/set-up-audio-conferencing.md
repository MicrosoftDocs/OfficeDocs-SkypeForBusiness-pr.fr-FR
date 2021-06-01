---
title: Configurer l’audioconférence pour Skype Entreprise
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: 'Découvrez comment configurer la Conférence rendez-vous ou l’Audioconférence pour les membres de votre entreprise qui doivent utiliser un téléphone pour participer à des téléconférences. '
ms.openlocfilehash: ce5d80b8be0fe2e6983229be8185bcdf02e06ab6
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237640"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="f371d-103">Configurer l’audioconférence pour Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="f371d-103">Set up Audio Conferencing for Skype for Business</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="f371d-104">Parfois, des personnes de votre organisation devront utiliser un téléphone pour rejoindre une réunion.</span><span class="sxs-lookup"><span data-stu-id="f371d-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="f371d-105">Skype Entreprise inclut uniquement la fonction d’audioconférence pour cette situation !</span><span class="sxs-lookup"><span data-stu-id="f371d-105">Skype for Business includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="f371d-106">Les personnes peuvent se rendre par téléphone Skype Entreprise réunions à l’aide d’un téléphone, au lieu d’utiliser l’application Skype Entreprise sur un appareil mobile ou un PC.</span><span class="sxs-lookup"><span data-stu-id="f371d-106">People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="f371d-107">Il vous suffit de configurer la fonctionnalité de conférence audio pour les utilisateurs qui comptent planifier ou organiser des réunions.</span><span class="sxs-lookup"><span data-stu-id="f371d-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="f371d-108">Les participants à la réunion qui se connectent n’ont pas besoin de licence ou de configuration particulière.</span><span class="sxs-lookup"><span data-stu-id="f371d-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="f371d-109">Pour trouver les questions fréquemment posées à propos des audioconférences, consultez [Questions courantes concernant les audioconférences](/MicrosoftTeams/audio-conferencing-common-questions).</span><span class="sxs-lookup"><span data-stu-id="f371d-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="f371d-110">Étape 1 : Déterminez si les audioconférence sont disponibles dans votre pays/région</span><span class="sxs-lookup"><span data-stu-id="f371d-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="f371d-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f371d-111"><a name="__top"> </a></span></span>

<span data-ttu-id="f371d-112">Allez à la page [Disponibilité des pays et des régions pour les audioconférences et les forfaits d’appel](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) et sélectionnez votre pays ou région pour obtenir des informations de disponibilité sur les audioconférences, ainsi que des informations sur le système téléphonique, les forfaits d’appel, les numéros payants et gratuits et les crédits de communications.</span><span class="sxs-lookup"><span data-stu-id="f371d-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="f371d-113">Étape 2 : Obtenir et attribuer des licences</span><span class="sxs-lookup"><span data-stu-id="f371d-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="f371d-114">Pour une audioconférence, vous avez besoin d’une licence pour chaque utilisateur qui établira des réunions.</span><span class="sxs-lookup"><span data-stu-id="f371d-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="f371d-115">Pour connaître les licences que vous devez acheter pour AudioConférence et leurs prix, consultez la Skype Entreprise [de modules supplémentaires.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="f371d-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="f371d-116">La fonctionnalité audioconférence est incluse dans les licences Office 365 Entreprise E5 et en tant que composant additionnel.</span><span class="sxs-lookup"><span data-stu-id="f371d-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="f371d-117">Une fois que vous avez acheté les licences d’audioconférence, vous devez les attribuer aux personnes qui vont planifier ou animer des réunions.</span><span class="sxs-lookup"><span data-stu-id="f371d-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="f371d-118">Pour [plus d’Applications Microsoft 365 pour les PME,](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) voir Attribuer ou supprimer des licences pour les personnes de votre organisation qui vont planifier ou diriger des réunions.</span><span class="sxs-lookup"><span data-stu-id="f371d-118">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="f371d-119">Nous vous recommandons également d’affecter des licences de crédits de communications (elles ne coûtent rien) aux mêmes personnes à qui vous avez attribué des licences à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="f371d-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="f371d-120">Pour savoir comment configurer les Crédits de communications, voir [Configurer les Crédits de communications pour votre entreprise](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="f371d-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="f371d-121">Vous pouvez également configurer les [audioconférences en mode « payer à la minute »](/microsoftteams/audio-conferencing-pay-per-minute).</span><span class="sxs-lookup"><span data-stu-id="f371d-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="f371d-122">Étape 3 : Obtenir les numéros de service pour vos ponts de conférence</span><span class="sxs-lookup"><span data-stu-id="f371d-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="f371d-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f371d-123"><a name="__top"> </a></span></span>

<span data-ttu-id="f371d-124">Pour les audioconférences, vous ne pouvez pas utiliser les numéros de téléphone pour les utilisateurs ; vous devez leur obtenir des numéros de service.</span><span class="sxs-lookup"><span data-stu-id="f371d-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="f371d-125">Vous pouvez obtenir des numéros de service payants ou gratuits pour vos ponts de conférence.</span><span class="sxs-lookup"><span data-stu-id="f371d-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="f371d-126">Il existe trois façons d’obtenir des numéros de service payants et gratuits  :</span><span class="sxs-lookup"><span data-stu-id="f371d-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="f371d-127">**Utilisez le centre Skype Entreprise d’administration de l’utilisateur.**</span><span class="sxs-lookup"><span data-stu-id="f371d-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="f371d-128">Pour certains pays ou certaines régions, vous pouvez obtenir des numéros de service pour vos ponts de conférence à l’aide du Skype Entreprise d’administration.</span><span class="sxs-lookup"><span data-stu-id="f371d-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="f371d-129">Voir [Obtention de numéros de téléphone de service](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="f371d-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="f371d-130">**Portage de vos numéros de service existants**.</span><span class="sxs-lookup"><span data-stu-id="f371d-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="f371d-131">Pour porter ou transférer des numéros existants de votre fournisseur de service ou de votre téléphone actuel vers Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="f371d-131">To port or transfer existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f371d-132">Vous pouvez consulter [Transfert des numéros de téléphone vers Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) ou [Gestion des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization) pour plus d’informations pour vous aider à effectuer ces opérations.</span><span class="sxs-lookup"><span data-stu-id="f371d-132">You can see [Transfer phone numbers to Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="f371d-133">**Utiliser un formulaire de demande pour de nouveaux numéros**.</span><span class="sxs-lookup"><span data-stu-id="f371d-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="f371d-134">Parfois (selon votre pays/région) vous ne pourrez pas obtenir vos nouveaux numéros de service à l’aide du Centre d’administration Skype Entreprise ou vous aurez besoin de numéros de téléphone ou indicatifs régionaux spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f371d-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="f371d-135">Si c'est le cas, vous devrez télécharger un formulaire et nous le renvoyer.</span><span class="sxs-lookup"><span data-stu-id="f371d-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="f371d-136">Pour plus d’informations, voir [Gestion des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="f371d-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="f371d-137">Étape 4 : Affecter un numéro de service pour le pont de conférence</span><span class="sxs-lookup"><span data-stu-id="f371d-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="f371d-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f371d-138"><a name="__top"> </a></span></span>

<span data-ttu-id="f371d-139">Une fois que vous obtenez vos numéros de téléphone payants et/ou gratuits pour le pont de conférence, vous devez les assigner afin qu’ils puissent être utilisés pour les invitations aux réunions.</span><span class="sxs-lookup"><span data-stu-id="f371d-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="f371d-140">Affecter un nouveau numéro de téléphone à votre pont d’audioconférence :</span><span class="sxs-lookup"><span data-stu-id="f371d-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="f371d-141">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **utilisant le Centre d’administration Skype Entreprise :**</span><span class="sxs-lookup"><span data-stu-id="f371d-141">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="f371d-142">Accédez au **Centre d’administration Microsoft 365** > **Centres d’administration** > **Teams** > **Portail de l'héritage**.</span><span class="sxs-lookup"><span data-stu-id="f371d-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="f371d-143">Sélectionnez **Voice** > **Numéros de téléphone**.</span><span class="sxs-lookup"><span data-stu-id="f371d-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="f371d-144">Sélectionnez le numéro de téléphone, puis cliquez sur **Affecter**.</span><span class="sxs-lookup"><span data-stu-id="f371d-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="f371d-145">Pour plus d’informations, consultez la rubrique [Modifier les numéros de téléphone sur votre pont d’audioconférence](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="f371d-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="f371d-146">Étape 5 : Définir les langues par défaut et alternatives pour un pont de conférence</span><span class="sxs-lookup"><span data-stu-id="f371d-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="f371d-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f371d-147"><a name="__top"> </a></span></span>

<span data-ttu-id="f371d-148">Vous pouvez ensuite définir les [langues](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) du attendant automatique pour l’audioconférence que le attendant de conférence utilise pour accueillir les appelants lorsqu’ils appellent un numéro de téléphone pour l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="f371d-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="f371d-149">![Icône affichant le logo Microsoft Teams](../images/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams** :</span><span class="sxs-lookup"><span data-stu-id="f371d-149">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="f371d-150">Dans le tableau de bord, accédez à **Réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="f371d-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="f371d-151">Sélectionnez le numéro de téléphone de pont de conférence, cliquez sur **Modifier**, puis choisissez la langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="f371d-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="f371d-152">![Icône montrant le logo ](../images/sfb-logo-30x30.png) **Skype Entreprise’aide du Centre d’Skype Entreprise d’administration :**</span><span class="sxs-lookup"><span data-stu-id="f371d-152">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="f371d-153">Allez dans le Centre d’administration > **centres d’administration**  >  **Teams**  >  **portail hérité.**</span><span class="sxs-lookup"><span data-stu-id="f371d-153">Go to the admin center > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="f371d-154">Sélectionnez **Audioconférences**  >  **Pont Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="f371d-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="f371d-155">Sélectionnez le numéro de téléphone du pont de conférence, sélectionnez Définir les **langues,** puis choisissez la langue par défaut.</span><span class="sxs-lookup"><span data-stu-id="f371d-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="f371d-156">Étape 6 : Définir vos paramètres de pont de conférence</span><span class="sxs-lookup"><span data-stu-id="f371d-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="f371d-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f371d-157"><a name="__top"> </a></span></span>
    
<span data-ttu-id="f371d-158">Après avoir configuré votre pont de conférence, vérifiez que les paramètres par défaut, tels que les notifications d’entrée/sortie et la longueur du code confidentiel sont ceux que vous souhaitez utiliser. Si ce n’est pas le cas, vous pouvez les modifier.</span><span class="sxs-lookup"><span data-stu-id="f371d-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="f371d-159">![Icône affichant le logo Microsoft Teams](../images/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams** :</span><span class="sxs-lookup"><span data-stu-id="f371d-159">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="f371d-160">Dans le tableau de bord, accédez à **Réunions** > **Ponts de conférence**.</span><span class="sxs-lookup"><span data-stu-id="f371d-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="f371d-161">Sélectionnez **Paramètres de Bridge**.</span><span class="sxs-lookup"><span data-stu-id="f371d-161">Select **Bridge settings**.</span></span> <span data-ttu-id="f371d-162">Cela ouvrira le volet **Paramètres de pont**.</span><span class="sxs-lookup"><span data-stu-id="f371d-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="f371d-163">Pour plus d’informations, voir [Changement des paramètres de pont d’audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="f371d-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="f371d-164">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **utilisant le Centre d’administration Skype Entreprise :**</span><span class="sxs-lookup"><span data-stu-id="f371d-164">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="f371d-165">Accédez au **Centre d’administration Microsoft 365** > **Centres d’administration** > **Teams** > **Portail de l'héritage**.</span><span class="sxs-lookup"><span data-stu-id="f371d-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="f371d-166">Sélectionnez **Les paramètres du pont** Microsoft de  >  **l’audioconférence.**</span><span class="sxs-lookup"><span data-stu-id="f371d-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="f371d-167">Cela ouvrira la page **Paramètres de pont Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f371d-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="f371d-168">Pour plus d’informations, voir [Changement des paramètres de pont d’audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="f371d-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="f371d-169">Étape 7: Attribuer des numéros de téléphone de connexion pour les utilisateurs qui animent des réunions</span><span class="sxs-lookup"><span data-stu-id="f371d-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="f371d-170">Après avoir créé un pont d’audioconférence, vous devez définir les numéros payants et gratuits de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f371d-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="f371d-171">Vous devez effectuer cette opération pour toutes les personnes de votre entreprise qui animent ou qui planifient des réunions.</span><span class="sxs-lookup"><span data-stu-id="f371d-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="f371d-172">![Icône affichant le logo Microsoft Teams](../images/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams** :</span><span class="sxs-lookup"><span data-stu-id="f371d-172">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="f371d-173">Dans le tableau de bord, cliquez sur **Utilisateurs**, sélectionnez l’utilisateur dans la liste, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f371d-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="f371d-174">Sélectionnez **Modifier** à côté de **Audioconférence**, puis dans le volet **Audioconférence**, choisissez un numéro dans les listes de **numéros payants** et de **numéros gratuits**.</span><span class="sxs-lookup"><span data-stu-id="f371d-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="f371d-175">![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **utilisant le Centre d’administration Skype Entreprise :**</span><span class="sxs-lookup"><span data-stu-id="f371d-175">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="f371d-176">Allez au Centre **Microsoft 365'administration**  >    >  **Teams’administration hérité.**</span><span class="sxs-lookup"><span data-stu-id="f371d-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="f371d-177">Sélectionnez **Utilisateurs de l’audioconférence,** sélectionnez l’utilisateur dans la liste  >  et cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="f371d-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="f371d-178">Si vous avez besoin de plus de détails, consultez [Sélectionner Microsoft en tant que fournisseur d’audioconférences](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="f371d-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="f371d-179">Étape 8 : Configuration des invitations aux réunions (facultatif)</span><span class="sxs-lookup"><span data-stu-id="f371d-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="f371d-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="f371d-180"><a name="__top"> </a></span></span>
 
<span data-ttu-id="f371d-181">Les numéros de connexion définis pour l'utilisateur seront ajoutés automatiquement aux invitations envoyées aux participants à la réunion.</span><span class="sxs-lookup"><span data-stu-id="f371d-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="f371d-182">Vous pouvez cependant ajouter vos propres liens d’aide et légaux, un texte et une petite image de l’entreprise si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="f371d-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="f371d-183">Voir [Personnaliser les invitations aux réunions](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="f371d-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="f371d-184">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="f371d-184">Related topics</span></span>

[<span data-ttu-id="f371d-185">Questions fréquentes à propos de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="f371d-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="f371d-186">Configurer Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f371d-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="f371d-187">Numéros de téléphone pour l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="f371d-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="f371d-188">Définition des options pour les réunions en ligne et les téléconférences</span><span class="sxs-lookup"><span data-stu-id="f371d-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
