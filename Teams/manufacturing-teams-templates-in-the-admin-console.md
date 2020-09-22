---
title: Commencer à utiliser les modèles de fabrication d’équipes dans la console d’administration
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
description: Découvrez comment utiliser les modèles teams pour créer des structures d’équipe conçues pour les besoins en fabrication en fournissant des paramètres prédéfinis, des canaux et des applications préinstallées à l’aide de la console d’administration.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 919bfc1bc3e13985ac90484cd203bf93201babd2
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171028"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="b81a8-103">Utiliser les modèles de fabrication d’équipes dans la console d’administration</span><span class="sxs-lookup"><span data-stu-id="b81a8-103">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="b81a8-104">Les modèles d’équipes vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications déjà installées.</span><span class="sxs-lookup"><span data-stu-id="b81a8-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b81a8-105">Les modèles d’équipes sont dotés de définitions préconfigurées de structures d’équipe conçues en fonction de leurs besoins en matière de fabrication.</span><span class="sxs-lookup"><span data-stu-id="b81a8-105">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="b81a8-106">Vous pouvez également développer les modèles teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b81a8-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="b81a8-107">Dans cet article, nous allons présenter chacun des modèles d’équipes et la façon dont nous vous conseillons de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="b81a8-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="b81a8-108">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation industrielle.</span><span class="sxs-lookup"><span data-stu-id="b81a8-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="b81a8-109">Nous partons du principe que vous avez déjà déployé teams service au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b81a8-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="b81a8-110">Si vous n’avez pas encore déployé Teams, commencez par lire la rubrique [comment déployer Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b81a8-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="b81a8-111">Pour en savoir plus sur les modèles d’équipe en général, consultez la rubrique [commencer à utiliser les modèles](get-started-with-teams-templates-in-the-admin-console.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="b81a8-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="b81a8-112">Qualité et sécurité</span><span class="sxs-lookup"><span data-stu-id="b81a8-112">Quality and safety</span></span>

<span data-ttu-id="b81a8-113">Centralisez la communication, l’accès aux ressources et aux opérations d’usines avec une équipe de production.</span><span class="sxs-lookup"><span data-stu-id="b81a8-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="b81a8-114">Incluez des documents de stratégie et de procédure, des vidéos de formation, des avis de sécurité, des processus de transfert de Shift.</span><span class="sxs-lookup"><span data-stu-id="b81a8-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="b81a8-115">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="b81a8-115">Base template type</span></span>|<span data-ttu-id="b81a8-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b81a8-116">baseTemplateId</span></span> | <span data-ttu-id="b81a8-117">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="b81a8-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="b81a8-118">Qualité et sécurité</span><span class="sxs-lookup"><span data-stu-id="b81a8-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="b81a8-119">Canaux</span><span class="sxs-lookup"><span data-stu-id="b81a8-119">Channels:</span></span> <ul><li><span data-ttu-id="b81a8-120">Général</span><span class="sxs-lookup"><span data-stu-id="b81a8-120">General</span></span><li><span data-ttu-id="b81a8-121">Annonces</span><span class="sxs-lookup"><span data-stu-id="b81a8-121">Announcements</span></span></li><li><span data-ttu-id="b81a8-122">Ligne 1</span><span class="sxs-lookup"><span data-stu-id="b81a8-122">Line 1</span></span></li><li><span data-ttu-id="b81a8-123">Ligne 2</span><span class="sxs-lookup"><span data-stu-id="b81a8-123">Line 2</span></span></li><li><span data-ttu-id="b81a8-124">Ligne 3</span><span class="sxs-lookup"><span data-stu-id="b81a8-124">Line 3</span></span></li><li><span data-ttu-id="b81a8-125">Technologique</span><span class="sxs-lookup"><span data-stu-id="b81a8-125">Safety</span></span></li><li><span data-ttu-id="b81a8-126">Formation</span><span class="sxs-lookup"><span data-stu-id="b81a8-126">Training</span></span></li><li><span data-ttu-id="b81a8-127">Tarification</span><span class="sxs-lookup"><span data-stu-id="b81a8-127">Maintenance</span></span></li><li><span data-ttu-id="b81a8-128">Outils amusants</span><span class="sxs-lookup"><span data-stu-id="b81a8-128">Fun stuff</span></span></li></ul> <span data-ttu-id="b81a8-129">Logiciels</span><span class="sxs-lookup"><span data-stu-id="b81a8-129">Apps:</span></span> <ul><li><span data-ttu-id="b81a8-130">Wiki</span><span class="sxs-lookup"><span data-stu-id="b81a8-130">Wiki</span></span></li></ul>|
||||
