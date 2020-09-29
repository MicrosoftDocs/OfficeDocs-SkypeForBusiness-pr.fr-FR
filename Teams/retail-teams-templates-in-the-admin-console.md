---
title: Utiliser les modèles commerciaux teams dans la console d’administration
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
description: Découvrez comment utiliser les modèles teams pour créer des structures d’équipe conçues pour les revendeurs grâce aux paramètres prédéfinis, aux canaux et aux applications préinstallées à l’aide de la console d’administration.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9e0a75c558888fcd1c558eb3f87718a85e22471
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294540"
---
# <a name="use-teams-retail-templates-in-the-admin-console"></a><span data-ttu-id="8bdce-103">Utiliser les modèles commerciaux teams dans la console d’administration</span><span class="sxs-lookup"><span data-stu-id="8bdce-103">Use Teams retail templates in the admin console</span></span>

<span data-ttu-id="8bdce-104">Les modèles d’équipes vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications déjà installées.</span><span class="sxs-lookup"><span data-stu-id="8bdce-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="8bdce-105">Les modèles d’équipes sont dotés de définitions prédéfinies de structures d’équipe conçues en fonction des besoins des détaillants.</span><span class="sxs-lookup"><span data-stu-id="8bdce-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="8bdce-106">Vous pouvez utiliser les modèles teams pour créer rapidement des types d’équipes adaptées aux détaillants et à déployer au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8bdce-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="8bdce-107">Vous pouvez également développer les modèles teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8bdce-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="8bdce-108">Dans cet article, nous allons présenter chacun des modèles d’équipes et la façon dont nous vous conseillons de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="8bdce-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="8bdce-109">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation commerciale.</span><span class="sxs-lookup"><span data-stu-id="8bdce-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="8bdce-110">Nous partons du principe que vous avez déjà déployé teams service au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8bdce-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="8bdce-111">Si vous n’avez pas encore déployé Teams, commencez par lire la rubrique [comment déployer Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8bdce-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="8bdce-112">Pour en savoir plus sur les modèles d’équipe en général, consultez la rubrique [commencer à utiliser les modèles](get-started-with-teams-templates-in-the-admin-console.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="8bdce-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="8bdce-113">Organiser un Store</span><span class="sxs-lookup"><span data-stu-id="8bdce-113">Organize a store</span></span>

<span data-ttu-id="8bdce-114">Rassemblez vos collaborateurs au sein d’une interface centralisée pour gérer les tâches, partager des documents et résoudre les problèmes des clients.</span><span class="sxs-lookup"><span data-stu-id="8bdce-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="8bdce-115">Intégrez des applications supplémentaires pour rationaliser les processus de début de & de fin de travail.</span><span class="sxs-lookup"><span data-stu-id="8bdce-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="8bdce-116">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="8bdce-116">Base template type</span></span> |<span data-ttu-id="8bdce-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8bdce-117">baseTemplateId</span></span> | <span data-ttu-id="8bdce-118">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="8bdce-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="8bdce-119">Organiser un Store</span><span class="sxs-lookup"><span data-stu-id="8bdce-119">Organize a store</span></span>| `retailStore`|<span data-ttu-id="8bdce-120">Canaux</span><span class="sxs-lookup"><span data-stu-id="8bdce-120">Channels:</span></span> <ul><li><span data-ttu-id="8bdce-121">Général</span><span class="sxs-lookup"><span data-stu-id="8bdce-121">General</span></span><li><span data-ttu-id="8bdce-122">Remise du Shift</span><span class="sxs-lookup"><span data-stu-id="8bdce-122">Shift handoff</span></span></li><li><span data-ttu-id="8bdce-123">LMS</span><span class="sxs-lookup"><span data-stu-id="8bdce-123">Learning</span></span></li></ul> <span data-ttu-id="8bdce-124">Logiciels</span><span class="sxs-lookup"><span data-stu-id="8bdce-124">Apps:</span></span> <ul><li><span data-ttu-id="8bdce-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="8bdce-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="8bdce-126">Collaboration avec les responsables</span><span class="sxs-lookup"><span data-stu-id="8bdce-126">Manager Collaboration</span></span>

<span data-ttu-id="8bdce-127">Le modèle de collaboration responsable est idéal pour créer une équipe pour un ensemble de responsables pour collaborer entre des boutiques et des régions, etc. Par exemple, si votre organisation a des régions, vous pouvez créer une équipe de collaboration en chef pour la région Californie et inclure tous les responsables du Windows Store de cette région ainsi que le responsable régional de cette région.</span><span class="sxs-lookup"><span data-stu-id="8bdce-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="8bdce-128">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="8bdce-128">Base template type</span></span>| <span data-ttu-id="8bdce-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8bdce-129">baseTemplateId</span></span> | <span data-ttu-id="8bdce-130">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="8bdce-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="8bdce-131">Collaboration avec le responsable commercial</span><span class="sxs-lookup"><span data-stu-id="8bdce-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="8bdce-132">Canaux</span><span class="sxs-lookup"><span data-stu-id="8bdce-132">Channels:</span></span> <ul><li><span data-ttu-id="8bdce-133">Général</span><span class="sxs-lookup"><span data-stu-id="8bdce-133">General</span></span><li><span data-ttu-id="8bdce-134">Opérations</span><span class="sxs-lookup"><span data-stu-id="8bdce-134">Operations</span></span></li><li><span data-ttu-id="8bdce-135">LMS</span><span class="sxs-lookup"><span data-stu-id="8bdce-135">Learning</span></span></li></ul> <span data-ttu-id="8bdce-136">Logiciels</span><span class="sxs-lookup"><span data-stu-id="8bdce-136">Apps:</span></span> <ul><li><span data-ttu-id="8bdce-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="8bdce-137">Wiki</span></span></li></ul>|
||||
