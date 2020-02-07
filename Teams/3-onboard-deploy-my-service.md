---
title: Déployer le service vocal cloud de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience: admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Téléchargez le manuel d’utilisation du site pour planifier le déploiement de vos équipes et accélérer et optimiser l’adoption des utilisateurs, la perception de la qualité et la satisfaction.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65a9c79dd29656b7bdc8563f0444d90133399f2b
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825172"
---
# <a name="deploy-my-service"></a><span data-ttu-id="ab5fa-103">Déployer mon service</span><span class="sxs-lookup"><span data-stu-id="ab5fa-103">Deploy my service</span></span>

<span data-ttu-id="ab5fa-104">Cet article fournit une vue d’ensemble de la configuration requise pour le déploiement approprié des services vocaux Cloud.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="ab5fa-105">En suivant les recommandations en matière de déploiement de services vocaux Cloud, vous pouvez vous assurer que vous disposez bien de toutes les exigences et que vous fournissez des résultats répétitifs.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="ab5fa-106">Manuel d’activation des sites pour les charges de travail Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="ab5fa-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="ab5fa-107">Utilisez ce manuel pour aider votre organisation à planifier et à exécuter correctement le déploiement des fonctionnalités vocales de Microsoft teams sur une base site par site.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="ab5fa-108">Incluant toutes les activités requises, les chronologies recommandées et les liens vers des instructions correspondantes pour chaque activité, le présent manuel décrit les conseils de bout en bout pour vous permettre de garantir le déploiement de votre voix teams pour un site donné, en insistant sur les facteurs importants. à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="ab5fa-109">En remplissant les activités de ce manuel, votre organisation peut :</span><span class="sxs-lookup"><span data-stu-id="ab5fa-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="ab5fa-110">Planifiez et planifiez efficacement le déploiement de votre équipe.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="ab5fa-111">Accélérez et optimisez l’adoption des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="ab5fa-112">Réduisez les besoins en matière de support et augmentez la satisfaction des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="ab5fa-113">Cet article et le manuel associé n’ont pas été prévus pour décrire chaque étape de configuration technique requise pour l’activation du service ou la fourniture de tonalités de numérotation à un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="ab5fa-114">Au lieu de cela, ils se concentrent sur les activités et les tâches qui sont recommandées pour intégrer facilement les utilisateurs et leur permettre d’utiliser les charges de travail vocales d’équipes grâce à une transition rapide et plus fluide, tout en minimisant le niveau de prise en charge requise.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="ab5fa-115">Pour obtenir des conseils techniques sur la configuration de votre environnement pour teams Voice, voir les listes de contrôle d’intégration pour la [Configuration des charges de travail vocales](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)d’équipe, la [configuration du routage direct dans teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), les [fonctionnalités de base](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)d’équipe, la [mise en réseau pour les équipes](onboarding-checklist-configure-networking.md)et [l’activation d’Office 365](onboarding-checklist-enable-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ab5fa-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](onboarding-checklist-configure-networking.md), and [enabling Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="ab5fa-116">Zones ciblées du manuel</span><span class="sxs-lookup"><span data-stu-id="ab5fa-116">Playbook focus areas</span></span>

<span data-ttu-id="ab5fa-117">Le manifeste consiste à traiter les facteurs qui influencent la perception de l’utilisateur par un déploiement vocal d’équipes.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="ab5fa-118">Les activités et les tâches sont regroupées dans les zones ciblées suivantes :</span><span class="sxs-lookup"><span data-stu-id="ab5fa-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="ab5fa-119">Validation de la disponibilité du service</span><span class="sxs-lookup"><span data-stu-id="ab5fa-119">Validation of service readiness</span></span>
    - <span data-ttu-id="ab5fa-120">Audioconférence,</span><span class="sxs-lookup"><span data-stu-id="ab5fa-120">Audio Conferencing</span></span>
    - <span data-ttu-id="ab5fa-121">Forfaits d’appel</span><span class="sxs-lookup"><span data-stu-id="ab5fa-121">Calling Plans</span></span>
    - <span data-ttu-id="ab5fa-122">Routage direct</span><span class="sxs-lookup"><span data-stu-id="ab5fa-122">Direct Routing</span></span>

-   <span data-ttu-id="ab5fa-123">Activation utilisateur</span><span class="sxs-lookup"><span data-stu-id="ab5fa-123">User enablement</span></span>

-   <span data-ttu-id="ab5fa-124">Points de terminaison</span><span class="sxs-lookup"><span data-stu-id="ab5fa-124">Endpoints</span></span>

-   <span data-ttu-id="ab5fa-125">Utilisation et qualité</span><span class="sxs-lookup"><span data-stu-id="ab5fa-125">Usage and quality</span></span>

-   <span data-ttu-id="ab5fa-126">Croissante</span><span class="sxs-lookup"><span data-stu-id="ab5fa-126">Adoption</span></span>

<span data-ttu-id="ab5fa-127">Le manuel [d’activation des sites pour les appels vocaux](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) est un classeur Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="ab5fa-128">Chacun de ces cinq domaines de focalisation est une feuille séparée dans le classeur, et chaque tâche et activité de déploiement est regroupée sur l’une de ces feuilles.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="ab5fa-129">![Capture d’écran du manuel d’activation du site](media/deploy-my-service-image1.png "Capture d’écran du manuel")</span><span class="sxs-lookup"><span data-stu-id="ab5fa-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="ab5fa-130">Vous allez créer une instance distincte du manuel pour chaque site dans le cadre de votre déploiement d’équipes.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="ab5fa-131">Utiliser le manuel</span><span class="sxs-lookup"><span data-stu-id="ab5fa-131">How to use the playbook</span></span>

<span data-ttu-id="ab5fa-132">Quelle que soit la taille et la complexité de l’emplacement, l’activation de chaque site exige de planifier vos tâches et vos activités au plus vite, et de les exécuter dans un ordre optimal, avant, pendant et après le déploiement réel du service.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="ab5fa-133">Nous vous recommandons de suivre ces étapes lors de la planification et de l’exécution de votre propre voyage dans Microsoft teams Voice.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="ab5fa-134">Téléchargez le [Manuel d’activation de site pour les appels vocaux (manuel)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) pour Microsoft teams Voice.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="ab5fa-135">Créez une copie distincte du manuel pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="ab5fa-136">Dans l’onglet de la feuille de passe du **{nom_site-code}**, remplacez **{SiteName-code}** par le nom de site et/ou le code du site pertinents.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="ab5fa-137">Entrez le **nom du site, le code du site**et la **Date de lancement prévue**, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="ab5fa-138">Il s’agit d’une étape essentielle, car elle ajuste les délais recommandés pour chaque activité du manuel.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="ab5fa-139">![Exemple avec le nom du site, le code du site et la date de lancement planifiée](media/deploy-my-service-image2.png "Exemple avec le nom de site New York, le code de site NY01 et la date de début planifiée 20-Mar-18")</span><span class="sxs-lookup"><span data-stu-id="ab5fa-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="ab5fa-140">Examinez chaque activité, effectuez les actions nécessaires et mettez à jour l’État à mesure que vous parcourez la chronologie.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="ab5fa-141">Le statut est représenté sous forme graphique, comme décrit ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="ab5fa-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="ab5fa-142">![Illustration d’une coche](media/deploy-my-service-image3.png) verte **: oui ou non applicable (vert) :** l’activité est terminée ou n’est pas applicable pour ce site, et aucune action supplémentaire n’est requise.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="ab5fa-143">![Image d’un point](media/deploy-my-service-image4.png) d’exclamation jaune <strong>l’activité n’est pas achevée (jaune) :</strong> l’activité n’a pas encore été achevée et doit être mise à jour sur Oui ou non.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="ab5fa-144">![Illustration d’un X rouge indiquant qu'](media/deploy-my-service-image5.png) il n’y a <strong>pas de no (rouge) :</strong> l’activité ne peut pas être effectuée en raison d’un problème et doit être acheminée vers la réunion d’État du projet.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="ab5fa-145">Le statut est répété dans chaque section, et le titre de section est mis en forme avec l’un de ces indicateurs d’État.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="ab5fa-146">Le **statut hebdomadaire** est également mis à jour automatiquement.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="ab5fa-147">![Capture d’écran des déploiements de l’état hebdomadaire dans le manuel](media/deploy-my-service-image6.png "Capture d’écran des déploiements de l’état hebdomadaire dans le manuel")</span><span class="sxs-lookup"><span data-stu-id="ab5fa-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="ab5fa-148">Répétez les étapes ci-dessus pour tous les emplacements que vous avez.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab5fa-149">Certaines étapes peuvent ne pas être applicables à tous les sites et emplacements.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="ab5fa-150">Si une activité spécifique n’est pas pertinente pour un site, vous devez sélectionner **non applicable** pour cette activité.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="ab5fa-151">**Ne supprimez pas** les lignes du manuel. dans le cas contraire, les formules de report ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="ab5fa-152">Soyez attentif aux activités qui peuvent durer plus longtemps que prévu (par exemple, le transfert de numéros et les activités d’approvisionnement).</span><span class="sxs-lookup"><span data-stu-id="ab5fa-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="ab5fa-153">Ces activités peuvent avoir un impact négatif sur la chronologie du déploiement de site.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="ab5fa-154">Veillez à vérifier et à mettre à jour la liste des activités et la chronologie associée de manière hebdomadaire, et à les présenter à des [réunions du Comité de direction](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) pour vous assurer que les parties prenantes sont consciente de l’état de chaque site et des écarts possibles de la planification du déploiement.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="ab5fa-155">Points de décision</span><span class="sxs-lookup"><span data-stu-id="ab5fa-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="ab5fa-156">Déterminez si le manuel d’activation du site est requis pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="ab5fa-157">Déterminez qui sera responsable de la personnalisation du manuel d’activation des sites de Microsoft teams pour chaque site que vous déploierez.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="ab5fa-158">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="ab5fa-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="ab5fa-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Télécharger le manuel d’activation de site</a>.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="ab5fa-160">Personnalisez le manuel d’activation de site pour votre premier site.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="ab5fa-161">Répétez cette procédure si nécessaire pour les sites supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->