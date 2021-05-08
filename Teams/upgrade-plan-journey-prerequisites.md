---
title: Conditions préalables et dépendances sur l’environnement pour la mise à niveau vers Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Utilisez ces instructions pour en savoir plus sur les conditions préalables et les dépendances environnementales pour le déploiement Teams votre organisation
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
ms.openlocfilehash: e9924c24f19da3cf17f8e8a124a03acc294c24b4
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282161"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="f365e-103">Conditions préalables et dépendances de l’environnement pour Teams</span><span class="sxs-lookup"><span data-stu-id="f365e-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="f365e-104">![Diagramme de voyage de mise à niveau mettant en relief la phase de préparation technique](media/upgrade-banner-tech-readiness.png "Étapes du voyage de mise à niveau, avec l’accentuation sur la phase de préparation technique")</span><span class="sxs-lookup"><span data-stu-id="f365e-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="f365e-105">Cet article fait partie de la phase de préparation technique de votre voyage de mise à niveau, une activité que vous terminez en parallèle de la phase de préparation utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f365e-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="f365e-106">Avant de poursuivre, confirmez que vous avez effectué ces activités à partir des étapes précédentes :</span><span class="sxs-lookup"><span data-stu-id="f365e-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="f365e-107">Demandez aux parties prenantes de votre projet</span><span class="sxs-lookup"><span data-stu-id="f365e-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="f365e-108">Étendue définie de votre projet</span><span class="sxs-lookup"><span data-stu-id="f365e-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="f365e-109">Coexistence et interopérabilité comprises entre les systèmes Skype Entreprise et Teams</span><span class="sxs-lookup"><span data-stu-id="f365e-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="f365e-110">Nous avons choisi votre chemin de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f365e-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="f365e-111">Teams combine plusieurs services Microsoft 365 Office 365 et dépend donc de l’implémentation et de l’opération correctes de ces services.</span><span class="sxs-lookup"><span data-stu-id="f365e-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="f365e-112">Ces services comprennent , mais ne sont pas limités, SharePoint Online, Exchange Online et OneDrive Entreprise.</span><span class="sxs-lookup"><span data-stu-id="f365e-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="f365e-113">Bien que certains services ne soient pas obligatoires, nous vous recommandons vivement de les implémenter tous.</span><span class="sxs-lookup"><span data-stu-id="f365e-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="f365e-114">Si vous choisissez de ne pas implémenter certains services, cela affectera les fonctionnalités que Teams pouvez offrir à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f365e-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="f365e-115">Par exemple, même si vous n’avez pas à implémenter SharePoint Online, Teams utilise SharePoint Online pour certaines fonctionnalités telles que le partage de fichiers dans les conversations de groupe. Par donc, si vous ne l’implémentez pas, les fonctionnalités offertes par le client seront réduites.</span><span class="sxs-lookup"><span data-stu-id="f365e-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="f365e-116">Consultez les articles suivants pour en savoir plus sur les conditions préalables et Teams interactions entre les autres technologies :</span><span class="sxs-lookup"><span data-stu-id="f365e-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="f365e-117">Si votre organisation n’a pas déployé d’Microsoft 365 charges Office 365 charges de travail, voir [Commencer.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="f365e-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="f365e-118">Si votre organisation n’a pas ajouté ou configuré un domaine vérifié pour Microsoft 365 ou Office 365, consultez [le Forum aux questions des](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)domaines.</span><span class="sxs-lookup"><span data-stu-id="f365e-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="f365e-119">Si votre organisation n’a pas synchronisé les identités avec les Azure Active Directory, consultez les modèles d’identité et [l’authentification dans Microsoft Teams.](identify-models-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="f365e-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="f365e-120">Si votre organisation ne dispose pas d'Exchange Online, reportez-vous à la page [Comprendre l’interaction entre Exchange et Microsoft Teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="f365e-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="f365e-121">Si votre organisation ne dispose pas de SharePoint Online, reportez-vous à la page [Comprendre l’interaction entre SharePoint Online et OneDrive Entreprise avec Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="f365e-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="f365e-122">Pour découvrir comment les [Microsoft 365 et comment Microsoft Teams interagir.](Office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="f365e-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="f365e-123">Si votre organisation est un établissement d’enseignement et que vous utilisez un système d’information sur les étudiants, voir Bienvenue dans [Microsoft Synchronisation des données scolaires](/schooldatasync) avant de déployer Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f365e-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="f365e-124">Si votre organisation envisage d’envisager des options d’appel de réseau téléphonique commuté (RST), consultez la connectivité Voix - Système téléphonique et [RSTN,](cloud-voice-landing-page.md)le [plan](calling-plan-landing-page.md)d’appel qui vous est le plus exact et [Système téléphonique routage direct.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="f365e-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="f365e-125">Pour vous assurer que toutes les exigences réseau ont été respectées avant de Teams, voir Préparer le réseau de votre organisation [pour l’Microsoft Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="f365e-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="f365e-126">Si vous utilisez actuellement Skype Entreprise Online Connector pour gérer vos services, vous devez passer au module Teams PowerShell et mettre à jour vos scripts PowerShell existants.</span><span class="sxs-lookup"><span data-stu-id="f365e-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="f365e-127">Pour [plus d’Skype Entreprise, voir Déplacer du connecteur en ligne vers Teams module PowerShell.](teams-powershell-move-from-sfbo.md)</span><span class="sxs-lookup"><span data-stu-id="f365e-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="f365e-128">Après avoir vérifié que votre environnement répond à toutes les conditions préalables applicables, évaluez votre environnement [actuel pour Teams.](upgrade-plan-journey-evaluate-environment.md)</span><span class="sxs-lookup"><span data-stu-id="f365e-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>