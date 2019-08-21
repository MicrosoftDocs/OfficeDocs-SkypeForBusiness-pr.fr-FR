---
title: Routage direct via le système téléphonique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1keywords: ms.teamsadmincenter.directrouting.overview
description: Page d’accueil pour le routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: 965fb26aee3d83550740e2ae7f855559fd9cdb79
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484058"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="465e6-103">Routage direct via le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="465e6-103">Phone System Direct Routing</span></span>

<span data-ttu-id="465e6-104">Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="465e6-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="465e6-105">Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="465e6-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="465e6-106">Vous avez peut-être déployé des [réunions & des conférences](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="465e6-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="465e6-107">Vous êtes désormais prêt à ajouter des charges de travail audio Cloud et vous avez décidé d’utiliser votre propre opérateur de téléphonie pour une connectivité de réseau téléphonique commuté (PSTN) à l’aide du routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="465e6-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="465e6-108">Avec le routage direct, vous pouvez utiliser le système téléphonique avec quasiment n’importe quel opérateur de téléphonie.</span><span class="sxs-lookup"><span data-stu-id="465e6-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="465e6-109">Cet article décrit les décisions de déploiement principales pour le routage direct ainsi que les considérations supplémentaires dont vous pouvez penser en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="465e6-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="465e6-110">Pour plus d’informations sur les services vocaux Cloud de Microsoft, consultez également la [voix Cloud de Microsoft teams](cloud-voice-landing-page.md) .</span><span class="sxs-lookup"><span data-stu-id="465e6-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="465e6-111">En savoir plus sur le routage direct</span><span class="sxs-lookup"><span data-stu-id="465e6-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="465e6-112">Les articles suivants fournissent des informations supplémentaires sur la configuration et l’utilisation du routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="465e6-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="465e6-113">La configuration du routage direct nécessite une bonne compréhension de la conception du routage PSTN.</span><span class="sxs-lookup"><span data-stu-id="465e6-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="465e6-114">Nous vous conseillons de lire tous les articles suivants pour comprendre comment planifier et configurer le routage direct:</span><span class="sxs-lookup"><span data-stu-id="465e6-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="465e6-115">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="465e6-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="465e6-116">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="465e6-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="465e6-117">Liste des contrôleurs de frontière de session certifiés pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="465e6-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="465e6-118">Contrôler et dépanner le routage direct</span><span class="sxs-lookup"><span data-stu-id="465e6-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="465e6-119">Par ailleurs, vous souhaiterez peut-être lire les articles suivants selon vos besoins:</span><span class="sxs-lookup"><span data-stu-id="465e6-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="465e6-120">Configurer un contrôleur de frontière de session pour plusieurs clients</span><span class="sxs-lookup"><span data-stu-id="465e6-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="465e6-121">Migrer vers un routage direct</span><span class="sxs-lookup"><span data-stu-id="465e6-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="465e6-122">Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN</span><span class="sxs-lookup"><span data-stu-id="465e6-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="465e6-123">Regardez la session suivante pour en savoir plus sur le routage direct: [routage direct dans Microsoft teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="465e6-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="465e6-124">Décisions liées au déploiement Core</span><span class="sxs-lookup"><span data-stu-id="465e6-124">Core deployment decisions</span></span>

<span data-ttu-id="465e6-125">Voici les principales décisions à prendre en considération pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="465e6-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="465e6-126">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="465e6-126">Ask yourself</span></span>|<span data-ttu-id="465e6-127">Action</span><span class="sxs-lookup"><span data-stu-id="465e6-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="465e6-128">Pour quels utilisateurs le routage direct est-il activé?</span><span class="sxs-lookup"><span data-stu-id="465e6-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="465e6-129">Pour plus d’informations, voir [activer les utilisateurs pour le service de routage direct](direct-routing-configure.md#enable-users-for-direct-routing-service).</span><span class="sxs-lookup"><span data-stu-id="465e6-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="465e6-130">Est-ce que je dispose des licences requises pour le routage direct?</span><span class="sxs-lookup"><span data-stu-id="465e6-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="465e6-131">Pour plus d’informations, reportez-vous à la rubrique [licences et autres exigences](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="465e6-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="465e6-132">Considérations en matière de contrôleur de bordure de session (SBC)</span><span class="sxs-lookup"><span data-stu-id="465e6-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="465e6-133">Avec le routage direct, vous connectez votre propre contrôleur de bordure de session (SBC) directement au système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="465e6-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="465e6-134">Pour obtenir la liste des contrôleurs de [frontière de session, voir prises en charge](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="465e6-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="465e6-135">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="465e6-135">Ask yourself</span></span>|<span data-ttu-id="465e6-136">Action</span><span class="sxs-lookup"><span data-stu-id="465e6-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="465e6-137">Où et comment dois-je déployer SBCs?</span><span class="sxs-lookup"><span data-stu-id="465e6-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="465e6-138">Pour plus d’informations, consultez [configurer le routage direct](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="465e6-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="465e6-139">Ai-je besoin de plusieurs clients?</span><span class="sxs-lookup"><span data-stu-id="465e6-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="465e6-140">Pour plus d’informations, consultez [configurer un contrôleur de bordure de session pour plusieurs clients](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="465e6-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="465e6-141">Considérations relatives au routage vocal</span><span class="sxs-lookup"><span data-stu-id="465e6-141">Voice routing considerations</span></span>

<span data-ttu-id="465e6-142">Vous devez configurer le système téléphonique pour acheminer les appels vers l’objet SBCs spécifique.</span><span class="sxs-lookup"><span data-stu-id="465e6-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="465e6-143">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="465e6-143">Ask yourself</span></span>|<span data-ttu-id="465e6-144">Action</span><span class="sxs-lookup"><span data-stu-id="465e6-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="465e6-145">Quelles sont les stratégies de routage vocal, l’utilisation RTC et les itinéraires vocaux nécessaires?</span><span class="sxs-lookup"><span data-stu-id="465e6-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="465e6-146">Pour plus d’informations sur le routage vocal, voir [configurer le routage](direct-routing-configure.md#configure-voice-routing)de la voix.</span><span class="sxs-lookup"><span data-stu-id="465e6-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="465e6-147">Quels utilisateurs seront attribués à la stratégie de routage vocale que j’ai définie?</span><span class="sxs-lookup"><span data-stu-id="465e6-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="465e6-148">Pour plus d’exemples, voir [configurer le routage](direct-routing-configure.md#configure-voice-routing)de la voix.</span><span class="sxs-lookup"><span data-stu-id="465e6-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="calling-and-interop-policies"></a><span data-ttu-id="465e6-149">Politiques d’appel et d’interopérabilité</span><span class="sxs-lookup"><span data-stu-id="465e6-149">Calling and interop policies</span></span>

<span data-ttu-id="465e6-150">Le routage direct est uniquement pris en charge par Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="465e6-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="465e6-151">Pour passer ou recevoir des appels RTC via le routage direct, vous devez configurer les stratégies nécessaires pour vérifier que les appels entrants sont reçus dans Teams.</span><span class="sxs-lookup"><span data-stu-id="465e6-151">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="465e6-152">Vous pouvez configurer les utilisateurs de manière à ce qu’ils configurent les équipes en tant que client préféré pour les appels en configurant le mode utilisateur pour les équipes uniquement ou en configurant les équipes en tant que client appelant préféré en attribuant le TeamsCallingPolicy et le TeamsInteropPolicy.</span><span class="sxs-lookup"><span data-stu-id="465e6-152">You can configure users to set Teams as their preferred client for calls by either configuring the user for Teams Only mode or configuring Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

|<span data-ttu-id="465e6-153">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="465e6-153">Ask yourself</span></span>|<span data-ttu-id="465e6-154">Action</span><span class="sxs-lookup"><span data-stu-id="465e6-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="465e6-155">Comment définir des équipes en tant que client préféré pour les appels?</span><span class="sxs-lookup"><span data-stu-id="465e6-155">How will I set Teams as the preferred client for calls?</span></span> | <span data-ttu-id="465e6-156">Pour plus d’informations, reportez-vous à [la section définir Microsoft teams en tant que client d’appel préféré pour les utilisateurs](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span><span class="sxs-lookup"><span data-stu-id="465e6-156">For more information, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="465e6-157">Considérations relatives au déploiement supplémentaire</span><span class="sxs-lookup"><span data-stu-id="465e6-157">Additional deployment considerations</span></span>

<span data-ttu-id="465e6-158">Vous voudrez peut-être prendre en compte les éléments suivants, en fonction des besoins et de la configuration de votre organisation:</span><span class="sxs-lookup"><span data-stu-id="465e6-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="465e6-159">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="465e6-159">Ask yourself</span></span>| <span data-ttu-id="465e6-160">Action</span><span class="sxs-lookup"><span data-stu-id="465e6-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="465e6-161">Avez-vous déjà un déploiement Skype entreprise Server avec connectivité hybride configuré?</span><span class="sxs-lookup"><span data-stu-id="465e6-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="465e6-162">Pour mieux comprendre comment le déploiement et la gestion des comptes d’utilisateurs dans un environnement hybride, voir [comptes d’utilisateurs dans un environnement hybride avec connectivité PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="465e6-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="465e6-163">Migrez-vous vers le routage direct à partir d’un plan d’appels ou d’un environnement Skype entreprise local?</span><span class="sxs-lookup"><span data-stu-id="465e6-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="465e6-164">Pour en savoir plus sur la migration vers le routage direct à partir d’un environnement existant, reportez-vous à la rubrique [migration vers le routage direct](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="465e6-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
