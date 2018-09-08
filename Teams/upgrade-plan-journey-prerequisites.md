---
title: Conditions préalables et les dépendances de l’environnement pour Microsoft Teams - Microsoft Teams
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: Utilisez ce guide pour en savoir plus sur les conditions préalables et les dépendances de l’environnement pour déployer des équipes au sein de votre organisation.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b798ae43d7a47543c78ca38a696a2368413539d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887506"
---
<span data-ttu-id="6f856-103">![Étapes du voyage mise à niveau, en mettant l’accent sur l’étape de préparation technique] (media/upgrade-banner-tech-readiness.png "Étapes du voyage mise à niveau, en mettant l’accent sur l’étape de préparation technique")</span><span class="sxs-lookup"><span data-stu-id="6f856-103">![Stages of the upgrade journey, with emphasis on the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="6f856-104">Cet article fait partie de la phase de préparation technique de votre parcours de mise à niveau, une activité que vous effectuez en parallèle à l’étape de préparation des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6f856-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="6f856-105">Avant de continuer, vérifiez que vous avez terminé ces activités à partir des étapes précédentes :</span><span class="sxs-lookup"><span data-stu-id="6f856-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

-   [<span data-ttu-id="6f856-106">Inscrit les parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="6f856-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="6f856-107">Définies par l’étendue de votre projet</span><span class="sxs-lookup"><span data-stu-id="6f856-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="6f856-108">Comprendre la coexistence et l’interopérabilité de Skype pour professionnels et les équipes</span><span class="sxs-lookup"><span data-stu-id="6f856-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="6f856-109">Choisi votre parcours de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="6f856-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="6f856-110">Conditions préalables et les dépendances de l’environnement pour les équipes</span><span class="sxs-lookup"><span data-stu-id="6f856-110">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="6f856-111">Les équipes combine plusieurs services Office 365 et est donc dépendent de la mise en oeuvre correcte et le fonctionnement de ces services.</span><span class="sxs-lookup"><span data-stu-id="6f856-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="6f856-112">Ces services englobent, mais ne sont pas limitées à, SharePoint Online, Exchange Online et OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="6f856-112">These services include—but aren’t limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="6f856-113">Bien que tous les services sont nécessaires, nous vous recommandons vivement de tous les implémenter.</span><span class="sxs-lookup"><span data-stu-id="6f856-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="6f856-114">Si vous choisissez de ne pas mettre en œuvre certains services, elle affecte les fonctionnalités que les équipes peuvent offrir à votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="6f856-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="6f856-115">Par exemple, si vous ne disposez pas d’implémenter SharePoint Online, les équipes s’appuie sur SharePoint Online pour certaines fonctionnalités telles que le partage de fichiers dans des conversations de groupe, donc ne pas l’implémentation de ce service permet de réduire les fonctionnalités offertes par le biais de la client.</span><span class="sxs-lookup"><span data-stu-id="6f856-115">For example, though you don’t have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="6f856-116">Voir les articles suivants pour en savoir plus sur les conditions préalables et la façon dont les équipes interagit avec d’autres technologies :</span><span class="sxs-lookup"><span data-stu-id="6f856-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

-   <span data-ttu-id="6f856-117">Si votre organisation n’a pas déployé les charges de travail Office 365, voir [Mise en route avec Office 365 pour entreprises](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="6f856-117">If your organization hasn’t deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

-   <span data-ttu-id="6f856-118">Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Office 365, voir [vérifier votre domaine à Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="6f856-118">If your organization hasn’t added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

-   <span data-ttu-id="6f856-119">Si votre organisation n’a pas synchronisé identités pour Azure Active Directory, voir [modèles d’identité et authentification dans les équipes Microsoft](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6f856-119">If your organization hasn’t synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

-   <span data-ttu-id="6f856-120">Si vous disposez d’un doesn¹t de votre organisation Exchange Online, voir [comprendre interagissent entre Exchange et les équipes Microsoft](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="6f856-120">If your organization doesn¹t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

-   <span data-ttu-id="6f856-121">Si votre organisation ne possède pas SharePoint Online, voir [comprendre comment SharePoint Online et OneDrive entreprise interagissent avec les équipes Microsoft](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="6f856-121">If your organization doesn’t have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

-   <span data-ttu-id="6f856-122">Découvrez comment [interagissent groupes Office 365 et les équipes Microsoft](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6f856-122">Learn how [Office 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

-   <span data-ttu-id="6f856-123">Si votre organisation est un établissement scolaire et que vous utilisez un système d’Information pour l’étudiant, [déployer la synchronisation des données de l’école](https://docs.microsoft.com/schooldatasync) avant de déployer Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6f856-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>
                                                                           

<span data-ttu-id="6f856-124">Après avoir vérifié que votre environnement remplit les conditions préalables d’applicables tous, [évaluer l’environnement actuel pour les équipes](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6f856-124">After you’ve verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>