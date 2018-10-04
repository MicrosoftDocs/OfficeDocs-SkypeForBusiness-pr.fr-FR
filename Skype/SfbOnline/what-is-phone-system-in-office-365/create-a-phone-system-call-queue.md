---
title: Créer une file d’attente de système téléphonique
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: "Apprenez à configurer le système téléphonique pour les files d'attente d'appels Office 365 (Cloud PBX) afin de recevoir un message d'accueil organisationnel, de la musique d'attente et une redirection des appels vers des téléopérateurs dans des listes de distribution et des groupes de sécurité. Vous pouvez également définir la taille maximale de la file d'attente, le délai d'attente et les options de gestion des appels. "
ms.openlocfilehash: 1952d6d180f5b9662b1e598ceb9d0b8d230640c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375148"
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="951fe-104">Créer une file d’attente de système téléphonique</span><span class="sxs-lookup"><span data-stu-id="951fe-104">Create a Phone System call queue</span></span>

<span data-ttu-id="951fe-p102">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span><span class="sxs-lookup"><span data-stu-id="951fe-p102">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="951fe-107">Les files d’attente des systèmes téléphoniques peuvent fournir :</span><span class="sxs-lookup"><span data-stu-id="951fe-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="951fe-108">Un message d'accueil pour l'organisation</span><span class="sxs-lookup"><span data-stu-id="951fe-108">An organizational greeting.</span></span>
    
- <span data-ttu-id="951fe-109">Une attente musicale</span><span class="sxs-lookup"><span data-stu-id="951fe-109">Music while people are waiting on hold.</span></span>
    
- <span data-ttu-id="951fe-110">Redirection d’appels pour appeler les agents dans les groupes de sécurité et les listes de distribution à extension messagerie.</span><span class="sxs-lookup"><span data-stu-id="951fe-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
    
- <span data-ttu-id="951fe-111">Définir des paramètres pour la taille maximale de file d’attente appel, délai d’expiration et options de gestion des appels.</span><span class="sxs-lookup"><span data-stu-id="951fe-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>
    
<span data-ttu-id="951fe-p103">When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.</span><span class="sxs-lookup"><span data-stu-id="951fe-p103">When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.</span></span>
  
<span data-ttu-id="951fe-114">Tous les appels en attente dans la file d’attente seront distribués à l’aide d’un mode de routage standard ou le mode de routage en série :</span><span class="sxs-lookup"><span data-stu-id="951fe-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="951fe-115">Avec le routage standard, le premier appel dans la file d’attente sonnera tous les agents en même temps.</span><span class="sxs-lookup"><span data-stu-id="951fe-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
    
- <span data-ttu-id="951fe-116">Avec le routage en série, le premier appel dans la file d’attente sonnera chez tous les téléopérateurs un à un.</span><span class="sxs-lookup"><span data-stu-id="951fe-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="951fe-117">Les téléopérateurs qui sont **déconnectés**, ont défini leur présence sur **Ne pas déranger,** ou ont désactivé la file d’attente ne seront pas appelés.</span><span class="sxs-lookup"><span data-stu-id="951fe-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="951fe-118">Une seule notification d'appel entrant (pour l'appel en tête de file) sera envoyée aux téléopérateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="951fe-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
    
- <span data-ttu-id="951fe-119">Lorsqu'un téléopérateur accepte l'appel, le prochain appel entrant dans la file d'attente sonnera pour les autres téléopérateurs.</span><span class="sxs-lookup"><span data-stu-id="951fe-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>
    
## <a name="step-1---getting-started"></a><span data-ttu-id="951fe-120">Étape 1 : prise en main</span><span class="sxs-lookup"><span data-stu-id="951fe-120">Step 1 - Getting started</span></span>

<span data-ttu-id="951fe-121">Avant de commencer à utiliser les files d'attente d'appels, il est impératif de noter les points suivants :</span><span class="sxs-lookup"><span data-stu-id="951fe-121">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="951fe-p104">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="951fe-p104">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="951fe-p105">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="951fe-p105">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="951fe-130">Pour en savoir plus sur Plans d'Appels Office 365, voir [Quels sont les forfaits d’appels dans Office 365 ?](/microsoftteams/what-are-calling-plans-in-office-365) et [Forfaits d'appels pour Office 365](/microsoftteams/calling-plans-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="951fe-130">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) and [Calling Plans for Office 365](/microsoftteams/calling-plans-for-office-365).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="951fe-131">Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge en tant que des Agents de file d’attente des appels.</span><span class="sxs-lookup"><span data-stu-id="951fe-131">Users hosted on-premises using Lync Server 2010 aren't supported as a Call Queue Agents.</span></span> 
  
- <span data-ttu-id="951fe-p106">You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.</span><span class="sxs-lookup"><span data-stu-id="951fe-p106">You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="951fe-134">Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des files d'attente. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="951fe-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span> 
  
- <span data-ttu-id="951fe-135">Lorsque vous distribuez les appels entrants à partir d’une file d’attente des appels système téléphonique, ces clients sont pris en charge pour les agents d’appel :</span><span class="sxs-lookup"><span data-stu-id="951fe-135">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>
    
  - <span data-ttu-id="951fe-136">Client de bureau Skype Entreprise 2016 (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="951fe-136">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="951fe-137">Client de bureau Lync 2013 (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="951fe-137">Lync desktop client 2013 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="951fe-p107">All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="951fe-p107">All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>
    
  - <span data-ttu-id="951fe-140">Client Mac Skype Entreprise (version 16.8.196 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="951fe-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span> 
    
  - <span data-ttu-id="951fe-141">Client Android Skype Entreprise (version 6.16.0.9 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="951fe-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
    
  - <span data-ttu-id="951fe-142">Client iPhone Skype Entreprise (version 6.16.0 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="951fe-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
    
  - <span data-ttu-id="951fe-143">Client Mac Skype Entreprise (version 6.16.0 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="951fe-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="951fe-144">Client Microsoft Teams Windows (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="951fe-144">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="951fe-145">Client Mac Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="951fe-145">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="951fe-146">Application iPhone Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="951fe-146">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="951fe-147">Application Android Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="951fe-147">Microsoft Teams Android app</span></span>
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="951fe-148">Étape 2 : obtention ou transfert de numéros de service gratuits ou payants</span><span class="sxs-lookup"><span data-stu-id="951fe-148">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="951fe-p108">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="951fe-p108">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>
  
> [!NOTE]
> <span data-ttu-id="951fe-p109">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span><span class="sxs-lookup"><span data-stu-id="951fe-p109">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="951fe-154">Étape 3 : création d'une file d'attente d'appels</span><span class="sxs-lookup"><span data-stu-id="951fe-154">Step 3 - Create a new Call Queue</span></span>

<span data-ttu-id="951fe-155">![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**</span><span class="sxs-lookup"><span data-stu-id="951fe-155">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="951fe-156">Dans le **Centre d'administration de Skype Entreprise**, cliquez sur **Routage des appels** > **Files d'attente d'appels**, puis cliquez sur **Ajouter nouveau**:</span><span class="sxs-lookup"><span data-stu-id="951fe-156">In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:</span></span>
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a><span data-ttu-id="951fe-157">Définissez le nom d'affichage de la file d'attente, un numéro de téléphone et un domaine (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="951fe-157">Set the call queue display name, phone number and domain (if any)</span></span>

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
<span data-ttu-id="951fe-159">![Numéro 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="951fe-159">![Number 1](../images/sfbcallout1.png)</span></span><br/>
<span data-ttu-id="951fe-p110">**Nom** Entrez un nom d'affichage descriptif pour la file d'attente d'appels. Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris.</span><span class="sxs-lookup"><span data-stu-id="951fe-p110">**Name** Enter a descriptive display name for the call queue. This is required and can contain up to 64 characters, including spaces. </span></span><br/> <span data-ttu-id="951fe-162">Ce nom sera affiché dans la notification de l'appel entrant.</span><span class="sxs-lookup"><span data-stu-id="951fe-162">This name will be displayed in the notification for the incoming call.</span></span>
***
<span data-ttu-id="951fe-163">![Numéro 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="951fe-163">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="951fe-p111">**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. </span><span class="sxs-lookup"><span data-stu-id="951fe-p111">**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. </span></span><br/> <span data-ttu-id="951fe-p112">If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="951fe-p112">If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)</span></span>
***
<span data-ttu-id="951fe-168">![Numéro 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="951fe-168">![Number 3](../images/sfbcallout3.png)</span></span><br/><span data-ttu-id="951fe-p113">**Domaine** S'il est disponible, sélectionnez le domaine Office 365 que vous souhaitez utiliser. Ce champ sera uniquement disponible si vous disposez de plusieurs domaine utilisés avec Office 365. Si c'est le cas, vous devez choisir le nom de domaine dans la liste. </span><span class="sxs-lookup"><span data-stu-id="951fe-p113">**Domain** If this is available, choose the Office 365 domain you want to use. This is only available if you have more than one domain being used with Office 365. If you have more than one, you must chose the domain name from the list. </span></span><br/> <span data-ttu-id="951fe-172">Par exemple, le domaine peut se présenter comme suit :  _contoso.com or redmond.contoso.com_</span><span class="sxs-lookup"><span data-stu-id="951fe-172">For example, you could have a domain like:  _contoso.com or redmond.contoso.com_</span></span>
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="951fe-173">Définir le message d'accueil et la musique lue pendant la mise en attente</span><span class="sxs-lookup"><span data-stu-id="951fe-173">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
<span data-ttu-id="951fe-175">![Numéro 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="951fe-175">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="951fe-p114">**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. </span><span class="sxs-lookup"><span data-stu-id="951fe-p114">**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. </span></span><br/> <span data-ttu-id="951fe-178">Vous pouvez télécharger un fichier audio (format .wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="951fe-178">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>
***
<span data-ttu-id="951fe-179">![Numéro 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="951fe-179">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="951fe-180">**Musicale** Vous pouvez utiliser la musique par défaut en attente fournie avec la file d’attente de l’appel, ou vous pouvez télécharger un fichier audio .wav ou .wma mp3 formats à utiliser en tant que votre musique personnalisée en attente.</span><span class="sxs-lookup"><span data-stu-id="951fe-180">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span> 
   

### <a name="select-the-call-distribution-method"></a><span data-ttu-id="951fe-181">Sélectionner la méthode de distribution d’appel</span><span class="sxs-lookup"><span data-stu-id="951fe-181">Select the call distribution method</span></span>

![Indique les options de méthodes de distribution d'appel](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
<span data-ttu-id="951fe-183">![Numéro 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="951fe-183">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="951fe-p115">**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. </span><span class="sxs-lookup"><span data-stu-id="951fe-p115">**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. </span></span><br/><br/> <span data-ttu-id="951fe-p116">When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span><span class="sxs-lookup"><span data-stu-id="951fe-p116">When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>   

> [!NOTE]
> <span data-ttu-id="951fe-189">Ce type de routage passera les agents qui sont **déconnectés**, qui ont réglé leur présence sur **Ne pas déranger** ou ont choisi d'être **exclus** de la réception d'appels depuis cette file d’attente.</span><span class="sxs-lookup"><span data-stu-id="951fe-189">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span> 
   
### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="951fe-190">Sélectionner une option d'exclusion d'agent</span><span class="sxs-lookup"><span data-stu-id="951fe-190">Select an agent opt out option</span></span>

![Montre la case à cocher d'exclusion de l’agent](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
<span data-ttu-id="951fe-192">![Numéro 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="951fe-192">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="951fe-193">**Option d'exclusion d'agent** Vous pouvez choisir d’autoriser les téléopérateurs à refuser de prendre des appels à partir d’une file d’attente spécifique en sélectionnant **Option d'exclusion d'agent**.</span><span class="sxs-lookup"><span data-stu-id="951fe-193">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>  <br/> <span data-ttu-id="951fe-p117">Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  </span><span class="sxs-lookup"><span data-stu-id="951fe-p117">Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  </span></span><br/><br/> <span data-ttu-id="951fe-196">Pour accéder à l’option d'exclusion, les agents peuvent procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="951fe-196">To access the opt-out option, agents can do the following:</span></span>
 1. <span data-ttu-id="951fe-197">Ouvrir **Options** dans leur client Skype Entreprise de bureau.</span><span class="sxs-lookup"><span data-stu-id="951fe-197">Open **Options** in their desktop Skype for Business client.</span></span> 
 2. <span data-ttu-id="951fe-198">Sous l’onglet **Renvoi d’appel**, cliquer sur le lien **Modifier les paramètres en ligne**.</span><span class="sxs-lookup"><span data-stu-id="951fe-198">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="951fe-199">Dans la page de paramètres utilisateur, cliquer sur **Files d’attente d'appels**, puis désactiver les cases à cocher des files d’attente desquelles ils souhaitent être exclus.</span><span class="sxs-lookup"><span data-stu-id="951fe-199">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>
 
    > [!NOTE] 
    > <span data-ttu-id="951fe-200">Les agents utilisant les clients Mac, mobile, ou Lync 2013, ou les utilisateurs Hybrid Voice qui sont hébergés localement à l’aide du serveur Skype Entreprise 2015, peuvent aller à [https://aka.ms/cqsettings](https://aka.ms/cqsettings) pour accéder à l’option d'exclusion.</span><span class="sxs-lookup"><span data-stu-id="951fe-200">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>
   
### <a name="add-call-agents-to-a-call-queue"></a><span data-ttu-id="951fe-201">Ajouter des téléopérateurs à une file d'attente d'appels</span><span class="sxs-lookup"><span data-stu-id="951fe-201">Add call agents to a call queue</span></span>

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Numéro 1](../images/sfbcallout1.png)<br/><br/><span data-ttu-id="951fe-204">Les téléopérateurs (50 maximum) peuvent être :</span><span class="sxs-lookup"><span data-stu-id="951fe-204">Call agents (50 maximum) can be:</span></span>
* <span data-ttu-id="951fe-205">Un utilisateur en ligne avec une licence de **Système téléphonique** et enregistré pour Enterprise Voice ou avec un forfait d'appel.</span><span class="sxs-lookup"><span data-stu-id="951fe-205">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span> <br/><br/> <span data-ttu-id="951fe-p118">**Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="951fe-p118">**Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span> <br/><br/>
* <span data-ttu-id="951fe-p119">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. </span><span class="sxs-lookup"><span data-stu-id="951fe-p119">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. </span></span><br/> 

  > [!NOTE] 
  > <span data-ttu-id="951fe-214">Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="951fe-214">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a><span data-ttu-id="951fe-215">Définir la taille maximale de la file d'attente et la durée maximale d'attente</span><span class="sxs-lookup"><span data-stu-id="951fe-215">Set the maximum queue size and maximum wait time</span></span>

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
<span data-ttu-id="951fe-217">![Numéro 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="951fe-217">![Number 1](../images/sfbcallout1.png)</span></span><br/><br/><span data-ttu-id="951fe-p120">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span><span class="sxs-lookup"><span data-stu-id="951fe-p120">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>
***
<span data-ttu-id="951fe-220">![Numéro 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="951fe-220">![Number 2](../images/sfbcallout2.png)</span></span><br/><br/><span data-ttu-id="951fe-221">**Lorsque le nombre maximal d’appels est atteint.** Lorsque la file d’attente d’appels atteint sa taille maximale (définie à l’aide de la valeur **maximale des appels dans la file d’attente** ), vous pouvez choisir que se passe-t-il au nouvel appel entrant.</span><span class="sxs-lookup"><span data-stu-id="951fe-221">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>
* <span data-ttu-id="951fe-222">**Déconnexion avec signal Occupé** L'appel sera déconnecté.</span><span class="sxs-lookup"><span data-stu-id="951fe-222">**Disconnect with a busy signal** The call will be disconnected.</span></span>
* <span data-ttu-id="951fe-223">**Transférer cet appel** Lorsque vous choisissez cette option, vous devez ces options :</span><span class="sxs-lookup"><span data-stu-id="951fe-223">**Forward this call to** When you choose this, you will have these options:</span></span>
  * <span data-ttu-id="951fe-p121">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span><span class="sxs-lookup"><span data-stu-id="951fe-p121">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span></span><br/> <br/><span data-ttu-id="951fe-227">Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [Configurer le système téléphonique de la messagerie vocale](/microsoftteams/set-up-phone-system-voicemail).</span><span class="sxs-lookup"><span data-stu-id="951fe-227">To learn about licensing required for voicemail, see [Set up Phone System voicemail](/microsoftteams/set-up-phone-system-voicemail).</span></span> 
     
    > [!Note]
    > <span data-ttu-id="951fe-228">Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="951fe-228">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>
     
  * <span data-ttu-id="951fe-229">**File d’attente des appels** Vous devez avoir déjà créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="951fe-229">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
  * <span data-ttu-id="951fe-p122">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="951fe-p122">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
***
<span data-ttu-id="951fe-232">![Numéro 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="951fe-232">![Number 3](../images/sfbcallout3.png)</span></span><br/><br/><span data-ttu-id="951fe-p123">**Durée d'attente d'un appel dans la file d'attente** Vous pouvez également décider de la durée maximale pendant laquelle un appel peut être mis en attente avant d'expirer ou d'être redirigé. La destination de redirection est basée sur la définition du paramètre **Lorsqu'un appel expire**. Le délai peut être défini entre 0 et 45 minutes. </span><span class="sxs-lookup"><span data-stu-id="951fe-p123">**How long a call can wait in the queue** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected. Where it will be redirected is based on how you set the **When a call times out** setting. You can set a time from 0 to 45 minutes. </span></span><br/><br/> <span data-ttu-id="951fe-p124">The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant.</span><span class="sxs-lookup"><span data-stu-id="951fe-p124">The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant.</span></span> 

***
<span data-ttu-id="951fe-239">![Numéro 4](../images/sfbcallout4.png)</span><span class="sxs-lookup"><span data-stu-id="951fe-239">![Number 4](../images/sfbcallout4.png)</span></span><br/><br/><span data-ttu-id="951fe-240">**Lorsqu'un appel expire** Lorsque l'appel atteint la limite définie par le paramètre **Durée d'attente d'un appel dans la file d'attente**, vous pouvez choisir le traitement ultérieur de l'appel en question :</span><span class="sxs-lookup"><span data-stu-id="951fe-240">**When a call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>
* <span data-ttu-id="951fe-241">**Déconnecter** L'appel sera déconnecté.</span><span class="sxs-lookup"><span data-stu-id="951fe-241">**Disconnect** The call will be disconnected.</span></span>
* <span data-ttu-id="951fe-242">**Transférer cet appel** Lorsque vous choisissez cette option, vous devez ces options :</span><span class="sxs-lookup"><span data-stu-id="951fe-242">**Forward this call to** When you choose this, you will have these options:</span></span>
  * <span data-ttu-id="951fe-p125">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span><span class="sxs-lookup"><span data-stu-id="951fe-p125">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span></span></br><br/>  <span data-ttu-id="951fe-246">Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [Configurer le système téléphonique de la messagerie vocale](/microsoftteams/set-up-phone-system-voicemail).</span><span class="sxs-lookup"><span data-stu-id="951fe-246">To learn about licensing required for voicemail, see [Set up Phone System voicemail](/microsoftteams/set-up-phone-system-voicemail).</span></span> 

    > [!Note]
    > <span data-ttu-id="951fe-247">Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="951fe-247">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>

  * <span data-ttu-id="951fe-248">**File d’attente des appels** Vous devez avoir déjà créé une autre file d’attente d’appel, mais une fois que vous le faites, vous pouvez sélectionner cette file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="951fe-248">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
  * <span data-ttu-id="951fe-p126">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="951fe-p126">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="951fe-251">Modifier l'ID de l’appelant de l’utilisateur pour le transformer en numéro de téléphone de la file d’attente</span><span class="sxs-lookup"><span data-stu-id="951fe-251">Changing the user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="951fe-252">Vous pouvez protéger l’identité d’un utilisateur en créant une stratégie utilisant la commande d'applet **New-CallingLineIdentity**, plutôt qu'en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appel.</span><span class="sxs-lookup"><span data-stu-id="951fe-252">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>
  
<span data-ttu-id="951fe-253">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="951fe-253">To do this, run:</span></span>
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="951fe-p127">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:</span><span class="sxs-lookup"><span data-stu-id="951fe-p127">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:</span></span>
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="951fe-256">Vous pouvez obtenir plus d’informations sur la façon d’apporter des modifications aux paramètres d’identification de l’appelant dans votre organisation [ici](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="951fe-256">You can get more information on how to make changes to caller ID settings in your organization [here](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="951fe-257">Vous souhaitez en savoir plus ?</span><span class="sxs-lookup"><span data-stu-id="951fe-257">Want to know more?</span></span>

<span data-ttu-id="951fe-258">Vous pouvez également utiliser PowerShell Windows pour créer et configurer des files d'attente.</span><span class="sxs-lookup"><span data-stu-id="951fe-258">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="951fe-259">Applets de commande de file d'attente d'appels</span><span class="sxs-lookup"><span data-stu-id="951fe-259">Call queue cmdlets</span></span>

<span data-ttu-id="951fe-260">Voici les applets de commande requis pour gérer une file d'attente d'appels.</span><span class="sxs-lookup"><span data-stu-id="951fe-260">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="951fe-261">Nouvelle-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="951fe-261">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [<span data-ttu-id="951fe-262">Configurer-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="951fe-262">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [<span data-ttu-id="951fe-263">Obtenir-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="951fe-263">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [<span data-ttu-id="951fe-264">Supprimer-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="951fe-264">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a><span data-ttu-id="951fe-265">Informations supplémentaires sur PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="951fe-265">More about Windows PowerShell</span></span>

- <span data-ttu-id="951fe-p128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="951fe-p128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="951fe-269">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="951fe-269">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="951fe-270">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="951fe-270">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="951fe-p129">Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="951fe-p129">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="951fe-273">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="951fe-273">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="951fe-274">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="951fe-274">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="951fe-275">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="951fe-275">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="951fe-276">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="951fe-276">Related topics</span></span>
[<span data-ttu-id="951fe-277">Voici les avantages du système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="951fe-277">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="951fe-278">Obtenir des numéros de téléphone de service pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="951fe-278">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="951fe-279">Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="951fe-279">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
