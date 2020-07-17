---
title: Mise à niveau de Microsoft teams | Évaluation de l’environnement, questions de découverte
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Suivez ces instructions pour en savoir plus sur la configuration requise pour évaluer votre environnement actuel et procéder à la mise à niveau vers Teams.
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
ms.openlocfilehash: 799d348f05c8fece6684d01768934faedcb7603f
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158742"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="9700e-103">Évaluez votre environnement avant de procéder à la mise à niveau vers teams</span><span class="sxs-lookup"><span data-stu-id="9700e-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="9700e-104">![Diagramme de route de mise à niveau, mettant l’accent sur l’étape de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du parcours de la mise à niveau, en mettant l’accent sur l’étape de préparation technique")</span><span class="sxs-lookup"><span data-stu-id="9700e-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="9700e-105">Cet article fait partie de l’étape de préparation technique de votre mouvement de mise à niveau, une activité que vous finalisez en parallèle avec l’étape de préparation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9700e-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="9700e-106">Avant de continuer, assurez-vous d’avoir suivi les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="9700e-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="9700e-107">Inscription des parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="9700e-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="9700e-108">Définition de l’objectif de votre projet</span><span class="sxs-lookup"><span data-stu-id="9700e-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="9700e-109">Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes</span><span class="sxs-lookup"><span data-stu-id="9700e-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="9700e-110">Choix de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="9700e-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="9700e-111">Cet article fournit une vue d’ensemble de la configuration requise pour évaluer correctement votre environnement actuel pour les équipes d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="9700e-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="9700e-112">L’évaluation de votre environnement vous permet d’identifier les risques et les exigences qui influenceront votre déploiement global.</span><span class="sxs-lookup"><span data-stu-id="9700e-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="9700e-113">En identifiant ces éléments à l’aide de la commande, vous pouvez ajuster la planification du succès.</span><span class="sxs-lookup"><span data-stu-id="9700e-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="9700e-114">Présentation du questionnaire de découverte</span><span class="sxs-lookup"><span data-stu-id="9700e-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="9700e-115">Pour obtenir les résultats de votre clé objective (OKRs), vous avez déjà effectué des décisions relatives aux services clés.</span><span class="sxs-lookup"><span data-stu-id="9700e-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="9700e-116">L’étape suivante consiste à effectuer une recherche environnementale pour évaluer tous les aspects relatifs à votre infrastructure, au réseau et aux opérations informatiques pour vérifier que votre organisation est prête à implémenter la solution.</span><span class="sxs-lookup"><span data-stu-id="9700e-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="9700e-117">La découverte est l’une des principales étapes principales que vous prenez lors de la planification de votre voyage vers Teams.</span><span class="sxs-lookup"><span data-stu-id="9700e-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="9700e-118">La découverte environnementale doit inclure une évaluation de la compatibilité réseau pour s’assurer que votre réseau peut prendre en charge la mise à niveau vers Teams.</span><span class="sxs-lookup"><span data-stu-id="9700e-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="9700e-119">Vous effectuez une découverte détaillée de votre environnement pour mieux comprendre son état actuel et révéler les difficultés ou, d’autant plus importants, les bloqueurs possibles d’exécution de votre déploiement d’équipes.</span><span class="sxs-lookup"><span data-stu-id="9700e-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="9700e-120">Vous identifiez les risques techniques dans le cadre d’une analyse environnementale et de l’évaluation de l’adoption, et vous développez un plan d’atténuation pour chaque risque identifié.</span><span class="sxs-lookup"><span data-stu-id="9700e-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="9700e-121">Vous devez incorporer ces informations dans le registre de risques.</span><span class="sxs-lookup"><span data-stu-id="9700e-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="9700e-122">Toutes les questions liées à votre infrastructure de collaboration existante et à Microsoft 365 365 ou à votre organisation, à la mise en réseau, aux points de terminaison, aux opérations et à l’adoption et à la disponibilité font partie du questionnaire de découverte environnementale.</span><span class="sxs-lookup"><span data-stu-id="9700e-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="9700e-123">Collaborer avec votre équipe de projet pour fournir les informations demandées autant de détails que possible pour faciliter vos activités de planification.</span><span class="sxs-lookup"><span data-stu-id="9700e-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="9700e-124">[Ce questionnaire](upgrade-plan-journey-discovery-questionnaire.md) est divisé en sections suivantes pour confirmer la compatibilité de votre organisation pour le déploiement d’équipes dans plusieurs domaines principaux :</span><span class="sxs-lookup"><span data-stu-id="9700e-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="9700e-125">Détails de l’organisation Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="9700e-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="9700e-126">Résumé de la plateforme de collaboration existante</span><span class="sxs-lookup"><span data-stu-id="9700e-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="9700e-127">Détails du déploiement de la plateforme de collaboration</span><span class="sxs-lookup"><span data-stu-id="9700e-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="9700e-128">Mise en réseau et accès aux services Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="9700e-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="9700e-129">Points de terminaison</span><span class="sxs-lookup"><span data-stu-id="9700e-129">Endpoints</span></span>
- <span data-ttu-id="9700e-130">Opérations</span><span class="sxs-lookup"><span data-stu-id="9700e-130">Operations</span></span>
- <span data-ttu-id="9700e-131">Adoption et préparation</span><span class="sxs-lookup"><span data-stu-id="9700e-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="9700e-132">Vous pouvez commencer par copier le questionnaire dans un document Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="9700e-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="9700e-133">Essayez de répondre à toutes vos questions et de capturer tous les détails lors de votre déplacement.</span><span class="sxs-lookup"><span data-stu-id="9700e-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="9700e-134">Point de décision</span><span class="sxs-lookup"><span data-stu-id="9700e-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="9700e-135">Qui sera chargé d’effectuer une évaluation de l’environnement ?</span><span class="sxs-lookup"><span data-stu-id="9700e-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="9700e-136">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="9700e-136">Next step</span></span></td><td><ul><li><span data-ttu-id="9700e-137">Documentez les résultats de l’évaluation de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="9700e-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="9700e-138">Équipe de projet</span><span class="sxs-lookup"><span data-stu-id="9700e-138">Project team</span></span>

<span data-ttu-id="9700e-139">Assurez-vous d’avoir engagé les personnes appropriées à votre équipe de projet.</span><span class="sxs-lookup"><span data-stu-id="9700e-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="9700e-140">Vérifiez les étapes que vous avez effectuées dans [inscrire les parties prenantes de votre projet](upgrade-enlist-stakeholders.md).</span><span class="sxs-lookup"><span data-stu-id="9700e-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="9700e-141">Après avoir évalué votre environnement, passez à l’étape suivante : [préparer votre service](upgrade-prepare-environment-prepare-service.md).</span><span class="sxs-lookup"><span data-stu-id="9700e-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
