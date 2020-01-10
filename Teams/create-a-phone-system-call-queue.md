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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: Apprenez à configurer le système téléphonique pour les files d’attente d’appels Cloud avec Microsoft Teams.
ms.openlocfilehash: 95cf9701705950d997e1d200fee117b5f8f9738b
ms.sourcegitcommit: 2fab6105dfc4c225de8c09ab79d9c2c273a3e4f6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/10/2020
ms.locfileid: "41005172"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="100cc-103">Créer une file d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="100cc-103">Create a Cloud call queue</span></span>

<span data-ttu-id="100cc-104">Les files d’attente d’appels Cloud peuvent fournir :</span><span class="sxs-lookup"><span data-stu-id="100cc-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="100cc-105">Message d’accueil.</span><span class="sxs-lookup"><span data-stu-id="100cc-105">A greeting message.</span></span>
- <span data-ttu-id="100cc-106">Musique pendant que les personnes sont en attente.</span><span class="sxs-lookup"><span data-stu-id="100cc-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="100cc-107">La redirection des appels vers des téléopérateurs dans des listes de distribution et des groupes de sécurité à extension messagerie.</span><span class="sxs-lookup"><span data-stu-id="100cc-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="100cc-108">Définir des paramètres différents, tels que la taille maximale de la file d’attente, le délai d’expiration et les options de traitement des appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="100cc-109">Boîte vocale partagée permettant aux appelants de laisser un message à une organisation.</span><span class="sxs-lookup"><span data-stu-id="100cc-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="100cc-110">Vous pouvez associer un numéro de téléphone à une file d’attente d’appels à l’aide d’un [compte de ressources](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="100cc-110">You would associate a phone number to a call queue using a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="100cc-111">Une file d’attente d’appels peut être numérotée directement ou consultée par une sélection dans un standard automatique.</span><span class="sxs-lookup"><span data-stu-id="100cc-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="100cc-112">L’appelant entend lire de la musique pendant qu’il est en attente et l’appel se connecte à la *première fois, première sortie* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="100cc-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="100cc-113">Tous les appels dans la file d’attente sont envoyés aux agents par le biais de l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="100cc-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="100cc-114">Avec le routage de l’attendant, le premier appel dans la file d’attente sonne sur tous les agents en même temps.</span><span class="sxs-lookup"><span data-stu-id="100cc-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="100cc-115">Avec le routage en série, le premier appel dans la file d’attente sonne tous les agents d’appel un par un.</span><span class="sxs-lookup"><span data-stu-id="100cc-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="100cc-116">Avec la répétition alternée, le routage des appels entrants est équilibré de telle sorte que chaque agent d’appel obtient le même nombre d’appels à partir de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="100cc-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="100cc-117">Les téléopérateurs qui sont **hors ligne**, ont défini leur présence sur **ne pas déranger** ou ont désactivé la file d’attente des appels ne recevront aucun appel.</span><span class="sxs-lookup"><span data-stu-id="100cc-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="100cc-118">Une seule notification d’appel entrant (pour l’appel en tête de file) sera envoyée aux téléopérateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="100cc-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="100cc-119">Lorsqu’un téléopérateur accepte l’appel, le prochain appel entrant dans la file d’attente sonnera pour les autres téléopérateurs.</span><span class="sxs-lookup"><span data-stu-id="100cc-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="100cc-120">Cet article s’applique à Microsoft teams et à Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="100cc-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="100cc-121">Étape 1 : prendre en main</span><span class="sxs-lookup"><span data-stu-id="100cc-121">Step 1 — Get started</span></span>

<span data-ttu-id="100cc-122">Pour commencer à utiliser les files d’attente d’appels, il est important de garder à l’esprit les points suivants :</span><span class="sxs-lookup"><span data-stu-id="100cc-122">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="100cc-123">Une file d’attente d’appels doit avoir un compte de ressources associé.</span><span class="sxs-lookup"><span data-stu-id="100cc-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="100cc-124">Pour plus d’informations sur les comptes de ressources, voir [gérer les comptes de ressources dans teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="100cc-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="100cc-125">Lorsque vous attribuez un numéro de téléphone à un compte de ressources, vous pouvez désormais utiliser la [licence utilisateur virtuel](teams-add-on-licensing/virtual-user.md)du système téléphonique sans frais.</span><span class="sxs-lookup"><span data-stu-id="100cc-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="100cc-126">Le système téléphonique autorise les numéros de téléphone au niveau de l’Organisation pour une standardisation automatique et des services de files d’attente de faible coût.</span><span class="sxs-lookup"><span data-stu-id="100cc-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="100cc-127">Les numéros de service de routage direct pour les files d’attente d’appels sont pris en charge pour les utilisateurs et agents Microsoft teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="100cc-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="100cc-128">Pour rediriger les appels vers des utilisateurs de votre organisation qui sont en ligne, ils doivent disposer d’une licence de **système téléphonique** et être activés pour Enterprise Voice ou disposer d’offres d’appels d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="100cc-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="100cc-129">Consultez la rubrique [affectation de licences Skype entreprise](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [affectation de licences Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="100cc-129">See [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="100cc-130">Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="100cc-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="100cc-131">Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="100cc-131">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="100cc-132">Pour en savoir plus sur les offres d’appels d’Office 365, voir [système téléphonique et](calling-plan-landing-page.md) offres d’appel et [forfaits pour Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="100cc-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="100cc-133">Vous ne pouvez attribuer des files d’attente d’appels Cloud qu’aux numéros de téléphone de service gratuits ou payants que vous avez dans le **Centre d’administration Microsoft teams** ou transférés à partir d’un autre fournisseur de service.</span><span class="sxs-lookup"><span data-stu-id="100cc-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="100cc-134">Les crédits de communication sont requis pour les numéros de service gratuits.</span><span class="sxs-lookup"><span data-stu-id="100cc-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="100cc-135">Les numéros de téléphone des utilisateurs (abonnés) ne peuvent pas être attribués aux numéros de service de file d’attente d’appels uniquement ou les numéros de téléphone gratuits peuvent être utilisés.</span><span class="sxs-lookup"><span data-stu-id="100cc-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="100cc-136">Les clients suivants sont pris en charge pour les agents d’appel associés à une file d’attente d’appels Cloud :</span><span class="sxs-lookup"><span data-stu-id="100cc-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="100cc-137">Client de bureau Skype entreprise 2016 (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="100cc-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="100cc-138">Client de bureau Lync 2013 (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="100cc-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="100cc-139">Tous les modèles de téléphone IP pris en charge par Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="100cc-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="100cc-140">Consultez [Obtention de numéros de téléphone pour Skype Entreprise Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="100cc-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="100cc-141">Client Skype entreprise pour Mac (version 16.8.196 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="100cc-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="100cc-142">Client Skype entreprise Android (version 6.16.0.9 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="100cc-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="100cc-143">Client Skype entreprise pour iPhone (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="100cc-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="100cc-144">Client Skype entreprise pour iPad (version 6.16.0 et versions ultérieures)</span><span class="sxs-lookup"><span data-stu-id="100cc-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="100cc-145">Client Microsoft Teams (versions 32 bits et 64 bits)</span><span class="sxs-lookup"><span data-stu-id="100cc-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="100cc-146">Client Microsoft teams Mac</span><span class="sxs-lookup"><span data-stu-id="100cc-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="100cc-147">Application Microsoft teams pour iPhone</span><span class="sxs-lookup"><span data-stu-id="100cc-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="100cc-148">Application Android Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="100cc-148">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="100cc-149">Les files d’attente d’appels disposant d’un numéro de routage direct ne seront pas prises en charge pour les clients Skype entreprise, les clients Lync ou les téléphones IP Skype entreprise en tant qu’agents.</span><span class="sxs-lookup"><span data-stu-id="100cc-149">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span> 

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="100cc-150">Étape 2 : Obtient ou transfère des numéros de service gratuits ou payants</span><span class="sxs-lookup"><span data-stu-id="100cc-150">Step 2 — Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="100cc-151">Pour pouvoir créer et configurer vos files d’attente d’appels, vous devez obtenir ou transférer vos numéros de service gratuits ou payants existants.</span><span class="sxs-lookup"><span data-stu-id="100cc-151">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="100cc-152">Une fois que vous avez obtenu**les numéros de** téléphone de service gratuits ou payants, ils s’affichent dans les >**numéros** > de téléphone > **vocaux** > du **Centre d’administration Microsoft teams**et le **type de numéro** est répertorié en tant que **service,** gratuit.</span><span class="sxs-lookup"><span data-stu-id="100cc-152">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers** > **ADD** >, and the **Number type** will be listed as **Service — Toll-Free**.</span></span> <span data-ttu-id="100cc-153">Pour obtenir vos numéros de service, reportez-vous à la rubrique [obtention de numéros de service](getting-service-phone-numbers.md) ou, si vous souhaitez transférer un numéro de service existant, reportez-vous à la section transférer des [numéros de téléphone vers Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="100cc-153">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="100cc-154">Si vous résidez en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration de Microsoft teams pour obtenir des numéros de service.</span><span class="sxs-lookup"><span data-stu-id="100cc-154">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="100cc-155">Pour plus d’informations sur la [gestion des numéros de téléphone de votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , voir gérer les numéros de téléphone situés en dehors des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="100cc-155">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="100cc-156">Lorsque vous configurez plusieurs standards automatiques, il est possible que vous affectiez uniquement un numéro de téléphone au compte de ressources principal du standard automatique, qui peut diriger les appelants vers vos files d’attente d’appels ou standards automatiques imbriqués.</span><span class="sxs-lookup"><span data-stu-id="100cc-156">When setting up multiple auto attendants you may only assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="100cc-157">Dans ces situations, vous créez tous les standards automatiques et les files d’attente d’appels dans votre système sans affecter d’options de clavier numérique, puis modifiez les paramètres ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="100cc-157">In those situations, you create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="100cc-158">Cela est nécessaire, car vous n’êtes pas autorisé à créer une option de liaison vers une file d’attente d’appels ou un standard automatique qui n’existe pas encore.</span><span class="sxs-lookup"><span data-stu-id="100cc-158">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>

## <a name="step-3--create-a-new-call-queue"></a><span data-ttu-id="100cc-159">Étape 3 : création d’une file d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="100cc-159">Step 3 — Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="100cc-160">Chaque file d’attente d’appels doit avoir un [compte de ressources](manage-resource-accounts.md)associé.</span><span class="sxs-lookup"><span data-stu-id="100cc-160">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="100cc-161">Vous devez d’abord créer le compte de ressources, puis vous pouvez l’associer à la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-161">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="100cc-162">Utilisation du centre d’administration Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="100cc-162">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="100cc-163">Dans le **Centre d’administration de Microsoft teams**, les**files d’attente d’appels** **vocaux** > , puis cliquez sur **+ Ajouter nouveau**:</span><span class="sxs-lookup"><span data-stu-id="100cc-163">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="100cc-164">Définir le nom d’affichage de la file d’attente d’appels et le compte de ressources</span><span class="sxs-lookup"><span data-stu-id="100cc-164">Set the call queue display name and resource account</span></span>

![Capture d’écran d’une nouvelle file d’attente d’appels avec des légendes numérotées](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="100cc-166">![Icône du numéro 1, qui référence une légende dans le](media/sfbcallout1.png)
**nom** de la capture d’écran précédente, entrez un nom d’affichage descriptif pour la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-166">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="100cc-167">Ce nom est obligatoire et peut contenir jusqu’à 64 caractères, y compris des espaces.</span><span class="sxs-lookup"><span data-stu-id="100cc-167">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="100cc-168">Ce nom s’affiche dans la notification de l’appel entrant.</span><span class="sxs-lookup"><span data-stu-id="100cc-168">This name is displayed in the notification for the incoming call.</span></span>

* * *

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

<span data-ttu-id="100cc-170">**Ajouter des comptes** Sélectionnez un compte de ressources.</span><span class="sxs-lookup"><span data-stu-id="100cc-170">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="100cc-171">Le compte de ressource est ou n’est pas associé à un numéro de service payant ou gratuit pour la file d’attente d’appels, mais chaque file d’attente d’appels nécessite un compte de ressources associé.</span><span class="sxs-lookup"><span data-stu-id="100cc-171">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="100cc-172">S’il n’y figure pas, vous devez obtenir des numéros de service et les affecter à un compte de ressources avant de pouvoir créer cette file d’attente d’appels, comme décrit précédemment.</span><span class="sxs-lookup"><span data-stu-id="100cc-172">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="100cc-173">Pour obtenir vos numéros de service, consultez la rubrique [obtention de numéros de téléphone de service](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="100cc-173">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="100cc-174">Pour créer un compte de ressources, voir [gérer les comptes de ressources dans teams](manage-resource-accounts.md) si vous souhaitez que votre file d’attente d’appels dispose d’un numéro de téléphone associé.</span><span class="sxs-lookup"><span data-stu-id="100cc-174">You create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="100cc-175">Le cas échéant, ou si vous avez besoin d’affecter un **domaine** , vous pouvez l’affecter au compte de ressources de la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-175">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="100cc-176">Définir le message d’accueil et la musique lue pendant la mise en attente</span><span class="sxs-lookup"><span data-stu-id="100cc-176">Set the greeting and music played while on hold</span></span>

![capture d’écran des options de salutation et de musique, avec des légendes numérotées](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

<span data-ttu-id="100cc-179">Le **message d’accueil** est facultatif.</span><span class="sxs-lookup"><span data-stu-id="100cc-179">**Greeting** is optional.</span></span> <span data-ttu-id="100cc-180">Il s’agit du message d’accueil qui est lu pour les personnes qui rejoignent le numéro de la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-180">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="100cc-181">Vous pouvez charger un fichier audio (formats. wav,. mp3 ou. WMA).</span><span class="sxs-lookup"><span data-stu-id="100cc-181">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

<span data-ttu-id="100cc-183">**Attente musicale** Vous pouvez utiliser l’attente de musique par défaut fournie avec la file d’attente d’appels ou vous pouvez charger un fichier audio au format. wav,. mp3 ou. WMA à utiliser comme votre musique personnalisée en attente.</span><span class="sxs-lookup"><span data-stu-id="100cc-183">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="100cc-184">Sélectionner les options de répondeur automatique</span><span class="sxs-lookup"><span data-stu-id="100cc-184">Select the call answering options</span></span>

![Capture d’écran des options de répondeur automatique](media/5d249515-d532-4af2-90da-011404028b89.png) 

<span data-ttu-id="100cc-186">Pour ajouter des agents directement, sans les ajouter à un groupe, cliquez sur **Ajouter des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="100cc-186">To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="100cc-187">Placez les agents individuels dans l’ordre dans lequel vous souhaitez qu’ils reçoivent l’appel.</span><span class="sxs-lookup"><span data-stu-id="100cc-187">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="100cc-188">Vous pouvez ajouter jusqu’à 20 agents individuels (pour ajouter plus de 20, les placer dans un groupe).</span><span class="sxs-lookup"><span data-stu-id="100cc-188">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="100cc-189">Les appels sont d’abord routés vers des agents individuels, puis vers les agents en groupes.</span><span class="sxs-lookup"><span data-stu-id="100cc-189">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="100cc-190">Vous pouvez sélectionner jusqu’à 200 opérateurs d’appel qui appartiennent à l’une des listes de diffusion ou groupes suivantes :</span><span class="sxs-lookup"><span data-stu-id="100cc-190">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="100cc-191">Groupe Office 365</span><span class="sxs-lookup"><span data-stu-id="100cc-191">Office 365 group</span></span>
- <span data-ttu-id="100cc-192">Groupe de sécurité</span><span class="sxs-lookup"><span data-stu-id="100cc-192">Security group</span></span>
- <span data-ttu-id="100cc-193">Liste de distribution</span><span class="sxs-lookup"><span data-stu-id="100cc-193">Distribution list</span></span>

<span data-ttu-id="100cc-194">Les agents d’appel sélectionnés doivent être l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="100cc-194">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="100cc-195">Utilisateurs en ligne avec une licence de système téléphonique et la voix entreprise activée</span><span class="sxs-lookup"><span data-stu-id="100cc-195">Online users with a Phone System license and Enterprise Voice enabled</span></span> 
- <span data-ttu-id="100cc-196">Utilisateurs en ligne avec un plan d’appels</span><span class="sxs-lookup"><span data-stu-id="100cc-196">Online users with a Calling Plan</span></span>
- <span data-ttu-id="100cc-197">Utilisateurs de Skype entreprise sur site</span><span class="sxs-lookup"><span data-stu-id="100cc-197">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="100cc-198">Cela s’applique également si vous souhaitez rediriger les appels vers des utilisateurs de votre organisation qui sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="100cc-198">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="100cc-199">Ces personnes doivent disposer d’une licence de **système téléphonique** et d’une voix entreprise activée **ou** avoir un plan d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-199">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="100cc-200">Pour plus d’informations, reportez-vous à la section [affectation de licences Skype entreprise](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [attribution de licences Microsoft teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)ou le [plan d’appels qui vous convient ?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="100cc-200">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="100cc-201">Pour activer un agent pour voix entreprise, vous pouvez utiliser Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="100cc-201">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="100cc-202">Par exemple, exécutez :`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="100cc-202">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="100cc-203">Utilisateurs disposant d’une licence de **système téléphonique** ou d’une offre d’appels ajoutée à un groupe Office 365 ; Liste de distribution à extension messagerie ; ou un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="100cc-203">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="100cc-204">La réception d’appels à partir d’une file d’attente peut durer jusqu’à trois heures pour un agent nouvellement ajouté dans une liste de distribution ou un groupe de sécurité.</span><span class="sxs-lookup"><span data-stu-id="100cc-204">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="100cc-205">Une liste de distribution ou un groupe de sécurité nouvellement créé peut nécessiter jusqu’à 48 heures de disponibilité pour une utilisation avec des files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-205">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="100cc-206">Les nouveaux groupes Office 365 sont disponibles presque immédiatement.</span><span class="sxs-lookup"><span data-stu-id="100cc-206">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="100cc-207">Si vos agents utilisent l’application Microsoft teams pour effectuer des appels de file d’attente d’appels, ils doivent être en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="100cc-207">If your agents are using Microsoft Teams App to take call queue calls, they need to be in TeamsOnly mode.</span></span>

![Capture d’écran du volet ajouter des agents d’appel](media/skype-for-business-add-agents-to-call-queue.png)

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

<span data-ttu-id="100cc-210">**Méthode de routage** Vous pouvez choisir **standard**, **série**ou **tourniquet** pour la méthode de distribution de votre file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-210">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="100cc-211">La totalité des files d’attente d’appels nouvelles et existantes est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="100cc-211">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="100cc-212">Lorsque le routage standard est utilisé, le premier appel dans la file d’attente sonne sur tous les agents d’appel en même temps.</span><span class="sxs-lookup"><span data-stu-id="100cc-212">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="100cc-213">Le premier agent d’appel pour décrocher l’appel obtient l’appel.</span><span class="sxs-lookup"><span data-stu-id="100cc-213">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="100cc-214">Le routage de l' **attendant** entraîne le premier appel dans la file d’attente pour sonner tous les agents d’appel en même temps.</span><span class="sxs-lookup"><span data-stu-id="100cc-214">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="100cc-215">Le premier agent d’appel pour décrocher l’appel obtient l’appel.</span><span class="sxs-lookup"><span data-stu-id="100cc-215">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="100cc-216">**Routage en série** les appels entrants sonnent un par un, en commençant par le début de la liste des agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="100cc-216">**Serial routing** incoming calls ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="100cc-217">Les agents ne peuvent pas être commandés dans la liste des agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="100cc-217">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="100cc-218">Si un agent est rejeté ou ne décroche pas d’appel, l’appel sonnera sur l’agent suivant dans la liste et tentera d’avoir accès à tous les agents un par un jusqu’à ce qu’il soit décroché ou arrive à expiration dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="100cc-218">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="100cc-219">Le routage en série ignorera les agents qui sont **hors ligne**, ont défini leur présence sur **ne pas déranger**ou a **refusé** d’obtenir des appels à partir de cette file d’attente.</span><span class="sxs-lookup"><span data-stu-id="100cc-219">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="100cc-220">**Tourniquet de tourniquet** qui achemine les appels entrants de telle sorte que chaque agent d’appel obtient le même nombre d’appels à partir de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="100cc-220">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="100cc-221">Cela pourrait être souhaitable dans un environnement de ventes entrantes pour garantir l’égalité des chances entre tous les agents d’appel.</span><span class="sxs-lookup"><span data-stu-id="100cc-221">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="100cc-222">Sélectionner une option d’annulation d’agent</span><span class="sxs-lookup"><span data-stu-id="100cc-222">Select an agent opt-out option</span></span>

![Capture d’écran des options d’annulation d’agent, avec des légendes numérotées](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

<span data-ttu-id="100cc-225">**L’agent peut refuser d'** avoir accès aux appels Vous pouvez choisir d’autoriser les agents de files d’attente d’appels à refuser d’effectuer des appels à partir d’une file d’attente particulière en activant cette option.</span><span class="sxs-lookup"><span data-stu-id="100cc-225">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="100cc-226">L’activation de cette option permet à tous les agents de cette file d’attente de démarrer ou d’arrêter de recevoir des appels à partir de la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-226">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="100cc-227">Vous pouvez révoquer les privilèges d’annulation de l’agent à tout moment en désactivant la case à cocher, pour que les agents le fassent automatiquement pour cette file d’attente (paramètre par défaut pour tous les agents).</span><span class="sxs-lookup"><span data-stu-id="100cc-227">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="100cc-228">Pour accéder à l’option d’annulation, les agents peuvent procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="100cc-228">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="100cc-229">Ouvrez les **options** de votre client Skype entreprise de bureau.</span><span class="sxs-lookup"><span data-stu-id="100cc-229">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="100cc-230">Dans l’onglet **transfert d’appel** , cliquez sur le lien modifier les **paramètres en ligne** .</span><span class="sxs-lookup"><span data-stu-id="100cc-230">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="100cc-231">Dans la page Paramètres utilisateur, cliquez sur **files d’attente d’appels**, puis désactivez les cases à cocher correspondant aux files d’attente pour lesquelles elles doivent être refusées.</span><span class="sxs-lookup"><span data-stu-id="100cc-231">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="100cc-232">Les agents qui utilisent des applications ou des points de terminaison autres que le bureau Skype entreprise peuvent accéder à l’option d’annulation [https://aka.ms/cqsettings](https://aka.ms/cqsettings)du portail des paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="100cc-232">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="100cc-233">Si les agents se trouvent dans des clients de bureau Microsoft Teams, ils peuvent refuser l’appel en utilisant les paramètres d’appel.</span><span class="sxs-lookup"><span data-stu-id="100cc-233">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

![capture d’écran des paramètres d’appel en annulation](media/create-a-phone-system-call-queue-image1.png)

<span data-ttu-id="100cc-235">![Icône du numéro 2 qui référence une légende dans le](media/sfbcallout2.png)
**paramètre alerte** de l’agent de capture d’écran précédent</span><span class="sxs-lookup"><span data-stu-id="100cc-235">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="100cc-236">Cela définit la durée d’un appel de l’agent pour être averti de l’appel avant que les méthodes de routage par série ou par répétition alternées soient déplacées vers l’agent suivant.</span><span class="sxs-lookup"><span data-stu-id="100cc-236">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="100cc-237">Le paramètre par défaut est de 30 secondes, mais peut être configuré pour une durée de 3 minutes maximum.</span><span class="sxs-lookup"><span data-stu-id="100cc-237">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="100cc-238">Définir les options de dépassement d’appel et de gestion des délais d’expiration</span><span class="sxs-lookup"><span data-stu-id="100cc-238">Set the call overflow and timeout handling options</span></span>

![Capture d’écran des options de traitement de dépassement de capacité, avec des légendes numérotées](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/sfbcallout1.png)

<span data-ttu-id="100cc-241">**Nombre maximal d’appels dans la file d’attente** Utilisez cette valeur pour définir le nombre maximal d’appels qui peuvent attendre dans la file d’attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="100cc-241">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="100cc-242">La valeur par défaut est 50, mais elle peut varier entre 0 et 200.</span><span class="sxs-lookup"><span data-stu-id="100cc-242">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="100cc-243">Lorsque cette limite est atteinte, l’appel est géré selon la configuration du paramètre **lorsque le nombre maximal d’appels est atteint** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="100cc-243">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/sfbcallout2.png)

<span data-ttu-id="100cc-245">**Lorsque le nombre maximum d’appels est atteint** Lorsque la file d’attente des appels atteint sa taille maximale (définie en utilisant le **nombre maximal d’appels dans la file d’attente** ), vous pouvez choisir ce qu’il advient des nouveaux appels entrants.</span><span class="sxs-lookup"><span data-stu-id="100cc-245">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="100cc-246">Se **déconnecter** L’appel est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="100cc-246">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="100cc-247">**Rediriger vers** Lorsque vous choisissez cette option, sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="100cc-247">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="100cc-248">**Personne de votre entreprise** Un utilisateur en ligne disposant d’une licence de **système téléphonique** et est activé pour voix entreprise ou avoir un plan d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-248">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="100cc-249">Vous pouvez la configurer de manière à ce que l’appelant puisse être dirigé vers la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="100cc-249">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="100cc-250">Pour cela, sélectionnez une **personne au sein de votre entreprise** et configurez cette personne pour que les appels soient transférés directement à la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="100cc-250">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="100cc-251">Pour en savoir plus sur les licences requises pour la boîte vocale, consultez la rubrique [configurer la messagerie vocale Cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="100cc-251">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="100cc-252">**Application vocale** Sélectionnez le nom d’un compte de ressources associé à une file d’attente d’appels ou à un standard automatique que vous avez déjà créé.</span><span class="sxs-lookup"><span data-stu-id="100cc-252">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![Icône du numéro 3 qui référence une légende dans la capture d’écran précédente](media/sfbcallout3.png)

<span data-ttu-id="100cc-254">**Délai d’appel : délai d’attente maximum** Vous pouvez également décider du temps qu’un appel peut mettre en attente dans la file d’attente avant qu’il arrive à expiration, et qu’il doive être redirigé ou déconnecté.</span><span class="sxs-lookup"><span data-stu-id="100cc-254">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="100cc-255">Le moment où il est redirigé dépend de la façon dont vous définissez le paramètre à la **fin de l’appel** .</span><span class="sxs-lookup"><span data-stu-id="100cc-255">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="100cc-256">Vous pouvez définir une heure comprise entre 0 et 45 minutes.</span><span class="sxs-lookup"><span data-stu-id="100cc-256">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="100cc-257">La valeur Timeout peut être définie en secondes, à des intervalles de 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="100cc-257">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="100cc-258">Cela vous permet de manipuler le flux d’appels avec une granularité plus fine.</span><span class="sxs-lookup"><span data-stu-id="100cc-258">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="100cc-259">Par exemple, vous pouvez spécifier que les appels qui ne sont pas traités par un agent dans un délai de 30 secondes s’exécutent dans un standard automatique de recherche d’annuaires.</span><span class="sxs-lookup"><span data-stu-id="100cc-259">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Icône du numéro 4, référençant une légende dans la capture d’écran précédente](media/sfbcallout4.png)

<span data-ttu-id="100cc-261">**Lorsque** le délai d’appel est épuisé Lorsque l’appel atteint la limite définie en fonction de la **durée pendant laquelle un appel peut patienter dans la file d’attente** , vous pouvez choisir ce qu’il advient de cet appel :</span><span class="sxs-lookup"><span data-stu-id="100cc-261">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="100cc-262">Se **déconnecter** L’appel est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="100cc-262">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="100cc-263">**Rediriger cet appel vers** Lorsque vous choisissez cette option, vous disposez des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="100cc-263">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="100cc-264">**Personne de votre entreprise** Un utilisateur en ligne disposant d’une licence de **système téléphonique** et est activé pour voix entreprise ou avec des plans d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-264">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="100cc-265">Vous pouvez le régler pour que la personne appelant soit redirigée vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="100cc-265">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="100cc-266">Pour cela, sélectionnez une **personne au sein de votre entreprise** et configurez cette personne pour que les appels soient transférés directement à la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="100cc-266">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="100cc-267">Pour en savoir plus sur les licences requises pour la boîte vocale, consultez la rubrique [configurer la messagerie vocale Cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="100cc-267">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="100cc-268">**Application vocale** Sélectionnez le nom d’un compte de ressources associé à une file d’attente d’appels ou à un standard automatique que vous avez déjà créé.</span><span class="sxs-lookup"><span data-stu-id="100cc-268">**Voice application** Select the name of a resource account associated with either a call queue or auto attendant that has already been created.</span></span>

## <a name="change-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="100cc-269">Modification de l’ID d’appelant d’un utilisateur pour les appels sortants</span><span class="sxs-lookup"><span data-stu-id="100cc-269">Change a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="100cc-270">Vous pouvez protéger l’identité d’un utilisateur en modifiant son ID d’appelant pour les appels sortants vers une file d’attente d’appels, le standard automatique ou n’importe quel numéro de service à l’aide de l’applet **de nouvelle cmdlet New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="100cc-270">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="100cc-271">Pour cela, exécutez :</span><span class="sxs-lookup"><span data-stu-id="100cc-271">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="100cc-272">Appliquez ensuite la stratégie à l’utilisateur à l’aide de l’applet **de demande Grant-CallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="100cc-272">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="100cc-273">Pour cela, exécutez :</span><span class="sxs-lookup"><span data-stu-id="100cc-273">To do this, run:</span></span>

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="100cc-274">Pour plus d’informations sur la configuration des paramètres d’identification de l’appelant au sein de votre organisation, consultez l’article [Comment l’identification de l’appelant peut être utilisée au sein de votre organisation](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="100cc-274">You can get more information on how to set caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="100cc-275">Cmdlets de files d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="100cc-275">Call queue cmdlets</span></span>

<span data-ttu-id="100cc-276">Vous pouvez également utiliser Windows PowerShell pour créer et configurer des files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-276">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="100cc-277">Voici les applets de passe que vous utilisez pour gérer une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="100cc-277">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="100cc-278">Nouveau-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="100cc-278">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="100cc-279">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="100cc-279">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="100cc-280">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="100cc-280">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="100cc-281">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="100cc-281">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="100cc-282">Informations supplémentaires sur PowerShell Windows</span><span class="sxs-lookup"><span data-stu-id="100cc-282">More about Windows PowerShell</span></span>

- <span data-ttu-id="100cc-283">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="100cc-283">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="100cc-284">Windows PowerShell vous permet de gérer Office 365 et Microsoft teams grâce à un point d’administration unique qui peut vous simplifier le travail quotidien lorsque vous avez plusieurs tâches à effectuer.</span><span class="sxs-lookup"><span data-stu-id="100cc-284">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="100cc-285">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="100cc-285">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="100cc-286">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="100cc-286">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="100cc-287">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="100cc-287">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="100cc-288">Windows PowerShell offre de nombreux avantages en termes de rapidité, de simplicité et de productivité par le biais du centre d’administration Microsoft Teams, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="100cc-288">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="100cc-289">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="100cc-289">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="100cc-290">Gérer Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="100cc-290">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="100cc-291">Configurer votre ordinateur pour Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="100cc-291">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="100cc-292">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="100cc-292">Related topics</span></span>

[<span data-ttu-id="100cc-293">Voici les avantages du système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="100cc-293">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="100cc-294">Obtention de numéros de téléphone de service</span><span class="sxs-lookup"><span data-stu-id="100cc-294">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="100cc-295">Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays</span><span class="sxs-lookup"><span data-stu-id="100cc-295">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="100cc-296">Nouveau-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="100cc-296">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
