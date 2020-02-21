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
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Page d’accueil pour le routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: d643c137145649c0843296300a909c520ba653a6
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157902"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="8ebc0-103">Routage direct via le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="8ebc0-103">Phone System Direct Routing</span></span>

<span data-ttu-id="8ebc0-104">Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="8ebc0-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="8ebc0-105">Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="8ebc0-106">Vous avez peut-être déployé des [réunions & des conférences](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="8ebc0-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="8ebc0-107">Vous êtes désormais prêt à ajouter des charges de travail audio Cloud et vous avez décidé d’utiliser votre propre opérateur de téléphonie pour une connectivité de réseau téléphonique commuté (PSTN) à l’aide du routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="8ebc0-108">Avec le routage direct, vous pouvez utiliser le système téléphonique avec quasiment n’importe quel opérateur de téléphonie.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="8ebc0-109">Cet article décrit les décisions de déploiement principales pour le routage direct ainsi que les considérations supplémentaires dont vous pouvez penser en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="8ebc0-110">Pour plus d’informations sur les services vocaux Cloud de Microsoft, consultez également la [voix Cloud de Microsoft teams](cloud-voice-landing-page.md) .</span><span class="sxs-lookup"><span data-stu-id="8ebc0-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="8ebc0-111">En savoir plus sur le routage direct</span><span class="sxs-lookup"><span data-stu-id="8ebc0-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="8ebc0-112">Les articles suivants fournissent des informations supplémentaires sur la configuration et l’utilisation du routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="8ebc0-113">La configuration du routage direct nécessite une bonne compréhension de la conception du routage PSTN.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="8ebc0-114">Nous vous conseillons de lire tous les articles suivants pour comprendre comment planifier et configurer le routage direct :</span><span class="sxs-lookup"><span data-stu-id="8ebc0-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="8ebc0-115">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="8ebc0-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="8ebc0-116">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="8ebc0-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="8ebc0-117">Liste des contrôleurs de frontière de session certifiés pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="8ebc0-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="8ebc0-118">Contrôler et dépanner le routage direct</span><span class="sxs-lookup"><span data-stu-id="8ebc0-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="8ebc0-119">Par ailleurs, vous souhaiterez peut-être lire les articles suivants selon vos besoins :</span><span class="sxs-lookup"><span data-stu-id="8ebc0-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="8ebc0-120">Configurer un contrôleur de frontière de session pour plusieurs clients</span><span class="sxs-lookup"><span data-stu-id="8ebc0-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="8ebc0-121">Migrer vers un routage direct</span><span class="sxs-lookup"><span data-stu-id="8ebc0-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="8ebc0-122">Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN</span><span class="sxs-lookup"><span data-stu-id="8ebc0-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="8ebc0-123">Regardez la session suivante pour en savoir plus sur le routage direct : [routage direct dans Microsoft teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="8ebc0-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="8ebc0-124">Décisions liées au déploiement Core</span><span class="sxs-lookup"><span data-stu-id="8ebc0-124">Core deployment decisions</span></span>

<span data-ttu-id="8ebc0-125">Voici les principales décisions à prendre en considération pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="8ebc0-126">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8ebc0-126">Ask yourself</span></span>|<span data-ttu-id="8ebc0-127">Action</span><span class="sxs-lookup"><span data-stu-id="8ebc0-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="8ebc0-128">Pour quels utilisateurs le routage direct est-il activé ?</span><span class="sxs-lookup"><span data-stu-id="8ebc0-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="8ebc0-129">Pour plus d’informations, voir [activer les utilisateurs pour le service de routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="8ebc0-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="8ebc0-130">Est-ce que je dispose des licences requises pour le routage direct ?</span><span class="sxs-lookup"><span data-stu-id="8ebc0-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="8ebc0-131">Pour plus d’informations, reportez-vous à la rubrique [licences et autres exigences](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="8ebc0-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="8ebc0-132">Considérations en matière de contrôleur de bordure de session (SBC)</span><span class="sxs-lookup"><span data-stu-id="8ebc0-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="8ebc0-133">Avec le routage direct, vous connectez votre propre contrôleur de bordure de session (SBC) directement au système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="8ebc0-134">Pour obtenir la liste des [contrôleurs de frontière de session, voir prises en charge](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="8ebc0-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="8ebc0-135">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8ebc0-135">Ask yourself</span></span>|<span data-ttu-id="8ebc0-136">Action</span><span class="sxs-lookup"><span data-stu-id="8ebc0-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8ebc0-137">Où et comment dois-je déployer SBCs ?</span><span class="sxs-lookup"><span data-stu-id="8ebc0-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="8ebc0-138">Pour plus d’informations, consultez [configurer le routage direct](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="8ebc0-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="8ebc0-139">Ai-je besoin de plusieurs clients ?</span><span class="sxs-lookup"><span data-stu-id="8ebc0-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="8ebc0-140">Pour plus d’informations, consultez [configurer un contrôleur de bordure de session pour plusieurs clients](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="8ebc0-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="8ebc0-141">Considérations relatives au routage vocal</span><span class="sxs-lookup"><span data-stu-id="8ebc0-141">Voice routing considerations</span></span>

<span data-ttu-id="8ebc0-142">Vous devez configurer le système téléphonique pour acheminer les appels vers l’objet SBCs spécifique.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="8ebc0-143">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8ebc0-143">Ask yourself</span></span>|<span data-ttu-id="8ebc0-144">Action</span><span class="sxs-lookup"><span data-stu-id="8ebc0-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="8ebc0-145">Quelles sont les stratégies de routage vocal, l’utilisation RTC et les itinéraires vocaux nécessaires ?</span><span class="sxs-lookup"><span data-stu-id="8ebc0-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="8ebc0-146">Pour plus d’informations sur le routage vocal, voir [configurer le routage](direct-routing-configure.md)de la voix.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="8ebc0-147">Quels utilisateurs seront attribués à la stratégie de routage vocale que j’ai définie ?</span><span class="sxs-lookup"><span data-stu-id="8ebc0-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="8ebc0-148">Pour plus d’exemples, voir [configurer le routage](direct-routing-configure.md)de la voix.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="8ebc0-149">Faire en sorte que les appels entrants soient dans le client teams à l’aide de TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="8ebc0-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="8ebc0-150">Le routage direct est uniquement pris en charge par Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="8ebc0-151">Pour recevoir des appels RTC via le routage direct, vous devez configurer TeamsUpgradePolicy pour vous assurer que les appels entrants sont reçus dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="8ebc0-152">Les utilisateurs doivent être en mode d’équipe uniquement, ce que vous pouvez faire en leur attribuant l’instance « UpgradeToTeams » de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="8ebc0-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="8ebc0-153">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8ebc0-153">Ask yourself</span></span>|<span data-ttu-id="8ebc0-154">Action</span><span class="sxs-lookup"><span data-stu-id="8ebc0-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="8ebc0-155">Que signifie le mode équipes uniquement ?</span><span class="sxs-lookup"><span data-stu-id="8ebc0-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="8ebc0-156">Pour plus d’informations, reportez-vous à la rubrique [Guide de migration et d’interopérabilité pour les organisations qui utilisent des équipes dans Skype entreprise](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="8ebc0-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="8ebc0-157">Considérations relatives au déploiement supplémentaire</span><span class="sxs-lookup"><span data-stu-id="8ebc0-157">Additional deployment considerations</span></span>

<span data-ttu-id="8ebc0-158">Vous voudrez peut-être prendre en compte les éléments suivants, en fonction des besoins et de la configuration de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="8ebc0-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="8ebc0-159">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="8ebc0-159">Ask yourself</span></span>| <span data-ttu-id="8ebc0-160">Action</span><span class="sxs-lookup"><span data-stu-id="8ebc0-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="8ebc0-161">Avez-vous déjà un déploiement Skype entreprise Server avec connectivité hybride configuré ?</span><span class="sxs-lookup"><span data-stu-id="8ebc0-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="8ebc0-162">Pour mieux comprendre comment le déploiement et la gestion des comptes d’utilisateurs dans un environnement hybride, voir [comptes d’utilisateurs dans un environnement hybride avec connectivité PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8ebc0-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="8ebc0-163">Migrez-vous vers le routage direct à partir d’un plan d’appels ou d’un environnement Skype entreprise local ?</span><span class="sxs-lookup"><span data-stu-id="8ebc0-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="8ebc0-164">Pour en savoir plus sur la migration vers le routage direct à partir d’un environnement existant, reportez-vous à la rubrique [migration vers le routage direct](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="8ebc0-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
