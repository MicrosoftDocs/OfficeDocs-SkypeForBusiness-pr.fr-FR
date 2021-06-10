---
title: Qu’est-ce que le tableau de bord de qualité des appels ?
ms.author: serdars
author: SerdarSoysal
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
description: Découvrez le tableau de bord de qualité des appels et comment l’utiliser pour consulter des rapports sur la qualité des réunions et des appels Microsoft Teams.
ms.openlocfilehash: d262449394d9ad880d13897988e40e26dd98578c
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593832"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="23b8e-103">Qu’est-ce que le tableau de bord de qualité des appels ?</span><span class="sxs-lookup"><span data-stu-id="23b8e-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="23b8e-104">Tableau de bord de qualité des appels de Microsoft (CQD) - Affiche la qualité des appels et des réunions, au niveau de l’organisation, pour Microsoft Teams, Skype Entreprise Online et [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype Entreprise Server 2019. </span><span class="sxs-lookup"><span data-stu-id="23b8e-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="23b8e-105">La dernière version du DQD comprend un flux de données en temps quasi réel [(NRT),](CQD-data-and-reports.md)ce qui signifie que les enregistrements d’appel sont disponibles dans le point de qualité des appels dans les 30 minutes après la fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="23b8e-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="23b8e-106">Chaque fois que le CQD inclut des informations d’identification des utilisateurs finux [(EUII),](CQD-data-and-reports.md#euii-data)il est géré de la même façon que [euII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23b8e-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="23b8e-107">Le CQD est conçu pour aider les Teams, les Skype Entreprise et les ingénieurs réseau à surveiller la qualité des appels et des réunions à l’échelle de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="23b8e-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="23b8e-108">Vous utiliserez le CQD pour optimiser **votre réseau afin** d’optimiser la qualité des performances.</span><span class="sxs-lookup"><span data-stu-id="23b8e-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="23b8e-109">Lorsque vous avez besoin d’examiner les informations d’appel et de réunion d’un utilisateur **spécifique,** utilisez les données de la qualité de la recherche conjointement avec l’analyse des appels par [utilisateur.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="23b8e-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="23b8e-110">Par exemple, vous pouvez déterminer que la qualité des appels d’un utilisateur (observée à l’aide de l’analyse des appels par utilisateur) est due à un problème de réseau qui affecte également de nombreux autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="23b8e-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="23b8e-111">Le CQD capture à la fois l’expérience d’appel individuelle et la qualité globale des appels effectués à l’aide d Teams ou Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="23b8e-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="23b8e-112">Grâce au CQD, des modèles globaux peuvent être mis en évidence pour que les ingénieurs réseau puisse évaluer en connaissance de cause la qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="23b8e-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="23b8e-113">Le CQD fournit des rapports sur les mesures de qualité des appels, qui fournissent des informations sur la qualité globale des appels, les flux client-serveur, les flux client et le SLA de [qualité vocale.](https://go.microsoft.com/fwlink/p/?linkid=846252)</span><span class="sxs-lookup"><span data-stu-id="23b8e-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Capture d’écran du tableau de bord de qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="23b8e-115">Dans le CQD, nous vous encourageons à télécharger les informations de bâtiment et de point de terminaison, qui vous permet d’utiliser des rapports de Location-Enhanced pour analyser la qualité et la fiabilité des appels au sein du bâtiment d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="23b8e-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="23b8e-116">Les données peuvent être évaluées pour déterminer si le problème est isolé pour un seul utilisateur ou affecte un segment plus important d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="23b8e-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="23b8e-117">Pour activer les affichages spécifiques du point de [](CQD-upload-tenant-building-data.md) terminaison ou du point de terminaison dans le DQD, un administrateur doit télécharger les informations de bâtiment ou de point de terminaison sur la page Données du client du Télécharger du point **de** terminaison.</span><span class="sxs-lookup"><span data-stu-id="23b8e-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Capture d’écran des rapports d’utilisation du tableau de Location-Enhanced qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="23b8e-119">Ne manquez pas [notre](quality-of-experience-review-guide.md) article Gérer la qualité des appels et des réunions, qui propose des conseils détaillés pour l’administrateur Teams ou l’ingénieur support responsable de la gestion de la qualité du service dans Teams.</span><span class="sxs-lookup"><span data-stu-id="23b8e-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="legacy-version-of-cqd-cqdlynccom"></a><span data-ttu-id="23b8e-120">Version héritée du CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="23b8e-120">Legacy version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="23b8e-121">La version actuelle de CQD ( https://CQD.Teams.microsoft.com) a remplacé l’ancienne version du CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="23b8e-121">The current version of CQD (https://CQD.Teams.microsoft.com) has replaced the legacy version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="23b8e-122">Vous pouvez toujours utiliser CQD.lync.com (disponible dans le Centre d’administration Skype Entreprise), mais depuis le 1er juillet 2020, il utilise les données du CQD. Teams.microsoft.com et vous ne pouvez plus afficher ni modifier vos données de bâtiment ou de requête à partir de l’ancien CQD (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="23b8e-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com and you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="23b8e-123">Si vous n’avez pas encore migré ces données depuis votre CQD.lync.com en avez encore besoin, enregistrez un ticket de support.</span><span class="sxs-lookup"><span data-stu-id="23b8e-123">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23b8e-124">À compter du 31 juillet 2021, nous retirons l’ancienne version du CQD (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="23b8e-124">As of July 31, 2021, we are retiring the legacy version of CQD (CQD.lync.com).</span></span> <span data-ttu-id="23b8e-125">Après cette date, vous serez automatiquement redirigé vers le CQD. Teams.microsoft.com tentez d’accéder à CQD.lync.com données de requête ou de création non mégérées seront perdues.</span><span class="sxs-lookup"><span data-stu-id="23b8e-125">After that date, you will be automatically redirected to CQD.Teams.microsoft.com when attempting to access CQD.lync.com, and any unmigrated building or query data will be lost.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="23b8e-126">Utiliser Power BI pour analyser les données du CQD</span><span class="sxs-lookup"><span data-stu-id="23b8e-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="23b8e-127">Nouveautés de janvier 2020 : télécharger Power BI modèles de [requête pour le CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="23b8e-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="23b8e-128">Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et signaler vos données de CQD.</span><span class="sxs-lookup"><span data-stu-id="23b8e-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="23b8e-129">Lisez Utiliser Power BI pour analyser les données [du CQD](CQD-Power-BI-query-templates.md) et en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="23b8e-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="23b8e-130">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="23b8e-130">Related topics</span></span>

[<span data-ttu-id="23b8e-131">Améliorer et surveiller la qualité des appels pour les Teams</span><span class="sxs-lookup"><span data-stu-id="23b8e-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="23b8e-132">Configurer le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="23b8e-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="23b8e-133">Télécharger données de bâtiment et de client</span><span class="sxs-lookup"><span data-stu-id="23b8e-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="23b8e-134">Données et rapports du CQD</span><span class="sxs-lookup"><span data-stu-id="23b8e-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="23b8e-135">Utiliser le CQD pour gérer la qualité des appels et des réunions</span><span class="sxs-lookup"><span data-stu-id="23b8e-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="23b8e-136">Dimensions et mesures disponibles dans le DQD</span><span class="sxs-lookup"><span data-stu-id="23b8e-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="23b8e-137">Classification des flux dans le CQD</span><span class="sxs-lookup"><span data-stu-id="23b8e-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="23b8e-138">Utiliser Power BI pour analyser les données du CQD</span><span class="sxs-lookup"><span data-stu-id="23b8e-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="23b8e-139">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="23b8e-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
