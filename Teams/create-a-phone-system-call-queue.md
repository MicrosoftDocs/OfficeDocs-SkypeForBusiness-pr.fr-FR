---
title: Créer une file d’attente de système téléphonique
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: phans, wasseemh
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
description: Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: 0d9113dfb3380872170d16ae5f657839f099a52a
ms.sourcegitcommit: e378b8652be6319755a04eb820761364c7faa916
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "30222431"
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="c0b74-104">Créer une file d’attente de système téléphonique</span><span class="sxs-lookup"><span data-stu-id="c0b74-104">Create a Phone System call queue</span></span>

<span data-ttu-id="c0b74-105">Appel de système téléphonique files d’attente contiennent le message d’accueil qui est utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la capacité de recherche pour l’agent disponible appel suivant gérer l’appel pendant les personnes qui appel Écoutez une musique d’attente.</span><span class="sxs-lookup"><span data-stu-id="c0b74-105">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="c0b74-106">Vous pouvez créer une seule ligne ou plusieurs files d’attente d’appel pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c0b74-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="c0b74-107">Les files d’attente des systèmes téléphoniques peuvent fournir :</span><span class="sxs-lookup"><span data-stu-id="c0b74-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="c0b74-108">Un message d'accueil pour l'organisation</span><span class="sxs-lookup"><span data-stu-id="c0b74-108">An organizational greeting.</span></span>
- <span data-ttu-id="c0b74-109">Une attente musicale</span><span class="sxs-lookup"><span data-stu-id="c0b74-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="c0b74-110">Redirection d’appels pour appeler les agents dans les groupes de sécurité et les listes de distribution à extension messagerie.</span><span class="sxs-lookup"><span data-stu-id="c0b74-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="c0b74-111">Définir des paramètres pour la taille maximale de file d’attente appel, délai d’expiration et options de gestion des appels.</span><span class="sxs-lookup"><span data-stu-id="c0b74-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="c0b74-112">Lorsqu’une personne appelle un numéro de téléphone qui est associé à une file d’attente des appels par le biais d’un [compte de ressource](manage-resource-accounts.md), elles seront entendre un message d’accueil premier (si une est configuré), puis ils sera placée dans la file d’attente et attendre le prochain agent appel disponible.</span><span class="sxs-lookup"><span data-stu-id="c0b74-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="c0b74-113">La personne qui entendront musique pendant qu’ils sont mis en attente en attente et les appels seront proposés aux agents appel par ordre *First In, First Out* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="c0b74-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="c0b74-114">Tous les appels en attente dans la file d’attente seront distribués à l’aide d’un mode de routage standard ou le mode de routage en série :</span><span class="sxs-lookup"><span data-stu-id="c0b74-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="c0b74-115">Avec le routage standard, le premier appel dans la file d’attente sonnera tous les agents en même temps.</span><span class="sxs-lookup"><span data-stu-id="c0b74-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="c0b74-116">Avec le routage en série, le premier appel dans la file d’attente sonnera chez tous les téléopérateurs un à un.</span><span class="sxs-lookup"><span data-stu-id="c0b74-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0b74-117">Les téléopérateurs qui sont **déconnectés**, ont défini leur présence sur **Ne pas déranger,** ou ont désactivé la file d’attente ne seront pas appelés.</span><span class="sxs-lookup"><span data-stu-id="c0b74-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="c0b74-118">Une seule notification d'appel entrant (pour l'appel en tête de file) sera envoyée aux téléopérateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="c0b74-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="c0b74-119">Lorsqu'un téléopérateur accepte l'appel, le prochain appel entrant dans la file d'attente sonnera pour les autres téléopérateurs.</span><span class="sxs-lookup"><span data-stu-id="c0b74-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="c0b74-120">Cet article s’applique à Microsoft Teams et Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="c0b74-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---getting-started"></a><span data-ttu-id="c0b74-121">Étape 1 : prise en main</span><span class="sxs-lookup"><span data-stu-id="c0b74-121">Step 1 - Getting started</span></span>

<span data-ttu-id="c0b74-122">Avant de commencer à utiliser les files d'attente d'appels, il est impératif de noter les points suivants :</span><span class="sxs-lookup"><span data-stu-id="c0b74-122">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="c0b74-123">Votre organisation doit avoir (au minimum), une licence entreprise E3 plus **Système téléphonique** ou une licence Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="c0b74-123">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="c0b74-124">Le nombre de licences utilisateur **Système téléphonique** qui sont assignés affecte le nombre de numéros de service qui sont disponibles pour être utilisés pour les files d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-124">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues.</span></span> <span data-ttu-id="c0b74-125">Le nombre de files d’attente de l’appel que peut avoir est varie selon le nombre de licences **Système téléphonique** et de **Conférence** qui sont assignés au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c0b74-125">The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="c0b74-126">Pour plus d’informations sur les licences, voir [Skype pour les licences d’entreprise et les équipes Microsoft module complémentaire](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c0b74-126">To learn more about licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0b74-127">Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou Office 365 appelant Plans.</span><span class="sxs-lookup"><span data-stu-id="c0b74-127">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="c0b74-128">Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c0b74-128">See  [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="c0b74-129">Pour les activer pour Entreprise Voice, vous pouvez utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0b74-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c0b74-130">Par exemple, exécutez : `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c0b74-130">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="c0b74-131">Pour en savoir plus sur Plans d'Appels Office 365, voir [Quels sont les forfaits d’appels dans Office 365 ?](what-are-calling-plans-in-office-365.md) et [Forfaits d'appels pour Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c0b74-131">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](what-are-calling-plans-in-office-365.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0b74-132">Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge comme une file d’attente d’appel Agents.</span><span class="sxs-lookup"><span data-stu-id="c0b74-132">Users hosted on-premises using Lync Server 2010 aren't supported as a call queue Agents.</span></span>
  
- <span data-ttu-id="c0b74-133">Vous pouvez uniquement attribuer payants et les numéros de téléphone gratuit service que vous avez obtenu dans le **Centre d’administration de Microsoft équipes** ou transférés à partir d’un autre fournisseur de services aux files d’attente des appels système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="c0b74-133">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Phone System call queues.</span></span> <span data-ttu-id="c0b74-134">Pour obtenir et utiliser les numéros de services gratuits, vous devez configurer les crédits de communication.</span><span class="sxs-lookup"><span data-stu-id="c0b74-134">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0b74-135">Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués à des files d'attente. Seuls les numéros de téléphone gratuits et payants peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="c0b74-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="c0b74-136">Lorsque vous distribuez les appels entrants à partir d’une file d’attente des appels système téléphonique, ces clients sont pris en charge pour les agents d’appel :</span><span class="sxs-lookup"><span data-stu-id="c0b74-136">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="c0b74-137">Client de bureau Skype Entreprise 2016 (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c0b74-137">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="c0b74-138">Client de bureau Lync 2013 (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c0b74-138">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="c0b74-139">Tous les modèles de téléphone IP pris en charge pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c0b74-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="c0b74-140">Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="c0b74-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>

  - <span data-ttu-id="c0b74-141">Client Mac Skype Entreprise (version 16.8.196 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="c0b74-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="c0b74-142">Client Android Skype Entreprise (version 6.16.0.9 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="c0b74-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="c0b74-143">Client iPhone Skype Entreprise (version 6.16.0 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="c0b74-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c0b74-144">Client Mac Skype Entreprise (version 6.16.0 et ultérieures)</span><span class="sxs-lookup"><span data-stu-id="c0b74-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c0b74-145">Client Microsoft Teams Windows (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c0b74-145">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="c0b74-146">Client Mac Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0b74-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="c0b74-147">Application iPhone Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0b74-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="c0b74-148">Application Android Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0b74-148">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="c0b74-149">Étape 2 : obtention ou transfert de numéros de service gratuits ou payants</span><span class="sxs-lookup"><span data-stu-id="c0b74-149">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="c0b74-150">Avant de pouvoir créer et configurer les files d'attente, vous devrez transférer vos numéros payants et gratuits existants.</span><span class="sxs-lookup"><span data-stu-id="c0b74-150">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="c0b74-151">Une fois que vous obtenez les numéros de téléphone gratuit service payant, ils s’affichent dans le **Centre d’administration de Microsoft équipes** > **vocale** > **numéros de téléphone**et la volonté de **type numérique** présent figurer en tant que **Service - gratuit**.</span><span class="sxs-lookup"><span data-stu-id="c0b74-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="c0b74-152">Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) , ou si vous souhaitez transférer un numéro de service existant, voir les [numéros de téléphone transfert vers Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c0b74-152">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0b74-153">Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration Microsoft Teams pour obtenir les numéros de service.</span><span class="sxs-lookup"><span data-stu-id="c0b74-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="c0b74-154">Accédez à [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire à partir de l’extérieur des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="c0b74-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="c0b74-155">Si vous configurez également les standards automatiques, vous devrez uniquement affecter un numéro de téléphone pour le compte du service de surveillance automatique principal de la ressource, puis d’appelants directs à votre file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-155">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="c0b74-156">Si tel est le cas, la file d’attente d’appel vous devrez être créé avant de pouvoir créer une option dans le standard automatique de sélectionne la file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-156">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="c0b74-157">Étape 3 : créer une nouvelle file d’attente d’appel</span><span class="sxs-lookup"><span data-stu-id="c0b74-157">Step 3 - Create a new call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0b74-158">Chaque file d’attente de l’appel doit posséder un [compte de ressource](manage-resource-accounts.md)associé.</span><span class="sxs-lookup"><span data-stu-id="c0b74-158">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="c0b74-159">Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer à la file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-159">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c0b74-160">À l’aide du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0b74-160">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c0b74-161">Dans le **Centre d’administration de Microsoft équipes**, **voix** >  **files d’attente des appels**, puis cliquez sur **+ Nouveau**:</span><span class="sxs-lookup"><span data-stu-id="c0b74-161">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="c0b74-162">Définir le complet de file d’attente appel qu’un compte nom et des ressources</span><span class="sxs-lookup"><span data-stu-id="c0b74-162">Set the call queue display name and resource account</span></span>

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="c0b74-164">![N ° 1](media/sfbcallout1.png)
**nom** Entrez un nom d’affichage de la description de la file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-164">![Number 1](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="c0b74-165">Le nom est obligatoire et peut contenir jusqu'à 64 caractères, espaces compris.</span><span class="sxs-lookup"><span data-stu-id="c0b74-165">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="c0b74-166">Ce nom sera affiché dans la notification de l'appel entrant.</span><span class="sxs-lookup"><span data-stu-id="c0b74-166">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="c0b74-168">**Ajouter des comptes** Sélectionnez un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="c0b74-168">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="c0b74-169">Le compte de la ressource peut être ou non associé à un numéro payant service ou le numéro de téléphone gratuit pour la file d’attente de l’appel, mais chaque file d’attente d’appel requiert un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="c0b74-169">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="c0b74-170">Si il n’existe pas dans la liste, vous devez obtenir les numéros de service et les affecter à un compte de ressource avant de pouvoir créer cette file d’attente de l’appel, comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="c0b74-170">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="c0b74-171">Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="c0b74-171">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> <span data-ttu-id="c0b74-172">Vous devez créer un compte de ressource, comme décrit dans [Gérer les comptes de ressources dans les équipes](manage-resource-accounts.md) si vous souhaitez que votre file d’attente de l’appel vers un numéro de téléphone associé.</span><span class="sxs-lookup"><span data-stu-id="c0b74-172">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="c0b74-173">Si vous souhaitez ou que vous devez lui assigner un **domaine** ferait en l’affectant au compte de ressources pour la file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-173">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="c0b74-174">Définir le message d'accueil et la musique lue pendant la mise en attente</span><span class="sxs-lookup"><span data-stu-id="c0b74-174">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="c0b74-177">Le **message d'accueil** est facultatif.</span><span class="sxs-lookup"><span data-stu-id="c0b74-177">**Greeting** is optional.</span></span> <span data-ttu-id="c0b74-178">Il s’agit du message d’accueil qui est diffusé aux utilisateurs d’appel dans le nombre de file d’attente d’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-178">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="c0b74-179">Vous pouvez télécharger un fichier audio (format .wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="c0b74-179">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="c0b74-181">**Musicale** Vous pouvez utiliser la musique par défaut en attente fournie avec la file d’attente de l’appel, ou vous pouvez télécharger un fichier audio .wav ou .wma mp3 formats à utiliser en tant que votre musique personnalisée en attente.</span><span class="sxs-lookup"><span data-stu-id="c0b74-181">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="c0b74-182">Sélectionnez l’options de répondeur automatique</span><span class="sxs-lookup"><span data-stu-id="c0b74-182">Select the call answering options</span></span>

![Indique les options de méthodes de distribution d'appel](media/5d249515-d532-4af2-90da-011404028b89.png)

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="c0b74-185">Vous pouvez sélectionner jusqu'à 200 agents appel appartenant à des listes de diffusion spécifiées ou des groupes.</span><span class="sxs-lookup"><span data-stu-id="c0b74-185">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="c0b74-186">Agents d’appel doivent être :</span><span class="sxs-lookup"><span data-stu-id="c0b74-186">Call agents must be either:</span></span>

- <span data-ttu-id="c0b74-187">Un utilisateur en ligne avec une licence de **Système téléphonique** et enregistré pour Enterprise Voice ou avec un forfait d'appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-187">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c0b74-188">Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou un Plan de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-188">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="c0b74-189">Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c0b74-189">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="c0b74-190">Pour les activer pour Entreprise Voice, vous pouvez utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0b74-190">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c0b74-191">Par exemple, exécutez : `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c0b74-191">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="c0b74-192">Les utilisateurs en ligne avec une licence de **Système téléphonique** et un forfait d’appels qui sont ajoutés à un groupe Office 365, une liste de distribution avec messagerie activée, ou un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="c0b74-192">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="c0b74-193">Jusqu'à 30 minutes peuvent être nécessaires pour qu'un nouvel agent ajouté à une liste de distribution ou à un groupe de sécurité commence à recevoir des appels depuis une file d'attente.</span><span class="sxs-lookup"><span data-stu-id="c0b74-193">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="c0b74-194">Un groupe de sécurité ou de la liste de distribution nouvellement créé peut prendre jusqu'à 48 heures soit disponible pour être utilisé avec les files d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-194">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="c0b74-195">Les groupes Office 365 nouvellement créés sont presqu'immédiatement disponibles.</span><span class="sxs-lookup"><span data-stu-id="c0b74-195">Newly created Office 365 Groups are available almost immediately.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c0b74-196">Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c0b74-196">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="c0b74-199">**Méthode de routage** Vous pouvez choisir soit **Attendant**, **série**ou **tourniquet (Round Robin)** pour la méthode de distribution en file d’attente de votre appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-199">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="c0b74-200">Toutes les files d’attente d'appels nouvelles et existantes seront réglés par défaut sur le routage à la chaîne.</span><span class="sxs-lookup"><span data-stu-id="c0b74-200">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="c0b74-201">Lorsque le routage standard est utilisé, le premier appel dans la file d’attente tous les agents appel sonnera en même temps.</span><span class="sxs-lookup"><span data-stu-id="c0b74-201">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="c0b74-202">Le premier agent d’appel pour identifier l’appel Obtient l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-202">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="c0b74-203">**Surveillance du routage** entraîne le premier appel dans la file d’attente pour faire sonner tous les agents d’appel en même temps.</span><span class="sxs-lookup"><span data-stu-id="c0b74-203">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="c0b74-204">Le premier agent d’appel pour identifier l’appel Obtient l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-204">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="c0b74-205">**Le routage de série** entraîne les appels entrants vers la sonnerie d’appel agents un par un, à partir du début de la liste d’appels de l’agent.</span><span class="sxs-lookup"><span data-stu-id="c0b74-205">**Serial routing** causes incoming calls to ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="c0b74-206">Si un agent manque ou ne décroche pas un appel, l’appel sonnera chez l’agent suivant dans la liste et tentera tous les agents un à un jusqu'à ce qu’il soit décroché ou que le délai d’attente s'épuise.</span><span class="sxs-lookup"><span data-stu-id="c0b74-206">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c0b74-207">Ce type de routage passera les agents qui sont **déconnectés**, qui ont réglé leur présence sur **Ne pas déranger** ou ont choisi d'être **exclus** de la réception d'appels depuis cette file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c0b74-207">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="c0b74-208">**Round robin** répartit le routage des appels entrants afin que chaque agent appel le même nombre d’appels à partir de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="c0b74-208">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="c0b74-209">Cela peut être très souhaitable dans un environnement de vente entrant afin de garantir l’opportunité égale entre tous les agents de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-209">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="c0b74-210">Sélectionner une option d'exclusion d'agent</span><span class="sxs-lookup"><span data-stu-id="c0b74-210">Select an agent opt out option</span></span>

![Montre la case à cocher d'exclusion de l’agent](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="c0b74-213">**Option d'exclusion d'agent** Vous pouvez choisir d’autoriser les téléopérateurs à refuser de prendre des appels à partir d’une file d’attente spécifique en sélectionnant **Option d'exclusion d'agent**.</span><span class="sxs-lookup"><span data-stu-id="c0b74-213">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="c0b74-214">L’activation de cette option permet de seront tous les agents de cette file d’attente pour démarrer ou arrêter de recevoir des appels à partir de cette file d’attente de l’appel à.</span><span class="sxs-lookup"><span data-stu-id="c0b74-214">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="c0b74-215">Vous pouvez révoquer le privilège d’exclusion d'agent à tout moment en désactivant la case à cocher, grâce à laquelle les agents sont automatiquement accrédités à nouveau pour cette file d’attente (paramètre par défaut pour tous les agents).</span><span class="sxs-lookup"><span data-stu-id="c0b74-215">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="c0b74-216">Pour accéder à l’option d'exclusion, les agents peuvent procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="c0b74-216">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="c0b74-217">Ouvrir **Options** dans leur client Skype Entreprise de bureau.</span><span class="sxs-lookup"><span data-stu-id="c0b74-217">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="c0b74-218">Sous l’onglet **Renvoi d’appel**, cliquer sur le lien **Modifier les paramètres en ligne**.</span><span class="sxs-lookup"><span data-stu-id="c0b74-218">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="c0b74-219">Dans la page de paramètres utilisateur, cliquer sur **Files d’attente d'appels**, puis désactiver les cases à cocher des files d’attente desquelles ils souhaitent être exclus.</span><span class="sxs-lookup"><span data-stu-id="c0b74-219">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0b74-220">Les agents utilisant les clients Mac, mobile, ou Lync 2013, ou les utilisateurs Hybrid Voice qui sont hébergés localement à l’aide du serveur Skype Entreprise 2015, peuvent aller à [https://aka.ms/cqsettings](https://aka.ms/cqsettings) pour accéder à l’option d'exclusion.</span><span class="sxs-lookup"><span data-stu-id="c0b74-220">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>

<span data-ttu-id="c0b74-221">![N ° 2](media/sfbcallout2.png)
**paramètre d’alerte de l’Agent**</span><span class="sxs-lookup"><span data-stu-id="c0b74-221">![Number 2](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="c0b74-222">Définit la durée d’un agent être averti d’un appel avant le numéro de série ou tourniquet (Round Robin) des méthodes de routage déplacement vers l’agent suivant.</span><span class="sxs-lookup"><span data-stu-id="c0b74-222">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="c0b74-223">Le paramètre par défaut est de 30 secondes, mais elle peut être définie pour 3 minutes.</span><span class="sxs-lookup"><span data-stu-id="c0b74-223">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="c0b74-224">Définir des options de gestion de l’appel de dépassement de capacité et délai d’expiration</span><span class="sxs-lookup"><span data-stu-id="c0b74-224">Set the call overflow and timeout handling options</span></span>

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="c0b74-227">**Nombre d'appels maximal dans la file d'attente** Utilisez cette valeur pour définir le nombre d'appels maximal qu'il peut y avoir simultanément dans la file d'attente.</span><span class="sxs-lookup"><span data-stu-id="c0b74-227">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="c0b74-228">La valeur par défaut est 50, mais elle compris entre 0 et 200.</span><span class="sxs-lookup"><span data-stu-id="c0b74-228">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="c0b74-229">Lorsque la limite est atteinte, l'appel sera traité de la manière définie par le paramètre **Lorsque la limite maximale du nombre d'appels est atteinte** ci-après.</span><span class="sxs-lookup"><span data-stu-id="c0b74-229">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="c0b74-231">**Lorsque le nombre maximal d’appels est atteint.** Lorsque la file d’attente d’appels atteint sa taille maximale (définie à l’aide de la valeur **maximale des appels dans la file d’attente** ), vous pouvez choisir que se passe-t-il au nouvel appel entrant.</span><span class="sxs-lookup"><span data-stu-id="c0b74-231">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="c0b74-232">**Déconnecter** L'appel sera déconnecté.</span><span class="sxs-lookup"><span data-stu-id="c0b74-232">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="c0b74-233">**Rediriger vers** Lorsque vous choisissez cette option, sélectionnez une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0b74-233">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="c0b74-234">**Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent un Plan de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-234">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="c0b74-235">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="c0b74-235">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="c0b74-236">Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="c0b74-236">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c0b74-237">Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [Configurer le système téléphonique de la messagerie vocale](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c0b74-237">To learn about licensing required for voicemail, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>

    > [!Note]
    > <span data-ttu-id="c0b74-238">Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c0b74-238">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>
  - <span data-ttu-id="c0b74-239">**Application vocale** Sélectionnez le nom de l’une file d’attente de l’appel ou qui a déjà été créée standard automatique.</span><span class="sxs-lookup"><span data-stu-id="c0b74-239">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Nombre 3](media/sfbcallout3.png)

<span data-ttu-id="c0b74-241">**Délai d’attente des appels : temps d’attente maximal** Vous pouvez également choisir combien de temps un appel peut être en attente dans la file d’attente avant qu’il arrive à expiration et doit être redirigé ou déconnecté.</span><span class="sxs-lookup"><span data-stu-id="c0b74-241">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="c0b74-242">La destination de redirection est basée sur la définition du paramètre **Lorsqu'un appel expire**.</span><span class="sxs-lookup"><span data-stu-id="c0b74-242">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="c0b74-243">Le délai peut être défini entre 0 et 45 minutes.</span><span class="sxs-lookup"><span data-stu-id="c0b74-243">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="c0b74-244">La valeur du délai d’attente peut être réglée en secondes, par intervalles de 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="c0b74-244">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="c0b74-245">Cela vous permet de manipuler le flux des appels avec une granularité plus fine.</span><span class="sxs-lookup"><span data-stu-id="c0b74-245">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="c0b74-246">Par exemple, vous pouvez spécifier que tous les appels qui sont sans réponse dans les 30 secondes par un agent d’accéder à un standard automatique de recherche dans l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="c0b74-246">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Numéro 4](media/sfbcallout4.png)

<span data-ttu-id="c0b74-248">**Lorsque le délai d’attente expire** Lorsque l’appel atteint la limite que vous définissez le paramètre de **la durée pendant laquelle un appel peut attendre dans la file d’attente** , vous pouvez choisir que se passe-t-il à cet appel :</span><span class="sxs-lookup"><span data-stu-id="c0b74-248">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="c0b74-249">**Déconnecter** L'appel sera déconnecté.</span><span class="sxs-lookup"><span data-stu-id="c0b74-249">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="c0b74-250">**Cet appel de redirection** Lorsque vous choisissez cette option, vous devez ces options :</span><span class="sxs-lookup"><span data-stu-id="c0b74-250">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="c0b74-251">**Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent des Plans de l’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-251">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="c0b74-252">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="c0b74-252">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="c0b74-253">Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="c0b74-253">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c0b74-254">Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [Configurer le système téléphonique de la messagerie vocale](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c0b74-254">To learn about licensing required for voicemail, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>

    > [!Note]
    > <span data-ttu-id="c0b74-255">Les utilisateurs hébergés sur site à l’aide de Lync Server 2010 ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c0b74-255">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>

  - <span data-ttu-id="c0b74-256">**Application vocale** Sélectionnez le nom de l’une file d’attente de l’appel ou qui a déjà été créée standard automatique.</span><span class="sxs-lookup"><span data-stu-id="c0b74-256">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="c0b74-257">Modification des ID de l’appelant d’un utilisateur pour qu’il soit le numéro de téléphone d’un appel de la file d’attente</span><span class="sxs-lookup"><span data-stu-id="c0b74-257">Changing a user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="c0b74-258">Vous pouvez protéger l’identité d’un utilisateur en créant une stratégie utilisant la commande d'applet **New-CallingLineIdentity**, plutôt qu'en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appel.</span><span class="sxs-lookup"><span data-stu-id="c0b74-258">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="c0b74-259">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c0b74-259">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="c0b74-260">Ensuite, appliquez la stratégie à l’utilisateur à l’aide de l’applet de commande **Grant-CallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="c0b74-260">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="c0b74-261">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c0b74-261">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="c0b74-262">Vous pouvez obtenir plus d’informations sur la façon d’apporter des modifications aux paramètres d’ID de l’appelant dans votre organisation dans l’article [ID d’appelant utilisation dans votre organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c0b74-262">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="c0b74-263">Vous souhaitez en savoir plus ?</span><span class="sxs-lookup"><span data-stu-id="c0b74-263">Want to know more?</span></span>

<span data-ttu-id="c0b74-264">Vous pouvez également utiliser PowerShell Windows pour créer et configurer des files d'attente.</span><span class="sxs-lookup"><span data-stu-id="c0b74-264">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="c0b74-265">Applets de commande de file d'attente d'appels</span><span class="sxs-lookup"><span data-stu-id="c0b74-265">Call queue cmdlets</span></span>

<span data-ttu-id="c0b74-266">Voici les applets de commande requis pour gérer une file d'attente d'appels.</span><span class="sxs-lookup"><span data-stu-id="c0b74-266">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="c0b74-267">Nouvelle-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="c0b74-267">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)

- [<span data-ttu-id="c0b74-268">Configurer-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="c0b74-268">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)

- [<span data-ttu-id="c0b74-269">Obtenir-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="c0b74-269">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)

- [<span data-ttu-id="c0b74-270">Supprimer-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="c0b74-270">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="c0b74-271">Informations supplémentaires sur PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="c0b74-271">More about Windows PowerShell</span></span>

- <span data-ttu-id="c0b74-272">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="c0b74-272">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c0b74-273">Avec Windows PowerShell, vous pouvez gérer Office 365 et Teams Microsoft à l’aide d’un point unique d’administration qui peut simplifier votre travail quotidien, lorsque vous avez plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="c0b74-273">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c0b74-274">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="c0b74-274">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="c0b74-275">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c0b74-275">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="c0b74-276">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0b74-276">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="c0b74-277">Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Microsoft Teams tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="c0b74-277">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c0b74-278">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="c0b74-278">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="c0b74-279">Gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0b74-279">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="c0b74-280">Configurer votre ordinateur pour Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0b74-280">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="c0b74-281">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c0b74-281">Related topics</span></span>

[<span data-ttu-id="c0b74-282">Voici les avantages du système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="c0b74-282">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c0b74-283">Obtenir des numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="c0b74-283">Getting service phone numbers</span></span>](/Skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="c0b74-284">Disponibilité des forfaits d'appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="c0b74-284">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="c0b74-285">Nouvelle CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c0b74-285">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
