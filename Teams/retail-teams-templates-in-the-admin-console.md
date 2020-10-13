---
title: Utiliser les modèles commerciaux teams dans le centre d’administration
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
description: Découvrez comment utiliser les modèles teams pour créer des structures d’équipe conçues pour les revendeurs grâce aux paramètres prédéfinis, aux canaux et aux applications préinstallées à l’aide du centre d’administration.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40e21687aa3d14b0cb9d51d4ba5f856eada3c538
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424564"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="342d7-103">Utiliser les modèles commerciaux teams dans le centre d’administration</span><span class="sxs-lookup"><span data-stu-id="342d7-103">Use Teams retail templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="342d7-104">Les modèles d’équipes vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications déjà installées.</span><span class="sxs-lookup"><span data-stu-id="342d7-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="342d7-105">Les modèles d’équipes sont dotés de définitions prédéfinies de structures d’équipe conçues en fonction des besoins des détaillants.</span><span class="sxs-lookup"><span data-stu-id="342d7-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="342d7-106">Vous pouvez utiliser les modèles teams pour créer rapidement des types d’équipes adaptées aux détaillants et à déployer au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="342d7-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="342d7-107">Vous pouvez également développer les modèles teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="342d7-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="342d7-108">Dans cet article, nous allons présenter chacun des modèles d’équipes et la façon dont nous vous conseillons de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="342d7-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="342d7-109">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation commerciale.</span><span class="sxs-lookup"><span data-stu-id="342d7-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="342d7-110">Nous partons du principe que vous avez déjà déployé teams service au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="342d7-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="342d7-111">Si vous n’avez pas encore déployé Teams, commencez par lire la rubrique [comment déployer Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="342d7-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="342d7-112">Pour en savoir plus sur les modèles d’équipe en général, consultez la rubrique [commencer à utiliser les modèles](get-started-with-teams-templates-in-the-admin-console.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="342d7-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="342d7-113">Organiser un Store</span><span class="sxs-lookup"><span data-stu-id="342d7-113">Organize a store</span></span>

<span data-ttu-id="342d7-114">Rassemblez vos collaborateurs au sein d’une interface centralisée pour gérer les tâches, partager des documents et résoudre les problèmes des clients.</span><span class="sxs-lookup"><span data-stu-id="342d7-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="342d7-115">Intégrez des applications supplémentaires pour rationaliser les processus de début de & de fin de travail.</span><span class="sxs-lookup"><span data-stu-id="342d7-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="342d7-116">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="342d7-116">Base template type</span></span> |<span data-ttu-id="342d7-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="342d7-117">baseTemplateId</span></span> | <span data-ttu-id="342d7-118">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="342d7-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="342d7-119">Organiser un Store</span><span class="sxs-lookup"><span data-stu-id="342d7-119">Organize a store</span></span>| `retailStore`|<span data-ttu-id="342d7-120">Canaux</span><span class="sxs-lookup"><span data-stu-id="342d7-120">Channels:</span></span> <ul><li><span data-ttu-id="342d7-121">Général</span><span class="sxs-lookup"><span data-stu-id="342d7-121">General</span></span><li><span data-ttu-id="342d7-122">Remise du Shift</span><span class="sxs-lookup"><span data-stu-id="342d7-122">Shift handoff</span></span></li><li><span data-ttu-id="342d7-123">LMS</span><span class="sxs-lookup"><span data-stu-id="342d7-123">Learning</span></span></li></ul> <span data-ttu-id="342d7-124">Logiciels</span><span class="sxs-lookup"><span data-stu-id="342d7-124">Apps:</span></span> <ul><li><span data-ttu-id="342d7-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="342d7-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="342d7-126">Collaboration avec les responsables</span><span class="sxs-lookup"><span data-stu-id="342d7-126">Manager Collaboration</span></span>

<span data-ttu-id="342d7-127">Le modèle de collaboration responsable est idéal pour créer une équipe pour un ensemble de responsables pour collaborer entre des boutiques et des régions, etc. Par exemple, si votre organisation a des régions, vous pouvez créer une équipe de collaboration en chef pour la région Californie et inclure tous les responsables du Windows Store de cette région ainsi que le responsable régional de cette région.</span><span class="sxs-lookup"><span data-stu-id="342d7-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="342d7-128">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="342d7-128">Base template type</span></span>| <span data-ttu-id="342d7-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="342d7-129">baseTemplateId</span></span> | <span data-ttu-id="342d7-130">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="342d7-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="342d7-131">Collaboration avec le responsable commercial</span><span class="sxs-lookup"><span data-stu-id="342d7-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="342d7-132">Canaux</span><span class="sxs-lookup"><span data-stu-id="342d7-132">Channels:</span></span> <ul><li><span data-ttu-id="342d7-133">Général</span><span class="sxs-lookup"><span data-stu-id="342d7-133">General</span></span><li><span data-ttu-id="342d7-134">Opérations</span><span class="sxs-lookup"><span data-stu-id="342d7-134">Operations</span></span></li><li><span data-ttu-id="342d7-135">LMS</span><span class="sxs-lookup"><span data-stu-id="342d7-135">Learning</span></span></li></ul> <span data-ttu-id="342d7-136">Logiciels</span><span class="sxs-lookup"><span data-stu-id="342d7-136">Apps:</span></span> <ul><li><span data-ttu-id="342d7-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="342d7-137">Wiki</span></span></li></ul>|
||||
