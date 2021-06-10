---
title: Déployer le service vocal cloud de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Téléchargez le manuel d’enablement de site pour planifier votre déploiement Teams optimiser et accélérer l’adoption, la perception de la qualité et la satisfaction des utilisateurs.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112630"
---
# <a name="deploy-my-service"></a><span data-ttu-id="2baf2-103">Déployer mon service</span><span class="sxs-lookup"><span data-stu-id="2baf2-103">Deploy my service</span></span>

<span data-ttu-id="2baf2-104">Cet article donne une vue d’ensemble des conditions requises pour déployer correctement les services vocaux cloud.</span><span class="sxs-lookup"><span data-stu-id="2baf2-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="2baf2-105">En suivant des instructions en exposant pour le déploiement des services vocaux cloud, vous pouvez vous assurer de prendre en compte toutes les exigences et d’obtenir des résultats répétés.</span><span class="sxs-lookup"><span data-stu-id="2baf2-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="2baf2-106">Manuel d’enablement de site pour les Microsoft Teams de travail vocales</span><span class="sxs-lookup"><span data-stu-id="2baf2-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="2baf2-107">Utilisez ce manuel pour aider votre organisation à planifier et exécuter correctement le déploiement des fonctionnalités vocales Microsoft Teams site par site.</span><span class="sxs-lookup"><span data-stu-id="2baf2-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="2baf2-108">Comprenant toutes les activités requises, les chronologies recommandées et des liens vers des recommandations correspondantes pour chaque activité, ce manuel couvre les conseils de bout en bout pour assurer la réussite d’un déploiement vocal Teams pour un site donné, en se concentreant sur les facteurs qui sont importants pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2baf2-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="2baf2-109">En complétant les activités de ce manuel, votre organisation peut :</span><span class="sxs-lookup"><span data-stu-id="2baf2-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="2baf2-110">Planifiez et planifiez efficacement votre Teams déploiement.</span><span class="sxs-lookup"><span data-stu-id="2baf2-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="2baf2-111">Optimisez et optimisez l’adoption par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2baf2-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="2baf2-112">Réduisez les besoins de support et augmentez la satisfaction des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2baf2-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="2baf2-113">Cet article et le manuel associé n’ont pas pour objet de décrire toutes les étapes de configuration technique requises pour l’enablement du service ou la fourniture de numéros de numérotation à un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="2baf2-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="2baf2-114">Au lieu de cela, ils se concentrent sur les activités et les tâches recommandées pour intégrer facilement les utilisateurs et leur faire commencer à consommer des charges de travail Teams vocales par le biais d’une transition rapide et fluide avec un taux d’adoption élevé, tout en réduisant les exigences de support.</span><span class="sxs-lookup"><span data-stu-id="2baf2-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="2baf2-115">Pour obtenir des conseils techniques sur la configuration de votre environnement pour voix Teams au mieux, consultez les listes de contrôle d’intégration pour configurer les charges de travail [vocales d’Teams,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)la configuration du routage direct dans [Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)les fonctionnalités principales de [Teams,](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)la mise en réseau de [Teams](prepare-network.md)et l’activation de Microsoft 365 ou [Office 365.](onboarding-checklist-enable-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="2baf2-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](prepare-network.md), and [enabling Microsoft 365 or Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="2baf2-116">Zones de focus du manuel</span><span class="sxs-lookup"><span data-stu-id="2baf2-116">Playbook focus areas</span></span>

<span data-ttu-id="2baf2-117">L’objectif du manuel est de traiter les facteurs qui influencent la vision de l’utilisateur d’un déploiement Teams voix.</span><span class="sxs-lookup"><span data-stu-id="2baf2-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="2baf2-118">Les activités et les tâches sont regroupées dans les zones de focus suivantes :</span><span class="sxs-lookup"><span data-stu-id="2baf2-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="2baf2-119">Validation de la disponibilité du service</span><span class="sxs-lookup"><span data-stu-id="2baf2-119">Validation of service readiness</span></span>
    - <span data-ttu-id="2baf2-120">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="2baf2-120">Audio Conferencing</span></span>
    - <span data-ttu-id="2baf2-121">Forfaits d’appel</span><span class="sxs-lookup"><span data-stu-id="2baf2-121">Calling Plans</span></span>
    - <span data-ttu-id="2baf2-122">Routage direct</span><span class="sxs-lookup"><span data-stu-id="2baf2-122">Direct Routing</span></span>

-   <span data-ttu-id="2baf2-123">Enablement utilisateur</span><span class="sxs-lookup"><span data-stu-id="2baf2-123">User enablement</span></span>

-   <span data-ttu-id="2baf2-124">Points de terminaison</span><span class="sxs-lookup"><span data-stu-id="2baf2-124">Endpoints</span></span>

-   <span data-ttu-id="2baf2-125">Utilisation et qualité</span><span class="sxs-lookup"><span data-stu-id="2baf2-125">Usage and quality</span></span>

-   <span data-ttu-id="2baf2-126">Adoption</span><span class="sxs-lookup"><span data-stu-id="2baf2-126">Adoption</span></span>

<span data-ttu-id="2baf2-127">Le [manuel d’enablement de site pour voix (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) est un Microsoft Excel de travail.</span><span class="sxs-lookup"><span data-stu-id="2baf2-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="2baf2-128">Chacun de ces cinq zones de focus est une feuille distincte dans le manuel, et chaque tâche et activité de déploiement est regroupée sur l’une de ces feuilles.</span><span class="sxs-lookup"><span data-stu-id="2baf2-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="2baf2-129">![Capture d’écran du manuel d’enablement de site](media/deploy-my-service-image1.png "Capture d’écran du manuel")</span><span class="sxs-lookup"><span data-stu-id="2baf2-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="2baf2-130">Vous devez créer une instance distincte du manuel pour chaque site dans l’étendue de votre déploiement Teams lecture.</span><span class="sxs-lookup"><span data-stu-id="2baf2-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="2baf2-131">Comment utiliser le manuel</span><span class="sxs-lookup"><span data-stu-id="2baf2-131">How to use the playbook</span></span>

<span data-ttu-id="2baf2-132">Quelle que soit la taille et la complexité de l’emplacement, l’activation de chaque site nécessite que vous planniez vos tâches et activités suffisamment tôt et que vous les exécutez dans un ordre optimal, avant, pendant et après le déploiement réel du service.</span><span class="sxs-lookup"><span data-stu-id="2baf2-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="2baf2-133">Nous vous recommandons de suivre ces étapes lorsque vous planifiez et exécutez votre propre voyage pour Microsoft Teams voix.</span><span class="sxs-lookup"><span data-stu-id="2baf2-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="2baf2-134">Téléchargez [le manuel d’enablement de site pour voix (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) Microsoft Teams Voice.</span><span class="sxs-lookup"><span data-stu-id="2baf2-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="2baf2-135">Créez une copie distincte du manuel pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="2baf2-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="2baf2-136">Dans l’onglet de la feuille nommée **Playbook pour {SiteName-Code},** remplacez **{SiteName-Code}** par le nom et/ou le code de site appropriés.</span><span class="sxs-lookup"><span data-stu-id="2baf2-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="2baf2-137">Entrez le **nom du site, le code du site** et la date de lancement **planifié,** comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2baf2-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="2baf2-138">Il s’agit d’une étape critique, car elle ajuste les délais recommandés pour chaque activité dans le manuel.</span><span class="sxs-lookup"><span data-stu-id="2baf2-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="2baf2-139">![Exemple avec nom de site, code de site et date de lancement planifié](media/deploy-my-service-image2.png "Exemple avec le nom du site de New York, le code de site NY01 et la date de lancement prévue du 20 mars 2018")</span><span class="sxs-lookup"><span data-stu-id="2baf2-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="2baf2-140">Examinez chaque activité, prenez les mesures nécessaires et mettez à jour l’état à mesure que vous vous y promenez dans la chronologie.</span><span class="sxs-lookup"><span data-stu-id="2baf2-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="2baf2-141">L’état est représenté graphiquement, comme décrit ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="2baf2-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="2baf2-142">![Illustration d’une coche verte Oui ou non ](media/deploy-my-service-image3.png) **applicable (vert)** : l’activité est terminée ou n’est pas applicable à ce site et aucune autre action n’est requise.</span><span class="sxs-lookup"><span data-stu-id="2baf2-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="2baf2-143">![Illustration d’un point d’exclamation jaune ](media/deploy-my-service-image4.png) <strong>L’activité n’est</strong> pas encore terminée (jaune) : l’activité n’a pas encore été effectuée et doit être mise à jour sur Oui ou Non dans son planning.</span><span class="sxs-lookup"><span data-stu-id="2baf2-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="2baf2-144">![Illustration d’un X rouge indiquant non (rouge) : l’activité ne peut pas se terminer en raison d’un problème et doit être portée à la réunion ](media/deploy-my-service-image5.png) <strong></strong> d’état du projet.</span><span class="sxs-lookup"><span data-stu-id="2baf2-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="2baf2-145&quot;>L’état est déployé dans chaque section et le titre de section est mis en forme avec l’un de ces indicateurs d’état.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;2baf2-145&quot;>The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id=&quot;2baf2-146&quot;>**L’état** hebdomadaire est également mis à jour automatiquement.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;2baf2-146&quot;>**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id=&quot;2baf2-147&quot;>![Capture d’écran des listes de rapport d’état hebdomadaires dans le manuel](media/deploy-my-service-image6.png &quot;Capture d’écran des listes de rapport d’état hebdomadaires dans le manuel")</span><span class="sxs-lookup"><span data-stu-id="2baf2-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="2baf2-148">Répétez les étapes ci-dessus pour tous vos emplacements.</span><span class="sxs-lookup"><span data-stu-id="2baf2-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2baf2-149">Certaines étapes peuvent ne pas être applicables à tous les emplacements et sites.</span><span class="sxs-lookup"><span data-stu-id="2baf2-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="2baf2-150">Si une activité spécifique n’est pas pertinente pour un site, vous devez sélectionner **Non applicable** pour cette activité.</span><span class="sxs-lookup"><span data-stu-id="2baf2-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="2baf2-151">**NE SUPPRIMEZ AUCUNE** ligne du manuel ; Si c’est le cas, les formules de rapport d’état ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="2baf2-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="2baf2-152">Faites attention aux activités qui peuvent prendre plus de temps que prévu, telles que les activités de portage de numéro et d’approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="2baf2-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="2baf2-153">Ces activités peuvent affecter négativement la chronologie du déploiement du site.</span><span class="sxs-lookup"><span data-stu-id="2baf2-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="2baf2-154">Veillez à examiner et à mettre à jour la [](./envision-steering-committee-complete-guide.md) liste des activités et la chronologie associée de façon hebdomadaire, et à les présenter lors de réunions de comité spécial afin de vous assurer que les parties prenantes sont conscientes de l’état de chaque site et des écarts possibles par rapport à la planification du déploiement.</span><span class="sxs-lookup"><span data-stu-id="2baf2-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](./envision-steering-committee-complete-guide.md) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="2baf2-155">Points de décision</span><span class="sxs-lookup"><span data-stu-id="2baf2-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="2baf2-156">Déterminez si le manuel d’enablement de site est requis pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="2baf2-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="2baf2-157">Décidez qui sera responsable de la personnalisation du manuel d’Microsoft Teams pour chaque site que vous allez déployer.</span><span class="sxs-lookup"><span data-stu-id="2baf2-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="2baf2-158">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="2baf2-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="2baf2-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Téléchargez le manuel d’enablement de site.</a></span><span class="sxs-lookup"><span data-stu-id="2baf2-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="2baf2-160">Personnalisez le manuel d’enablement de site pour votre premier site.</span><span class="sxs-lookup"><span data-stu-id="2baf2-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="2baf2-161">Répétez l’une des répétitions nécessaires pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="2baf2-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->