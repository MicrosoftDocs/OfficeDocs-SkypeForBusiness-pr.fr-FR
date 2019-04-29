---
title: Routage direct via le système téléphonique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
F1keywords: ms.teamsadmincenter.directrouting.overview
description: Page d’accueil routage Direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59f7cf4f1249956f3c763d12fcd96bf5c10a9fac
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401834"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="ecdb6-103">Routage direct via le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="ecdb6-103">Phone System Direct Routing</span></span>

<span data-ttu-id="ecdb6-104">Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="ecdb6-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="ecdb6-105">Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="ecdb6-106">Peut-être que vous avez déployé la [conférence & de réunions](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="ecdb6-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="ecdb6-107">Vous êtes maintenant prêt à ajouter des charges de travail de voix dans le cloud, et vous avez décidé d’utiliser votre propre opérateur de téléphonie pour la connectivité Public réseau de téléphonique commuté (RTC) à l’aide de routage d’un système téléphonique directe.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="ecdb6-108">Avec le routage Direct, vous pouvez utiliser le système téléphonique avec n’importe quel opérateur de téléphonie.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="ecdb6-109">Cet article décrit les décisions de déploiement principaux pour le routage Direct ainsi que les considérations supplémentaires que vous souhaiterez peut-être considération, en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="ecdb6-110">Vous devez également lire [Cloud vocale dans les équipes Microsoft](cloud-voice-landing-page.md) pour plus d’informations sur les offres de voix de cloud de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="ecdb6-111">Pour plus d’informations sur le routage Direct</span><span class="sxs-lookup"><span data-stu-id="ecdb6-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="ecdb6-112">Les articles suivants fournissent plus d’informations sur la configuration et l’utilisation du routage Direct de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="ecdb6-113">Configuration du routage Direct nécessite la compréhension de la conception du routage PSTN.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="ecdb6-114">Vous devez lire tous ces articles pour comprendre comment planifier et configurer le routage Direct :</span><span class="sxs-lookup"><span data-stu-id="ecdb6-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="ecdb6-115">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="ecdb6-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="ecdb6-116">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="ecdb6-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="ecdb6-117">Liste des contrôleurs de frontière de session certifiés pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="ecdb6-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="ecdb6-118">Contrôler et dépanner le routage direct</span><span class="sxs-lookup"><span data-stu-id="ecdb6-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="ecdb6-119">En outre, vous pouvez souhaiter lire les articles suivants, selon vos besoins :</span><span class="sxs-lookup"><span data-stu-id="ecdb6-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="ecdb6-120">Configurer un contrôleur de frontière de session pour plusieurs clients</span><span class="sxs-lookup"><span data-stu-id="ecdb6-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="ecdb6-121">Migrer vers un routage direct</span><span class="sxs-lookup"><span data-stu-id="ecdb6-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="ecdb6-122">Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN</span><span class="sxs-lookup"><span data-stu-id="ecdb6-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="ecdb6-123">Regarder la session suivante pour en savoir plus sur le routage Direct : [Routage Direct dans les équipes Microsoft](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="ecdb6-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="ecdb6-124">Décisions liées au déploiement Core</span><span class="sxs-lookup"><span data-stu-id="ecdb6-124">Core deployment decisions</span></span>

<span data-ttu-id="ecdb6-125">Il s’agit des décisions clés à prendre en compte pour le routage Direct.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="ecdb6-126">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="ecdb6-126">Ask yourself</span></span>|<span data-ttu-id="ecdb6-127">Action</span><span class="sxs-lookup"><span data-stu-id="ecdb6-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="ecdb6-128">Pour les utilisateurs qui seront Activer routage Direct ?</span><span class="sxs-lookup"><span data-stu-id="ecdb6-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="ecdb6-129">Pour plus d’informations, voir [Activer les utilisateurs pour le Service de routage Direct](direct-routing-configure.md#enable-users-for-direct-routing-service).</span><span class="sxs-lookup"><span data-stu-id="ecdb6-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="ecdb6-130">J’ai les licences requises pour le routage Direct ?</span><span class="sxs-lookup"><span data-stu-id="ecdb6-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="ecdb6-131">Pour plus d’informations, voir [licences et autres composants requis](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="ecdb6-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="ecdb6-132">Considérations relatives à la session contrôleur de périphérie (SBC)</span><span class="sxs-lookup"><span data-stu-id="ecdb6-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="ecdb6-133">Avec le routage Direct, vous vous connectez à votre propre contrôleur de Session en périphérie (SBC) directement au système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="ecdb6-134">Pour une liste de SBC certifié, voir [Contrôleurs de frontière de Session pris en charge](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="ecdb6-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="ecdb6-135">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="ecdb6-135">Ask yourself</span></span>|<span data-ttu-id="ecdb6-136">Action</span><span class="sxs-lookup"><span data-stu-id="ecdb6-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="ecdb6-137">Où et comment allez déployer SBCs ?</span><span class="sxs-lookup"><span data-stu-id="ecdb6-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="ecdb6-138">Pour plus d’informations, voir [Configurer le routage Direct](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="ecdb6-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="ecdb6-139">Je dispose de plusieurs clients ?</span><span class="sxs-lookup"><span data-stu-id="ecdb6-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="ecdb6-140">Pour plus d’informations, voir [configurer une Session Border Controller pour plusieurs clients](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="ecdb6-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="ecdb6-141">Considérations relatives au routage de voix</span><span class="sxs-lookup"><span data-stu-id="ecdb6-141">Voice routing considerations</span></span>

<span data-ttu-id="ecdb6-142">Vous devez configurer le système téléphonique pour acheminer les appels vers la SBC spécifique.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="ecdb6-143">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="ecdb6-143">Ask yourself</span></span>|<span data-ttu-id="ecdb6-144">Action</span><span class="sxs-lookup"><span data-stu-id="ecdb6-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="ecdb6-145">Les stratégies de routage voix PSTN et d’utilisation des itinéraires ai-je besoin créer ?</span><span class="sxs-lookup"><span data-stu-id="ecdb6-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="ecdb6-146">Pour les informations de routage des communications vocales, voir [Configurer le routage de la voix](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="ecdb6-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="ecdb6-147">Les utilisateurs qui seront attribués à la stratégie de routage voix pour définir ?</span><span class="sxs-lookup"><span data-stu-id="ecdb6-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="ecdb6-148">Consultez les exemples de [Configurer Routage des communications vocales](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="ecdb6-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="calling-and-interop-policies"></a><span data-ttu-id="ecdb6-149">Stratégies d’appel et interopérabilités</span><span class="sxs-lookup"><span data-stu-id="ecdb6-149">Calling and interop policies</span></span>

<span data-ttu-id="ecdb6-150">Routage direct est uniquement pris en charge avec Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="ecdb6-151">Pour passer ou recevoir des appels PSTN par le biais de routage Direct, vous devez configurer les stratégies nécessaires pour garantir les appels entrants sont reçus dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-151">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="ecdb6-152">Vous pouvez configurer les utilisateurs pour définir les équipes comme leur client par défaut pour les appels par configuration de l’utilisateur pour le mode équipes uniquement ou configurer des équipes en tant que client appelant par défaut en affectant la TeamsCallingPolicy et le TeamsInteropPolicy.</span><span class="sxs-lookup"><span data-stu-id="ecdb6-152">You can configure users to set Teams as their preferred client for calls by either configuring the user for Teams Only mode or configuring Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

|<span data-ttu-id="ecdb6-153">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="ecdb6-153">Ask yourself</span></span>|<span data-ttu-id="ecdb6-154">Action</span><span class="sxs-lookup"><span data-stu-id="ecdb6-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="ecdb6-155">Comment activer les équipes comme client par défaut pour les appels ?</span><span class="sxs-lookup"><span data-stu-id="ecdb6-155">How will I set Teams as the preferred client for calls?</span></span> | <span data-ttu-id="ecdb6-156">Pour plus d’informations, voir [définir les équipes Microsoft en tant que préférable appel client pour les utilisateurs](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span><span class="sxs-lookup"><span data-stu-id="ecdb6-156">For more information, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="ecdb6-157">Autres aspects du déploiement</span><span class="sxs-lookup"><span data-stu-id="ecdb6-157">Additional deployment considerations</span></span>

<span data-ttu-id="ecdb6-158">Vous souhaiterez peut-être prendre en compte les éléments suivants, selon les besoins de votre organisation et la configuration :</span><span class="sxs-lookup"><span data-stu-id="ecdb6-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="ecdb6-159">Posez-vous la question</span><span class="sxs-lookup"><span data-stu-id="ecdb6-159">Ask yourself</span></span>| <span data-ttu-id="ecdb6-160">Action</span><span class="sxs-lookup"><span data-stu-id="ecdb6-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="ecdb6-161">Vous avez un Skype existant pour le déploiement de serveur d’entreprise avec connectivité hybride configurée ?</span><span class="sxs-lookup"><span data-stu-id="ecdb6-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="ecdb6-162">Pour comprendre comment les comptes d’utilisateurs dans un environnement hybride sont mis en service et gérées, voir [comptes d’utilisateurs dans un environnement hybride avec une connectivité PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ecdb6-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="ecdb6-163">Vous migrez vers routage Direct à partir de l’appel de planifier ou d’un Skype pour un environnement sur site ?</span><span class="sxs-lookup"><span data-stu-id="ecdb6-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="ecdb6-164">Pour en savoir plus sur la migration vers routage Direct à partir d’un environnement existant, consultez [migration vers routage Direct](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="ecdb6-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
