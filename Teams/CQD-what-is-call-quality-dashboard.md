---
title: Qu’est-ce que le tableau de bord de qualité des appels (bord) ?
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: En savoir plus sur le tableau de bord de qualité des appels (bord) et sur son utilisation pour afficher des rapports sur la réunion et la qualité d’appel dans Microsoft Teams.
ms.openlocfilehash: b7830d60139991b7ccc18679af798c74430e8ed1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088242"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="bbad6-103">Qu’est-ce que le tableau de bord de qualité des appels (bord) ?</span><span class="sxs-lookup"><span data-stu-id="bbad6-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="bbad6-104">Le tableau de bord de qualité des appels Microsoft (bord) : [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) affiche la qualité des appels et des réunions, au **niveau**de l’organisation, pour Microsoft Teams, Skype entreprise Online et Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bbad6-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="bbad6-105">La version la plus récente de bord comprend un [flux de données en temps réel (NRT)](CQD-data-and-reports.md), ce qui signifie que les enregistrements d’appels sont disponibles dans bord dans les 30 minutes de la fin d’un appel.</span><span class="sxs-lookup"><span data-stu-id="bbad6-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="bbad6-106">Partout où bord inclut les données d’identification de l' [utilisateur final (EUII)](CQD-data-and-reports.md#euii-data), il est géré de la même manière que [EUII dans Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="bbad6-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="bbad6-107">BORD est conçu pour permettre aux administrateurs d’équipe, aux administrateurs Skype entreprise et aux ingénieurs réseau de surveiller la qualité des appels et des réunions à l’échelle de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="bbad6-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="bbad6-108">Vous pouvez utiliser bord pour **optimiser votre réseau** et renforcer la qualité des performances.</span><span class="sxs-lookup"><span data-stu-id="bbad6-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="bbad6-109">Lorsque vous recherchez des informations sur les appels et les réunions pour un **utilisateur spécifique**, utilisez les données bord conjointement avec l' [analyse](use-call-analytics-to-troubleshoot-poor-call-quality.md)par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bbad6-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="bbad6-110">Par exemple, en utilisant bord, vous pouvez déterminer si la qualité d’appel d’un utilisateur (que vous avez observé lors d’une analyse d’appel par utilisateur) est due à un problème de réseau qui affecte également de nombreux autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bbad6-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="bbad6-111">BORD capture les appels individuels et la qualité générale des appels passés à l’aide d’équipes ou de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="bbad6-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="bbad6-112">Avec bord, les modèles globaux peuvent devenir évidents, afin que les ingénieurs du réseau puissent effectuer des analyses éclairées de la qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="bbad6-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="bbad6-113">BORD fournit des rapports sur les métriques de la qualité d’appel qui vous permettent d’avoir une vue d’ensemble de la qualité des appels, des flux client-client, des flux client-client et du [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de qualité vocale.</span><span class="sxs-lookup"><span data-stu-id="bbad6-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Capture d’écran du tableau de bord de qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="bbad6-115">Dans bord, nous vous encourageons à télécharger des informations sur la création et le point de terminaison, qui vous permet d’utiliser des rapports d’emplacement pour analyser la qualité et la fiabilité des appels au sein d’un immeuble.</span><span class="sxs-lookup"><span data-stu-id="bbad6-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="bbad6-116">Les données peuvent être évaluées pour déterminer si le problème est limité à un utilisateur unique ou s’il concerne un plus grand nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bbad6-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="bbad6-117">Pour activer le bâtiment ou les vues spécifiques aux points de terminaison dans bord, un administrateur doit [Télécharger les informations de construction ou de point de terminaison](CQD-upload-tenant-building-data.md) sur la page de téléchargement de données du **client** bord.</span><span class="sxs-lookup"><span data-stu-id="bbad6-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Capture d’écran des rapports d’emplacement du tableau de bord de qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="bbad6-119">Ne manquez pas notre article [gérer l’appel et la qualité](quality-of-experience-review-guide.md) de la réunion, qui offre des instructions détaillées au sein de l’administrateur teams ou du technicien de support responsable de la gestion de la qualité du service dans Teams.</span><span class="sxs-lookup"><span data-stu-id="bbad6-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="bbad6-120">Version antérieure de bord (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="bbad6-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="bbad6-121">La version actuelle de bord ( https://CQD.Teams.microsoft.com) remplace l’ancienne version d’bord ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="bbad6-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="bbad6-122">Vous pouvez toujours utiliser CQD.lync.com (disponible dans le centre d’administration Skype entreprise), mais à partir du 1er juillet 2020, il utilise les données de bord. Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="bbad6-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="bbad6-123">Nous désactivons l’accès à CQD.lync.com bientôt, donc vous devez accéder à bord. Teams.microsoft.com si vous ne l’avez pas déjà fait.</span><span class="sxs-lookup"><span data-stu-id="bbad6-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbad6-124">À compter du 1er juillet 2020, vous ne pouvez plus afficher ni modifier vos données de bâtiment ou de requête à partir de l’ancien bord (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="bbad6-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="bbad6-125">Si vous n’avez pas déjà migré ces données à partir de CQD.lync.com et que vous en avez encore besoin, consignez un ticket de support.</span><span class="sxs-lookup"><span data-stu-id="bbad6-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="bbad6-126">Utiliser Power BI pour analyser des données de bord</span><span class="sxs-lookup"><span data-stu-id="bbad6-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="bbad6-127">Nouveauté de janvier 2020 : [Télécharger les modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="bbad6-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="bbad6-128">Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et enregistrer vos données bord.</span><span class="sxs-lookup"><span data-stu-id="bbad6-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="bbad6-129">Pour en savoir plus, voir [utiliser Power bi pour analyser les données de bord](CQD-Power-BI-query-templates.md) .</span><span class="sxs-lookup"><span data-stu-id="bbad6-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="bbad6-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bbad6-130">Related topics</span></span>

[<span data-ttu-id="bbad6-131">Améliorer et surveiller la qualité des appels pour teams</span><span class="sxs-lookup"><span data-stu-id="bbad6-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="bbad6-132">Configurer le tableau de bord de qualité des appels (bord)</span><span class="sxs-lookup"><span data-stu-id="bbad6-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="bbad6-133">Télécharger le client et générer des données</span><span class="sxs-lookup"><span data-stu-id="bbad6-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="bbad6-134">Rapports et données bord</span><span class="sxs-lookup"><span data-stu-id="bbad6-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="bbad6-135">Utiliser bord pour gérer la qualité des appels et des réunions</span><span class="sxs-lookup"><span data-stu-id="bbad6-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="bbad6-136">Dimensions et mesures disponibles dans bord</span><span class="sxs-lookup"><span data-stu-id="bbad6-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="bbad6-137">Classification des flux dans bord</span><span class="sxs-lookup"><span data-stu-id="bbad6-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="bbad6-138">Utiliser Power BI pour analyser des données de bord</span><span class="sxs-lookup"><span data-stu-id="bbad6-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="bbad6-139">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="bbad6-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)