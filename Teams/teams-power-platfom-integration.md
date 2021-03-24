---
title: Intégration de Teams à Microsoft Power Platform
author: cichur
ms.author: v-cichur
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
description: Découvrez l’intégration de Teams aux outils de la plateforme Microsoft Power Platform, notamment Power BI, les applications Power, Power automatiser et les agents virtuels Power.
ms.openlocfilehash: c6442cd654dd8da6e26de048d50b7c80ef95cf26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111040"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="9c690-103">Intégration de Teams à Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="9c690-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="9c690-104">Microsoft Power Platform permet aux utilisateurs d’accélérer leur développement à l’aide d’outils à faible code pour analyser des données à l’aide de **Power BI,** de créer des applications personnalisées à l’aide de **Power Apps,** d’automatiser les processus à l’aide de **Power Automate** et de créer des robots intelligents à l’aide d’agents virtuels **Power Virtual Plus** rapidement que jamais.</span><span class="sxs-lookup"><span data-stu-id="9c690-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="9c690-105">Grâce au passage au travail distant et hybride, Microsoft Teams permet aux utilisateurs du monde entier de continuer à créer, à collaborer et à communiquer.</span><span class="sxs-lookup"><span data-stu-id="9c690-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="9c690-106">Avec plus de 75 millions d’utilisateurs actifs par jour, Teams est la manière dont les personnes travaillent.</span><span class="sxs-lookup"><span data-stu-id="9c690-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Image résumant Teams et la plateforme Microsoft Power Platform":::

<span data-ttu-id="9c690-108">Microsoft Power Platform offre de nombreuses fonctionnalités d’intégration avec Teams, qui vous permettent d’incorporer des rapports **Power BI** dans l’espace de travail Teams, d’incorporer des applications créées à l’aide de **Power Apps** en tant qu’onglet ou application personnelle, de déclencher un flux Power **Automate** à partir de n’importe quel message ou d’utiliser des cartes adaptatives, et d’ajouter votre robot créé à l’aide d’agents virtuels **Power** à Teams pour que les autres membres de votre organisation interagissent.</span><span class="sxs-lookup"><span data-stu-id="9c690-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="9c690-109">Depuis septembre 2020, l’intégration à Microsoft Power Platform a été améliorée pour que les utilisateurs disposent des interfaces suivantes sans jamais quitter *l’interface teams*:</span><span class="sxs-lookup"><span data-stu-id="9c690-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="9c690-110">Créez et partagez des tableaux de bord, des rapports et des applications à l’aide **de Power BI** pour prendre des décisions éclairées par les données.</span><span class="sxs-lookup"><span data-stu-id="9c690-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="9c690-111">Créez et partagez des applications conçues à cet effet à l’aide d’un studio **Power Apps** intégré en vous connectant à vos données métiers stockées dans la nouvelle plateforme de données sous-jacente (Microsoft Dataverse pour Teams), Microsoft 365 ou dans d’autres sources de données via des connecteurs.</span><span class="sxs-lookup"><span data-stu-id="9c690-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="9c690-112">Créez des flux de travail automatisés entre vos applications et services pour synchroniser des fichiers, recevoir des notifications, collecter des données et bien plus encore à l’aide **de Power Automate.**</span><span class="sxs-lookup"><span data-stu-id="9c690-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="9c690-113">Créez des robots à l’aide d’une interface graphique guidée sans code à l’aide **d’agents** virtuels Power pour créer facilement des assistants numériques dans Teams et les mettre à la disposition de vos collègues pour qu’ils discutent.</span><span class="sxs-lookup"><span data-stu-id="9c690-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="9c690-114">Les nouvelles fonctionnalités de création d’applications, de bots et de flux de travail sont backed par la nouvelle plateforme de données intégrée à faible code pour Teams, [Dataverse](/powerapps/teams/overview-data-platform)pour Teams, qui fournit un stockage des données relationnelles, des types de données enrichis, une gouvernance de niveau entreprise et un déploiement de solution en un seul clic.</span><span class="sxs-lookup"><span data-stu-id="9c690-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](/powerapps/teams/overview-data-platform), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="9c690-115">Dataverse pour Teams est intégré à [Microsoft Dataverse.](/powerapps/maker/common-data-service/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="9c690-115">Dataverse for Teams is built on top of [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="9c690-116">Avec Dataverse pour Teams, les utilisateurs de Teams peuvent rechercher et installer des solutions personnalisées et prêtes à l’emploi à partir du magasin d’applications Teams qui présente des scénarios courants dans différents secteurs.</span><span class="sxs-lookup"><span data-stu-id="9c690-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="9c690-117">Vous pouvez personnaliser et étendre ces solutions personnalisées afin de les adapter à la personnalisation et aux exigences de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9c690-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="9c690-118">Gestion des licences</span><span class="sxs-lookup"><span data-stu-id="9c690-118">Licensing</span></span>

<span data-ttu-id="9c690-119">Les nouvelles fonctionnalités sont disponibles pour les abonnements Microsoft 365 sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="9c690-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="9c690-120">Pour plus d’informations sur les conditions de licence requises pour Power Apps, Power Automate, les agents virtuels Power et Dataverse pour Teams, voir [Gestion des licences.](/power-platform/admin/about-teams-environment)</span><span class="sxs-lookup"><span data-stu-id="9c690-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](/power-platform/admin/about-teams-environment).</span></span>
- <span data-ttu-id="9c690-121">Pour plus d’informations sur les conditions de licence requises pour Power BI, voir [La exigences.](/power-bi/collaborate-share/service-collaborate-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="9c690-121">For more information about licensing requirements for Power BI, see [Requirements](/power-bi/collaborate-share/service-collaborate-microsoft-teams).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="9c690-122">Comment puis-je commencer ?</span><span class="sxs-lookup"><span data-stu-id="9c690-122">How do I get started?</span></span>

- [<span data-ttu-id="9c690-123">Power BI et Teams</span><span class="sxs-lookup"><span data-stu-id="9c690-123">Power BI and Teams</span></span>](/power-bi/collaborate-share/service-collaborate-microsoft-teams)
- [<span data-ttu-id="9c690-124">Power Apps et Teams</span><span class="sxs-lookup"><span data-stu-id="9c690-124">Power Apps and Teams</span></span>](/powerapps/teams/overview)
- [<span data-ttu-id="9c690-125">Power Automate et Teams</span><span class="sxs-lookup"><span data-stu-id="9c690-125">Power Automate and Teams</span></span>](/power-automate/teams/overview)
- [<span data-ttu-id="9c690-126">Agents et équipes virtuels Power</span><span class="sxs-lookup"><span data-stu-id="9c690-126">Power Virtual Agents and Teams</span></span>](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)