---
title: Évaluer votre environnement avant de mettre à niveau vers Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez les conditions requises pour évaluer correctement votre environnement actuel pour la mise à niveau vers Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: aeb236edddea69c1c112b695c9323de19da46092
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282201"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="6399d-103">Évaluer votre environnement avant de mettre à niveau vers Teams</span><span class="sxs-lookup"><span data-stu-id="6399d-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="6399d-104">![Diagramme de voyage de mise à niveau mettant en relief la phase de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du voyage de mise à niveau, avec l’accentuation sur la phase de préparation technique")</span><span class="sxs-lookup"><span data-stu-id="6399d-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="6399d-105">Cet article fait partie de la phase de préparation technique de votre voyage de mise à niveau, une activité que vous terminez en parallèle de la phase de préparation utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6399d-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="6399d-106">Avant de poursuivre, confirmez que vous avez effectué ces activités à partir des étapes précédentes :</span><span class="sxs-lookup"><span data-stu-id="6399d-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="6399d-107">Demandez aux parties prenantes de votre projet</span><span class="sxs-lookup"><span data-stu-id="6399d-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="6399d-108">Étendue définie de votre projet</span><span class="sxs-lookup"><span data-stu-id="6399d-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="6399d-109">Coexistence et interopérabilité comprises entre les systèmes Skype Entreprise et Teams</span><span class="sxs-lookup"><span data-stu-id="6399d-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="6399d-110">Nous avons choisi votre chemin de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="6399d-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="6399d-111">Cet article donne une vue d’ensemble des conditions requises pour évaluer correctement votre environnement actuel pour l’Teams.</span><span class="sxs-lookup"><span data-stu-id="6399d-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="6399d-112">En évaluez votre environnement, vous identifiez les risques et les exigences qui influenceront votre déploiement global.</span><span class="sxs-lookup"><span data-stu-id="6399d-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="6399d-113">En identifiant au préalable ces éléments, vous pouvez ajuster votre planification pour être réussi.</span><span class="sxs-lookup"><span data-stu-id="6399d-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="6399d-114">Présentation du questionnaire de découverte</span><span class="sxs-lookup"><span data-stu-id="6399d-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="6399d-115">Pour obtenir les résultats de votre clé d’objectif (OKR), vous avez précédemment pris des décisions importantes en matière de service.</span><span class="sxs-lookup"><span data-stu-id="6399d-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="6399d-116">L’étape suivante consiste à effectuer la découverte de l’environnement afin d’évaluer tous les aspects liés à votre infrastructure informatique, votre réseau et vos opérations pour confirmer que votre organisation est prête à implémenter la solution.</span><span class="sxs-lookup"><span data-stu-id="6399d-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="6399d-117">La découverte est l’une des premières étapes clés que vous devez suivre lorsque vous planifiez votre parcours vers Teams.</span><span class="sxs-lookup"><span data-stu-id="6399d-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="6399d-118">La découverte de l’environnement doit inclure une évaluation de la disponibilité du réseau pour s’assurer que votre réseau peut prendre en charge la mise à niveau vers Teams.</span><span class="sxs-lookup"><span data-stu-id="6399d-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="6399d-119">Vous effectuez une découverte détaillée de votre environnement pour mieux comprendre son état actuel et révéler les difficultés ou, encore plus importantes, les bloqueurs possibles dans l’exécution de votre déploiement de Teams.</span><span class="sxs-lookup"><span data-stu-id="6399d-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="6399d-120">Vous identifiez les risques techniques dans le cadre d’une évaluation de l’environnement et de l’évaluation de la préparation pour l’adoption, et développez un plan d’atténuation pour chaque risque identifié.</span><span class="sxs-lookup"><span data-stu-id="6399d-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="6399d-121">Vous devez incorporer ces informations dans le registre des risques.</span><span class="sxs-lookup"><span data-stu-id="6399d-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="6399d-122">Toutes les questions relatives à votre infrastructure de collaboration existante et à votre organisation Microsoft 365 ou Office 365, à la mise en réseau, aux points de terminaison, aux opérations, à l’adoption et à la préparation sont incluses dans le questionnaire de détection de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="6399d-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="6399d-123">Travaillez avec votre équipe de projet pour fournir les informations demandées avec autant de détails que possible afin de faciliter vos activités de planification.</span><span class="sxs-lookup"><span data-stu-id="6399d-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="6399d-124">[Le questionnaire](upgrade-plan-journey-discovery-questionnaire.md) est divisé entre les sections suivantes pour confirmer que votre organisation est prête pour le déploiement de Teams dans plusieurs domaines principaux :</span><span class="sxs-lookup"><span data-stu-id="6399d-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="6399d-125">Microsoft 365 ou Office 365 détails de votre organisation</span><span class="sxs-lookup"><span data-stu-id="6399d-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="6399d-126">Résumé de la plateforme de collaboration existante</span><span class="sxs-lookup"><span data-stu-id="6399d-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="6399d-127">Détails du déploiement de la plateforme de collaboration</span><span class="sxs-lookup"><span data-stu-id="6399d-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="6399d-128">Réseaux et accès à Microsoft 365 services Office 365 réseau</span><span class="sxs-lookup"><span data-stu-id="6399d-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="6399d-129">Points de terminaison</span><span class="sxs-lookup"><span data-stu-id="6399d-129">Endpoints</span></span>
- <span data-ttu-id="6399d-130">Opérations</span><span class="sxs-lookup"><span data-stu-id="6399d-130">Operations</span></span>
- <span data-ttu-id="6399d-131">Adoption et préparation</span><span class="sxs-lookup"><span data-stu-id="6399d-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="6399d-132">Vous pouvez commencer par copier le questionnaire dans un Microsoft Word document.</span><span class="sxs-lookup"><span data-stu-id="6399d-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="6399d-133">Essayez de répondre à toutes les questions et capturez tous les détails à mesure que vous vous déplacez.</span><span class="sxs-lookup"><span data-stu-id="6399d-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="6399d-134">Point de décision</span><span class="sxs-lookup"><span data-stu-id="6399d-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="6399d-135">Qui vous serez responsable de l’évaluation de l’environnement ?</span><span class="sxs-lookup"><span data-stu-id="6399d-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="6399d-136">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="6399d-136">Next step</span></span></td><td><ul><li><span data-ttu-id="6399d-137">Documenter les résultats de l’évaluation de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="6399d-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="6399d-138">Project d’équipe</span><span class="sxs-lookup"><span data-stu-id="6399d-138">Project team</span></span>

<span data-ttu-id="6399d-139">Assurez-vous d’avoir impliqué les bons employés pour votre équipe de projet.</span><span class="sxs-lookup"><span data-stu-id="6399d-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="6399d-140">Vérifiez les étapes que vous avez effectuées dans [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md).</span><span class="sxs-lookup"><span data-stu-id="6399d-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="6399d-141">Après avoir évalué votre environnement, passer à l’étape suivante : [Préparer votre service.](upgrade-prepare-environment-prepare-service.md)</span><span class="sxs-lookup"><span data-stu-id="6399d-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>