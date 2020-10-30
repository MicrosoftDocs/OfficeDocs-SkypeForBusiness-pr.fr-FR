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
ms.openlocfilehash: 9013bda2f83a63776dfbf9110a0863dcf68c0ddb
ms.sourcegitcommit: bc471f18e40e37456edc9696e11b175581847617
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2020
ms.locfileid: "48800597"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="38d44-104">Utiliser les modèles de fabrication d’équipes dans le centre d’administration</span><span class="sxs-lookup"><span data-stu-id="38d44-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="38d44-105">Les modèles d’équipes vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications déjà installées.</span><span class="sxs-lookup"><span data-stu-id="38d44-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="38d44-106">Les modèles d’équipes sont dotés de définitions préconfigurées de structures d’équipe conçues en fonction de leurs besoins en matière de fabrication.</span><span class="sxs-lookup"><span data-stu-id="38d44-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="38d44-107">Vous pouvez également développer les modèles teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="38d44-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="38d44-108">Dans cet article, nous allons présenter chacun des modèles d’équipes et nous vous conseillons de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="38d44-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="38d44-109">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation industrielle.</span><span class="sxs-lookup"><span data-stu-id="38d44-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="38d44-110">Vous avez déjà déployé le service teams au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="38d44-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="38d44-111">Si vous n’avez pas encore déployé Teams, commencez par lire la rubrique [comment déployer Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="38d44-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="38d44-112">Pour en savoir plus sur les modèles d’équipe en général, voir [commencer à utiliser les modèles](get-started-with-teams-templates-in-the-admin-console.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="38d44-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="38d44-113">Qualité et sécurité</span><span class="sxs-lookup"><span data-stu-id="38d44-113">Quality and safety</span></span>

<span data-ttu-id="38d44-114">Centralisez la communication, l’accès aux ressources et aux opérations d’usines avec une équipe de production.</span><span class="sxs-lookup"><span data-stu-id="38d44-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="38d44-115">Incluez des documents de stratégie et de procédure, des vidéos de formation, des avis de sécurité, des processus de transfert de Shift.</span><span class="sxs-lookup"><span data-stu-id="38d44-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="38d44-116">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="38d44-116">Base template type</span></span>|<span data-ttu-id="38d44-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="38d44-117">baseTemplateId</span></span> | <span data-ttu-id="38d44-118">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="38d44-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="38d44-119">Qualité et sécurité</span><span class="sxs-lookup"><span data-stu-id="38d44-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="38d44-120">Canaux</span><span class="sxs-lookup"><span data-stu-id="38d44-120">Channels:</span></span> <ul><li><span data-ttu-id="38d44-121">Général</span><span class="sxs-lookup"><span data-stu-id="38d44-121">General</span></span><li><span data-ttu-id="38d44-122">Annonces</span><span class="sxs-lookup"><span data-stu-id="38d44-122">Announcements</span></span></li><li><span data-ttu-id="38d44-123">Ligne 1</span><span class="sxs-lookup"><span data-stu-id="38d44-123">Line 1</span></span></li><li><span data-ttu-id="38d44-124">Ligne 2</span><span class="sxs-lookup"><span data-stu-id="38d44-124">Line 2</span></span></li><li><span data-ttu-id="38d44-125">Ligne 3</span><span class="sxs-lookup"><span data-stu-id="38d44-125">Line 3</span></span></li><li><span data-ttu-id="38d44-126">Technologique</span><span class="sxs-lookup"><span data-stu-id="38d44-126">Safety</span></span></li><li><span data-ttu-id="38d44-127">Formation</span><span class="sxs-lookup"><span data-stu-id="38d44-127">Training</span></span></li><li><span data-ttu-id="38d44-128">Tarification</span><span class="sxs-lookup"><span data-stu-id="38d44-128">Maintenance</span></span></li><li><span data-ttu-id="38d44-129">Outils amusants</span><span class="sxs-lookup"><span data-stu-id="38d44-129">Fun stuff</span></span></li></ul> <span data-ttu-id="38d44-130">Logiciels</span><span class="sxs-lookup"><span data-stu-id="38d44-130">Apps:</span></span> <ul><li><span data-ttu-id="38d44-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="38d44-131">Wiki</span></span></li></ul>|
||||
