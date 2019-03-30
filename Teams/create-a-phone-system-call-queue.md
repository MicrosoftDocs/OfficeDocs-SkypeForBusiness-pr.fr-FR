---
title: Créer une file d’attente d’appel
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Découvrez comment configurer le système téléphonique de files d’attente des appels système téléphonique pour vous donner une organisation message d’accueil, une musique d’attente et rediriger les appels pour appeler les agents dans des listes de distribution et les groupes de sécurité. Vous pouvez également définir la taille maximale de file d’attente, délai d’expiration et options de gestion des appels.
ms.openlocfilehash: a44bd5b00b47655dc950ee01f82ffd0c0a308466
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012972"
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="4359a-104">Créer une file d’attente appel système téléphonique</span><span class="sxs-lookup"><span data-stu-id="4359a-104">Create a Phone System call queue</span></span>

<span data-ttu-id="4359a-105">Appel de système téléphonique files d’attente contiennent le message d’accueil qui est utilisés lorsqu’une personne appelle un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la capacité de recherche pour l’agent disponible appel suivant gérer l’appel pendant les personnes qui appel Écoutez une musique d’attente.</span><span class="sxs-lookup"><span data-stu-id="4359a-105">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="4359a-106">Vous pouvez créer une seule ligne ou plusieurs files d’attente d’appel pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4359a-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="4359a-107">Files d’attente des appels téléphoniques système peuvent fournir :</span><span class="sxs-lookup"><span data-stu-id="4359a-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="4359a-108">Un message d’accueil d’organisation.</span><span class="sxs-lookup"><span data-stu-id="4359a-108">An organizational greeting.</span></span>
- <span data-ttu-id="4359a-109">Musique pendant que les utilisateurs sont en attente de suspension.</span><span class="sxs-lookup"><span data-stu-id="4359a-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="4359a-110">Redirection d’appels pour appeler les agents dans les groupes de sécurité et les listes de distribution à extension messagerie.</span><span class="sxs-lookup"><span data-stu-id="4359a-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="4359a-111">Définir des paramètres pour la taille maximale de file d’attente appel, délai d’expiration et options de gestion des appels.</span><span class="sxs-lookup"><span data-stu-id="4359a-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="4359a-112">Lorsqu’une personne appelle un numéro de téléphone qui est associé à une file d’attente des appels par le biais d’un [compte de ressource](manage-resource-accounts.md), elles seront entendre un message d’accueil premier (si une est configuré), puis ils sera placée dans la file d’attente et attendre le prochain agent appel disponible.</span><span class="sxs-lookup"><span data-stu-id="4359a-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="4359a-113">La personne qui entendront musique pendant qu’ils sont mis en attente en attente et les appels seront proposés aux agents appel par ordre *First In, First Out* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="4359a-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="4359a-114">Tous les appels en attente dans la file d’attente seront distribués à l’aide d’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="4359a-114">All calls waiting in the queue will be distributed using one of the following methods:</span></span>
  
- <span data-ttu-id="4359a-115">Avec le routage standard, le premier appel dans la file d’attente sonnera tous les agents en même temps.</span><span class="sxs-lookup"><span data-stu-id="4359a-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="4359a-116">Avec le routage en série, le premier appel dans la file d’attente sonnera tous les agents appel un par un.</span><span class="sxs-lookup"><span data-stu-id="4359a-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
- <span data-ttu-id="4359a-117">Avec tourniquet, le routage des appels entrants est équilibré afin que chaque agent appel le même nombre d’appels à partir de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="4359a-117">With round robin, routing of incoming calls is balanced so that each call agent will get the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4359a-118">Appel des agents qui sont **en mode hors connexion**, ont défini leur présence **ne pas** déranger ou qui ont opté en dehors de la file d’attente de l’appel ne sera pas appelés.</span><span class="sxs-lookup"><span data-stu-id="4359a-118">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="4359a-119">Vous recevrez uniquement une notification d’appel entrant (pour l’appel à la tête de la file d’attente) à la fois vers les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-119">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="4359a-120">Une fois un agent appel accepte l’appel, le prochain appel entrant dans la file d’attente démarre simultanée des agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-120">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="4359a-121">Cet article s’applique à Microsoft Teams et Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="4359a-121">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="4359a-122">Étape 1 : mise en route</span><span class="sxs-lookup"><span data-stu-id="4359a-122">Step 1 - Get started</span></span>

<span data-ttu-id="4359a-123">Pour commencer à l’aide de files d’attente d’appel, il est important de n’oubliez pas de choses :</span><span class="sxs-lookup"><span data-stu-id="4359a-123">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="4359a-124">Un standard automatique est nécessaire d’avoir un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="4359a-124">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="4359a-125">Pour plus d’informations sur les comptes de ressources, voir [Gérer les comptes de ressources dans les équipes](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="4359a-125">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="4359a-126">Si vous souhaitez affecter un numéro de routage Direct, vous devez acquérir et affecter les licences suivantes aux comptes ressource \(Office 365 entreprise E1, E3 ou E5, avec le module complémentaire système téléphonique\).</span><span class="sxs-lookup"><span data-stu-id="4359a-126">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="4359a-127">Si vous affectez un numéro de service Microsoft au lieu de cela, vous devez acquérir et affecter les licences suivantes à votre compte de ressource \(Office 365 entreprise E1, E3 ou E5, avec le module complémentaire système téléphonique et un Plan d’appel de\).</span><span class="sxs-lookup"><span data-stu-id="4359a-127">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="4359a-128">Microsoft fonctionne sur un modèle de licence approprié pour les applications telles que les standards automatiques de nuage et les files d’attente des appels, maintenant vous devez utiliser le modèle de gestion des licences utilisateur pour.</span><span class="sxs-lookup"><span data-stu-id="4359a-128">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!NOTE]
> <span data-ttu-id="4359a-129">Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou Office 365 appelant Plans.</span><span class="sxs-lookup"><span data-stu-id="4359a-129">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="4359a-130">Voir [Assigner de Skype pour les licences d’entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [licences attribuer les équipes Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4359a-130">See  [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="4359a-131">Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4359a-131">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="4359a-132">Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="4359a-132">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="4359a-133">Pour en savoir plus sur Office 365 appelant Plans, voir le [système téléphonique et Plans de l’appel](calling-plan-landing-page.md) et [Appel des Plans pour Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="4359a-133">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="4359a-134">Vous pouvez uniquement attribuer payants et les numéros de téléphone gratuit service que vous avez obtenu dans le **Centre d’administration de Microsoft équipes** ou transférés à partir d’un autre fournisseur de services aux files d’attente des appels système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="4359a-134">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Phone System call queues.</span></span> <span data-ttu-id="4359a-135">Pour obtenir et utiliser des numéros gratuits service, vous devez configurer les crédits de Communications.</span><span class="sxs-lookup"><span data-stu-id="4359a-135">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4359a-136">Numéros de téléphone de l’utilisateur (abonné) ne peut pas être affectés à appeler des files d’attente - le service seulement payant ou numéros de téléphone peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="4359a-136">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="4359a-137">Lorsque vous distribuez les appels entrants à partir d’une file d’attente des appels système téléphonique, ces clients sont pris en charge pour les agents d’appel :</span><span class="sxs-lookup"><span data-stu-id="4359a-137">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="4359a-138">Skype pour le client de bureau Business 2016 (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="4359a-138">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="4359a-139">Client de bureau Lync 2013 (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="4359a-139">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="4359a-140">Tous les modèles de téléphone IP pris en charge pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4359a-140">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="4359a-141">Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="4359a-141">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="4359a-142">Mac Skype pour Client d’entreprise (version 16.8.196 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="4359a-142">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="4359a-143">Android Skype pour Client d’entreprise (version 6.16.0.9 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="4359a-143">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="4359a-144">iPhone Skype pour Client d’entreprise (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="4359a-144">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="4359a-145">iPad Skype pour Client d’entreprise (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="4359a-145">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="4359a-146">Client Microsoft équipes Windows (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="4359a-146">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="4359a-147">Client Microsoft équipes Mac</span><span class="sxs-lookup"><span data-stu-id="4359a-147">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="4359a-148">Microsoft Teams iPhone application</span><span class="sxs-lookup"><span data-stu-id="4359a-148">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="4359a-149">Les équipes Microsoft pour Android</span><span class="sxs-lookup"><span data-stu-id="4359a-149">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="4359a-150">Étape 2 : obtention ou transfert payant ou des numéros de téléphone gratuit service</span><span class="sxs-lookup"><span data-stu-id="4359a-150">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="4359a-151">Avant de pouvoir créer et configurer les files d'attente, vous devrez transférer vos numéros payants et gratuits existants.</span><span class="sxs-lookup"><span data-stu-id="4359a-151">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="4359a-152">Une fois que vous obtenez les numéros de téléphone gratuit service payant, ils s’affichent dans le **Centre d’administration de Microsoft équipes** > **vocale** > **numéros de téléphone**et la volonté de **type numérique** présent figurer en tant que **Service - gratuit**.</span><span class="sxs-lookup"><span data-stu-id="4359a-152">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="4359a-153">Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) , ou si vous souhaitez transférer un numéro de service existant, voir les [numéros de téléphone transfert vers Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="4359a-153">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4359a-154">Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration Microsoft Teams pour obtenir les numéros de service.</span><span class="sxs-lookup"><span data-stu-id="4359a-154">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="4359a-155">Accédez à [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire à partir de l’extérieur des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="4359a-155">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="4359a-156">Si vous configurez également les standards automatiques, vous devrez uniquement affecter un numéro de téléphone pour le compte du service de surveillance automatique principal de la ressource, puis d’appelants directs à votre file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-156">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="4359a-157">Si tel est le cas, la file d’attente d’appel vous devrez être créé avant de pouvoir créer une option dans le standard automatique de sélectionne la file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-157">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="4359a-158">Étape 3 : créer une nouvelle file d’attente d’appel</span><span class="sxs-lookup"><span data-stu-id="4359a-158">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="4359a-159">Chaque file d’attente de l’appel doit posséder un [compte de ressource](manage-resource-accounts.md)associé.</span><span class="sxs-lookup"><span data-stu-id="4359a-159">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="4359a-160">Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer à la file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-160">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4359a-161">À l’aide du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4359a-161">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="4359a-162">Dans le **Centre d’administration de Microsoft équipes**, **voix** >  **files d’attente des appels**, puis cliquez sur **+ Nouveau**:</span><span class="sxs-lookup"><span data-stu-id="4359a-162">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="4359a-163">Définir le complet de file d’attente appel qu’un compte nom et des ressources</span><span class="sxs-lookup"><span data-stu-id="4359a-163">Set the call queue display name and resource account</span></span>

![Configuration d’une file d’attente de l’appel.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="4359a-165">![N ° 1](media/sfbcallout1.png)
**nom** Entrez un nom d’affichage de la description de la file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-165">![Number 1](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="4359a-166">Cela est nécessaire et peut contenir jusqu'à 64 caractères, espaces compris.</span><span class="sxs-lookup"><span data-stu-id="4359a-166">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="4359a-167">Ce nom s’affichera dans la notification de l’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="4359a-167">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="4359a-169">**Ajouter des comptes** Sélectionnez un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="4359a-169">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="4359a-170">Le compte de la ressource peut être ou non associé à un numéro payant service ou le numéro de téléphone gratuit pour la file d’attente de l’appel, mais chaque file d’attente d’appel requiert un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="4359a-170">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="4359a-171">Si il n’existe pas dans la liste, vous devez obtenir les numéros de service et les affecter à un compte de ressource avant de pouvoir créer cette file d’attente de l’appel, comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="4359a-171">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="4359a-172">Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="4359a-172">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> <span data-ttu-id="4359a-173">Vous devez créer un compte de ressource, comme décrit dans [Gérer les comptes de ressources dans les équipes](manage-resource-accounts.md) si vous souhaitez que votre file d’attente de l’appel vers un numéro de téléphone associé.</span><span class="sxs-lookup"><span data-stu-id="4359a-173">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="4359a-174">Si vous souhaitez ou que vous devez lui assigner un **domaine** ferait en l’affectant au compte de ressources pour la file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-174">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="4359a-175">Définir le message d’accueil et la musique joué suspendu</span><span class="sxs-lookup"><span data-stu-id="4359a-175">Set the greeting and music played while on hold</span></span>

![Configuration d’une file d’attente de l’appel.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="4359a-178">**Message d’accueil** est facultative.</span><span class="sxs-lookup"><span data-stu-id="4359a-178">**Greeting** is optional.</span></span> <span data-ttu-id="4359a-179">Il s’agit du message d’accueil qui est diffusé aux utilisateurs d’appel dans le nombre de file d’attente d’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-179">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="4359a-180">Vous pouvez télécharger un fichier audio (format .wav, .mp3 ou .wma).</span><span class="sxs-lookup"><span data-stu-id="4359a-180">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="4359a-182">**Musicale** Vous pouvez utiliser la musique par défaut en attente fournie avec la file d’attente de l’appel, ou vous pouvez télécharger un fichier audio .wav ou .wma mp3 formats à utiliser en tant que votre musique personnalisée en attente.</span><span class="sxs-lookup"><span data-stu-id="4359a-182">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="4359a-183">Sélectionnez l’options de répondeur automatique</span><span class="sxs-lookup"><span data-stu-id="4359a-183">Select the call answering options</span></span>

![Indique l’appel de méthode options de distribution](media/5d249515-d532-4af2-90da-011404028b89.png)

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="4359a-186">Vous pouvez sélectionner jusqu'à 200 agents appel appartenant à des listes de diffusion spécifiées ou des groupes.</span><span class="sxs-lookup"><span data-stu-id="4359a-186">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="4359a-187">Agents d’appel doivent être :</span><span class="sxs-lookup"><span data-stu-id="4359a-187">Call agents must be either:</span></span>

- <span data-ttu-id="4359a-188">Un utilisateur en ligne avec une licence de **Système téléphonique** et activé pour Enterprise Voice ou avec un Plan de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-188">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4359a-189">Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou un Plan de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-189">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="4359a-190">Voir [Assigner de Skype pour les licences d’entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [licences attribuer les équipes Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4359a-190">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

 <span data-ttu-id="4359a-191">Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4359a-191">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="4359a-192">Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="4359a-192">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="4359a-193">Utilisateurs en ligne avec une licence de **Système téléphonique** et un Plan d’appel qui sont ajoutés à un groupe d’Office 365, une liste de Distribution à extension messagerie ou un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="4359a-193">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="4359a-194">Il peut prendre jusqu'à 30 minutes pour un nouvel agent ajouté pour une liste de distribution ou un groupe de sécurité pour commencer à recevoir des appels à partir d’une file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-194">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="4359a-195">Un groupe de sécurité ou de la liste de distribution nouvellement créé peut prendre jusqu'à 48 heures soit disponible pour être utilisé avec les files d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-195">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="4359a-196">Nouvellement créé Office 365 groupes sont presque immédiatement disponibles.</span><span class="sxs-lookup"><span data-stu-id="4359a-196">Newly created Office 365 Groups are available almost immediately.</span></span>

![Configurer les files d’attente de l’appel.](media/skype-for-business-add-agents-to-call-queue.png)

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="4359a-199">**Méthode de routage** Vous pouvez choisir soit **Attendant**, **série**ou **tourniquet (Round Robin)** pour la méthode de distribution en file d’attente de votre appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-199">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="4359a-200">Toutes les files d’attente de nouveaux et existants appel aura attendant routage sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="4359a-200">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="4359a-201">Lorsque le routage standard est utilisé, le premier appel dans la file d’attente tous les agents appel sonnera en même temps.</span><span class="sxs-lookup"><span data-stu-id="4359a-201">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="4359a-202">Le premier agent d’appel pour identifier l’appel Obtient l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-202">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="4359a-203">**Surveillance du routage** entraîne le premier appel dans la file d’attente pour faire sonner tous les agents d’appel en même temps.</span><span class="sxs-lookup"><span data-stu-id="4359a-203">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="4359a-204">Le premier agent d’appel pour identifier l’appel Obtient l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-204">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="4359a-205">**Le routage de série** entraîne les appels entrants vers la sonnerie d’appel agents un par un, à partir du début de la liste d’appels de l’agent.</span><span class="sxs-lookup"><span data-stu-id="4359a-205">**Serial routing** causes incoming calls to ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="4359a-206">Si un agent fait disparaître ou ne récupère pas d’un appel, l’appel sonnera l’agent suivant dans la liste et essayez de tous les agents un par un jusqu'à ce qu’elle est choisie ou délai d’attente dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="4359a-206">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="4359a-207">Ce type de routage ignore les agents qui sont **en mode hors connexion**, qui ont la valeur leur présence **ne pas déranger**ou ont **choisi** de recevoir des appels à partir de cette file d’attente.</span><span class="sxs-lookup"><span data-stu-id="4359a-207">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="4359a-208">**Round robin** répartit le routage des appels entrants afin que chaque agent appel le même nombre d’appels à partir de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="4359a-208">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="4359a-209">Cela peut être très souhaitable dans un environnement de vente entrant afin de garantir l’opportunité égale entre tous les agents de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-209">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="4359a-210">Sélectionnez un agent exclure option</span><span class="sxs-lookup"><span data-stu-id="4359a-210">Select an agent opt out option</span></span>

![Case à cocher indique que l’agent d’abonnement](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="4359a-213">**Agent exclure option** Vous pouvez choisir d’autoriser les agents de file d’attente d’appel refuser de prendre des appels à partir d’une file d’attente spécifique en sélectionnant **l’Option Refuser l’Agent**.</span><span class="sxs-lookup"><span data-stu-id="4359a-213">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="4359a-214">L’activation de cette option permet de seront tous les agents de cette file d’attente pour démarrer ou arrêter de recevoir des appels à partir de cette file d’attente de l’appel à.</span><span class="sxs-lookup"><span data-stu-id="4359a-214">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="4359a-215">Vous pouvez révoquer le privilège d’annulations agent à tout moment en désactivant la case à cocher, à l’origine des agents sont automatiquement accrédité pour cette file d’attente à nouveau (paramètre par défaut pour tous les agents).</span><span class="sxs-lookup"><span data-stu-id="4359a-215">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="4359a-216">Pour accéder à l’option exclure, les agents peuvent procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4359a-216">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="4359a-217">Ouvrez **les Options** dans leur bureau Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4359a-217">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="4359a-218">Sous l’onglet **Transfert d’appel** , cliquez sur le lien **Modifier les paramètres en ligne** .</span><span class="sxs-lookup"><span data-stu-id="4359a-218">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="4359a-219">Dans la page de paramètres utilisateur, cliquez sur **Appeler les files d’attente**, puis désactivez les cases à cocher des files d’attente pour lesquelles ils souhaitent sortir.</span><span class="sxs-lookup"><span data-stu-id="4359a-219">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4359a-220">Agents à l’aide de Mac, mobile, ou clients Lync 2013 ou les utilisateurs de voix hybride qui sont hébergés sur site à l’aide de Skype pour serveur Business 2015, peut atteindre [https://aka.ms/cqsettings](https://aka.ms/cqsettings) pour accéder à l’abonnement option.</span><span class="sxs-lookup"><span data-stu-id="4359a-220">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>

<span data-ttu-id="4359a-221">![N ° 2](media/sfbcallout2.png)
**paramètre d’alerte de l’Agent**</span><span class="sxs-lookup"><span data-stu-id="4359a-221">![Number 2](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="4359a-222">Définit la durée d’un agent être averti d’un appel avant le numéro de série ou tourniquet (Round Robin) des méthodes de routage déplacement vers l’agent suivant.</span><span class="sxs-lookup"><span data-stu-id="4359a-222">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="4359a-223">Le paramètre par défaut est de 30 secondes, mais elle peut être définie pour 3 minutes.</span><span class="sxs-lookup"><span data-stu-id="4359a-223">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="4359a-224">Définir des options de gestion de l’appel de dépassement de capacité et délai d’expiration</span><span class="sxs-lookup"><span data-stu-id="4359a-224">Set the call overflow and timeout handling options</span></span>

![Configurer une file d’attente de l’appel.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="4359a-227">**Nombre maximal des appels dans la file d’attente** Permet de définir les appels maximales qui peuvent attendre dans la file d’attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="4359a-227">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="4359a-228">La valeur par défaut est 50, mais elle compris entre 0 et 200.</span><span class="sxs-lookup"><span data-stu-id="4359a-228">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="4359a-229">Lorsque cette limite est atteinte, l’appel sera géré de façon que vous avez défini le paramètre **lorsque le nombre maximal d’appels est atteint** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4359a-229">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="4359a-231">**Lorsque le nombre maximal d’appels est atteint.** Lorsque la file d’attente d’appels atteint sa taille maximale (définie à l’aide de la valeur **maximale des appels dans la file d’attente** ), vous pouvez choisir que se passe-t-il au nouvel appel entrant.</span><span class="sxs-lookup"><span data-stu-id="4359a-231">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="4359a-232">**Se déconnecter** L’appel sera déconnecté.</span><span class="sxs-lookup"><span data-stu-id="4359a-232">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="4359a-233">**Rediriger vers** Lorsque vous choisissez cette option, sélectionnez une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4359a-233">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="4359a-234">**Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent un Plan de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-234">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="4359a-235">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="4359a-235">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="4359a-236">Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="4359a-236">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="4359a-237">Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [configuration de la messagerie vocale dans le nuage](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="4359a-237">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="4359a-238">**Application vocale** Sélectionnez le nom de l’une file d’attente de l’appel ou qui a déjà été créée standard automatique.</span><span class="sxs-lookup"><span data-stu-id="4359a-238">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Nombre 3](media/sfbcallout3.png)

<span data-ttu-id="4359a-240">**Délai d’attente des appels : temps d’attente maximal** Vous pouvez également choisir combien de temps un appel peut être en attente dans la file d’attente avant qu’il arrive à expiration et doit être redirigé ou déconnecté.</span><span class="sxs-lookup"><span data-stu-id="4359a-240">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="4359a-241">Où elle sera redirigée est basée sur la façon dont vous définissez le paramètre **lorsqu’un appel arrive à expiration** .</span><span class="sxs-lookup"><span data-stu-id="4359a-241">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="4359a-242">Vous pouvez définir une durée de 0 à 45 minutes.</span><span class="sxs-lookup"><span data-stu-id="4359a-242">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="4359a-243">Peut avoir la valeur du délai d’attente en secondes, toutes les 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="4359a-243">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="4359a-244">Cela vous permet de manipuler le flux des appels avec une plus fine granularité.</span><span class="sxs-lookup"><span data-stu-id="4359a-244">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="4359a-245">Par exemple, vous pouvez spécifier que tous les appels qui sont sans réponse dans les 30 secondes par un agent d’accéder à un standard automatique de recherche dans l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="4359a-245">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Numéro 4](media/sfbcallout4.png)

<span data-ttu-id="4359a-247">**Lorsque le délai d’attente expire** Lorsque l’appel atteint la limite que vous définissez le paramètre de **la durée pendant laquelle un appel peut attendre dans la file d’attente** , vous pouvez choisir que se passe-t-il à cet appel :</span><span class="sxs-lookup"><span data-stu-id="4359a-247">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="4359a-248">**Se déconnecter** L’appel sera déconnecté.</span><span class="sxs-lookup"><span data-stu-id="4359a-248">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="4359a-249">**Cet appel de redirection** Lorsque vous choisissez cette option, vous devez ces options :</span><span class="sxs-lookup"><span data-stu-id="4359a-249">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="4359a-250">**Personne de votre société** Un utilisateur en ligne avec une licence de **Système téléphonique** et être activé pour Enterprise Voice ou possèdent des Plans de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-250">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="4359a-251">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="4359a-251">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="4359a-252">Pour ce faire, sélectionnez une **personne de votre société** et définissez cette personne pour que leurs appels transférés directement vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="4359a-252">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="4359a-253">Pour plus d’informations sur les licences requises pour la messagerie vocale, voir [configuration de la messagerie vocale dans le nuage](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="4359a-253">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="4359a-254">**Application vocale** Sélectionnez le nom de l’une file d’attente de l’appel ou qui a déjà été créée standard automatique.</span><span class="sxs-lookup"><span data-stu-id="4359a-254">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="4359a-255">Modification des ID de l’appelant d’un utilisateur pour les appels sortants</span><span class="sxs-lookup"><span data-stu-id="4359a-255">Changing a user's Caller ID for outbound calls</span></span> 

<span data-ttu-id="4359a-256">Vous pouvez protéger l’identité d’un utilisateur en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appel, de standard automatique ou de n’importe quel nombre de service au lieu de cela en créant une stratégie à l’aide de l’applet de commande **New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="4359a-256">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="4359a-257">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4359a-257">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="4359a-258">Ensuite, appliquer la stratégie à l’utilisateur à l’aide de l’applet de commande **Grant-CallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="4359a-258">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="4359a-259">Pour ce faire, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4359a-259">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="4359a-260">Vous pouvez obtenir plus d’informations sur la façon d’apporter des modifications aux paramètres d’ID de l’appelant dans votre organisation dans l’article [ID d’appelant utilisation dans votre organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="4359a-260">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="4359a-261">Vous souhaitez en savoir plus ?</span><span class="sxs-lookup"><span data-stu-id="4359a-261">Want to know more?</span></span>

<span data-ttu-id="4359a-262">Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-262">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="4359a-263">Cmdlets de file d’attente</span><span class="sxs-lookup"><span data-stu-id="4359a-263">Call queue cmdlets</span></span>

<span data-ttu-id="4359a-264">Voici les applets de commande dont vous avez besoin pour gérer une file d’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="4359a-264">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="4359a-265">Nouvelle CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="4359a-265">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="4359a-266">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="4359a-266">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="4359a-267">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="4359a-267">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="4359a-268">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="4359a-268">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="4359a-269">Informations supplémentaires sur PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="4359a-269">More about Windows PowerShell</span></span>

- <span data-ttu-id="4359a-270">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="4359a-270">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4359a-271">Avec Windows PowerShell, vous pouvez gérer Office 365 et Teams Microsoft à l’aide d’un point unique d’administration qui peut simplifier votre travail quotidien, lorsque vous avez plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="4359a-271">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4359a-272">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="4359a-272">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="4359a-273">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4359a-273">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="4359a-274">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4359a-274">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="4359a-275">Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Microsoft Teams tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="4359a-275">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="4359a-276">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="4359a-276">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="4359a-277">Gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4359a-277">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="4359a-278">Configurer votre ordinateur pour Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4359a-278">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="4359a-279">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="4359a-279">Related topics</span></span>

[<span data-ttu-id="4359a-280">Voici les avantages du système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="4359a-280">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="4359a-281">Obtention de numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="4359a-281">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="4359a-282">Disponibilité des forfaits d'appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="4359a-282">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="4359a-283">Nouvelle CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="4359a-283">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
