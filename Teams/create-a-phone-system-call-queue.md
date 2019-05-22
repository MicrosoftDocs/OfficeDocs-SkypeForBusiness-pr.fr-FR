---
title: Créer une file d’attente d’appel
ms.author: crowe
author: CarolynRowe
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Apprenez à configurer le système téléphonique pour les files d’attente d’appels Cloud afin de vous donner un message d’accueil professionnel, de la musique en attente et de rediriger les appels d’appel vers des listes de distribution et des groupes de sécurité. Vous pouvez également définir la taille maximale de la file d’attente, le délai d’expiration et les options de traitement des appels.
ms.openlocfilehash: e32ab12c63f20439d21c9c1829cd4b32bdd34d70
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344684"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="e41b7-104">Créer une file d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="e41b7-104">Create a Cloud call queue</span></span>

<span data-ttu-id="e41b7-105">Les files d’attente d’appels Cloud incluent des messages d’accueil qui sont utilisés lorsque quelqu’un vous appelle pour appeler un numéro de téléphone pour votre organisation, la possibilité de mettre automatiquement les appels en attente et la possibilité de rechercher le prochain agent d’appel disponible pour gérer l’appel alors que les personnes qui rejoignent les appels sont écouter de la musique pendant l’attente.</span><span class="sxs-lookup"><span data-stu-id="e41b7-105">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="e41b7-106">Vous pouvez créer des files d’attente d’appels uniques ou multiples pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e41b7-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="e41b7-107">Les files d’attente d’appels Cloud peuvent fournir:</span><span class="sxs-lookup"><span data-stu-id="e41b7-107">Cloud call queues can provide:</span></span>
  
- <span data-ttu-id="e41b7-108">Un message d’accueil professionnel.</span><span class="sxs-lookup"><span data-stu-id="e41b7-108">An organizational greeting.</span></span>
- <span data-ttu-id="e41b7-109">Musique pendant que les personnes sont en attente.</span><span class="sxs-lookup"><span data-stu-id="e41b7-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="e41b7-110">Redirection des appels vers des téléopérateurs dans des listes de distribution et des groupes de sécurité à extension messagerie.</span><span class="sxs-lookup"><span data-stu-id="e41b7-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="e41b7-111">Création de paramètres pour la taille maximale de la file d’attente d’appels, le délai d’expiration et les options de traitement des appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="e41b7-112">Lorsque quelqu’un vous appelle pour appeler un numéro de téléphone associé à une file d’attente d’appels via un [compte de ressource](manage-resource-accounts.md), il entend d’abord un message d’accueil (s’il y a une configuration), puis il est placé dans la file d’attente et attend que le prochain agent d’appel soit disponible.</span><span class="sxs-lookup"><span data-stu-id="e41b7-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="e41b7-113">La personne qui appelle entend entendre de la musique alors qu’elle est en attente, et les appels sont proposés aux téléopérateurs pour la *première* fois (FIFO).</span><span class="sxs-lookup"><span data-stu-id="e41b7-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="e41b7-114">Tous les appels en attente dans la file d’attente seront distribués à l’aide de l’une des méthodes suivantes:</span><span class="sxs-lookup"><span data-stu-id="e41b7-114">All calls waiting in the queue will be distributed using one of the following methods:</span></span>
  
- <span data-ttu-id="e41b7-115">Avec le routage de l’attendant, le premier appel dans la file d’attente sonne sur tous les agents en même temps.</span><span class="sxs-lookup"><span data-stu-id="e41b7-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="e41b7-116">Lorsque le routage est en série, le premier appel dans la file d’attente sonne sur tous les agents d’appel un par un.</span><span class="sxs-lookup"><span data-stu-id="e41b7-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
- <span data-ttu-id="e41b7-117">Avec la répétition alternée, le routage des appels entrants est équilibré de telle sorte que chaque agent d’appel puisse obtenir le même nombre d’appels à partir de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="e41b7-117">With round robin, routing of incoming calls is balanced so that each call agent will get the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e41b7-118">Les téléopérateurs qui sont **hors ligne**, ont défini leur présence sur **ne pas** déranger ou ont désactivé la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-118">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="e41b7-119">Une seule notification d’appel entrant (pour l’appel en tête de file) sera envoyée aux téléopérateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="e41b7-119">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="e41b7-120">Lorsqu’un téléopérateur accepte l’appel, le prochain appel entrant dans la file d’attente sonnera pour les autres téléopérateurs.</span><span class="sxs-lookup"><span data-stu-id="e41b7-120">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="e41b7-121">Cet article s’applique à Microsoft teams et à Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="e41b7-121">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="e41b7-122">Étape 1: commencer</span><span class="sxs-lookup"><span data-stu-id="e41b7-122">Step 1 - Get started</span></span>

<span data-ttu-id="e41b7-123">Pour commencer à utiliser les files d’attente d’appels, il est important de garder à l’esprit les points suivants:</span><span class="sxs-lookup"><span data-stu-id="e41b7-123">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="e41b7-124">Une file d’attente d’appels doit avoir un compte de ressources associé.</span><span class="sxs-lookup"><span data-stu-id="e41b7-124">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="e41b7-125">Pour plus d’informations sur les comptes de ressources, voir [gérer les comptes de ressources dans teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="e41b7-125">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="e41b7-126">Si vous envisagez d’affecter un numéro d’acheminement direct, vous devez acquérir et attribuer les licences suivantes à \(votre compte de ressources Office 365 entreprise E1, E3 ou E5, à l’aide\)du composant additionnel du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="e41b7-126">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="e41b7-127">Si vous affectez un numéro de service Microsoft à la place, vous devez acquérir et attribuer les licences suivantes à votre compte \(de ressources Office 365 entreprise E1, E3 ou E5, avec le module complémentaire du système téléphonique et un\)plan d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-127">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="e41b7-128">Il vous suffit de créer une licence pour les comptes de ressources avec un numéro de téléphone qui leur est attribué.</span><span class="sxs-lookup"><span data-stu-id="e41b7-128">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="e41b7-129">Dans une file d’attente d’appels ou de standards automatiques imbriqués, vous n’avez pas besoin de vous attribuer une licence au reste des standards automatiques ou des files d’attente d’appels s’ils ne disposent pas de numéros de téléphone associés.</span><span class="sxs-lookup"><span data-stu-id="e41b7-129">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them.</span></span> 

> [!NOTE] 
> <span data-ttu-id="e41b7-130">Les numéros de service de routage direct pour le standard automatique et les files d’attente d’appels sont uniquement pris en charge pour les utilisateurs et les agents Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e41b7-130">Direct Routing service numbers for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE] 
> <span data-ttu-id="e41b7-131">Microsoft travaille sur un modèle de licence sans frais pour des applications telles que les standards automatiques de Cloud et les files d’attente d’appels, pour le moment, vous devez utiliser le modèle de gestion des licences utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e41b7-131">Microsoft is working on a cost-free licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!NOTE]
> <span data-ttu-id="e41b7-132">Pour rediriger les appels vers des utilisateurs de votre organisation qui sont en ligne, ils doivent disposer d’une licence de **système téléphonique** et être activés pour Enterprise Voice ou disposer d’offres d’appels d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="e41b7-132">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="e41b7-133">Consultez la rubrique [affectation de licences Skype entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [affectation de licences Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="e41b7-133">See  [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="e41b7-134">Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e41b7-134">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="e41b7-135">Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="e41b7-135">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="e41b7-136">Pour en savoir plus sur les offres d’appels d’Office 365, voir [système téléphonique et](calling-plan-landing-page.md) offres d’appel et [forfaits pour Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="e41b7-136">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="e41b7-137">Vous ne pouvez attribuer que des numéros de service payants et gratuits que vous avez disponibles dans le **Centre d’administration Microsoft teams** ou que vous avez transférés d’un autre fournisseur de services vers des files d’attente d’appels Cloud.</span><span class="sxs-lookup"><span data-stu-id="e41b7-137">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Cloud call queues.</span></span> <span data-ttu-id="e41b7-138">Pour obtenir et utiliser des numéros de service gratuits, vous devez configurer des crédits de communication.</span><span class="sxs-lookup"><span data-stu-id="e41b7-138">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e41b7-139">Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués aux numéros de service de file d’attente d’appels uniquement ou les numéros de téléphone gratuits peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="e41b7-139">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="e41b7-140">Lorsque vous distribuez les appels entrants depuis une file d’attente d’appels Cloud, ces clients sont pris en charge pour les téléopérateurs:</span><span class="sxs-lookup"><span data-stu-id="e41b7-140">When you are distributing the incoming calls from a Cloud call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="e41b7-141">Client de bureau Skype entreprise 2016 (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="e41b7-141">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="e41b7-142">Client de bureau Lync 2013 (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="e41b7-142">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="e41b7-143">Tous les modèles de téléphone IP pris en charge par Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e41b7-143">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="e41b7-144">Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="e41b7-144">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="e41b7-145">Client Skype entreprise pour Mac (version 16.8.196 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="e41b7-145">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="e41b7-146">Client Skype entreprise Android (version 6.16.0.9 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="e41b7-146">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="e41b7-147">Client Skype entreprise pour iPhone (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="e41b7-147">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="e41b7-148">Client Skype entreprise pour iPad (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="e41b7-148">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="e41b7-149">Client Microsoft Teams (versions 32 et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="e41b7-149">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="e41b7-150">Client Microsoft teams Mac</span><span class="sxs-lookup"><span data-stu-id="e41b7-150">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="e41b7-151">Application Microsoft teams pour iPhone</span><span class="sxs-lookup"><span data-stu-id="e41b7-151">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="e41b7-152">Application Android Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e41b7-152">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="e41b7-153">Étape 2: réception ou transfert de numéros de service gratuits ou payants</span><span class="sxs-lookup"><span data-stu-id="e41b7-153">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="e41b7-154">Avant de pouvoir créer et configurer les files d'attente, vous devrez transférer vos numéros payants et gratuits existants.</span><span class="sxs-lookup"><span data-stu-id="e41b7-154">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="e41b7-155">Une fois que vous avez obtenu les numéros de téléphone de service gratuits ou payants, ceux-ci apparaissent dans les**numéros de téléphone\*\*\*\*vocaux** > du centre > d' **administration Microsoft teams**et le **type de numéro** mentionné est répertorié en tant que **service-** gratuit.</span><span class="sxs-lookup"><span data-stu-id="e41b7-155">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="e41b7-156">Pour obtenir vos numéros de service, reportez-vous à la rubrique [obtention de numéros de service](getting-service-phone-numbers.md) ou, si vous souhaitez transférer un numéro de service existant, reportez-vous à la section transférer des [numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="e41b7-156">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e41b7-157">Si vous résidez en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration de Microsoft teams pour obtenir des numéros de service.</span><span class="sxs-lookup"><span data-stu-id="e41b7-157">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="e41b7-158">Pour plus d’informations sur la [gestion des numéros de téléphone de votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , voir gérer les numéros de téléphone situés en dehors des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="e41b7-158">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="e41b7-159">Si vous configurez également des standards automatiques, il est possible que vous n’ayez besoin d’affecter un numéro de téléphone au compte de ressources principal du standard automatique, puis de lui envoyer des appelants directs.</span><span class="sxs-lookup"><span data-stu-id="e41b7-159">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="e41b7-160">Si tel est le cas, la file d’attente des appels doit être créée avant de pouvoir créer une option dans le standard automatique qui sélectionne la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-160">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="e41b7-161">Étape 3: création d’une file d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="e41b7-161">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="e41b7-162">Chaque file d’attente d’appels doit avoir un [compte de ressources](manage-resource-accounts.md)associé.</span><span class="sxs-lookup"><span data-stu-id="e41b7-162">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="e41b7-163">Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer à la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-163">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e41b7-164">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e41b7-164">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e41b7-165">Dans le **Centre d’administration de Microsoft teams**, les**files d’attente d’appels** **vocaux** >  , puis cliquez sur **+ Ajouter nouveau**:</span><span class="sxs-lookup"><span data-stu-id="e41b7-165">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="e41b7-166">Définir le nom d’affichage de la file d’attente d’appels et le compte de ressources</span><span class="sxs-lookup"><span data-stu-id="e41b7-166">Set the call queue display name and resource account</span></span>

![Configuration d’une file d’attente d’appels.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="e41b7-168">![](media/sfbcallout1.png)
**Nom** du numéro 1 Entrez un nom descriptif pour la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-168">![Number 1](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="e41b7-169">Cela est obligatoire et peut contenir jusqu’à 64 caractères, y compris des espaces.</span><span class="sxs-lookup"><span data-stu-id="e41b7-169">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="e41b7-170">Ce nom sera affiché dans la notification de l’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="e41b7-170">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="e41b7-172">**Ajouter des comptes** Sélectionnez un compte de ressources.</span><span class="sxs-lookup"><span data-stu-id="e41b7-172">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="e41b7-173">Le compte de ressource est ou n’est pas associé à un numéro de service payant ou gratuit pour la file d’attente d’appels, mais chaque file d’attente d’appels nécessite un compte de ressources associé.</span><span class="sxs-lookup"><span data-stu-id="e41b7-173">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="e41b7-174">S’il n’y figure pas, vous devez obtenir des numéros de service et les affecter à un compte de ressources avant de pouvoir créer cette file d’attente d’appels, comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="e41b7-174">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="e41b7-175">Pour obtenir vos numéros de service, consultez la rubrique [obtention de numéros de téléphone de service](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="e41b7-175">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="e41b7-176">Vous devez créer un compte de ressources conformément aux instructions de la section [gérer les comptes de ressources dans teams](manage-resource-accounts.md) si vous souhaitez que votre file d’attente d’appels dispose d’un numéro de téléphone associé.</span><span class="sxs-lookup"><span data-stu-id="e41b7-176">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="e41b7-177">Le cas échéant, ou si vous avez besoin d’affecter un **domaine** , vous pouvez l’affecter au compte de ressources de la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-177">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="e41b7-178">Définir le message d’accueil et la musique lue pendant la mise en attente</span><span class="sxs-lookup"><span data-stu-id="e41b7-178">Set the greeting and music played while on hold</span></span>

![Configuration d’une file d’attente d’appels.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="e41b7-181">Le **message d’accueil** est facultatif.</span><span class="sxs-lookup"><span data-stu-id="e41b7-181">**Greeting** is optional.</span></span> <span data-ttu-id="e41b7-182">Il s’agit du message d’accueil qui est lu pour les personnes qui rejoignent le numéro de la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-182">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="e41b7-183">Vous pouvez charger un fichier audio (formats. wav,. mp3 ou. WMA).</span><span class="sxs-lookup"><span data-stu-id="e41b7-183">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="e41b7-185">**Attente musicale** Vous pouvez utiliser l’attente de musique par défaut fournie avec la file d’attente d’appels ou vous pouvez charger un fichier audio au format. wav,. mp3 ou. WMA à utiliser comme votre musique personnalisée en attente.</span><span class="sxs-lookup"><span data-stu-id="e41b7-185">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="e41b7-186">Sélectionner les options de répondeur automatique</span><span class="sxs-lookup"><span data-stu-id="e41b7-186">Select the call answering options</span></span>

![Affiche les options de méthode de distribution des appels](media/5d249515-d532-4af2-90da-011404028b89.png)

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="e41b7-189">Vous pouvez sélectionner jusqu’à 200 téléopérateurs appartenant à des listes de diffusion ou groupes spécifiés.</span><span class="sxs-lookup"><span data-stu-id="e41b7-189">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="e41b7-190">Les agents d’appel doivent être:</span><span class="sxs-lookup"><span data-stu-id="e41b7-190">Call agents must be either:</span></span>

- <span data-ttu-id="e41b7-191">Un utilisateur en ligne disposant d’une licence de **système téléphonique** et activé pour voix entreprise ou avec un plan d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-191">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e41b7-192">Pour rediriger les appels vers des utilisateurs de votre organisation qui sont en ligne, ils doivent disposer d’une licence de **système téléphonique** et être activées pour voix entreprise ou avoir un plan d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-192">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="e41b7-193">Consultez la rubrique [affectation de licences Skype entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [affectation de licences Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="e41b7-193">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

 <span data-ttu-id="e41b7-194">Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e41b7-194">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="e41b7-195">Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="e41b7-195">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="e41b7-196">Utilisateurs en ligne disposant d’une licence de **système téléphonique** et d’un plan d’appels qui sont ajoutés à un groupe Office 365, une liste de distribution à extension messagerie ou un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="e41b7-196">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="e41b7-197">L’ajout d’un nouvel agent à un nouvel agent pour une liste de distribution ou un groupe de sécurité à partir d’une file d’attente peut durer jusqu’à 3 heures.</span><span class="sxs-lookup"><span data-stu-id="e41b7-197">It might take up to 3 hours for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="e41b7-198">Une liste de distribution ou un groupe de sécurité nouvellement créé peut nécessiter jusqu’à 48 heures de disponibilité pour une utilisation avec des files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-198">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="e41b7-199">Les nouveaux groupes Office 365 sont disponibles presque immédiatement.</span><span class="sxs-lookup"><span data-stu-id="e41b7-199">Newly created Office 365 Groups are available almost immediately.</span></span>

![Configurez des files d’attente d’appels.](media/skype-for-business-add-agents-to-call-queue.png)

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="e41b7-202">**Méthode de routage** Vous pouvez choisir **standard**, **série**ou **tourniquet** pour la méthode de distribution de votre file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-202">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="e41b7-203">La totalité des files d’attente d’appels nouvelles et existantes est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="e41b7-203">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="e41b7-204">Lorsque le routage de l’assistance est utilisé, le premier appel dans la file d’attente sonne tous les agents d’appel en même temps.</span><span class="sxs-lookup"><span data-stu-id="e41b7-204">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="e41b7-205">Le premier agent d’appel pour décrocher l’appel obtient l’appel.</span><span class="sxs-lookup"><span data-stu-id="e41b7-205">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="e41b7-206">Le routage de l' **attendant** entraîne le premier appel dans la file d’attente pour sonner tous les agents d’appel en même temps.</span><span class="sxs-lookup"><span data-stu-id="e41b7-206">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="e41b7-207">Le premier agent d’appel pour décrocher l’appel obtient l’appel.</span><span class="sxs-lookup"><span data-stu-id="e41b7-207">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="e41b7-208">Les appels entrants de **routage en série** sonneront entre les agents un par un, en commençant par le début de la liste de l’agent d’appel.</span><span class="sxs-lookup"><span data-stu-id="e41b7-208">**Serial routing** incoming calls will ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="e41b7-209">Les agents ne peuvent pas être commandés dans la liste des agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="e41b7-209">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="e41b7-210">Si un agent est rejeté ou ne décroche pas d’appel, l’appel sonnera sur l’agent suivant dans la liste et tentera d’avoir accès à tous les agents un par un jusqu’à ce qu’il soit décroché ou arrive à expiration dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="e41b7-210">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="e41b7-211">Le routage en série ignorera les agents qui sont **hors ligne**, ont défini leur présence sur **ne pas**déranger ou a **refusé** d’obtenir des appels à partir de cette file d’attente.</span><span class="sxs-lookup"><span data-stu-id="e41b7-211">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="e41b7-212">**Tourniquet alterne** le routage des appels entrants de telle sorte que chaque agent d’appel puisse obtenir le même nombre d’appels à partir de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="e41b7-212">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="e41b7-213">Il est possible que cela soit très désirable dans un environnement de ventes entrantes pour garantir l’égalité des chances entre tous les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="e41b7-213">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="e41b7-214">Sélectionner une option de désactivation de l’agent</span><span class="sxs-lookup"><span data-stu-id="e41b7-214">Select an agent opt out option</span></span>

![Case à cocher Désactiver l’agent](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="e41b7-217">**Option de refus d’agent** Vous pouvez choisir d’autoriser les agents de files d’attente d’appels à désactiver les appels d’une file d’attente particulière en sélectionnant **l’option agent opt out**.</span><span class="sxs-lookup"><span data-stu-id="e41b7-217">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="e41b7-218">L’activation de cette option permet à tous les agents de cette file d’attente de démarrer ou d’arrêter de recevoir des appels à partir de la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-218">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="e41b7-219">Vous pouvez révoquer les privilèges d’annulation de l’agent à tout moment en désactivant la case à cocher, pour que les agents le fassent automatiquement pour cette file d’attente (paramètre par défaut pour tous les agents).</span><span class="sxs-lookup"><span data-stu-id="e41b7-219">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="e41b7-220">Pour accéder à l’option d’annulation, les agents peuvent procéder comme suit:</span><span class="sxs-lookup"><span data-stu-id="e41b7-220">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="e41b7-221">Ouvrez les **options** de votre client Skype entreprise de bureau.</span><span class="sxs-lookup"><span data-stu-id="e41b7-221">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="e41b7-222">Dans l’onglet **transfert d’appel** , cliquez sur le lien modifier les **paramètres en ligne** .</span><span class="sxs-lookup"><span data-stu-id="e41b7-222">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="e41b7-223">Dans la page Paramètres utilisateur, cliquez sur **files d’attente d’appels**, puis désactivez les cases à cocher correspondant aux files d’attente pour lesquelles elles doivent être refusées.</span><span class="sxs-lookup"><span data-stu-id="e41b7-223">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e41b7-224">Les agents utilisant des applications ou des points de terminaison autres que le bureau Skype entreprise peuvent accéder à l’option option opt [https://aka.ms/cqsettings](https://aka.ms/cqsettings)du portail des paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e41b7-224">Agents using apps or endpoints other than Skype for Business Desktop can access the opt out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="e41b7-225">![Paramètre d'](media/sfbcallout2.png)
**alerte d’agent** numéro 2</span><span class="sxs-lookup"><span data-stu-id="e41b7-225">![Number 2](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="e41b7-226">Cela définit la durée d’un appel de l’agent pour être averti de l’appel avant que les méthodes de routage par série ou par répétition alternées soient déplacées vers l’agent suivant.</span><span class="sxs-lookup"><span data-stu-id="e41b7-226">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="e41b7-227">Le paramètre par défaut est de 30 secondes, mais peut être configuré pour une durée de 3 minutes maximum.</span><span class="sxs-lookup"><span data-stu-id="e41b7-227">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="e41b7-228">Définir les options de dépassement d’appel et de gestion des délais d’expiration</span><span class="sxs-lookup"><span data-stu-id="e41b7-228">Set the call overflow and timeout handling options</span></span>

![Configurer une file d’attente d’appels.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Numéro 1](media/sfbcallout1.png)

<span data-ttu-id="e41b7-231">**Nombre maximal d’appels dans la file d’attente** Utilisez cette valeur pour définir le nombre maximal d’appels qui peuvent attendre dans la file d’attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="e41b7-231">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="e41b7-232">La valeur par défaut est 50, mais elle peut varier entre 0 et 200.</span><span class="sxs-lookup"><span data-stu-id="e41b7-232">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="e41b7-233">Lorsque cette limite est atteinte, l’appel est géré en procédant comme suit **lorsque le nombre maximal d’appels est atteint** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e41b7-233">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Numéro 2](media/sfbcallout2.png)

<span data-ttu-id="e41b7-235">**Lorsque le nombre maximum d’appels est atteint** Lorsque la file d’attente des appels atteint sa taille maximale (définie en utilisant le **nombre maximal d’appels dans la file d’attente** ), vous pouvez choisir ce qu’il advient des nouveaux appels entrants.</span><span class="sxs-lookup"><span data-stu-id="e41b7-235">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="e41b7-236">\*\*\*\* Se déconnecter L’appel sera déconnecté.</span><span class="sxs-lookup"><span data-stu-id="e41b7-236">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="e41b7-237">**Rediriger vers** Lorsque vous choisissez cette option, sélectionnez l’une des options suivantes:</span><span class="sxs-lookup"><span data-stu-id="e41b7-237">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="e41b7-238">**Personne de votre entreprise** Un utilisateur en ligne disposant d’une licence de **système téléphonique** et est activé pour voix entreprise ou avoir un plan d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-238">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="e41b7-239">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="e41b7-239">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="e41b7-240">Pour cela, sélectionnez une **personne au sein de votre entreprise** et configurez cette personne pour que les appels soient transférés directement à la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="e41b7-240">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="e41b7-241">Pour en savoir plus sur les licences requises pour la boîte vocale, consultez la rubrique [configurer la messagerie vocale Cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="e41b7-241">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="e41b7-242">**Application vocale** Sélectionnez le nom d’une file d’attente d’appels ou d’un standard automatique qui a déjà été créé.</span><span class="sxs-lookup"><span data-stu-id="e41b7-242">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Nombre 3](media/sfbcallout3.png)

<span data-ttu-id="e41b7-244">**Délai d’appel: délai d’attente maximum** Vous pouvez également décider du temps qu’un appel peut mettre en attente dans la file d’attente avant qu’il arrive à expiration, et qu’il doive être redirigé ou déconnecté.</span><span class="sxs-lookup"><span data-stu-id="e41b7-244">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="e41b7-245">L’endroit où il sera redirigé dépend de la manière dont vous définissez le **délai d’appel** .</span><span class="sxs-lookup"><span data-stu-id="e41b7-245">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="e41b7-246">Vous pouvez définir une heure comprise entre 0 et 45 minutes.</span><span class="sxs-lookup"><span data-stu-id="e41b7-246">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="e41b7-247">La valeur Timeout peut être définie en secondes, à des intervalles de 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="e41b7-247">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="e41b7-248">Cela vous permet de manipuler le flux d’appels avec une granularité plus fine.</span><span class="sxs-lookup"><span data-stu-id="e41b7-248">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="e41b7-249">Par exemple, vous pouvez spécifier que les appels qui ne sont pas traités par un agent dans un délai de 30 secondes s’exécutent dans un standard automatique de recherche d’annuaires.</span><span class="sxs-lookup"><span data-stu-id="e41b7-249">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Numéro 4](media/sfbcallout4.png)

<span data-ttu-id="e41b7-251">**Lorsque** le délai d’appel est épuisé Lorsque l’appel atteint la limite définie en fonction de la **durée pendant laquelle un appel peut patienter dans la file d’attente** , vous pouvez choisir ce qu’il advient de cet appel:</span><span class="sxs-lookup"><span data-stu-id="e41b7-251">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="e41b7-252">\*\*\*\* Se déconnecter L’appel sera déconnecté.</span><span class="sxs-lookup"><span data-stu-id="e41b7-252">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="e41b7-253">**Rediriger cet appel vers** Lorsque vous choisissez cette option, vous disposez des options suivantes:</span><span class="sxs-lookup"><span data-stu-id="e41b7-253">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="e41b7-254">**Personne de votre entreprise** Un utilisateur en ligne disposant d’une licence de **système téléphonique** et est activé pour voix entreprise ou avec des plans d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-254">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="e41b7-255">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="e41b7-255">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="e41b7-256">Pour cela, sélectionnez une **personne au sein de votre entreprise** et configurez cette personne pour que les appels soient transférés directement à la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="e41b7-256">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="e41b7-257">Pour en savoir plus sur les licences requises pour la boîte vocale, consultez la rubrique [configurer la messagerie vocale Cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="e41b7-257">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="e41b7-258">**Application vocale** Sélectionnez le nom d’une file d’attente d’appels ou d’un standard automatique qui a déjà été créé.</span><span class="sxs-lookup"><span data-stu-id="e41b7-258">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="e41b7-259">Modification de l’ID d’appelant d’un utilisateur pour les appels sortants</span><span class="sxs-lookup"><span data-stu-id="e41b7-259">Changing a user's Caller ID for outbound calls</span></span> 

<span data-ttu-id="e41b7-260">Vous pouvez protéger l’identité d’un utilisateur en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appels, le standard automatique ou tout autre numéro de service en créant une stratégie à l’aide de l’applet **de nouvelle cmdlet New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="e41b7-260">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="e41b7-261">Pour cela, exécutez:</span><span class="sxs-lookup"><span data-stu-id="e41b7-261">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="e41b7-262">Appliquez ensuite la stratégie à l’utilisateur à l’aide de l’applet **de demande Grant-CallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="e41b7-262">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="e41b7-263">Pour cela, exécutez:</span><span class="sxs-lookup"><span data-stu-id="e41b7-263">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="e41b7-264">Pour plus d’informations sur la modification des paramètres d’identification de l’appelant au sein de votre organisation, consultez l’article [comment utiliser l’identification de l’appelant au sein de votre organisation](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="e41b7-264">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="e41b7-265">Vous souhaitez en savoir plus ?</span><span class="sxs-lookup"><span data-stu-id="e41b7-265">Want to know more?</span></span>

<span data-ttu-id="e41b7-266">Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-266">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="e41b7-267">Cmdlets de files d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="e41b7-267">Call queue cmdlets</span></span>

<span data-ttu-id="e41b7-268">Voici les applets de passe dont vous avez besoin pour gérer une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e41b7-268">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="e41b7-269">Nouveau-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="e41b7-269">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="e41b7-270">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="e41b7-270">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="e41b7-271">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="e41b7-271">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="e41b7-272">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="e41b7-272">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="e41b7-273">Informations supplémentaires sur PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="e41b7-273">More about Windows PowerShell</span></span>

- <span data-ttu-id="e41b7-274">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="e41b7-274">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e41b7-275">Windows PowerShell vous permet de gérer Office 365 et Microsoft teams à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="e41b7-275">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="e41b7-276">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="e41b7-276">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="e41b7-277">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e41b7-277">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="e41b7-278">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e41b7-278">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="e41b7-279">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration de Microsoft Teams, par exemple, lorsque vous apportez des modifications à de nombreux utilisateurs en même temps.</span><span class="sxs-lookup"><span data-stu-id="e41b7-279">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e41b7-280">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="e41b7-280">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="e41b7-281">Gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e41b7-281">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="e41b7-282">Configurer votre ordinateur pour Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e41b7-282">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="e41b7-283">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e41b7-283">Related topics</span></span>

[<span data-ttu-id="e41b7-284">Voici les avantages du système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="e41b7-284">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="e41b7-285">Obtention de numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="e41b7-285">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="e41b7-286">Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="e41b7-286">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="e41b7-287">Nouveau-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="e41b7-287">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
