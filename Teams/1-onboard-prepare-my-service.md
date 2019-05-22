---
title: Préparer le déploiement du service vocal cloud de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Utilisez les listes de contrôle d’intégration pour préparer Office 365 pour teams et configurer les fonctionnalités principales, la mise en réseau et les charges de travail de l’équipe Cloud.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c2316376bd2dfddce99e63fe4ab66c5e33eb813e
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344828"
---
# <a name="prepare-my-service"></a><span data-ttu-id="e8f53-103">Préparer mon service</span><span class="sxs-lookup"><span data-stu-id="e8f53-103">Prepare my service</span></span>

<span data-ttu-id="e8f53-104">Cet article fournit une vue d’ensemble des exigences relatives à la préparation des services vocaux Cloud pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e8f53-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="e8f53-105">En préparant correctement, vous pouvez être sûr que vous êtes prêt à fournir des fonctionnalités de voix Cloud à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e8f53-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="e8f53-106">Listes de vérification de l’intégration des charges de travail vocales de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e8f53-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="e8f53-107">Les listes de vérification suivantes vous guident tout au long des étapes d’implémentation des fonctionnalités de conférence audio, de système téléphonique avec des plans d’appel («plans d’appel») et de routage direct du système téléphonique («routage directe») dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e8f53-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="e8f53-108">Préparer Office 365 pour teams</span><span class="sxs-lookup"><span data-stu-id="e8f53-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="e8f53-109">Configurer les fonctionnalités principales de teams</span><span class="sxs-lookup"><span data-stu-id="e8f53-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="e8f53-110">Configurer la mise en réseau</span><span class="sxs-lookup"><span data-stu-id="e8f53-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="e8f53-111">Configurer des charges de travail vocales Cloud dans teams</span><span class="sxs-lookup"><span data-stu-id="e8f53-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="e8f53-112">Configurer le routage direct dans teams</span><span class="sxs-lookup"><span data-stu-id="e8f53-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="e8f53-113">Les tâches et les activités de ces listes de vérification constituent les éléments de «tâches de base» qui s’appliquent à tous les déploiements de fonctionnalités de voix Cloud avec Teams.</span><span class="sxs-lookup"><span data-stu-id="e8f53-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="e8f53-114">Vous pouvez personnaliser les listes de contrôle de façon à inclure les activités et tâches spécifiques à votre propre équipe.</span><span class="sxs-lookup"><span data-stu-id="e8f53-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="e8f53-115">Ce guide est axé uniquement sur les offres d’appel, l’audioconférence et le routage direct.</span><span class="sxs-lookup"><span data-stu-id="e8f53-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="e8f53-116">Si vous débutez avec Teams, passez en revue la [vue d’ensemble de Microsoft teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e8f53-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="e8f53-117">Pour obtenir des instructions générales sur la planification du déploiement de teams, commencez par [déployer la discussion, les équipes, les canaux et les applications dans Microsoft teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="e8f53-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="e8f53-118">Utilisez les listes de vérification fournies pour effectuer le suivi de l’état de chacune des activités et tâches individuelles et être sûr de ne pas ignorer les étapes critiques.</span><span class="sxs-lookup"><span data-stu-id="e8f53-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="e8f53-119">Chaque activité inclut une description détaillée des actions et références requises pour les informations supplémentaires que vous pouvez utiliser pour effectuer cette activité.</span><span class="sxs-lookup"><span data-stu-id="e8f53-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="e8f53-120">Bien que nous vous recommandons de suivre les listes de vérification dans l’ordre, la séquence exacte dépend de la portée de votre déploiement, de la configuration et de la complexité de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="e8f53-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="e8f53-121">Ils sont organisés pour prendre en charge un déploiement d’équipes «Greenfield» (un seul qui ne dispose pas de la présence d’une version précédente de Skype entreprise Online) ou la migration de Skype entreprise Online vers Teams.</span><span class="sxs-lookup"><span data-stu-id="e8f53-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="e8f53-122">Si vous effectuez une migration à partir de Skype entreprise Online, vous avez peut-être déjà terminé certaines de ces activités et vous pouvez les ignorer maintenant.</span><span class="sxs-lookup"><span data-stu-id="e8f53-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="e8f53-123">Lorsque vous intégrez des utilisateurs au niveau de chaque site, nous vous conseillons vivement d’utiliser le [Manuel d’utilisation du site pour les appels vocaux (Guide d’utilisation des sites)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) comme guide supplémentaire de ces listes de vérification.</span><span class="sxs-lookup"><span data-stu-id="e8f53-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="e8f53-124">La plupart des paramètres de configuration sont communs entre teams et Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="e8f53-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="e8f53-125">Pour configurer ces paramètres, vous devez utiliser le centre d’administration Microsoft 365 et le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e8f53-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="e8f53-126">Points de décision</span><span class="sxs-lookup"><span data-stu-id="e8f53-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="e8f53-127">Qui est responsable de l’affichage des listes de vérification d’intégration?</span><span class="sxs-lookup"><span data-stu-id="e8f53-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="e8f53-128">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="e8f53-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="e8f53-129">Téléchargez les listes de vérification de l’intégration.</span><span class="sxs-lookup"><span data-stu-id="e8f53-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="e8f53-130">Parcourez les éléments de liste de vérification d’intégration conformément au plan de déploiement de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e8f53-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="e8f53-131">Poursuite de l’intégration</span><span class="sxs-lookup"><span data-stu-id="e8f53-131">Continue onboarding</span></span>

<span data-ttu-id="e8f53-132">Après avoir effectué ces listes de vérification, vous aurez bien ajouté les fonctionnalités de voix à votre déploiement d’équipes.</span><span class="sxs-lookup"><span data-stu-id="e8f53-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="e8f53-133">À l’étape suivante, utilisez le [Manuel d’utilisation du site pour les appels vocaux](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) pour vous aider à intégrer vos utilisateurs sur chaque site et à veiller à planifier et à exécuter des activités importantes de votre site.</span><span class="sxs-lookup"><span data-stu-id="e8f53-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="e8f53-134">Site prêt par le plan de déploiement du site</span><span class="sxs-lookup"><span data-stu-id="e8f53-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="e8f53-135">Définir le processus de gestion des services</span><span class="sxs-lookup"><span data-stu-id="e8f53-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="e8f53-136">Exécution des tests et de la correction</span><span class="sxs-lookup"><span data-stu-id="e8f53-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="e8f53-137">Test des charges de travail vocales Cloud dans teams</span><span class="sxs-lookup"><span data-stu-id="e8f53-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="e8f53-138">Une fois que vous avez défini et documenté les plans de réussite et de mise en œuvre technique de votre équipe dans le centre d’administration, l’étape suivante consiste à confirmer que votre organisation a effectué la configuration souhaitée. les attentes et les exigences sont satisfaites par le biais des fonctionnalités, des fonctionnalités et de la facilité d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="e8f53-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="e8f53-139">Avant de déployer un déploiement pilote ou final dans votre environnement de production, vous devez effectuer cette étape de validation.</span><span class="sxs-lookup"><span data-stu-id="e8f53-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="e8f53-140">Vous pouvez utiliser le plan de réussite pour les entreprises que vous avez défini lors de la phase enVision afin de baser la détermination des activités, des attentes, des cas de test des fonctionnalités et des fonctionnalités ainsi que de l’étendue globale de la phase de test.</span><span class="sxs-lookup"><span data-stu-id="e8f53-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="e8f53-141">Définir votre approche de test</span><span class="sxs-lookup"><span data-stu-id="e8f53-141">Define your testing approach</span></span>

<span data-ttu-id="e8f53-142">Dans sa forme la plus simple, votre approche de test est basée sur les fonctionnalités de la fonction d’audioconférence, des plans d’appel ou du service de routage direct, et le développement d’un plan de test pour vérifier que les exigences relatives aux fonctionnalités sont satisfaites pour les utilisateurs concernés.</span><span class="sxs-lookup"><span data-stu-id="e8f53-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="e8f53-143">Voici un exemple de plan de test pour la phase intégrée d’une implémentation de l’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e8f53-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="e8f53-144">Fonction de conférence audio à tester</span><span class="sxs-lookup"><span data-stu-id="e8f53-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="e8f53-145">Résumé des résultats</span><span class="sxs-lookup"><span data-stu-id="e8f53-145">Results summary</span></span> | <span data-ttu-id="e8f53-146">Remarques supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e8f53-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="e8f53-147">Planifier une réunion teams ad hoc contenant des informations de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="e8f53-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="e8f53-148">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="e8f53-148">Pass/Fail</span></span>   | <span data-ttu-id="e8f53-149">DÉFINIR</span><span class="sxs-lookup"><span data-stu-id="e8f53-149">TBD</span></span> |
| <span data-ttu-id="e8f53-150">Utiliser un téléphone pour la partie audio d’une réunion en composant une réunion à partir du RTC grâce aux informations de connexion fournies</span><span class="sxs-lookup"><span data-stu-id="e8f53-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="e8f53-151">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="e8f53-151">Pass/Fail</span></span> | <span data-ttu-id="e8f53-152">DÉFINIR</span><span class="sxs-lookup"><span data-stu-id="e8f53-152">TBD</span></span> |
| <span data-ttu-id="e8f53-153">Joindre d’autres personnes à une réunion existante en composant un numéro de téléphone via le RTC</span><span class="sxs-lookup"><span data-stu-id="e8f53-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="e8f53-154">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="e8f53-154">Pass/Fail</span></span> | <span data-ttu-id="e8f53-155">DÉFINIR</span><span class="sxs-lookup"><span data-stu-id="e8f53-155">TBD</span></span> |



| <span data-ttu-id="e8f53-156">Fonction d’appel ou plan de routage direct à tester</span><span class="sxs-lookup"><span data-stu-id="e8f53-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="e8f53-157">Résumé des résultats</span><span class="sxs-lookup"><span data-stu-id="e8f53-157">Results summary</span></span> | <span data-ttu-id="e8f53-158">Remarques supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e8f53-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="e8f53-159">Passer un appel RTC en composant un numéro PSTN</span><span class="sxs-lookup"><span data-stu-id="e8f53-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="e8f53-160">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="e8f53-160">Pass/Fail</span></span>       | <span data-ttu-id="e8f53-161">DÉFINIR</span><span class="sxs-lookup"><span data-stu-id="e8f53-161">TBD</span></span> |
| <span data-ttu-id="e8f53-162">Recevez un appel RTC en composant votre numéro RTC depuis une ligne externe (mobile, fixe)</span><span class="sxs-lookup"><span data-stu-id="e8f53-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="e8f53-163">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="e8f53-163">Pass/Fail</span></span> | <span data-ttu-id="e8f53-164">DÉFINIR</span><span class="sxs-lookup"><span data-stu-id="e8f53-164">TBD</span></span>|
| <span data-ttu-id="e8f53-165">Transférer un appel PSTN d’un utilisateur de teams vers un autre</span><span class="sxs-lookup"><span data-stu-id="e8f53-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="e8f53-166">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="e8f53-166">Pass/Fail</span></span> | <span data-ttu-id="e8f53-167">DÉFINIR</span><span class="sxs-lookup"><span data-stu-id="e8f53-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="e8f53-168">Pour vous aider à effectuer des tests de création de cas de test en tant que point de départ, consultez la liste des recommandations en matière d’utilisateurs disponibles aux [réunions et aux appels d’équipe](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span><span class="sxs-lookup"><span data-stu-id="e8f53-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="e8f53-169">Configuration des charges de travail de voix Cloud pour teams</span><span class="sxs-lookup"><span data-stu-id="e8f53-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="e8f53-170">À présent que vous avez défini votre approche de test, l’étape suivante consiste à configurer votre environnement de services et vos utilisateurs dans le cadre des fonctionnalités de voix Cloud de teams.</span><span class="sxs-lookup"><span data-stu-id="e8f53-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="e8f53-171">Pour plus d’informations, consultez:</span><span class="sxs-lookup"><span data-stu-id="e8f53-171">For additional information, see:</span></span>

- [<span data-ttu-id="e8f53-172">Planification technique de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="e8f53-172">Technical Planning for Audio Conferencing</span></span>](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [<span data-ttu-id="e8f53-173">Configurer Audioconférence pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e8f53-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="e8f53-174">Planification technique du système téléphonique avec les offres d’appels</span><span class="sxs-lookup"><span data-stu-id="e8f53-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="e8f53-175">Configuration de forfaits d’appels pour Skype entreprise et Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e8f53-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="e8f53-176">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="e8f53-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="e8f53-177">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="e8f53-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="e8f53-178">Exécuter le plan de test</span><span class="sxs-lookup"><span data-stu-id="e8f53-178">Execute the test plan</span></span>

[//]: # (Puis-je modifier mon profil? «L’utilisateur» semblait un peu ambigu.)
<span data-ttu-id="e8f53-180">Après la configuration de l’environnement de l’utilisateur et du service, la dernière étape de test inclut l’exécution du plan de test avec le focus sur la validation des fonctionnalités et des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="e8f53-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="e8f53-181">**Conditions préalables et hypothèses de test de l’audioconférence pour les utilisateurs et sites dans l’étendue:**</span><span class="sxs-lookup"><span data-stu-id="e8f53-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="e8f53-182">La définition d’un cas d’utilisation professionnelle pour le service de conférence audio a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="e8f53-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="e8f53-183">Une licence est requise pour les conférences audio et est affectée.</span><span class="sxs-lookup"><span data-stu-id="e8f53-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="e8f53-184">La liste des sites d’entreprise et des groupes d’utilisateurs a été identifiée.</span><span class="sxs-lookup"><span data-stu-id="e8f53-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="e8f53-185">La liste des numéros de téléphone de conférence rendez-vous et des numéros en fonction de la langue que vous avez choisie a été identifiée et configurée.</span><span class="sxs-lookup"><span data-stu-id="e8f53-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="e8f53-186">[Crédits de communication](what-are-communications-credits.md) (si nécessaire) ont été configurés pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e8f53-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="e8f53-187">Les paramètres du pont de conférence audio ont été identifiés et configurés (longueur du code confidentiel, notifications d’entrée/sortie, préférence d’activation de notification).</span><span class="sxs-lookup"><span data-stu-id="e8f53-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="e8f53-188">Les stratégies de conférences client et les paramètres de plan de numérotation qui prennent en charge les scénarios de numérotation de l’audioconférence peuvent être identifiés, configurés et appliqués.</span><span class="sxs-lookup"><span data-stu-id="e8f53-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="e8f53-189">Les exigences en matière de conformité de l’audioconférence ont été identifiées et configurées.</span><span class="sxs-lookup"><span data-stu-id="e8f53-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="e8f53-190">**Offres d’appel tests requis et hypothèses pour les utilisateurs et sites dans l’étendue:**</span><span class="sxs-lookup"><span data-stu-id="e8f53-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="e8f53-191">La définition d’un cas d’utilisation professionnelle pour le Service plans d’appel a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="e8f53-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="e8f53-192">Les licences nécessaires pour les plans d’appel sont disponibles et ont été attribuées.</span><span class="sxs-lookup"><span data-stu-id="e8f53-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="e8f53-193">La liste des sites d’entreprise et des groupes d’utilisateurs a été identifiée.</span><span class="sxs-lookup"><span data-stu-id="e8f53-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="e8f53-194">Les numéros de téléphone à attribuer à des utilisateurs ou qui ont été portés à Microsoft et sont disponibles sur le portail du client.</span><span class="sxs-lookup"><span data-stu-id="e8f53-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="e8f53-195">[Crédits de communication](what-are-communications-credits.md) (si nécessaire) ont été configurés pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e8f53-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="e8f53-196">Les stratégies utilisateur client et les paramètres de plan de numérotation prenant en charge les scénarios d’appel d’offres sont identifiés, configurés et appliqués.</span><span class="sxs-lookup"><span data-stu-id="e8f53-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="e8f53-197">Les plans d’appel doivent avoir été identifiés et configurés.</span><span class="sxs-lookup"><span data-stu-id="e8f53-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="e8f53-198">**Conditions préalables et hypothèses de test de routage directes pour les utilisateurs et sites dans l’étendue:**</span><span class="sxs-lookup"><span data-stu-id="e8f53-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="e8f53-199">La définition de cas d’utilisation professionnelle pour le service de routage direct a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="e8f53-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="e8f53-200">La licence requise pour le routage direct est disponible et affectée.</span><span class="sxs-lookup"><span data-stu-id="e8f53-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="e8f53-201">La liste des sites d’entreprise et des groupes d’utilisateurs a été identifiée.</span><span class="sxs-lookup"><span data-stu-id="e8f53-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="e8f53-202">Un [contrôleur de bordure de session (SBC) certifié](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) a été déployé, configuré et associé au système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="e8f53-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="e8f53-203">La voix entreprise est activée et les numéros de téléphone ont été attribués.</span><span class="sxs-lookup"><span data-stu-id="e8f53-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="e8f53-204">Les stratégies de routage de la voix ont été identifiées, configurées et attribuées.</span><span class="sxs-lookup"><span data-stu-id="e8f53-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="e8f53-205">Microsoft teams a été défini comme client appelant préféré pour les utilisateurs de l’étendue.</span><span class="sxs-lookup"><span data-stu-id="e8f53-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="e8f53-206">Les exigences en matière de conformité au routage direct ont été identifiées et configurées.</span><span class="sxs-lookup"><span data-stu-id="e8f53-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="e8f53-207">Points de décision</span><span class="sxs-lookup"><span data-stu-id="e8f53-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="e8f53-208">Déterminez les fonctionnalités de la fonctionnalité de conférence audio qui seront déployées (décision du service).</span><span class="sxs-lookup"><span data-stu-id="e8f53-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="e8f53-209">Identifiez les exigences de fonctionnalités des utilisateurs pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="e8f53-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="e8f53-210">Identifiez les exigences de configuration de service pour les conférences audio.</span><span class="sxs-lookup"><span data-stu-id="e8f53-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="e8f53-211">Déterminez si les plans de routage ou d’appel directs seront déployés et configurés.</span><span class="sxs-lookup"><span data-stu-id="e8f53-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="e8f53-212">Déterminez les fonctionnalités de fonctionnalités de système téléphonique qui seront déployées (décision de service).</span><span class="sxs-lookup"><span data-stu-id="e8f53-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="e8f53-213">Identifiez les exigences de fonctionnalités des utilisateurs pour les appels d’offres ou le routage direct.</span><span class="sxs-lookup"><span data-stu-id="e8f53-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="e8f53-214">Identifiez les exigences de configuration de service pour les abonnements d’appels ou le routage direct.</span><span class="sxs-lookup"><span data-stu-id="e8f53-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="e8f53-215">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="e8f53-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="e8f53-216">Développez et documentez l’approche de votre plan de test.</span><span class="sxs-lookup"><span data-stu-id="e8f53-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="e8f53-217">Préparez votre environnement et vos utilisateurs à l’étendue des fonctionnalités de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="e8f53-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="e8f53-218">Préparez votre environnement et vos utilisateurs dans le cadre des appels d’offres ou du routage direct.</span><span class="sxs-lookup"><span data-stu-id="e8f53-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="e8f53-219">Exécutez la validation de test pour les fonctionnalités de conférence audio que vous souhaitez activer.</span><span class="sxs-lookup"><span data-stu-id="e8f53-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="e8f53-220">Exécutez la validation de test pour les offres d’appels ou les fonctionnalités de routage directes que vous souhaitez activer.</span><span class="sxs-lookup"><span data-stu-id="e8f53-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="e8f53-221">Pour les échecs de test, vérifiez que votre configuration est correcte, consultez les Articles de la communauté et, si nécessaire, déclenchez une demande de support.</span><span class="sxs-lookup"><span data-stu-id="e8f53-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="e8f53-222">Pour obtenir des instructions détaillées supplémentaires sur l’exécution de tests pour l’audioconférence dans Teams, voir le [Guide de test détaillé pour audioconférence](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="e8f53-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="e8f53-223">Pour obtenir des instructions détaillées supplémentaires sur l’exécution de tests pour les plans d’appel dans Teams, voir le [Guide de test détaillé du système téléphonique](onboarding-test-plan-for-enterprises-Phone-System.md).</span><span class="sxs-lookup"><span data-stu-id="e8f53-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
