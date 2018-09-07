---
title: Préparer le déploiement du service en nuage vocale Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Utilisez des listes de vérification embarquement préparer Office 365 pour les équipes et la configuration des fonctionnalités principales d’équipes, mise en réseau et les charges de travail voix en nuage.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e115ac93a63fb007787a4324c56793c996723c64
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850204"
---
# <a name="prepare-my-service"></a><span data-ttu-id="507b3-103">Préparer mon service</span><span class="sxs-lookup"><span data-stu-id="507b3-103">Prepare my service</span></span>

<span data-ttu-id="507b3-104">Cet article donne une vue d’ensemble de la configuration requise pour la préparation des services de téléphonie pour votre organisation en nuage.</span><span class="sxs-lookup"><span data-stu-id="507b3-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="507b3-105">Préparer correctement, vous pouvez être que vous êtes prêt à fournir la communication vocale à votre organisation en nuage.</span><span class="sxs-lookup"><span data-stu-id="507b3-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="507b3-106">Intégration des listes de contrôle pour Microsoft Teams vocale des charges de travail</span><span class="sxs-lookup"><span data-stu-id="507b3-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="507b3-107">Listes de vérification suivantes vous guident tout au long de la procédure pour l’implémentation de conférence Audio, système téléphonique avec l’appel (« appel Plans ») des Plans et fonctionnalités téléphone système routage Direct (« routage Direct ») dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="507b3-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="507b3-108">Préparation d’Office 365 pour les équipes</span><span class="sxs-lookup"><span data-stu-id="507b3-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="507b3-109">Configurer les fonctionnalités principales d’équipes</span><span class="sxs-lookup"><span data-stu-id="507b3-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="507b3-110">Configurer la mise en réseau</span><span class="sxs-lookup"><span data-stu-id="507b3-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="507b3-111">Configurer des charges de travail dans le nuage vocale dans les équipes</span><span class="sxs-lookup"><span data-stu-id="507b3-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="507b3-112">Configurer le routage Direct dans les équipes</span><span class="sxs-lookup"><span data-stu-id="507b3-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="507b3-113">Les tâches et activités dans ces listes de contrôle sont les éléments principaux « tâches » qui s’appliquent à chaque déploiement de fonctionnalités vocales de nuage avec les équipes.</span><span class="sxs-lookup"><span data-stu-id="507b3-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="507b3-114">Vous pouvez personnaliser les listes de vérification pour inclure les activités et les tâches qui sont spécifiques à votre propre parcours équipes.</span><span class="sxs-lookup"><span data-stu-id="507b3-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="507b3-115">Ce guide porte uniquement sur les Plans de l’appel, conférence Audio et au routage Direct.</span><span class="sxs-lookup"><span data-stu-id="507b3-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="507b3-116">Si vous êtes novice en équipes, consultez [Vue d’ensemble des équipes de Microsoft](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="507b3-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="507b3-117">Pour obtenir des instructions générales pour la planification de votre déploiement d’équipes, consultez le [Guide de planification équipes Microsoft](quick-start-enable-teams.md).</span><span class="sxs-lookup"><span data-stu-id="507b3-117">For general guidance for planning your Teams deployment, see the [Microsoft Teams Planning Guide](quick-start-enable-teams.md).</span></span>

<span data-ttu-id="507b3-118">Utilisez les listes de vérification fournies pour suivre l’état de chaque tâche et de l’activité individuelle et effectué pour vous assurer que toutes les étapes critiques.</span><span class="sxs-lookup"><span data-stu-id="507b3-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="507b3-119">Chaque activité comprend une description détaillée des actions requises et des références à des informations supplémentaires que vous pouvez utiliser pour effectuer cette activité.</span><span class="sxs-lookup"><span data-stu-id="507b3-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="507b3-120">Bien que nous vous conseillons de suivre les listes de contrôle dans l’ordre, l’ordre exact dépend de l’étendue de votre déploiement et de la configuration et la complexité de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="507b3-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="507b3-121">Elles sont organisées pour prendre en charge soit une » dans un environnement vierge » des équipes de déploiement (une avec aucun Skype précédent de la présence en ligne Business) ou la migration à partir de Skype pour Business Online aux équipes.</span><span class="sxs-lookup"><span data-stu-id="507b3-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="507b3-122">Si vous migrez à partir de Skype pour Business Online, vous pourrez avoir déjà effectué certaines de ces activités et pourrez ignorer maintenant.</span><span class="sxs-lookup"><span data-stu-id="507b3-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="507b3-123">Lorsque vous êtes embarquement utilisateurs sur site par site, que nous vous recommandons vivement d’utiliser la [Lecture d’activation de Site pour la voix (lecture)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) comme un guide supplémentaire à ces listes de contrôle.</span><span class="sxs-lookup"><span data-stu-id="507b3-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="507b3-124">La plupart des paramètres de configuration sont communes entre les équipes et Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="507b3-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="507b3-125">Office 365 Skype pour le centre d’Administration Business vous permet de configurer ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="507b3-125">You use Office 365 Skype for Business Administration Center to configure those settings.</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="507b3-126">Points de décision</span><span class="sxs-lookup"><span data-stu-id="507b3-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="507b3-127">Qui sera responsable de la surveillance de l’exécution de l’intégration des listes de contrôle ?</span><span class="sxs-lookup"><span data-stu-id="507b3-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="507b3-128">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="507b3-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="507b3-129">Télécharger les listes de vérification embarquement.</span><span class="sxs-lookup"><span data-stu-id="507b3-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="507b3-130">Parcourez les éléments de liste de vérification embarquement détaillées conformément au plan de déploiement de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="507b3-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="507b3-131">Continuez d’intégration</span><span class="sxs-lookup"><span data-stu-id="507b3-131">Continue onboarding</span></span>

<span data-ttu-id="507b3-132">Après avoir terminé ces listes de contrôle, vous allez avez ajouté des fonctionnalités vocales pour votre déploiement d’équipes.</span><span class="sxs-lookup"><span data-stu-id="507b3-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="507b3-133">L’étape suivante, utilisez la [Lecture d’activation de Site pour la voix (lecture)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) pour vous aider intégrée à vos utilisateurs sur chaque site et vous assurer que vous planifier et exécutez des activités spécifiques au site importantes.</span><span class="sxs-lookup"><span data-stu-id="507b3-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="507b3-134">Plan de déploiement de Site par Site prêt</span><span class="sxs-lookup"><span data-stu-id="507b3-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="507b3-135">Établir un processus de gestion de Service</span><span class="sxs-lookup"><span data-stu-id="507b3-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="507b3-136">Exécutez le test et correction</span><span class="sxs-lookup"><span data-stu-id="507b3-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="507b3-137">Test cloud voix des charges de travail en équipe</span><span class="sxs-lookup"><span data-stu-id="507b3-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="507b3-138">Après avoir défini et documenté vos équipes cloud voix entreprise réussite et les techniques de mise en œuvre dans le cadre de la phase de prévoir et entreprendre la configuration souhaitée dans le centre d’administration, l’étape suivante consiste à confirmer que votre organisation attentes et les exigences sont remplies par le biais de fonctionnalités, les fonctionnalités et les possibilités d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="507b3-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="507b3-139">Vous devez effectuer cette étape de validation avant de déployer un déploiement pilote ou final dans votre environnement de production.</span><span class="sxs-lookup"><span data-stu-id="507b3-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="507b3-140">Vous pouvez vous appuyer sur le plan de réussite définis lors de la phase de prévoir pour servir de base pour déterminer les activités, les attentes, caractéristiques et fonctionnalités des cas de test et étendue globale pour être évaluée pendant la phase de test.</span><span class="sxs-lookup"><span data-stu-id="507b3-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="507b3-141">Définir votre approche de test</span><span class="sxs-lookup"><span data-stu-id="507b3-141">Define your testing approach</span></span>

<span data-ttu-id="507b3-142">Dans sa forme la plus simple, votre approche de test est basée sur votre examen les fonctionnalités de conférence Audio, des Plans de l’appel, ou planifier le service de routage Direct et développement d’un test vérifier que vos besoins de fonctionnalités sont remplies pour les utilisateurs dans l’étendue.</span><span class="sxs-lookup"><span data-stu-id="507b3-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="507b3-143">Vous trouverez ci-dessous un plan de test d’exemple pour la phase d’une implémentation de services d’audioconférence intégrée.</span><span class="sxs-lookup"><span data-stu-id="507b3-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="507b3-144">Fonctionnalité de conférence audio à tester</span><span class="sxs-lookup"><span data-stu-id="507b3-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="507b3-145">Résumé des résultats</span><span class="sxs-lookup"><span data-stu-id="507b3-145">Results summary</span></span> | <span data-ttu-id="507b3-146">Remarques supplémentaires</span><span class="sxs-lookup"><span data-stu-id="507b3-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="507b3-147">Planifier une réunion ad hoc équipes qui contient les informations d’audioconférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="507b3-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="507b3-148">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="507b3-148">Pass/Fail</span></span>   | <span data-ttu-id="507b3-149">TBD</span><span class="sxs-lookup"><span data-stu-id="507b3-149">TBD</span></span> |
| <span data-ttu-id="507b3-150">Utiliser un téléphone pour la réunion audio en vous connectant à une réunion à partir de la passerelle PSTN avec les informations de numérotation fournies</span><span class="sxs-lookup"><span data-stu-id="507b3-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="507b3-151">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="507b3-151">Pass/Fail</span></span> | <span data-ttu-id="507b3-152">TBD</span><span class="sxs-lookup"><span data-stu-id="507b3-152">TBD</span></span> |
| <span data-ttu-id="507b3-153">Participer à d’autres personnes à une réunion existante à un appel sortant via le réseau téléphonique commuté</span><span class="sxs-lookup"><span data-stu-id="507b3-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="507b3-154">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="507b3-154">Pass/Fail</span></span> | <span data-ttu-id="507b3-155">TBD</span><span class="sxs-lookup"><span data-stu-id="507b3-155">TBD</span></span> |



| <span data-ttu-id="507b3-156">Plans d’appel ou de routage Direct des fonctionnalités à tester</span><span class="sxs-lookup"><span data-stu-id="507b3-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="507b3-157">Résumé des résultats</span><span class="sxs-lookup"><span data-stu-id="507b3-157">Results summary</span></span> | <span data-ttu-id="507b3-158">Remarques supplémentaires</span><span class="sxs-lookup"><span data-stu-id="507b3-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="507b3-159">Émettre un appel RTC en composant un numéro RTC</span><span class="sxs-lookup"><span data-stu-id="507b3-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="507b3-160">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="507b3-160">Pass/Fail</span></span>       | <span data-ttu-id="507b3-161">TBD</span><span class="sxs-lookup"><span data-stu-id="507b3-161">TBD</span></span> |
| <span data-ttu-id="507b3-162">Recevoir un appel RTC par votre numérotation PSTN à partir d’une ligne externe (mobile, fixe)</span><span class="sxs-lookup"><span data-stu-id="507b3-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="507b3-163">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="507b3-163">Pass/Fail</span></span> | <span data-ttu-id="507b3-164">TBD</span><span class="sxs-lookup"><span data-stu-id="507b3-164">TBD</span></span>|
| <span data-ttu-id="507b3-165">Transférer un appel PSTN d’un utilisateur d’équipes à un autre</span><span class="sxs-lookup"><span data-stu-id="507b3-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="507b3-166">Réussite/échec</span><span class="sxs-lookup"><span data-stu-id="507b3-166">Pass/Fail</span></span> | <span data-ttu-id="507b3-167">TBD</span><span class="sxs-lookup"><span data-stu-id="507b3-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="507b3-168">Pour faciliter la création des cas de test comme point de départ, voir la liste des [équipes de réunions et appels](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)disponible Guide de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="507b3-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="507b3-169">Configurer des charges de travail voix dans le nuage pour les équipes</span><span class="sxs-lookup"><span data-stu-id="507b3-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="507b3-170">Maintenant que vous avez défini votre approche de test, l’étape suivante consiste à configurer votre environnement de service et les utilisateurs dans la portée de fonctionnalités vocales de nuage équipes.</span><span class="sxs-lookup"><span data-stu-id="507b3-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="507b3-171">Pour plus d’informations, voir :</span><span class="sxs-lookup"><span data-stu-id="507b3-171">For additional information, see:</span></span>

- [<span data-ttu-id="507b3-172">Planification technique de l’audioconférence</span><span class="sxs-lookup"><span data-stu-id="507b3-172">Technical Planning for Audio Conferencing</span></span>](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [<span data-ttu-id="507b3-173">Configurer la conférence Audio pour Skype entreprise et Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="507b3-173">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

- [<span data-ttu-id="507b3-174">Techniques de planification du système téléphonique avec les Plans d’appel</span><span class="sxs-lookup"><span data-stu-id="507b3-174">Technical Planning for Phone System with Calling Plans</span></span>](phone-system-with-calling-plans.md#technical-planning-for-phone-system-with-calling-plans)

- [<span data-ttu-id="507b3-175">Configurer des Plans de l’appel pour Skype pour les entreprises et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="507b3-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="507b3-176">Planifier le routage Direct</span><span class="sxs-lookup"><span data-stu-id="507b3-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="507b3-177">Configurer le routage Direct</span><span class="sxs-lookup"><span data-stu-id="507b3-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="507b3-178">Exécuter le plan de test</span><span class="sxs-lookup"><span data-stu-id="507b3-178">Execute the test plan</span></span>

[//]: # (OK modifier ? « Utilisateur » semblaient un peu ambigu pour moi.)
<span data-ttu-id="507b3-180">Une fois que l’environnement de l’utilisateur et le service ont été configurés, la dernière étape de test inclut l’exécution du plan de test ayant le focus sur la validation des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="507b3-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="507b3-181">**Test des conditions préalables et hypothèses pour les utilisateurs et les sites dans l’étendue de conférence audio :**</span><span class="sxs-lookup"><span data-stu-id="507b3-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="507b3-182">Entreprise utiliser la définition de cas pour la conférence Audio service a été effectué.</span><span class="sxs-lookup"><span data-stu-id="507b3-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="507b3-183">Licences requises pour une audioconférence est disponible et a été affecté.</span><span class="sxs-lookup"><span data-stu-id="507b3-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="507b3-184">La liste des sites d’organisation et des groupes d’utilisateurs ont été identifiés.</span><span class="sxs-lookup"><span data-stu-id="507b3-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="507b3-185">La liste des dédié et partagés audioconférence rendez-vous numéros avec préférence linguistique ont été identifiés et configuré.</span><span class="sxs-lookup"><span data-stu-id="507b3-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="507b3-186">[Communications générique](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (si nécessaire) ont été configurés pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="507b3-186">[Communications Credits](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="507b3-187">Paramètres pont de conférence audio conférence ont été identifiés et configuré (longueur du code confidentiel, les notifications d’entrée/sortie, préférence de notification d’activation).</span><span class="sxs-lookup"><span data-stu-id="507b3-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="507b3-188">Stratégies de conférence des clients et planifier les paramètres qui prennent en charge la conférence rendez-vous scénarios identifiés, configurés et appliqués de numérotation.</span><span class="sxs-lookup"><span data-stu-id="507b3-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="507b3-189">Exigences de conformité de conférence audio ont été identifiés et configurés.</span><span class="sxs-lookup"><span data-stu-id="507b3-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="507b3-190">**L’appel de Plans de test des conditions préalables et hypothèses pour les utilisateurs et les sites dans l’étendue :**</span><span class="sxs-lookup"><span data-stu-id="507b3-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="507b3-191">Entreprise utiliser la définition de cas pour l’appel des Plans de service a été effectué.</span><span class="sxs-lookup"><span data-stu-id="507b3-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="507b3-192">Licences requises pour l’appel des Plans est disponible et a été affecté.</span><span class="sxs-lookup"><span data-stu-id="507b3-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="507b3-193">La liste des sites d’organisation et des groupes d’utilisateurs ont été identifiés.</span><span class="sxs-lookup"><span data-stu-id="507b3-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="507b3-194">Numéros de téléphone à attribuer aux utilisateurs qui ont été acquis ou prise en charge par Microsoft et qui sont disponibles dans le portail client.</span><span class="sxs-lookup"><span data-stu-id="507b3-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="507b3-195">[Communications générique](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (si nécessaire) ont été configurés pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="507b3-195">[Communications Credits](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="507b3-196">Stratégies de client utilisateur et les paramètres de plan de numérotation qui prennent en charge les scénarios d’appel de Plans ont été identifiés, configurés et appliqués.</span><span class="sxs-lookup"><span data-stu-id="507b3-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="507b3-197">Plans d’exigences de conformité ont été identifiés et configurés l’appel.</span><span class="sxs-lookup"><span data-stu-id="507b3-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="507b3-198">**Routage direct test des conditions préalables et hypothèses pour les utilisateurs et les sites dans l’étendue :**</span><span class="sxs-lookup"><span data-stu-id="507b3-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="507b3-199">Entreprise utiliser la définition de cas pour le routage Direct service a été effectué.</span><span class="sxs-lookup"><span data-stu-id="507b3-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="507b3-200">Licences requises pour le routage directe est disponible et a été affecté.</span><span class="sxs-lookup"><span data-stu-id="507b3-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="507b3-201">La liste des sites d’organisation et des groupes d’utilisateurs ont été identifiés.</span><span class="sxs-lookup"><span data-stu-id="507b3-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="507b3-202">Un [certifié contrôleur de session en périphérie (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) a été déployé, configuré et associé à un système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="507b3-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="507b3-203">Voix entreprise a été activé, et les numéros de téléphone ont été attribués.</span><span class="sxs-lookup"><span data-stu-id="507b3-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="507b3-204">Stratégies de routage voix ont été identifiés, configurés et affectés.</span><span class="sxs-lookup"><span data-stu-id="507b3-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="507b3-205">Microsoft Teams a été défini en tant que client appelant par défaut pour les utilisateurs dans l’étendue.</span><span class="sxs-lookup"><span data-stu-id="507b3-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="507b3-206">Exigences de conformité de routage directs ont été identifiés et configurés.</span><span class="sxs-lookup"><span data-stu-id="507b3-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="507b3-207">Points de décision</span><span class="sxs-lookup"><span data-stu-id="507b3-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="507b3-208">Déterminer les fonctionnalités de conférence Audio seront déployées (décision de service).</span><span class="sxs-lookup"><span data-stu-id="507b3-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="507b3-209">Identifiez les exigences de fonctionnalités utilisateur pour une audioconférence.</span><span class="sxs-lookup"><span data-stu-id="507b3-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="507b3-210">Identifiez les exigences de configuration de service pour une audioconférence.</span><span class="sxs-lookup"><span data-stu-id="507b3-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="507b3-211">Décider si routage Direct ou des Plans de l’appel sera déployés et configurés.</span><span class="sxs-lookup"><span data-stu-id="507b3-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="507b3-212">Déterminer les fonctionnalités du système téléphonique seront déployées (décision de service).</span><span class="sxs-lookup"><span data-stu-id="507b3-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="507b3-213">Identifiez les exigences de fonctionnalités utilisateur pour l’appel des Plans ou routage Direct.</span><span class="sxs-lookup"><span data-stu-id="507b3-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="507b3-214">Identifier le besoin de configuration de service pour l’appel des Plans ou routage Direct.</span><span class="sxs-lookup"><span data-stu-id="507b3-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="507b3-215">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="507b3-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="507b3-216">Développez et documentez votre approche de plan de test.</span><span class="sxs-lookup"><span data-stu-id="507b3-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="507b3-217">Préparer votre environnement de service et les utilisateurs dans la portée de fonctionnalités de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="507b3-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="507b3-218">Préparer votre environnement de service et les utilisateurs dans l’étendue pour les fonctionnalités de routage Direct ou de Plans de l’appel.</span><span class="sxs-lookup"><span data-stu-id="507b3-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="507b3-219">Exécuter le test de validation pour les fonctionnalités de conférence Audio que vous souhaitez activer.</span><span class="sxs-lookup"><span data-stu-id="507b3-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="507b3-220">Exécuter le test de validation pour les fonctionnalités de routage Direct ou de Plans de l’appel que vous souhaitez activer.</span><span class="sxs-lookup"><span data-stu-id="507b3-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="507b3-221">Pour les échecs de test, vérifiez que votre configuration est correcte, passez en revue les articles de la Communauté, et, si nécessaire, génère une demande de support.</span><span class="sxs-lookup"><span data-stu-id="507b3-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="507b3-222">Pour plus d’instructions détaillées sur la façon d’effectuer les tests pour une audioconférence dans les équipes, voir le [détaillées test guide pour une audioconférence](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="507b3-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="507b3-223">Pour plus d’instructions détaillées sur la façon d’effectuer les tests de l’appel des Plans dans les équipes, voir le [détaillées test guide pour le système téléphonique](onboarding-test-plan-for-enterprises-Phone-System.md).</span><span class="sxs-lookup"><span data-stu-id="507b3-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
