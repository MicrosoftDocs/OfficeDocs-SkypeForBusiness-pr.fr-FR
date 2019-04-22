---
title: Mise à niveau de Skype Entreprise vers Microsoft Teams
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Utiliser une structure ayant fait ses preuves pour aides les équipes de démarche mise à niveau de votre organisation à passer de Skype Entreprise à Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
F1keywords: ms.teamsadmincenter.dashboard.widget.upgrade.opt-in
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60094153f0e48187b0437bce1f25077c742ad773
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "30641178"
---
# <a name="skype-for-business-to-microsoft-teams-upgrade"></a><span data-ttu-id="53f13-103">Mise à niveau de Skype Entreprise vers Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="53f13-103">[Prepare upgrade Skype for Business to Microsoft Teams</span></span>

<span data-ttu-id="53f13-104">Prenant en charge de la vision de communication intelligente de Microsoft, Microsoft Teams est le hub central pour le travail d’équipe, combinant conversations, réunions, appels, collaboration, intégration à l’application et stockage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="53f13-104">Supporting Microsoft’s intelligent communications vision, Microsoft Teams is the central hub for teamwork, bringing together chat, meetings, calling, collaboration, app integration, and file storage.</span></span> <span data-ttu-id="53f13-105">En tant que client existant de Skype Entreprise, vous êtes invité à mettre à niveau vers Microsoft Teams, pour découvrir l’intégralité des fonctionnalités de communication et de collaboration dans une expérience client unique.</span><span class="sxs-lookup"><span data-stu-id="53f13-105">As an existing Skype for Business customer, you’re invited to upgrade to Microsoft Teams, to experience this full suite of communication and collaboration capabilities in a single client experience.</span></span>

<span data-ttu-id="53f13-106">Votre mise à niveau peut prendre du temps, et nous sommes là pour vous épauler à chaque étape du processus.</span><span class="sxs-lookup"><span data-stu-id="53f13-106">Your upgrade journey might take some time, and we’re here to support you every step of the way.</span></span> <span data-ttu-id="53f13-107">Que ce soit si vous débutez avec Teams, ou vous utilisez déjà Teams en parallèle avec Skype Entreprise, ou vous êtes prêt à mettre à niveau, nous mettons tout en œuvre pour vous fournir le niveau approprié de conseils pour votre organisation et vous encourageons à effectuer les étapes suivantes pour commencer à réaliser le valeur que Teams peut apporter à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="53f13-107">Whether you’re just getting started with Teams, already using Teams alongside Skype for Business, or ready to upgrade, we’re working hard to bring you the right level of guidance for your organization and encourage you to take the next steps to begin realizing the value Teams can offer your organization.</span></span>

<span data-ttu-id="53f13-108">Afficher cette [Vue d’ensemble](https://aka.ms/UpgradeOverview) pour découvrir une introduction à la mise à niveau de Skype Entreprise à Teams, y compris les principaux concepts, infrastructure et chemins de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="53f13-108">View this [overview](https://aka.ms/UpgradeOverview) for an introduction to the Skype for Business to Teams upgrade journey, including core concepts, framework, and upgrade paths.</span></span>

> [!Tip]
> <span data-ttu-id="53f13-109">Regardez la session suivante pour en savoir plus sur la mise à niveau de Skype Entreprise vers Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="53f13-109">Watch the following session to learn about the Upgrade from Skype for Business to Microsoft Teams:</span></span>
> - <span data-ttu-id="53f13-110">[Présentation de la mise à niveau](https://aka.ms/teams-upgrade-intro) </span><span class="sxs-lookup"><span data-stu-id="53f13-110">[Introduction to Upgrade](https://aka.ms/teams-upgrade-intro) (33 minutes)</span></span>
> - [<span data-ttu-id="53f13-111">Planifier votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="53f13-111">Plan for your upgrade journey</span></span>](https://aka.ms/teams-upgrade-plan)
> - <span data-ttu-id="53f13-112">[Coexistence et interopérabilité](https://aka.ms/teams-upgrade-coexistence-interop)</span><span class="sxs-lookup"><span data-stu-id="53f13-112">[Coexistence and Interoperability](https://aka.ms/teams-upgrade-coexistence-interop) (53 minutes)</span></span>
> - <span data-ttu-id="53f13-113">[Expérience de l’administrateur](https://aka.ms/teams-upgrade-admin)</span><span class="sxs-lookup"><span data-stu-id="53f13-113">[Administrator experience](https://aka.ms/teams-upgrade-admin) (24 minutes)</span></span>

## <a name="upgrade-journey-framework"></a><span data-ttu-id="53f13-114">Infrastructure de route de la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="53f13-114">Upgrade journey framework</span></span>

<span data-ttu-id="53f13-115">Pour vous aider face aux questions que vous vous posez quant à la démarche de mise à niveau, nous avons utilisé une infrastructure ayant fait ses preuves pour favoriser la modification, incorporer les conseils, astuces et ressources dans l’ensemble.</span><span class="sxs-lookup"><span data-stu-id="53f13-115">To help take the guesswork out of your upgrade journey, we’ve employed a proven success framework for driving change, incorporating guidance, tips, and resources throughout.</span></span> <span data-ttu-id="53f13-116">Chaque étape s’appuie sur la précédente et pour obtenir de meilleurs résultats, nous vous recommandons de suivre les étapes décrites dans l’ordre.</span><span class="sxs-lookup"><span data-stu-id="53f13-116">Each step builds on the previous one and for optimal results, we recommend following the steps in order.</span></span>

<span data-ttu-id="53f13-117">Comme illustré ci-dessous, une mise à niveau réussie commence en assemblant la bonne équipe à l’étape des parties prenantes du projet et en continuant à la définition de projet où sont solidifiés l’étendue, les objectifs et la chronologie.</span><span class="sxs-lookup"><span data-stu-id="53f13-117">As illustrated below, a successful upgrade begins by bringing the right team together in the Project Stakeholder stage and then moving to Project Definition where the scope, goals, and timeline are solidified.</span></span> <span data-ttu-id="53f13-118">Cela vous permet de créer une base solide pour votre mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="53f13-118">This helps create a solid foundation for your upgrade journey.</span></span> <span data-ttu-id="53f13-119">À partir de là, il est essentiel pour vous préparer pour la compatibilité technique _et_ les étapes de préparation utilisateur avant de passer à un déploiement et à l’implémentation.</span><span class="sxs-lookup"><span data-stu-id="53f13-119">From there, it’s critical to prepare for both the Technical Readiness _and_ User Readiness stages before moving on to Deployment and Implementation.</span></span> <span data-ttu-id="53f13-120">Planifier un pilote pour valider la préparation avant un large déploiement.</span><span class="sxs-lookup"><span data-stu-id="53f13-120">Plan for a pilot to validate readiness before a broad rollout.</span></span> <span data-ttu-id="53f13-121">Pour un bénéfice maximal pendant l’étape d’Excellence Opérationnelle, établir un plan qui surveille la qualité et accélère l’adoption par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="53f13-121">For maximum benefit during the Operational Excellence stage, establish a plan that monitors for quality and accelerates user adoption.</span></span>

> [!Tip]
> <span data-ttu-id="53f13-122">Pour vous aider à parcourir votre mise à niveau, recherchez ce graphique sur des pages associées pour identifier où vous vous trouvez dans le processus.</span><span class="sxs-lookup"><span data-stu-id="53f13-122">To help you navigate through your upgrade journey, look for this graphic on related pages to identify where you are in the process.</span></span> <span data-ttu-id="53f13-123">![Vérifiez que votre projet est configuré pour réussir avec l’équipe de projet appropriée. Définissez votre objectif général de projet, des objectifs et la chronologie. Confirmez la préparation technique et utilisateur. Exécutez votre plan de déploiement. Conservez l’enthousiasme pour optimiser les résultats. ] (media/upgrade-banner-main.png "Vérifiez que votre projet est configuré pour réussir avec l’équipe de projet appropriée. Définissez votre objectif général de projet, des objectifs et la chronologie. Confirmez la préparation technique et utilisateur. Exécutez votre plan de déploiement. Conservez l’enthousiasme pour optimiser les résultats.")</span><span class="sxs-lookup"><span data-stu-id="53f13-123">![Ensure your project is set up for success with the right project team. Define your project scope, goals, and timeline. Confirm both technical and user readiness. Execute your rollout plan. Maintain momentum to maximize results.](media/upgrade-banner-main.png "Ensure your project is set up for success with the right project team. Define your project scope, goals, and timeline. Confirm both technical and user readiness. Execute your rollout plan. Maintain momentum to maximize results.")</span></span>

## <a name="to-get-started"></a><span data-ttu-id="53f13-124">Pour commencer... </span><span class="sxs-lookup"><span data-stu-id="53f13-124">To get you started</span></span>

<span data-ttu-id="53f13-125">Nous comprenons que les clients ne sont pas tous les mêmes.</span><span class="sxs-lookup"><span data-stu-id="53f13-125">We understand that customers don’t come one-size-fits-all.</span></span> <span data-ttu-id="53f13-126">Pour une flexibilité supplémentaire, nous avons organisé l’infrastructure en deux chemins : Mise à niveau de base et Mise à niveau Pro.</span><span class="sxs-lookup"><span data-stu-id="53f13-126">For added flexibility, we’ve organized the framework into two paths: Upgrade Basic and Upgrade Pro.</span></span> <span data-ttu-id="53f13-127">Vous pouvez choisir le plan qui convient le mieux aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="53f13-127">Choose the journey that best meets your organization’s needs.</span></span>

<span data-ttu-id="53f13-128">Sélectionnez une des options suivantes ou découvrez les deux pour déterminer le chemin d’accès optimal pour vous.</span><span class="sxs-lookup"><span data-stu-id="53f13-128">Select one of the options below or explore both to determine the optimal path for you.</span></span> <span data-ttu-id="53f13-129">Plus d’informations seront prochainement mises en ligne, donc vérifiez ici tandis que votre organisation continue ses premiers pas avec Teams.</span><span class="sxs-lookup"><span data-stu-id="53f13-129">More information will be coming online over time, so check back as your organization continues its journey to Teams.</span></span> <span data-ttu-id="53f13-130">Pour nous aider à mieux comprendre votre chemin de mise à niveau et quelles recommandations supplémentaires pourraient être utiles, prenez quelques instants pour nous<a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR-5Km9f5gDtNpbRf-TAnN_NUMzhYOUlNR1QzS1hSS0ZXRzAxVEVVVjg1Mi4u" target="_blank">faire part de vos commentaires</a>.</span><span class="sxs-lookup"><span data-stu-id="53f13-130">To help us better understand your upgrade path and what additional guidance might be helpful, take a moment to <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR-5Km9f5gDtNpbRf-TAnN_NUMzhYOUlNR1QzS1hSS0ZXRzAxVEVVVjg1Mi4u" target="_blank">share your feedback</a>.</span></span>

<div class="mx-tableFixed">
<table>
<tbody>
<tr><td><a href="https://docs.microsoft.com/MicrosoftTeams/upgrade-basic"><img src="media/upgrade-to-teams-upgrade-basic-icon.png" alt="Designed for smaller organizations or those with simple deployments of Skype for Business (IM only or IM plus basic meeting functionality), the Upgrade Basic checklist steps you through activities designed to quickly move your entire organization to Teams."></a></td>
<td>
<a href="https://docs.microsoft.com/MicrosoftTeams/upgrade-pro"><img src="media/upgrade-to-teams-upgrade-pro-icon.png" alt="Designed for enterprise customers, or those with more tailored deployments such as hybrid or voice, the Upgrade Pro guide details technical and user readiness activities to better accommodate the unique attributes of an organization."></a></td></tr>
</tbody></table>
</div>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
