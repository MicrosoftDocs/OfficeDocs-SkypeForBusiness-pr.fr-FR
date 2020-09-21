---
title: Commencer à utiliser des modèles financiers d’équipe à l’aide de la console d’administration
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les modèles teams pour créer des structures d’équipe conçues pour les besoins financiers en fournissant des paramètres prédéfinis, des canaux et des applications préinstallées à l’aide de la console d’administration.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 270e03d58a89cf35132f254d2dd1af55d894e8d0
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136014"
---
# <a name="use-teams-financial-templates-in-the-admin-console"></a><span data-ttu-id="74476-103">Utiliser les modèles financiers d’équipes dans la console d’administration</span><span class="sxs-lookup"><span data-stu-id="74476-103">Use Teams financial templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="74476-104">Les modèles d’équipes vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications déjà installées.</span><span class="sxs-lookup"><span data-stu-id="74476-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="74476-105">Les modèles d’équipes disposent de définitions prédéfinies de structures d’équipe conçues en fonction de vos besoins financiers.</span><span class="sxs-lookup"><span data-stu-id="74476-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="74476-106">Vous pouvez également développer les modèles teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="74476-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="74476-107">Dans cet article, nous allons présenter chacun des modèles d’équipes et la façon dont nous vous conseillons de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="74476-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="74476-108">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation financière.</span><span class="sxs-lookup"><span data-stu-id="74476-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="74476-109">Nous partons du principe que vous avez déjà déployé teams service au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="74476-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="74476-110">Si vous n’avez pas encore déployé Teams, commencez par lire la rubrique [comment déployer Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="74476-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="74476-111">Pour en savoir plus sur les modèles d’équipe en général, consultez la rubrique [commencer à utiliser les modèles](get-started-with-teams-templates-in-the-admin-console.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="74476-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="74476-112">Crise générale ou événement</span><span class="sxs-lookup"><span data-stu-id="74476-112">Global crisis or event</span></span>

<span data-ttu-id="74476-113">Centralisation de la collaboration pour votre équipe de crise sur différentes unités de travail et permet de créer des plans de continuité d’activité, de partager des conseils de fonctionnement à distance, de suivre les communications client et de garder le contact avec les annonces et les actualités.</span><span class="sxs-lookup"><span data-stu-id="74476-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="74476-114">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="74476-114">Base template type</span></span>|<span data-ttu-id="74476-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="74476-115">baseTemplateId</span></span> | <span data-ttu-id="74476-116">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="74476-116">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="74476-117">Collaborer sur une crise générale ou un événement</span><span class="sxs-lookup"><span data-stu-id="74476-117">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="74476-118">Canaux</span><span class="sxs-lookup"><span data-stu-id="74476-118">Channels:</span></span> <ul><li><span data-ttu-id="74476-119">Général</span><span class="sxs-lookup"><span data-stu-id="74476-119">General</span></span><li><span data-ttu-id="74476-120">Annonces</span><span class="sxs-lookup"><span data-stu-id="74476-120">Announcements</span></span></li><li><span data-ttu-id="74476-121">Actualité du monde</span><span class="sxs-lookup"><span data-stu-id="74476-121">World news</span></span></li><li><span data-ttu-id="74476-122">Continuité de l’activité</span><span class="sxs-lookup"><span data-stu-id="74476-122">Business continuity</span></span></li><li><span data-ttu-id="74476-123">Travail distant</span><span class="sxs-lookup"><span data-stu-id="74476-123">Remote working</span></span></li><li><span data-ttu-id="74476-124">Commes internes</span><span class="sxs-lookup"><span data-stu-id="74476-124">Internal comms</span></span></li><li><span data-ttu-id="74476-125">Commes externes</span><span class="sxs-lookup"><span data-stu-id="74476-125">External comms</span></span></li><li><span data-ttu-id="74476-126">Réclamations de clients</span><span class="sxs-lookup"><span data-stu-id="74476-126">Customer complaints</span></span></li><li><span data-ttu-id="74476-127">Complimenter</span><span class="sxs-lookup"><span data-stu-id="74476-127">Kudos</span></span></li><li><span data-ttu-id="74476-128">Mise à jour de la direction</span><span class="sxs-lookup"><span data-stu-id="74476-128">Executive update</span></span></li></ul><span data-ttu-id="74476-129">Logiciels</span><span class="sxs-lookup"><span data-stu-id="74476-129">Apps:</span></span> <ul><li><span data-ttu-id="74476-130">Éloge</span><span class="sxs-lookup"><span data-stu-id="74476-130">Praise</span></span></li><li><span data-ttu-id="74476-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="74476-131">Wiki</span></span></li><li><span data-ttu-id="74476-132">Associates</span><span class="sxs-lookup"><span data-stu-id="74476-132">Website</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="74476-133">Collaborer au sein d’une succursale bancaire</span><span class="sxs-lookup"><span data-stu-id="74476-133">Collaborate within a bank branch</span></span>

<span data-ttu-id="74476-134">Centralisation de la collaboration pour les employés de votre succursale dans huddles, les réunions des clients, les processus d’entreprise tels que la collaboration sur les hypothèques, et la conservation de tout le monde en boucle sur les annonces et les complimenter.</span><span class="sxs-lookup"><span data-stu-id="74476-134">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="74476-135">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="74476-135">Base template type</span></span> |<span data-ttu-id="74476-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="74476-136">baseTemplateId</span></span>| <span data-ttu-id="74476-137">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="74476-137">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="74476-138">Collaborer au sein d’une succursale bancaire</span><span class="sxs-lookup"><span data-stu-id="74476-138">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="74476-139">Canaux</span><span class="sxs-lookup"><span data-stu-id="74476-139">Channels:</span></span> <ul><li><span data-ttu-id="74476-140">Général</span><span class="sxs-lookup"><span data-stu-id="74476-140">General</span></span><li><span data-ttu-id="74476-141">Annonces</span><span class="sxs-lookup"><span data-stu-id="74476-141">Announcements</span></span></li><li><span data-ttu-id="74476-142">Huddles</span><span class="sxs-lookup"><span data-stu-id="74476-142">Huddles</span></span></li><li><span data-ttu-id="74476-143">Réunions des clients</span><span class="sxs-lookup"><span data-stu-id="74476-143">Customer meetings</span></span></li><li><span data-ttu-id="74476-144">Conseils</span><span class="sxs-lookup"><span data-stu-id="74476-144">Coaching</span></span></li><li><span data-ttu-id="74476-145">Développement de compétences</span><span class="sxs-lookup"><span data-stu-id="74476-145">Skills development</span></span></li><li><span data-ttu-id="74476-146">Traitement des prêts</span><span class="sxs-lookup"><span data-stu-id="74476-146">Loan processing</span></span></li><li><span data-ttu-id="74476-147">Réclamations de clients</span><span class="sxs-lookup"><span data-stu-id="74476-147">Customer complaints</span></span></li><li><span data-ttu-id="74476-148">Complimenter</span><span class="sxs-lookup"><span data-stu-id="74476-148">Kudos</span></span></li><li><span data-ttu-id="74476-149">Outils amusants</span><span class="sxs-lookup"><span data-stu-id="74476-149">Fun stuff</span></span></li><li><span data-ttu-id="74476-150">Conformité</span><span class="sxs-lookup"><span data-stu-id="74476-150">Compliance</span></span></li></ul>|
||||

