---
title: Commencer à utiliser teams fabrication de modèles dans le centre d’administration
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
description: Apprenez à utiliser. Les modèles teams permettent de créer des structures d’équipe conçues pour la fabrication en fournissant des paramètres prédéfinis, des canaux et des applications préinstallées à l’aide du centre d’administration.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51a28e997e5c7c0b36fb49cd0bb46768b7808a29
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662219"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="b2435-104">Utiliser les modèles de fabrication d’équipes dans le centre d’administration</span><span class="sxs-lookup"><span data-stu-id="b2435-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="b2435-105">Les modèles d’équipes vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications déjà installées.</span><span class="sxs-lookup"><span data-stu-id="b2435-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b2435-106">Les modèles d’équipes sont dotés de définitions préconfigurées de structures d’équipe conçues en fonction de leurs besoins en matière de fabrication.</span><span class="sxs-lookup"><span data-stu-id="b2435-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="b2435-107">Vous pouvez également développer les modèles teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b2435-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="b2435-108">Dans cet article, nous allons présenter chacun des modèles d’équipes et nous vous conseillons de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="b2435-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="b2435-109">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation industrielle.</span><span class="sxs-lookup"><span data-stu-id="b2435-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="b2435-110">Vous avez déjà déployé le service teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b2435-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="b2435-111">Si vous n’avez pas encore déployé Teams, commencez par lire la rubrique [comment déployer Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b2435-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="b2435-112">Pour en savoir plus sur les modèles d’équipe en général, voir [commencer à utiliser les modèles](get-started-with-teams-templates-in-the-admin-console.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="b2435-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="b2435-113">Qualité et sécurité</span><span class="sxs-lookup"><span data-stu-id="b2435-113">Quality and safety</span></span>

<span data-ttu-id="b2435-114">Centralisez la communication, l’accès aux ressources et aux opérations d’usines avec une équipe de production.</span><span class="sxs-lookup"><span data-stu-id="b2435-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="b2435-115">Incluez des documents de stratégie et de procédure, des vidéos de formation, des avis de sécurité, des processus de transfert de Shift.</span><span class="sxs-lookup"><span data-stu-id="b2435-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="b2435-116">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="b2435-116">Base template type</span></span>|<span data-ttu-id="b2435-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b2435-117">baseTemplateId</span></span>| <span data-ttu-id="b2435-118">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="b2435-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="b2435-119">Qualité et sécurité</span><span class="sxs-lookup"><span data-stu-id="b2435-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="b2435-120">Canaux</span><span class="sxs-lookup"><span data-stu-id="b2435-120">Channels:</span></span> <ul><li><span data-ttu-id="b2435-121">Général</span><span class="sxs-lookup"><span data-stu-id="b2435-121">General</span></span><li><span data-ttu-id="b2435-122">Annonces</span><span class="sxs-lookup"><span data-stu-id="b2435-122">Announcements</span></span></li><li><span data-ttu-id="b2435-123">Ligne 1</span><span class="sxs-lookup"><span data-stu-id="b2435-123">Line 1</span></span></li><li><span data-ttu-id="b2435-124">Ligne 2</span><span class="sxs-lookup"><span data-stu-id="b2435-124">Line 2</span></span></li><li><span data-ttu-id="b2435-125">Ligne 3</span><span class="sxs-lookup"><span data-stu-id="b2435-125">Line 3</span></span></li><li><span data-ttu-id="b2435-126">Technologique</span><span class="sxs-lookup"><span data-stu-id="b2435-126">Safety</span></span></li><li><span data-ttu-id="b2435-127">Formation</span><span class="sxs-lookup"><span data-stu-id="b2435-127">Training</span></span></li><li><span data-ttu-id="b2435-128">Tarification</span><span class="sxs-lookup"><span data-stu-id="b2435-128">Maintenance</span></span></li><li><span data-ttu-id="b2435-129">Outils amusants</span><span class="sxs-lookup"><span data-stu-id="b2435-129">Fun stuff</span></span></li></ul> <span data-ttu-id="b2435-130">Logiciels</span><span class="sxs-lookup"><span data-stu-id="b2435-130">Apps:</span></span> <ul><li><span data-ttu-id="b2435-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="b2435-131">Wiki</span></span></li><li><span data-ttu-id="b2435-132">Planificateur</span><span class="sxs-lookup"><span data-stu-id="b2435-132">Planner</span></span></li></ul>|
||||
