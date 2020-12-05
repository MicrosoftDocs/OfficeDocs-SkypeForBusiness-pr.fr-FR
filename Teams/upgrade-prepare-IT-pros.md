---
title: Préparer votre équipe informatique pour Microsoft teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez comment préparer le personnel informatique au sein de votre organisation pour le déploiement et la prise en charge de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 680106618d610d0adc3f93658e3a522d63850e24
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578457"
---
# <a name="prepare-your-it-staff-for-microsoft-teams"></a><span data-ttu-id="9c3a3-103">Préparer votre équipe informatique pour Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="9c3a3-103">Prepare your IT staff for Microsoft Teams</span></span>

<span data-ttu-id="9c3a3-104">![Diagramme de route de mise à niveau, mettant l’accent sur l’étape de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du parcours de la mise à niveau, en mettant l’accent sur l’étape de préparation technique")</span><span class="sxs-lookup"><span data-stu-id="9c3a3-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="9c3a3-105">Cet article fait partie de l’étape de préparation technique de votre mouvement de mise à niveau, une activité que vous finalisez en parallèle avec l’étape de préparation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9c3a3-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="9c3a3-106">Avant de continuer, assurez-vous d’avoir suivi les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="9c3a3-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="9c3a3-107">Inscription des parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="9c3a3-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="9c3a3-108">Définition de l’objectif de votre projet</span><span class="sxs-lookup"><span data-stu-id="9c3a3-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="9c3a3-109">Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes</span><span class="sxs-lookup"><span data-stu-id="9c3a3-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="9c3a3-110">Choix de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="9c3a3-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="9c3a3-111">Les administrateurs de votre organisation Microsoft 365 ou Office 365, les prospectus techniques et l’assistance technique sont responsables pour une utilisation optimale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9c3a3-111">Your Microsoft 365 or Office 365 organization admins, technical leads, and support desk are accountable for driving a high-quality user experience.</span></span> <span data-ttu-id="9c3a3-112">Cela implique de vérifier que votre réseau est prêt pour la prise en charge des équipes, de configurer teams pour vos utilisateurs et de pouvoir résoudre efficacement les problèmes qui peuvent survenir.</span><span class="sxs-lookup"><span data-stu-id="9c3a3-112">This includes ensuring that your network is ready to support Teams, configuring Teams for your users, and being able to effectively troubleshoot and resolve issues that might arise.</span></span>

<span data-ttu-id="9c3a3-113">Partagez les ressources suivantes avec les membres du personnel informatique et confirmez qu’ils sont prêts à prendre en charge les utilisateurs avant de commencer la mise à niveau vers teams :</span><span class="sxs-lookup"><span data-stu-id="9c3a3-113">Share the following resources with your IT staff members, and confirm that they're ready to support users before you begin your upgrade to Teams:</span></span>

- [<span data-ttu-id="9c3a3-114">Formation à Microsoft Teams pour les administrateurs</span><span class="sxs-lookup"><span data-stu-id="9c3a3-114">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)
- [<span data-ttu-id="9c3a3-115">Contacter le support relatif aux produits d’entreprises- Aide de l’administrateur</span><span class="sxs-lookup"><span data-stu-id="9c3a3-115">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [<span data-ttu-id="9c3a3-116">Résoudre les problèmes de connectivité avec le client de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9c3a3-116">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>](connectivity-issues.md)
- [<span data-ttu-id="9c3a3-117">Utiliser les fichiers journaux pour le dépannage de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9c3a3-117">Use log files in troubleshooting Microsoft Teams</span></span>](log-files.md)



| | |
|---|---|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="9c3a3-119">Points de décision</span><span class="sxs-lookup"><span data-stu-id="9c3a3-119">Decision points</span></span>|<ul><li><span data-ttu-id="9c3a3-120">Avez-vous impliqué tout le personnel du support technique susceptible de s’impliquer dans le déploiement et la prise en charge des équipes ?</span><span class="sxs-lookup"><span data-stu-id="9c3a3-120">Have you involved all support staff who are likely to be involved in deploying and supporting Teams?</span></span></li><li><span data-ttu-id="9c3a3-121">Avez-vous développé un plan de formation pour l’intégration de membres du personnel supplémentaire lors de la mise à niveau ?</span><span class="sxs-lookup"><span data-stu-id="9c3a3-121">Have you developed a training plan for onboarding additional staff as your upgrade progresses?</span></span></li></ul> |
| ![Icône montrant les étapes suivantes](media/audio_conferencing_image9.png)<br/><span data-ttu-id="9c3a3-123">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="9c3a3-123">Next steps</span></span>|<ul><li><span data-ttu-id="9c3a3-124">Vérifiez que le personnel informatique a les informations dont il a besoin.</span><span class="sxs-lookup"><span data-stu-id="9c3a3-124">Verify that IT staff has the information they need.</span></span></li><li><span data-ttu-id="9c3a3-125">Reportez-vous à vos offres de formation et de préparation lorsque de nouvelles fonctionnalités sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="9c3a3-125">Revisit your training and preparation plans as new features are released.</span></span></li></ul>|

<span data-ttu-id="9c3a3-126">Après avoir préparé votre équipe informatique pour Teams, vérifiez que votre environnement répond à toutes les [conditions préalables](upgrade-plan-journey-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="9c3a3-126">After you've prepared your IT staff for Teams, verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md).</span></span>
