---
title: Intégration de teams avec Microsoft Power Platform
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: kvivek
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Familiarisez-vous avec l’intégration de teams avec les outils de plateforme Microsoft Power BI, tels que Power BI, les applications puissantes, la gestion automatique des informations et les agents d’alimentation virtuelles.
ms.openlocfilehash: 81d673069e972f4627a8bfab18095e81803dd4b1
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085674"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="88f08-103">Intégration de teams avec Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="88f08-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="88f08-104">Microsoft Power Platform permet aux utilisateurs d’accélérer leur développement grâce aux outils de code bas permettant d’analyser des données à l’aide de **Power bi**, de générer des applications personnalisées à l’aide **d’applications de gestion** de l’alimentation, d’automatiser les processus à l’aide de **Power automate** et de créer des robots intelligents utilisant plus rapidement les **agents de la** fonction d’alimentation</span><span class="sxs-lookup"><span data-stu-id="88f08-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="88f08-105">Lorsque vous passez des tâches distantes et hybrides, Microsoft teams vous permet de continuer à créer, à collaborer et à communiquer.</span><span class="sxs-lookup"><span data-stu-id="88f08-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="88f08-106">Avec plus de 75 millions utilisateurs actifs quotidiennement, teams est la façon dont les personnes travaillent.</span><span class="sxs-lookup"><span data-stu-id="88f08-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Image récapitulative des équipes et de Microsoft Power Platform":::

<span data-ttu-id="88f08-108">Microsoft Power Platform fournit de nombreuses fonctionnalités d’intégration aux équipes qui vous permettent d’intégrer des rapports **Power bi** dans l’espace de travail Teams, de **mettre** en place des applications créées à l’aide de **Power Apps** en tant qu’onglet ou application personnelle, de déclencher un flux automatique à partir de n’importe quel message ou d’utiliser des cartes adaptatives, et d’ajouter votre robot créé à l’aide d' **agents**</span><span class="sxs-lookup"><span data-stu-id="88f08-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="88f08-109">À compter du 2020 de septembre, l’intégration avec Microsoft Power Platform s’est améliorée pour permettre aux utilisateurs d’effectuer les opérations suivantes *sans avoir à quitter l’interface teams*:</span><span class="sxs-lookup"><span data-stu-id="88f08-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="88f08-110">Créez et partagez des tableaux de bord, des rapports et des applications à l’aide de **Power bi** pour prendre des décisions basées sur les données.</span><span class="sxs-lookup"><span data-stu-id="88f08-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="88f08-111">Créez et partagez des applications de faible code à usage personnel à l’aide d’un Studio **puissant Apps** Studio en établissant une connexion à vos données métiers stockées dans la nouvelle plate-forme de données sous-jacente (Microsoft Dataverse pour Teams), Microsoft 365 ou dans d’autres sources de données à l’aide de connecteurs.</span><span class="sxs-lookup"><span data-stu-id="88f08-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="88f08-112">Créez des flux de travail automatisés entre vos applications et services permettant de synchroniser des fichiers, de recevoir des notifications, de collecter des données, etc., à l’aide de **Power automate**.</span><span class="sxs-lookup"><span data-stu-id="88f08-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="88f08-113">Construisez des robots à l’aide d’une interface graphique guidée sans code grâce à des **agents d’alimentation virtuelle** permettant de créer facilement des assistants numériques dans teams et de les mettre à la disposition de vos collègues pour discuter avec eux.</span><span class="sxs-lookup"><span data-stu-id="88f08-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="88f08-114">Les nouvelles fonctionnalités de création d’applications, de robots et de flux de travail sont représentées par la nouvelle plate-forme de données à faible code intégrée pour Teams, [Dataverse pour les équipes](https://go.microsoft.com/fwlink/?linkid=2143541), qui fournit un espace de stockage de données relationnelles, des types de données enrichis, une gouvernance d’entreprise et un déploiement de solution en un clic.</span><span class="sxs-lookup"><span data-stu-id="88f08-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="88f08-115">Dataverse pour teams est conçu en haut de [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="88f08-115">Dataverse for Teams is built on top of [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="88f08-116">Dataverse pour teams permet aux utilisateurs de teams de rechercher et d’installer des solutions personnalisées prêtes à l’emploi dans l’App Store d’équipes qui présentent des scénarios courants dans les industries.</span><span class="sxs-lookup"><span data-stu-id="88f08-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="88f08-117">Vous pouvez personnaliser et étendre ces solutions personnalisées pour s’adapter à la personnalisation et aux exigences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="88f08-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="88f08-118">Licence</span><span class="sxs-lookup"><span data-stu-id="88f08-118">Licensing</span></span>

<span data-ttu-id="88f08-119">Les nouvelles fonctionnalités sont disponibles pour les abonnements Select Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88f08-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="88f08-120">Pour plus d’informations sur les exigences en matière de licences pour les applications Power, automate et Dataverse pour Teams, voir gestion des [licences](https://go.microsoft.com/fwlink/?linkid=2143647).</span><span class="sxs-lookup"><span data-stu-id="88f08-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="88f08-121">Pour plus d’informations sur les exigences en matière de licences pour Power BI, voir [Configuration requise](https://go.microsoft.com/fwlink/?linkid=2143490).</span><span class="sxs-lookup"><span data-stu-id="88f08-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="88f08-122">Comment puis-je commencer ?</span><span class="sxs-lookup"><span data-stu-id="88f08-122">How do I get started?</span></span>

- [<span data-ttu-id="88f08-123">Power BI et équipes</span><span class="sxs-lookup"><span data-stu-id="88f08-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="88f08-124">Applications Power et Teams</span><span class="sxs-lookup"><span data-stu-id="88f08-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="88f08-125">Automate et équipe Power</span><span class="sxs-lookup"><span data-stu-id="88f08-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="88f08-126">Agents et équipes de secteur virtuel</span><span class="sxs-lookup"><span data-stu-id="88f08-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
