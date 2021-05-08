---
title: Configurer le tableau de bord de qualité des appels
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
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
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Découvrez comment activer et utiliser le tableau de bord de qualité des appels et obtenir des rapports récapitulatifs sur la qualité des appels.
ms.openlocfilehash: c71cb25732a99f207467a988ad0db54c959d15f4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52254352"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="cf63c-103">Configurer le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="cf63c-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="cf63c-104">Ouvrez le tableau de bord de qualité des appels microsoft (CQD) à l’adresse [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (connectez-vous avec vos informations d’identification d’administrateur).</span><span class="sxs-lookup"><span data-stu-id="cf63c-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="cf63c-105">Vous pouvez également vous rendre au Teams d’administration et sélectionner **Le tableau de bord de qualité des appels.**</span><span class="sxs-lookup"><span data-stu-id="cf63c-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Capture d’écran du bouton Du tableau de bord qualité des appels Teams centre d’administration":::

<span data-ttu-id="cf63c-107">Dans la page qui s’ouvre, cliquez sur Se **connectez** et entrez les informations de votre compte d’Microsoft Teams administrateur général.</span><span class="sxs-lookup"><span data-stu-id="cf63c-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Administrator account information.</span></span> <span data-ttu-id="cf63c-108">Une fois que vous vous connectez pour la première fois, le CQD commence à collecter et à traiter les données.</span><span class="sxs-lookup"><span data-stu-id="cf63c-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="cf63c-109">N’oubliez pas que le traitement d’un nombre suffisant de données peut prendre une ou plusieurs heures afin d’afficher des résultats significatifs dans les rapports.</span><span class="sxs-lookup"><span data-stu-id="cf63c-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="cf63c-110">Le CQD indique la qualité des appels et des réunions, au niveau de l’organisation, pour Microsoft Teams, Skype Entreprise Online et Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cf63c-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="cf63c-111">Pour utiliser le CQD Skype Entreprise Server 2019, vous devez [configurer Call Data Connector.](/skypeforbusiness/hybrid/configure-call-data-connector)</span><span class="sxs-lookup"><span data-stu-id="cf63c-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="cf63c-112">Voir [Planifier le connecteur de données d’appel](/skypeforbusiness/hybrid/plan-call-data-connector) avant de commencer.</span><span class="sxs-lookup"><span data-stu-id="cf63c-112">See [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="cf63c-113">Attribuer des rôles d’administrateur pour l’accès au CQD</span><span class="sxs-lookup"><span data-stu-id="cf63c-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="cf63c-114">Attribuez [des](/microsoft-365/admin/add-users/about-admin-roles) rôles pour accéder au DQD aux personnes qui doivent l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="cf63c-114">Assign [roles](/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="cf63c-115">Si vous souhaitez que les utilisateurs non administrateurs (par exemple, des ingénieurs du support technique et des agents du support technique) utilisent le tableau de bord de qualité des appels, vous pouvez leur attribuer un des rôles suivants, ce qui donne accès au tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="cf63c-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="cf63c-116">Afficher des rapports</span><span class="sxs-lookup"><span data-stu-id="cf63c-116">View reports</span></span>  |<span data-ttu-id="cf63c-117">Afficher les champs EUII</span><span class="sxs-lookup"><span data-stu-id="cf63c-117">View EUII fields</span></span>  |<span data-ttu-id="cf63c-118">Créer des rapports</span><span class="sxs-lookup"><span data-stu-id="cf63c-118">Create reports</span></span>  |<span data-ttu-id="cf63c-119">Télécharger de création de données</span><span class="sxs-lookup"><span data-stu-id="cf63c-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="cf63c-120">Administrateur général</span><span class="sxs-lookup"><span data-stu-id="cf63c-120">Global Administrator</span></span>     |<span data-ttu-id="cf63c-121">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-121">Yes</span></span>         |<span data-ttu-id="cf63c-122">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-122">Yes</span></span>         |<span data-ttu-id="cf63c-123">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-123">Yes</span></span>         |<span data-ttu-id="cf63c-124">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-124">Yes</span></span>         |
|<span data-ttu-id="cf63c-125">Teams Administrateur</span><span class="sxs-lookup"><span data-stu-id="cf63c-125">Teams Administrator</span></span>     |<span data-ttu-id="cf63c-126">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-126">Yes</span></span>         |<span data-ttu-id="cf63c-127">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-127">Yes</span></span>         |<span data-ttu-id="cf63c-128">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-128">Yes</span></span>         |<span data-ttu-id="cf63c-129">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-129">Yes</span></span>         |
|<span data-ttu-id="cf63c-130">Administrateur des communications Teams</span><span class="sxs-lookup"><span data-stu-id="cf63c-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="cf63c-131">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-131">Yes</span></span>         |<span data-ttu-id="cf63c-132">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-132">Yes</span></span>         |<span data-ttu-id="cf63c-133">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-133">Yes</span></span>         |<span data-ttu-id="cf63c-134">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-134">Yes</span></span>         |
|<span data-ttu-id="cf63c-135">Ingénieur du support technique pour les communications Teams</span><span class="sxs-lookup"><span data-stu-id="cf63c-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="cf63c-136">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-136">Yes</span></span>         |<span data-ttu-id="cf63c-137">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-137">Yes</span></span>         |<span data-ttu-id="cf63c-138">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-138">Yes</span></span>         |<span data-ttu-id="cf63c-139">Non</span><span class="sxs-lookup"><span data-stu-id="cf63c-139">No</span></span>         |
|<span data-ttu-id="cf63c-140">Teams Spécialiste du support pour les communications</span><span class="sxs-lookup"><span data-stu-id="cf63c-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="cf63c-141">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-141">Yes</span></span>         |<span data-ttu-id="cf63c-142">Non</span><span class="sxs-lookup"><span data-stu-id="cf63c-142">No</span></span>         |<span data-ttu-id="cf63c-143">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-143">Yes</span></span>         |<span data-ttu-id="cf63c-144">Non</span><span class="sxs-lookup"><span data-stu-id="cf63c-144">No</span></span>         |
|<span data-ttu-id="cf63c-145">Skype Entreprise Administrateur</span><span class="sxs-lookup"><span data-stu-id="cf63c-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="cf63c-146">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-146">Yes</span></span>         |<span data-ttu-id="cf63c-147">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-147">Yes</span></span>         |<span data-ttu-id="cf63c-148">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-148">Yes</span></span>         |<span data-ttu-id="cf63c-149">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-149">Yes</span></span>         |
|<span data-ttu-id="cf63c-150">Lecteur global</span><span class="sxs-lookup"><span data-stu-id="cf63c-150">Global Reader</span></span> |<span data-ttu-id="cf63c-151">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-151">Yes</span></span>         |<span data-ttu-id="cf63c-152">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-152">Yes</span></span>         |<span data-ttu-id="cf63c-153">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-153">Yes</span></span>         |<span data-ttu-id="cf63c-154">Non</span><span class="sxs-lookup"><span data-stu-id="cf63c-154">No</span></span>         |
|<span data-ttu-id="cf63c-155">Lecteur de<sup>rapports 1</sup></span><span class="sxs-lookup"><span data-stu-id="cf63c-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="cf63c-156">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-156">Yes</span></span>         |<span data-ttu-id="cf63c-157">Non</span><span class="sxs-lookup"><span data-stu-id="cf63c-157">No</span></span>         |<span data-ttu-id="cf63c-158">Oui</span><span class="sxs-lookup"><span data-stu-id="cf63c-158">Yes</span></span>         |<span data-ttu-id="cf63c-159">Non</span><span class="sxs-lookup"><span data-stu-id="cf63c-159">No</span></span>         |

<span data-ttu-id="cf63c-160"><sup>1</sup> En plus de lire les rapports du CQD, le Lecteur de rapports peut afficher tous les rapports d’activité du Centre d’administration et tous les rapports du pack de contenu [Adoption Microsoft 365'équipe.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f) [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)</span><span class="sxs-lookup"><span data-stu-id="cf63c-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="cf63c-161">Si la fonction [EUII (identification](CQD-data-and-reports.md#euii-data) utilisateur final) n’est pas disponibles et que vous avez l’un des rôles autorisés à consulter ces informations, n’oubliez pas que le DQD conserve la fonction EUII uniquement pendant 28 jours.</span><span class="sxs-lookup"><span data-stu-id="cf63c-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="cf63c-162">Tous les éléments de plus de 28 jours sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="cf63c-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="cf63c-163">Pour plus d’informations sur ces rôles, voir À [propos Office 365 rôles d’administrateur.](/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="cf63c-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="cf63c-164">Une fois que vous vous connectez pour la première fois, le CQD commence à collecter et à traiter les données.</span><span class="sxs-lookup"><span data-stu-id="cf63c-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="cf63c-165">Depuis décembre 2019, vous pouvez toujours accéder à l’ancienne version du CQD (cqd.lync.com), bien que le portail hérité vous donne un lien vers le dernier CQD (cqd.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="cf63c-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="cf63c-166">Finalement, l’ancienne version du CQD sera désaffectée.</span><span class="sxs-lookup"><span data-stu-id="cf63c-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="cf63c-167">À compter du 1er juillet 2020, l’ancienne version du CQD accède aux données du dernier DQD.</span><span class="sxs-lookup"><span data-stu-id="cf63c-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="cf63c-168">Migrer des données et des rapports à partir d’une version précédente du CQD</span><span class="sxs-lookup"><span data-stu-id="cf63c-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf63c-169">À compter du 1er juillet 2020, vous ne pourrez plus migrer les données et les rapports à partir de l’ancien CQD https://CQD.lync.com) (.</span><span class="sxs-lookup"><span data-stu-id="cf63c-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="cf63c-170">Utiliser Power BI pour analyser les données du CQD</span><span class="sxs-lookup"><span data-stu-id="cf63c-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="cf63c-171">Nouveautés de janvier 2020 : télécharger Power BI modèles de [requête pour le CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="cf63c-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="cf63c-172">Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et signaler vos données de CQD.</span><span class="sxs-lookup"><span data-stu-id="cf63c-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="cf63c-173">Lisez Utiliser Power BI pour analyser les données du [CQD](CQD-Power-BI-query-templates.md) et en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="cf63c-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="cf63c-174">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="cf63c-174">Related topics</span></span>

[<span data-ttu-id="cf63c-175">Améliorer et surveiller la qualité des appels pour les Teams</span><span class="sxs-lookup"><span data-stu-id="cf63c-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="cf63c-176">Qu’est-ce que le CQD ?</span><span class="sxs-lookup"><span data-stu-id="cf63c-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="cf63c-177">Télécharger données client et bâtiment</span><span class="sxs-lookup"><span data-stu-id="cf63c-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="cf63c-178">Données et rapports du CQD</span><span class="sxs-lookup"><span data-stu-id="cf63c-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="cf63c-179">Utiliser le CQD pour gérer la qualité des appels et des réunions</span><span class="sxs-lookup"><span data-stu-id="cf63c-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="cf63c-180">Dimensions et mesures disponibles dans le DQD</span><span class="sxs-lookup"><span data-stu-id="cf63c-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="cf63c-181">Classification des flux dans le DQD</span><span class="sxs-lookup"><span data-stu-id="cf63c-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="cf63c-182">Utiliser Power BI pour analyser les données du CQD</span><span class="sxs-lookup"><span data-stu-id="cf63c-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)