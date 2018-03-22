---
title: Déploiement de service vocal de cloud Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Téléchargez le manuel d’activation de Site pour planifier votre déploiement d’équipes et d’accélérer et d’optimiser l’adoption par les utilisateurs, la perception de la qualité et de satisfaction.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ddccd9c52e25ae9d0069119641aa7e8a8077d56
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
# <a name="deploy-my-service"></a><span data-ttu-id="a10da-103">Déployer mon service</span><span class="sxs-lookup"><span data-stu-id="a10da-103">Deploy my service</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="a10da-104">Manuel de prise en charge de site pour les charges de travail Teams de Microsoft voice</span><span class="sxs-lookup"><span data-stu-id="a10da-104">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="a10da-105">Ce manuel permet d’aider votre entreprise à planifier et exécuter le déploiement de fonctionnalités vocales de Microsoft Teams sur une base site par site.</span><span class="sxs-lookup"><span data-stu-id="a10da-105">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="a10da-106">Y compris toutes les activités, recommandé de chronologies et des liens correspondants de recommandations pour chaque activité, ce manuel traite des conseils de bout en bout pour garantir un déploiement réussi de voix équipes pour un site donné, en mettant l’accent sur des facteurs qui sont importants pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a10da-106">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="a10da-107">En effectuant les activités dans ce manuel, votre entreprise peut :</span><span class="sxs-lookup"><span data-stu-id="a10da-107">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="a10da-108">Planifier et planifier le déploiement de vos équipes de manière efficace.</span><span class="sxs-lookup"><span data-stu-id="a10da-108">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="a10da-109">Accélérez et optimisez l’adoption par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a10da-109">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="a10da-110">Réduire les besoins en support et accroître la satisfaction de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a10da-110">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="a10da-111">Cet article et le manuel associé ne sont pas destinés à décrire chaque étape de la configuration technique requise pour l’activation des services ou fourniture de tonalité à un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="a10da-111">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="a10da-112">À la place, ils se concentrent sur les activités et tâches recommandés aux utilisateurs intégrés facilement et les commence à consommer des charges de travail aux équipes voix via une transition rapide et sans heurts avec un fort engouement, tout en réduisant les exigences en matière de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a10da-112">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="a10da-113">Pour des conseils sur la meilleure façon de configurer votre environnement pour la voix d’équipes techniques, reportez-vous à l’intégration des listes de contrôle pour la [Configuration des charges de travail aux équipes voice](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams), [les fonctionnalités de base aux équipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities), [mise en réseau pour les équipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)et [l’activation d’Office 365 ](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).</span><span class="sxs-lookup"><span data-stu-id="a10da-113">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams), [Teams core capabilities](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities), [networking for Teams](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking), and [enabling Office 365](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="a10da-114">Domaines manuel</span><span class="sxs-lookup"><span data-stu-id="a10da-114">Playbook focus areas</span></span>

<span data-ttu-id="a10da-115">Le manuel vise à relever les facteurs qui influencent la perception de l’utilisateur d’un déploiement de voix d’équipes.</span><span class="sxs-lookup"><span data-stu-id="a10da-115">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="a10da-116">Les tâches et les activités sont regroupées dans les domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="a10da-116">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="a10da-117">Validation de la disponibilité du service</span><span class="sxs-lookup"><span data-stu-id="a10da-117">Validation of service readiness</span></span>

-   <span data-ttu-id="a10da-118">Activation de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="a10da-118">User enablement</span></span>

-   <span data-ttu-id="a10da-119">Points de terminaison</span><span class="sxs-lookup"><span data-stu-id="a10da-119">Endpoints</span></span>

-   <span data-ttu-id="a10da-120">L’utilisation et la qualité</span><span class="sxs-lookup"><span data-stu-id="a10da-120">Usage and quality</span></span>

-   <span data-ttu-id="a10da-121">Adoption</span><span class="sxs-lookup"><span data-stu-id="a10da-121">Adoption</span></span>

<span data-ttu-id="a10da-122">Le [Manuel d’activation de Site pour la voix (manuel)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) est un classeur Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="a10da-122">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="a10da-123">Chacun de ces cinq domaines est une feuille distincte dans le classeur, et chaque tâche de déploiement et les activités sont regroupées sur l’une de ces feuilles.</span><span class="sxs-lookup"><span data-stu-id="a10da-123">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="a10da-124">![Capture d’écran du manuel] (media/deploy-my-service-image1.png "Capture d’écran du manuel")</span><span class="sxs-lookup"><span data-stu-id="a10da-124">![Screenshot of the playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="a10da-125">Vous allez créer une instance distincte de la manuel pour chaque site dans la portée de votre déploiement d’équipes.</span><span class="sxs-lookup"><span data-stu-id="a10da-125">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="a10da-126">Comment utiliser le manuel</span><span class="sxs-lookup"><span data-stu-id="a10da-126">How to use the playbook</span></span>

<span data-ttu-id="a10da-127">Quelle que soit la taille et la complexité de l’emplacement, l’activation de chaque site nécessite que vous planifiez vos tâches et vos activités suffisamment tôt et de les exécuter dans l’ordre optimal : avant, pendant et après le déploiement du service proprement dit.</span><span class="sxs-lookup"><span data-stu-id="a10da-127">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="a10da-128">Nous vous recommandons de suivre ces étapes de planifier et d’exécuter votre propre parcours à voix de Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a10da-128">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1.  <span data-ttu-id="a10da-129">Téléchargez le [manuel d’activation de Site pour la voix (manuel)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) pour les équipes Microsoft Voice.</span><span class="sxs-lookup"><span data-stu-id="a10da-129">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2.  <span data-ttu-id="a10da-130">Créer une copie distincte de la manuel pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="a10da-130">Create a separate copy of the playbook for each site.</span></span>

3.  <span data-ttu-id="a10da-131">Sous l’onglet de la feuille intitulée **manuel pour le Code {SiteName}**, remplacez **{Nom de site-Code}** avec le nom du site approprié et/ou le code de site.</span><span class="sxs-lookup"><span data-stu-id="a10da-131">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4.  <span data-ttu-id="a10da-132">Entrez le **nom du Site, code de Site**et la **date de lancement prévue**, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a10da-132">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="a10da-133">Il s’agit d’une étape essentielle, car elle ajuste les délais recommandés pour chaque activité dans le manuel.</span><span class="sxs-lookup"><span data-stu-id="a10da-133">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

    <span data-ttu-id="a10da-134">![Exemple de nom de site de New York, NY01, le code de site et date de lancement prévue de 20-Mar-18] (media/deploy-my-service-image2.png "Exemple de nom de site de New York, NY01, le code de site et date de lancement prévue de 20-Mar-18")</span><span class="sxs-lookup"><span data-stu-id="a10da-134">![Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5.  <span data-ttu-id="a10da-135">Passez en revue chaque activité, prennent les mesures nécessaires et mettre à jour le statut que vous passez en revue le scénario.</span><span class="sxs-lookup"><span data-stu-id="a10da-135">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="a10da-136">État est représenté graphiquement, comme décrit ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="a10da-136">Status is represented graphically, as described below:</span></span>
    <ul>
    <li><span data-ttu-id="a10da-137">![Coche verte](media/deploy-my-service-image3.png) **Oui ou non applicable (vert) :** l’activité a été achevée, ou il n’est pas applicable à ce site, et aucune action supplémentaire n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a10da-137">![Green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
    <li><span data-ttu-id="a10da-138">![Point d’exclamation jaune](media/deploy-my-service-image4.png) **l’activité n’est pas achevée encore (jaune) :** l’activité n’a pas encore terminée et il doit être mis à jour à Oui ou non selon sa planification.</span><span class="sxs-lookup"><span data-stu-id="a10da-138">![Yellow exclamation point](media/deploy-my-service-image4.png) **The activity isn’t completed yet (yellow):** The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
    <li><span data-ttu-id="a10da-139">![Rouge X](media/deploy-my-service-image5.png) **Aucun (rouge) :** l’activité ne peut pas être terminée en raison d’un problème et doit être exécutée à la réunion.</span><span class="sxs-lookup"><span data-stu-id="a10da-139">![Red X](media/deploy-my-service-image5.png) **No (red):** The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6.  <span data-ttu-id="a10da-140">Le statut est reporté dans chaque section, et l’en-tête de section est mis en forme avec l’un de ces indicateurs d’état.</span><span class="sxs-lookup"><span data-stu-id="a10da-140">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="a10da-141">**Rapport hebdomadaire** est également mis à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a10da-141">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="a10da-142">![Capture d’écran du hebdomadaire état roll-ups dans le manuel] (media/deploy-my-service-image6.png "Capture d’écran du hebdomadaire état roll-ups dans le manuel")</span><span class="sxs-lookup"><span data-stu-id="a10da-142">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="a10da-143">Répétez les étapes ci-dessus pour tous les emplacements que vous avez.</span><span class="sxs-lookup"><span data-stu-id="a10da-143">Repeat the steps above for all the locations you have.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a10da-144">Certaines étapes n’est peut-être pas applicables à tous les sites et emplacements.</span><span class="sxs-lookup"><span data-stu-id="a10da-144">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="a10da-145">Si une activité donnée ne correspond pas à un site, vous devez sélectionner **non applicable** pour cette activité.</span><span class="sxs-lookup"><span data-stu-id="a10da-145">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="a10da-146">**Ne supprimez pas** les lignes dans le manuel ; Dans ce cas, les formules de cumul d’état ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="a10da-146">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="a10da-147">Faites attention aux activités qui peuvent prendre plus de temps que vous prévues, telles que le portage des numéros et des activités d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="a10da-147">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="a10da-148">Ces activités peuvent une incidence négative sur la barre de planning de déploiement de site.</span><span class="sxs-lookup"><span data-stu-id="a10da-148">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="a10da-149">Veillez à passer en revue et mettre à jour la liste des activités et la chronologie associée toutes les semaines, les présenter aux [réunions du comité de direction](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) pour vous assurer que les parties prenantes sont informés de l’état de chaque site et tous les écarts possibles à partir de la planification du déploiement.</span><span class="sxs-lookup"><span data-stu-id="a10da-149">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="a10da-150">Points de décision</span><span class="sxs-lookup"><span data-stu-id="a10da-150">Decision points</span></span></td><td><ul><li><span data-ttu-id="a10da-151">Décider si le manuel de prise en charge du Site est nécessaire pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="a10da-151">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="a10da-152">Déterminer qui sera responsable de la personnalisation de la manuel d’activation de Site pour le Teams de Microsoft pour tous les sites que vous allez déployer.</span><span class="sxs-lookup"><span data-stu-id="a10da-152">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you'll deploy.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="a10da-153">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="a10da-153">Next steps</span></span></td><td><ul><li><span data-ttu-id="a10da-154">Téléchargez le manuel de prise en charge du Site.</span><span class="sxs-lookup"><span data-stu-id="a10da-154">Download the Site Enablement Playbook.</span></span></li><li><span data-ttu-id="a10da-155">Personnaliser le manuel de gestion de Site pour votre site premier.</span><span class="sxs-lookup"><span data-stu-id="a10da-155">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="a10da-156">Répétez si nécessaire pour les sites supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="a10da-156">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->