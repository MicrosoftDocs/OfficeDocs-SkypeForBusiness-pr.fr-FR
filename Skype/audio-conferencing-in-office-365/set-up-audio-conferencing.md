---
title: "Configurer la conférence Audio pour Skype entreprise et Teams Microsoft"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: "Apprenez à configurer les conférences audio ou accès à distance pour les personnes de votre entreprise qui ont besoin de joindre des conférences téléphoniques à l’aide d’un téléphone. "
ms.openlocfilehash: fd427abf14d3d705bc9f846f32a27d9be62967e8
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="24160-103">Configurer la conférence Audio pour Skype entreprise et Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="24160-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="24160-104">Parfois, les membres de votre organisation devront utiliser un téléphone pour composer le numéro de la réunion.</span><span class="sxs-lookup"><span data-stu-id="24160-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="24160-105">Skype pour les entreprises et les Teams Microsoft incluent la fonctionnalité de conférence audio seulement cette situation !</span><span class="sxs-lookup"><span data-stu-id="24160-105">Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="24160-106">Personnes peut appeler Skype pour les réunions d’entreprise ou Teams de Microsoft à l’aide d’un téléphone, au lieu d’utiliser le Skype pour une application métier ou Teams de Microsoft sur un PC ou un périphérique mobile.</span><span class="sxs-lookup"><span data-stu-id="24160-106">People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="24160-107">Vous devez uniquement configurer d’Audio conférence pour les personnes qui souhaitent planifier ou de mener des réunions.</span><span class="sxs-lookup"><span data-stu-id="24160-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="24160-108">Participants à la réunion qui se connectent en n’avez pas besoin des licences attribuées ou autre programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="24160-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="24160-109">Pour les questions fréquemment posées à propos des conférences de données Audio, consultez [questions courantes d’audioconférence](audio-conferencing-common-questions.md).</span><span class="sxs-lookup"><span data-stu-id="24160-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
  
## <a name="step-1-buy-and-assign-licenses"></a><span data-ttu-id="24160-110">Étape 1 : acheter et affecter des licences</span><span class="sxs-lookup"><span data-stu-id="24160-110">Step 1: Buy and assign licenses</span></span>
<span data-ttu-id="24160-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="24160-111"></span></span>

<span data-ttu-id="24160-112">Vous devez être un [sur Office 365 rôles d’administrateur](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="24160-112">You must be an [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
  
1. <span data-ttu-id="24160-113">Découvrez si audioconférence dans Office 365 est disponible dans votre pays/région.</span><span class="sxs-lookup"><span data-stu-id="24160-113">Find out if Audio Conferencing in Office 365 is available in your country/region.</span></span> <span data-ttu-id="24160-114">[Pays et région de disponibilité pour les conférences Audio et les Plans d’appel](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="24160-114">[Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> 
    
2. <span data-ttu-id="24160-115">Découvrez les licences que vous devez acheter pour les conférences Audio et comment leur coût.</span><span class="sxs-lookup"><span data-stu-id="24160-115">Learn which licenses you need to buy for Audio Conferencing, and how much they will cost.</span></span> <span data-ttu-id="24160-116">Voir [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestionnaire de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)et acheter les licences.</span><span class="sxs-lookup"><span data-stu-id="24160-116">See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses.</span></span> 
    
3. <span data-ttu-id="24160-117">[Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que vous avez achetées aux collègues qui vont planifier ou animer des réunions.</span><span class="sxs-lookup"><span data-stu-id="24160-117">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
4. <span data-ttu-id="24160-118">Si vous avez acheté des licences de module complémentaire **Audioconférence** et crédits de la communication, les affecter trop.</span><span class="sxs-lookup"><span data-stu-id="24160-118">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too.</span></span> <span data-ttu-id="24160-119">Pour obtenir des instructions, reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="24160-119">For instructions, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a><span data-ttu-id="24160-120">Étape 2 : Choisissez votre fournisseur de conférence audio</span><span class="sxs-lookup"><span data-stu-id="24160-120">Step 2: Decide on your audio conferencing provider</span></span>
<span data-ttu-id="24160-121"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="24160-121"></span></span>

<span data-ttu-id="24160-122">Un fournisseur de conférence audio fournit un *pont de conférence audio*.</span><span class="sxs-lookup"><span data-stu-id="24160-122">An audio conferencing provider supplies an *audio conferencing bridge*.</span></span> <span data-ttu-id="24160-123">Le pont de conférence définit les numéros de téléphone, broches, les ID de conférence pour les réunions.</span><span class="sxs-lookup"><span data-stu-id="24160-123">The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings.</span></span> <span data-ttu-id="24160-124">Décider s’il faut utiliser Microsoft ou un fournisseur de conférence audio de tiers :</span><span class="sxs-lookup"><span data-stu-id="24160-124">Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>
  
> [!NOTE]
> <span data-ttu-id="24160-125">Les utilisateurs de Microsoft Teams ne peut pas utilisateur d’un fournisseur de conférence audio de tiers.</span><span class="sxs-lookup"><span data-stu-id="24160-125">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span> 
  
- <span data-ttu-id="24160-126">**Microsoft en tant que votre fournisseur de conférence audio**: Si vous souhaitez que la solution la plus simple pour les conférences audio, choisissez Microsoft en tant que votre fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="24160-126">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>
    
- <span data-ttu-id="24160-127">**Tiers en tant que votre fournisseur de conférence audio**: Si vous êtes dans un pays où la conférence Audio dans Office 365 n’est pas disponible, la qualité de service n’est pas idéale en raison de son emplacement ou vous avez un contrat existant, choisissez un audio tiers fournisseur de la conférence.</span><span class="sxs-lookup"><span data-stu-id="24160-127">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider.</span></span> <span data-ttu-id="24160-128">Pour rechercher un fournisseur, accédez à [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span><span class="sxs-lookup"><span data-stu-id="24160-128">To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span></span>
    
> [!TIP]
> <span data-ttu-id="24160-129">Dans votre organisation, vous pouvez avoir certains utilisateurs de Microsoft comme leur fournisseur de conférence audio, les personnes qui utilisent un fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="24160-129">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider.</span></span> <span data-ttu-id="24160-130">Mais cela sera plus complexe, vous pouvez configurer et gérer.</span><span class="sxs-lookup"><span data-stu-id="24160-130">But this will be more complicated for you to set up and manage.</span></span> 
  
<span data-ttu-id="24160-131">Pour une comparaison détaillée entre Microsoft comme fournisseur audio et d’un fournisseur tiers, consultez [comparaison de fournisseurs de conférence audio](compare-audio-conferencing-providers.md).</span><span class="sxs-lookup"><span data-stu-id="24160-131">For a detailed comparison between Microsoft as your audio provider and a third-party provider, see [Compare audio conferencing providers](compare-audio-conferencing-providers.md).</span></span> 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a><span data-ttu-id="24160-132">Étape 3 : Affectez le fournisseur de conférence audio pour les personnes qui avance ou planifient des réunions</span><span class="sxs-lookup"><span data-stu-id="24160-132">Step 3: Assign the audio conferencing provider to people who lead or schedule meetings</span></span>
<span data-ttu-id="24160-133"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="24160-133"></span></span>

<span data-ttu-id="24160-134">Maintenant que vous avez choisi votre fournisseur de conférence audio, vous devez affecter le fournisseur à des personnes de votre organisation qui avance ou planifier des réunions.</span><span class="sxs-lookup"><span data-stu-id="24160-134">Now that you've decided on your audio conferencing provider, you need to assign the provider to people in your organization who lead or schedule meetings.</span></span> <span data-ttu-id="24160-135">Procédez selon l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="24160-135">Do one of the following:</span></span> 
  
- <span data-ttu-id="24160-136">[Affectation de Microsoft en tant que le fournisseur de conférence audio](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="24160-136">[Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="24160-137">[Affecter un comme fournisseur de conférence audio tiers](assign-a-third-party-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="24160-137">[Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
## <a name="step-4-set-up-meeting-invitations"></a><span data-ttu-id="24160-138">Étape 4 : Définir des invitations à une réunion</span><span class="sxs-lookup"><span data-stu-id="24160-138">Step 4: Set up meeting invitations</span></span>
<span data-ttu-id="24160-139"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="24160-139"></span></span>

<span data-ttu-id="24160-140">Les étapes suivantes sont **facultatives**, mais beaucoup d’administrateurs comme les exécuter :</span><span class="sxs-lookup"><span data-stu-id="24160-140">The following steps are **optional**, but a lot of admins like to do them:</span></span>
  
1. <span data-ttu-id="24160-141">[Invitations à personnaliser](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="24160-141">[Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span> <span data-ttu-id="24160-142">Les numéros de connexion définis pour l'utilisateur seront ajoutés automatiquement aux invitations envoyées aux participants.</span><span class="sxs-lookup"><span data-stu-id="24160-142">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees.</span></span> <span data-ttu-id="24160-143">Toutefois, vous pouvez ajouter votre propre aide et liens juridiques, un message texte et graphique de petite entreprise.</span><span class="sxs-lookup"><span data-stu-id="24160-143">However, you can add your own help and legal links, a text message, and small company graphic.</span></span>
    
2. <span data-ttu-id="24160-144">[Jeu de numéros de téléphone Audio conférence pour les organisateurs qui sont inclus dans les invitations de réunion](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="24160-144">[Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span> <span data-ttu-id="24160-145">C’est le numéro de téléphone qui s’affiche lors de la réunion est planifiée par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="24160-145">This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>
    
3. <span data-ttu-id="24160-146">Pour [définir les langues de surveillance automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing.md) la surveillance automatique de conférence audio utilise pour accueillir un appelant lorsqu’ils se connectent à un numéro de téléphone de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="24160-146">[Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number.</span></span> <span data-ttu-id="24160-147">Cette étape s’applique uniquement si vous utilisez Microsoft comme fournisseur audio.</span><span class="sxs-lookup"><span data-stu-id="24160-147">This step only applies if you're using Microsoft as your audio provider.</span></span>
    
4. <span data-ttu-id="24160-148">[Définir la longueur de la broche pour les réunions de la conférence de l’Audio](set-the-pin-length-for-audio-conferencing-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="24160-148">[Set the length of the PIN for Audio Conferencing meetings](set-the-pin-length-for-audio-conferencing-meetings.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="24160-149">Cette fonctionnalité n’est pas encore disponible pour les clients à l’aide d’Office 365 exploités par 21Vianet en Chine.</span><span class="sxs-lookup"><span data-stu-id="24160-149">This feature is not yet available to customers using Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="24160-150">Pour plus d’informations, reportez-vous à la section [en savoir plus sur Office 365 exploités par 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span><span class="sxs-lookup"><span data-stu-id="24160-150">To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span> 
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="24160-151">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="24160-151">Related topics</span></span>

[<span data-ttu-id="24160-152">Questions fréquentes à propos de l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="24160-152">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="24160-153">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="24160-153">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="24160-154">Numéros de téléphone pour l'audioconférence</span><span class="sxs-lookup"><span data-stu-id="24160-154">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="24160-155">Définir des options pour les réunions en ligne et des conférences téléphoniques</span><span class="sxs-lookup"><span data-stu-id="24160-155">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

