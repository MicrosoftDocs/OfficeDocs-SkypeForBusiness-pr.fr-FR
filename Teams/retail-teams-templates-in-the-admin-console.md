---
title: Utiliser les modèles de vente au détail Teams dans le Centre d’administration
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
description: Découvrez comment utiliser les modèles Teams pour créer des structures d’équipe conçues pour les besoins d’un revendeur en fournissant des paramètres, des canaux et des applications préinstallées à l’aide du Centre d'administration.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a63602f07e0c248b4decbc733e41b16fdafc3911
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117612"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="3e375-103">Utiliser les modèles de vente au détail Teams dans le Centre d’administration</span><span class="sxs-lookup"><span data-stu-id="3e375-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="3e375-104">Les modèles Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d'applications préinstallées.</span><span class="sxs-lookup"><span data-stu-id="3e375-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="3e375-105">Les modèles Teams ont des définitions pré-conçues pour les structures d’équipe conçues autour des besoins d’un revendeur.</span><span class="sxs-lookup"><span data-stu-id="3e375-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="3e375-106">Vous pouvez utiliser des modèles Teams pour créer rapidement les types d’équipes qui fonctionnent bien pour les revendeurs et les déployer au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3e375-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="3e375-107">Vous pouvez également étendre les modèles Teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3e375-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="3e375-108">Cet article présente chacun des modèles Teams et décrit leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="3e375-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="3e375-109">Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de vente au détail.</span><span class="sxs-lookup"><span data-stu-id="3e375-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="3e375-110">Nous partons du principe que vous avez déjà déployé le service Teams dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3e375-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="3e375-111">Si vous n’avez pas encore déployé Teams, commencez par lire l’article [Comment déployer Microsoft Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3e375-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="3e375-112">Pour en savoir plus sur les modèles d’équipe en général, consultez [Prise en main des modèles Teams](get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="3e375-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="3e375-113">Organiser un magasin</span><span class="sxs-lookup"><span data-stu-id="3e375-113">Organize a store</span></span>

<span data-ttu-id="3e375-114">Rassemblez vos employés dans une expérience centralisée pour gérer les tâches, partager des documents et résoudre les problèmes des clients.</span><span class="sxs-lookup"><span data-stu-id="3e375-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="3e375-115">Intégrez des applications supplémentaires pour simplifier les processus de démarrage et de fin des shifts.</span><span class="sxs-lookup"><span data-stu-id="3e375-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="3e375-116">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="3e375-116">Base template type</span></span> |<span data-ttu-id="3e375-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3e375-117">baseTemplateId</span></span> | <span data-ttu-id="3e375-118">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="3e375-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="3e375-119">Organiser un magasin</span><span class="sxs-lookup"><span data-stu-id="3e375-119">Organize a store</span></span>|`retailStore`|<span data-ttu-id="3e375-120">Canaux :</span><span class="sxs-lookup"><span data-stu-id="3e375-120">Channels:</span></span> <ul><li><span data-ttu-id="3e375-121">Général</span><span class="sxs-lookup"><span data-stu-id="3e375-121">General</span></span><li><span data-ttu-id="3e375-122">Transfert de shift</span><span class="sxs-lookup"><span data-stu-id="3e375-122">Shift handoff</span></span></li><li><span data-ttu-id="3e375-123">Apprentissage</span><span class="sxs-lookup"><span data-stu-id="3e375-123">Learning</span></span></li></ul> <span data-ttu-id="3e375-124">Applications :</span><span class="sxs-lookup"><span data-stu-id="3e375-124">Apps:</span></span> <ul><li><span data-ttu-id="3e375-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="3e375-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="3e375-126">Collaboration des responsables</span><span class="sxs-lookup"><span data-stu-id="3e375-126">Manager Collaboration</span></span>

<span data-ttu-id="3e375-127">Le modèle de collaboration entre responsables est idéal pour créer une équipe permettant à un ensemble de responsables de collaborer entre magasins/régions, etc. Par exemple, si votre organisation comporte des régions, vous pouvez créer une équipe de collaboration entre responsables pour la région de Californie et y inclure tous les responsables de magasin de cette région, ainsi que le responsable régional de cette région.</span><span class="sxs-lookup"><span data-stu-id="3e375-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="3e375-128">Type de modèle de base</span><span class="sxs-lookup"><span data-stu-id="3e375-128">Base template type</span></span>| <span data-ttu-id="3e375-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3e375-129">baseTemplateId</span></span> | <span data-ttu-id="3e375-130">Propriétés fournies avec ce modèle de base</span><span class="sxs-lookup"><span data-stu-id="3e375-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="3e375-131">Vente au détail : collaboration entre responsables</span><span class="sxs-lookup"><span data-stu-id="3e375-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="3e375-132">Canaux :</span><span class="sxs-lookup"><span data-stu-id="3e375-132">Channels:</span></span> <ul><li><span data-ttu-id="3e375-133">Général</span><span class="sxs-lookup"><span data-stu-id="3e375-133">General</span></span><li><span data-ttu-id="3e375-134">Opérations</span><span class="sxs-lookup"><span data-stu-id="3e375-134">Operations</span></span></li><li><span data-ttu-id="3e375-135">Apprentissage</span><span class="sxs-lookup"><span data-stu-id="3e375-135">Learning</span></span></li></ul> <span data-ttu-id="3e375-136">Applications :</span><span class="sxs-lookup"><span data-stu-id="3e375-136">Apps:</span></span> <ul><li><span data-ttu-id="3e375-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="3e375-137">Wiki</span></span></li></ul>|
||||