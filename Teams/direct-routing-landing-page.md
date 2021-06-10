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
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: En savoir plus sur le routage direct, comme la configuration, les décisions de déploiement essentielles nécessaires et les considérations relatives au routage vocal.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4298cc34122d6b3bb7d9f9bb1f8698aec864426f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122208"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="a7e71-103">Routage direct via le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="a7e71-103">Phone System Direct Routing</span></span>

<span data-ttu-id="a7e71-104">Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="a7e71-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="a7e71-105">Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a7e71-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="a7e71-106">Vous avez peut-être déployé [des réunions & conférences.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="a7e71-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="a7e71-107">Vous êtes maintenant prêt à ajouter des charges de travail vocales dans le cloud, et vous avez décidé d’utiliser votre propre opérateur de téléphonie pour la connectivité de réseau téléphonique public commuté (PSTN) à l’aide du Système téléphonique routage direct.</span><span class="sxs-lookup"><span data-stu-id="a7e71-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="a7e71-108">Le routage direct vous permet d’utiliser le système téléphonique avec presque tous les opérateurs.</span><span class="sxs-lookup"><span data-stu-id="a7e71-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="a7e71-109">Cet article décrit les principales décisions prises en matière de déploiement pour le routage direct, ainsi que des considérations supplémentaires à prendre en considération, en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a7e71-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="a7e71-110">Pour plus d’informations sur les offres vocales cloud de [Microsoft, vous](cloud-voice-landing-page.md) devez également lire l’Microsoft Teams Cloud Voice.</span><span class="sxs-lookup"><span data-stu-id="a7e71-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="a7e71-111">En savoir plus sur le routage direct</span><span class="sxs-lookup"><span data-stu-id="a7e71-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="a7e71-112">Les articles suivants fournissent des informations supplémentaires sur la configuration et l’utilisation Système téléphonique routage direct.</span><span class="sxs-lookup"><span data-stu-id="a7e71-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="a7e71-113">La configuration du routage direct nécessite une compréhension de la conception du routage PSTN.</span><span class="sxs-lookup"><span data-stu-id="a7e71-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="a7e71-114">Vous devez lire tous les articles suivants pour comprendre comment planifier et configurer le routage direct :</span><span class="sxs-lookup"><span data-stu-id="a7e71-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="a7e71-115">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="a7e71-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="a7e71-116">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="a7e71-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="a7e71-117">Liste des contrôleurs de frontière de session certifiés pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="a7e71-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="a7e71-118">Contrôler et dépanner le routage direct</span><span class="sxs-lookup"><span data-stu-id="a7e71-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="a7e71-119">En outre, vous souhaitez peut-être lire les articles suivants selon vos besoins :</span><span class="sxs-lookup"><span data-stu-id="a7e71-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="a7e71-120">Configurer un contrôleur de frontière de session pour plusieurs clients</span><span class="sxs-lookup"><span data-stu-id="a7e71-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="a7e71-121">Migrer vers un routage direct</span><span class="sxs-lookup"><span data-stu-id="a7e71-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="a7e71-122">Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN</span><span class="sxs-lookup"><span data-stu-id="a7e71-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="a7e71-123">Regardez la session suivante pour en savoir plus sur le routage direct : [routage direct dans Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="a7e71-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="a7e71-124">Décisions liées au déploiement Core</span><span class="sxs-lookup"><span data-stu-id="a7e71-124">Core deployment decisions</span></span>

<span data-ttu-id="a7e71-125">Il s’agit des principales décisions à prendre en considération pour le routage direct.</span><span class="sxs-lookup"><span data-stu-id="a7e71-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="a7e71-126">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="a7e71-126">Ask yourself</span></span>|<span data-ttu-id="a7e71-127">Action</span><span class="sxs-lookup"><span data-stu-id="a7e71-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="a7e71-128">Pour quels utilisateurs activer le routage direct ?</span><span class="sxs-lookup"><span data-stu-id="a7e71-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="a7e71-129">Pour plus d’informations, voir [Activer le service de routage direct pour les utilisateurs.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="a7e71-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="a7e71-130">Ai-je les licences requises pour le routage direct ?</span><span class="sxs-lookup"><span data-stu-id="a7e71-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="a7e71-131">Pour plus d’informations, voir [Licences et autres conditions requises.](direct-routing-plan.md#licensing-and-other-requirements)</span><span class="sxs-lookup"><span data-stu-id="a7e71-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="a7e71-132">Considérations en considérations du contrôleur de session border Controller (SBC)</span><span class="sxs-lookup"><span data-stu-id="a7e71-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="a7e71-133">Avec le routage direct, vous connectez votre propre contrôleur de session Border Controller (SBC) directement à Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="a7e71-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="a7e71-134">Pour obtenir la liste des SBCs [certifiés,](direct-routing-border-controllers.md)voir Contrôleurs de session en bordure pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a7e71-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="a7e71-135">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="a7e71-135">Ask yourself</span></span>|<span data-ttu-id="a7e71-136">Action</span><span class="sxs-lookup"><span data-stu-id="a7e71-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="a7e71-137">Où et comment puis-je déployer des SBCS ?</span><span class="sxs-lookup"><span data-stu-id="a7e71-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="a7e71-138">Pour plus d’informations, [voir Configurer le routage direct](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="a7e71-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="a7e71-139">Ai-je plusieurs locataires ?</span><span class="sxs-lookup"><span data-stu-id="a7e71-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="a7e71-140">Pour plus d’informations, voir [Configurer un contrôleur de session en bordure pour plusieurs locataires.](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="a7e71-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="a7e71-141">Considérations en cas de routage vocal</span><span class="sxs-lookup"><span data-stu-id="a7e71-141">Voice routing considerations</span></span>

<span data-ttu-id="a7e71-142">Vous devrez configurer les Système téléphonique router les appels vers des SCS spécifiques.</span><span class="sxs-lookup"><span data-stu-id="a7e71-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="a7e71-143">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="a7e71-143">Ask yourself</span></span>|<span data-ttu-id="a7e71-144">Action</span><span class="sxs-lookup"><span data-stu-id="a7e71-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="a7e71-145">Quelles stratégies de routage vocal, utilisation PSTN et itinéraires vocux dois-je créer ?</span><span class="sxs-lookup"><span data-stu-id="a7e71-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="a7e71-146">Pour plus d’informations sur le routage vocal, voir [Configurer le routage vocal.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="a7e71-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="a7e71-147">Quels utilisateurs seront affectés à la stratégie de routage voix que je définisse ?</span><span class="sxs-lookup"><span data-stu-id="a7e71-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="a7e71-148">Consultez les [exemples dans Configurer le routage vocal.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="a7e71-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="a7e71-149">Assurez-vous que les appels entrants arrivent dans le client Teams à l’aide de TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="a7e71-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="a7e71-150">Le routage direct n’est pris en charge qu’avec Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a7e71-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="a7e71-151">Pour recevoir des appels PSTN via un routage direct, vous devez configurer TeamsUpgradePolicy pour vous assurer que les appels entrants soient reçus dans Teams.</span><span class="sxs-lookup"><span data-stu-id="a7e71-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="a7e71-152">Les utilisateurs doivent être en mode Teams uniquement, ce que vous pouvez faire en leur attribuant l’instance « UpgradeToTeams » de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="a7e71-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="a7e71-153">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="a7e71-153">Ask yourself</span></span>|<span data-ttu-id="a7e71-154">Action</span><span class="sxs-lookup"><span data-stu-id="a7e71-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="a7e71-155">Que signifie Teams mode Uniquement ?</span><span class="sxs-lookup"><span data-stu-id="a7e71-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="a7e71-156">Pour plus d’informations, consultez les conseils sur la migration et l’interopérabilité pour les organisations qui [utilisent Teams avec d Skype Entreprise.](./migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="a7e71-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="a7e71-157">Considérations supplémentaires en cas de déploiement</span><span class="sxs-lookup"><span data-stu-id="a7e71-157">Additional deployment considerations</span></span>

<span data-ttu-id="a7e71-158">Vous pouvez envisager les considérations suivantes en fonction des besoins et de la configuration de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="a7e71-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="a7e71-159">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="a7e71-159">Ask yourself</span></span>| <span data-ttu-id="a7e71-160">Action</span><span class="sxs-lookup"><span data-stu-id="a7e71-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="a7e71-161">Avez-vous déjà un déploiement Skype Entreprise Server hybride avec une connectivité hybride configurée ?</span><span class="sxs-lookup"><span data-stu-id="a7e71-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="a7e71-162">Pour mieux comprendre la manière dont les comptes d’utilisateur dans un environnement hybride sont provisionés et gérés, consultez Comptes d’utilisateurs dans un environnement hybride avec connectivité [PSTN.](direct-routing-user-accounts-in-a-hybrid-environment.md)</span><span class="sxs-lookup"><span data-stu-id="a7e71-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="a7e71-163">Migrez-vous vers un routage direct à partir d’un plan d’appels ou d’Skype Entreprise un environnement local ?</span><span class="sxs-lookup"><span data-stu-id="a7e71-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="a7e71-164">Pour plus d’informations sur la migration vers le routage direct à partir d’un environnement existant, voir Migration [vers Un routage direct.](direct-routing-migrating.md)</span><span class="sxs-lookup"><span data-stu-id="a7e71-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||