---
title: Conditions préalables pour Microsoft teams | Mise à niveau des dépendances
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Utilisez ces instructions pour en savoir plus sur les conditions préalables et les dépendances environnementales du déploiement d’équipes au sein de votre organisation.
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
ms.openlocfilehash: 241c1f2ab0287b6beb2a99386b2f04b1f7cbfb28
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666066"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="56a35-103">Prérequis et dépendances environnementales pour les équipes</span><span class="sxs-lookup"><span data-stu-id="56a35-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="56a35-104">![Diagramme de route de mise à niveau, mettant l’accent sur l’étape de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du parcours de la mise à niveau, en mettant l’accent sur l’étape de préparation technique")</span><span class="sxs-lookup"><span data-stu-id="56a35-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="56a35-105">Cet article fait partie de l’étape de préparation technique de votre mouvement de mise à niveau, une activité que vous finalisez en parallèle avec l’étape de préparation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="56a35-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="56a35-106">Avant de continuer, assurez-vous d’avoir suivi les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="56a35-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="56a35-107">Inscription des parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="56a35-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="56a35-108">Définition de l’objectif de votre projet</span><span class="sxs-lookup"><span data-stu-id="56a35-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="56a35-109">Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes</span><span class="sxs-lookup"><span data-stu-id="56a35-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="56a35-110">Choix de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="56a35-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="56a35-111">Teams combine plusieurs services Microsoft 365 et Office 365 et dépend par conséquent du bon fonctionnement et de l’application de ces services.</span><span class="sxs-lookup"><span data-stu-id="56a35-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="56a35-112">Ces services incluent, sans s’y limiter, SharePoint Online, Exchange Online et OneDrive entreprise.</span><span class="sxs-lookup"><span data-stu-id="56a35-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="56a35-113">Même si certains services ne sont pas requis, nous vous conseillons vivement de les implémenter.</span><span class="sxs-lookup"><span data-stu-id="56a35-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="56a35-114">Si vous choisissez de ne pas implémenter certains services, cela a un impact sur les fonctionnalités que teams peut fournir à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="56a35-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="56a35-115">Par exemple, si vous n’avez pas besoin d’implémenter SharePoint Online, Teams ne dépend pas de SharePoint Online pour certaines fonctionnalités, telles que le partage de fichiers dans les conversations de groupe, de sorte qu’il n’est pas nécessaire d’implémenter ce service pour réduire les fonctionnalités proposées par le client.</span><span class="sxs-lookup"><span data-stu-id="56a35-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="56a35-116">Pour en savoir plus sur les conditions préalables et la façon dont les équipes interagissent avec d’autres technologies, voir les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="56a35-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="56a35-117">Si votre organisation n’a pas déployé de charges de travail Microsoft 365 ou Office 365, voir [commencer](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="56a35-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="56a35-118">Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Microsoft 365 ou Office 365, voir [Forum aux questions sur les domaines](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="56a35-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="56a35-119">Si votre organisation n’a pas de synchronisation des identités dans Azure Active Directory, voir [modèles d’identité et authentification dans Microsoft teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="56a35-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="56a35-120">Si votre organisation ne dispose pas de<sup>1</sup>t Exchange Online, voir [comprendre comment Exchange et Microsoft teams interagissent](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="56a35-120">If your organization doesn<sup>1</sup>t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="56a35-121">Si votre organisation ne dispose pas de SharePoint Online, voir [comprendre comment SharePoint Online et OneDrive entreprise interagissent avec Microsoft teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="56a35-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="56a35-122">Découvrez comment [interagissent avec les groupes microsoft 365 et Microsoft teams](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="56a35-122">Learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="56a35-123">Si votre organisation est une institution éducative et que vous utilisez un système d’information sur les étudiants, vous devez [déployer School Data Sync](https://docs.microsoft.com/schooldatasync) avant de déployer Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="56a35-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="56a35-124">Après avoir vérifié que votre environnement répond à tous les éléments requis concernés, [évaluez votre environnement actuel pour teams](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="56a35-124">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
