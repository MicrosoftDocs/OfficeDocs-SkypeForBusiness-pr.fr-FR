---
title: Utiliser les modèles d’équipe de fabrication dans le Centre d’administration
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
description: Découvrez comment utiliser les modèles d’équipe pour créer des structures d’équipe conçues pour des besoins de fabrication en fournissant des paramètres, des canaux et des applications prédéfinfines à l’aide du Centre d’administration.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec27cba4336d86f51a32582440d5d7902ffca2b9
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684481"
---
# <a name="use-manufacturing-team-templates-in-the-admin-center"></a><span data-ttu-id="d28e8-103">Utiliser des modèles d’équipe de fabrication dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="d28e8-103">Use manufacturing team templates in the admin center</span></span>

<span data-ttu-id="d28e8-104">Les modèles d’équipe vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="d28e8-104">Team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="d28e8-105">Les modèles d’équipe ont des définitions pré-intégrées de structures d’équipe conçues autour des besoins de fabrication.</span><span class="sxs-lookup"><span data-stu-id="d28e8-105">Team templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="d28e8-106">Vous pouvez également étendre les modèles d’équipe pour créer des équipes adaptées aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d28e8-106">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="d28e8-107">Dans cet article, nous introduisons chacun des modèles d’équipe et vous recommandons de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="d28e8-107">In this article, we introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="d28e8-108">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de fabrication.</span><span class="sxs-lookup"><span data-stu-id="d28e8-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="d28e8-109">Vous avez déjà déployé le service Teams dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d28e8-109">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="d28e8-110">Si vous n’avez pas encore déployé Teams, commencez par lire l’article [Comment déployer Microsoft Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d28e8-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="d28e8-111">Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles d’équipe.](get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="d28e8-111">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="d28e8-112">Qualité et sécurité</span><span class="sxs-lookup"><span data-stu-id="d28e8-112">Quality and safety</span></span>

<span data-ttu-id="d28e8-113">Centralisez la communication, l’accès aux ressources et les opérations d’usine avec une équipe d’usine de fabrication.</span><span class="sxs-lookup"><span data-stu-id="d28e8-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="d28e8-114">Inclure des documents de stratégie et de procédure, des vidéos de formation, des avis de sécurité, des processus de transfert.</span><span class="sxs-lookup"><span data-stu-id="d28e8-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="d28e8-115">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="d28e8-115">Base template type</span></span>|<span data-ttu-id="d28e8-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d28e8-116">baseTemplateId</span></span>| <span data-ttu-id="d28e8-117">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="d28e8-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="d28e8-118">Qualité et sécurité</span><span class="sxs-lookup"><span data-stu-id="d28e8-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="d28e8-119">Canaux :</span><span class="sxs-lookup"><span data-stu-id="d28e8-119">Channels:</span></span> <ul><li><span data-ttu-id="d28e8-120">Général</span><span class="sxs-lookup"><span data-stu-id="d28e8-120">General</span></span><li><span data-ttu-id="d28e8-121">Annonces</span><span class="sxs-lookup"><span data-stu-id="d28e8-121">Announcements</span></span></li><li><span data-ttu-id="d28e8-122">Ligne 1</span><span class="sxs-lookup"><span data-stu-id="d28e8-122">Line 1</span></span></li><li><span data-ttu-id="d28e8-123">Ligne 2</span><span class="sxs-lookup"><span data-stu-id="d28e8-123">Line 2</span></span></li><li><span data-ttu-id="d28e8-124">Ligne 3</span><span class="sxs-lookup"><span data-stu-id="d28e8-124">Line 3</span></span></li><li><span data-ttu-id="d28e8-125">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d28e8-125">Safety</span></span></li><li><span data-ttu-id="d28e8-126">Formation</span><span class="sxs-lookup"><span data-stu-id="d28e8-126">Training</span></span></li><li><span data-ttu-id="d28e8-127">Maintenance</span><span class="sxs-lookup"><span data-stu-id="d28e8-127">Maintenance</span></span></li><li><span data-ttu-id="d28e8-128">Amusant</span><span class="sxs-lookup"><span data-stu-id="d28e8-128">Fun stuff</span></span></li></ul> <span data-ttu-id="d28e8-129">Applications :</span><span class="sxs-lookup"><span data-stu-id="d28e8-129">Apps:</span></span> <ul><li><span data-ttu-id="d28e8-130">Wiki</span><span class="sxs-lookup"><span data-stu-id="d28e8-130">Wiki</span></span></li><li><span data-ttu-id="d28e8-131">Planificateur</span><span class="sxs-lookup"><span data-stu-id="d28e8-131">Planner</span></span></li></ul>|
||||