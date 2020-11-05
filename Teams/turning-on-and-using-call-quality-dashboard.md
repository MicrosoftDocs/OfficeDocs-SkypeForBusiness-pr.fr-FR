---
title: Configurer le tableau de bord de qualité des appels (bord)
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
description: Apprenez-en davantage sur l’activation et l’utilisation du tableau de bord de qualité des appels et obtenez des rapports de synthèse sur la qualité des appels.
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918649"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="c8d04-103">Configurer le tableau de bord de qualité des appels (bord)</span><span class="sxs-lookup"><span data-stu-id="c8d04-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="c8d04-104">Ouvrez le tableau de bord de qualité des appels bord ( [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Connectez-vous à l’aide de vos informations d’identification d’administrateur).</span><span class="sxs-lookup"><span data-stu-id="c8d04-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="c8d04-105">Ou accédez au centre d’administration teams et sélectionnez **tableau de bord de qualité des appels**.</span><span class="sxs-lookup"><span data-stu-id="c8d04-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Capture d’écran du bouton tableau de bord de qualité des appels dans le centre d’administration teams":::

<span data-ttu-id="c8d04-107">Dans la page qui s’ouvre, cliquez sur **se connecter** , puis entrez les informations de votre compte d’administrateur général ou du compte d’administrateur de service Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c8d04-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Admin account information.</span></span> <span data-ttu-id="c8d04-108">Lorsque vous vous connectez pour la première fois, bord commence à collecter et à traiter les données.</span><span class="sxs-lookup"><span data-stu-id="c8d04-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="c8d04-109">Gardez à l’esprit qu’il est possible que l’affichage des résultats pertinents dans les rapports puisse prendre une ou plusieurs heures.</span><span class="sxs-lookup"><span data-stu-id="c8d04-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="c8d04-110">BORD indique la qualité des appels et des réunions à un niveau de l’organisation, pour Microsoft Teams, Skype entreprise Online et Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c8d04-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c8d04-111">Pour utiliser bord avec Skype entreprise Server 2019, vous devez [configurer un connecteur de données d’appel](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span><span class="sxs-lookup"><span data-stu-id="c8d04-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="c8d04-112">Pour commencer, voir [connecteur des données d’appel](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) .</span><span class="sxs-lookup"><span data-stu-id="c8d04-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="c8d04-113">Attribuer des rôles d’administrateur pour accéder à bord</span><span class="sxs-lookup"><span data-stu-id="c8d04-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="c8d04-114">Attribuez des [rôles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) pour accéder à bord aux personnes qui ont besoin de les utiliser.</span><span class="sxs-lookup"><span data-stu-id="c8d04-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="c8d04-115">Si vous voulez que les utilisateurs qui ne sont pas des administrateurs (par exemple, les ingénieurs de support et les agents d’assistance) puissent utiliser le tableau de bord de qualité des appels, vous pouvez attribuer à ces utilisateurs l’un des rôles suivants, qui donnent accès à bord.</span><span class="sxs-lookup"><span data-stu-id="c8d04-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="c8d04-116">Afficher les rapports</span><span class="sxs-lookup"><span data-stu-id="c8d04-116">View reports</span></span>  |<span data-ttu-id="c8d04-117">Afficher les champs de EUII</span><span class="sxs-lookup"><span data-stu-id="c8d04-117">View EUII fields</span></span>  |<span data-ttu-id="c8d04-118">Créer des rapports</span><span class="sxs-lookup"><span data-stu-id="c8d04-118">Create reports</span></span>  |<span data-ttu-id="c8d04-119">Télécharger les données de bâtiment</span><span class="sxs-lookup"><span data-stu-id="c8d04-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="c8d04-120">Administrateur général d’Office 365</span><span class="sxs-lookup"><span data-stu-id="c8d04-120">Office 365 Global Administrator</span></span>     |<span data-ttu-id="c8d04-121">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-121">Yes</span></span>         |<span data-ttu-id="c8d04-122">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-122">Yes</span></span>         |<span data-ttu-id="c8d04-123">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-123">Yes</span></span>         |<span data-ttu-id="c8d04-124">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-124">Yes</span></span>         |
|<span data-ttu-id="c8d04-125">Administrateur du service Teams</span><span class="sxs-lookup"><span data-stu-id="c8d04-125">Teams Service Administrator</span></span>     |<span data-ttu-id="c8d04-126">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-126">Yes</span></span>         |<span data-ttu-id="c8d04-127">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-127">Yes</span></span>         |<span data-ttu-id="c8d04-128">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-128">Yes</span></span>         |<span data-ttu-id="c8d04-129">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-129">Yes</span></span>         |
|<span data-ttu-id="c8d04-130">Administrateur des communications Teams</span><span class="sxs-lookup"><span data-stu-id="c8d04-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="c8d04-131">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-131">Yes</span></span>         |<span data-ttu-id="c8d04-132">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-132">Yes</span></span>         |<span data-ttu-id="c8d04-133">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-133">Yes</span></span>         |<span data-ttu-id="c8d04-134">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-134">Yes</span></span>         |
|<span data-ttu-id="c8d04-135">Ingénieur du support technique pour les communications Teams</span><span class="sxs-lookup"><span data-stu-id="c8d04-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="c8d04-136">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-136">Yes</span></span>         |<span data-ttu-id="c8d04-137">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-137">Yes</span></span>         |<span data-ttu-id="c8d04-138">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-138">Yes</span></span>         |<span data-ttu-id="c8d04-139">Non</span><span class="sxs-lookup"><span data-stu-id="c8d04-139">No</span></span>         |
|<span data-ttu-id="c8d04-140">Spécialiste du support des communications teams</span><span class="sxs-lookup"><span data-stu-id="c8d04-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="c8d04-141">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-141">Yes</span></span>         |<span data-ttu-id="c8d04-142">Non</span><span class="sxs-lookup"><span data-stu-id="c8d04-142">No</span></span>         |<span data-ttu-id="c8d04-143">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-143">Yes</span></span>         |<span data-ttu-id="c8d04-144">Non</span><span class="sxs-lookup"><span data-stu-id="c8d04-144">No</span></span>         |
|<span data-ttu-id="c8d04-145">Administrateur Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="c8d04-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="c8d04-146">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-146">Yes</span></span>         |<span data-ttu-id="c8d04-147">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-147">Yes</span></span>         |<span data-ttu-id="c8d04-148">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-148">Yes</span></span>         |<span data-ttu-id="c8d04-149">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-149">Yes</span></span>         |
|<span data-ttu-id="c8d04-150">Lecteur global Azure AD</span><span class="sxs-lookup"><span data-stu-id="c8d04-150">Azure AD Global Reader</span></span> |<span data-ttu-id="c8d04-151">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-151">Yes</span></span>         |<span data-ttu-id="c8d04-152">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-152">Yes</span></span>         |<span data-ttu-id="c8d04-153">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-153">Yes</span></span>         |<span data-ttu-id="c8d04-154">Non</span><span class="sxs-lookup"><span data-stu-id="c8d04-154">No</span></span>         |
|<span data-ttu-id="c8d04-155">Office 365-rapports sur le lecteur<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c8d04-155">Office 365 Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="c8d04-156">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-156">Yes</span></span>         |<span data-ttu-id="c8d04-157">Non</span><span class="sxs-lookup"><span data-stu-id="c8d04-157">No</span></span>         |<span data-ttu-id="c8d04-158">Oui</span><span class="sxs-lookup"><span data-stu-id="c8d04-158">Yes</span></span>         |<span data-ttu-id="c8d04-159">Non</span><span class="sxs-lookup"><span data-stu-id="c8d04-159">No</span></span>         |

<span data-ttu-id="c8d04-160"><sup>1</sup> en plus de lire des rapports bord, le lecteur de rapports d' 365 Office peut afficher tous les [rapports d’activité](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) dans le centre d’administration et les rapports du [Pack de contenu adoption de Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span><span class="sxs-lookup"><span data-stu-id="c8d04-160"><sup>1</sup> In addition to reading CQD reports, the Office 365 Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="c8d04-161">Si vous ne voyez pas [EUII (informations d’identification de l’utilisateur final)](CQD-data-and-reports.md#euii-data) et que vous disposez de l’un des rôles autorisés à voir ces informations, n’oubliez pas que bord ne conserve que EUII pendant 28 jours.</span><span class="sxs-lookup"><span data-stu-id="c8d04-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="c8d04-162">Les éléments datant de plus de 28 jours sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="c8d04-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="c8d04-163">Pour plus d’informations sur ces rôles, voir [à propos des rôles d’administrateur Office 365](/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="c8d04-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="c8d04-164">Lorsque vous vous connectez pour la première fois, bord commence à collecter et à traiter les données.</span><span class="sxs-lookup"><span data-stu-id="c8d04-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="c8d04-165">À compter du 2019 de décembre, vous pouvez toujours accéder à l’ancienne version de bord (cqd.lync.com), bien que le portail hérité vous donne un lien vers le dernier bord (cqd.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c8d04-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="c8d04-166">Par la suite, l’ancienne version de bord sera mise hors service.</span><span class="sxs-lookup"><span data-stu-id="c8d04-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="c8d04-167">À compter du 1er juillet 2020, l’ancienne version de bord accède aux données depuis la dernière bord.</span><span class="sxs-lookup"><span data-stu-id="c8d04-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="c8d04-168">Migrer des données et des rapports à partir d’une version précédente de bord</span><span class="sxs-lookup"><span data-stu-id="c8d04-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8d04-169">À partir du 1er juillet 2020, vous ne pouvez plus migrer les données et les rapports à partir de l’ancien bord ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="c8d04-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="c8d04-170">Utiliser Power BI pour analyser des données de bord</span><span class="sxs-lookup"><span data-stu-id="c8d04-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="c8d04-171">Nouveauté de janvier 2020 : [Télécharger les modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="c8d04-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="c8d04-172">Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et enregistrer vos données bord.</span><span class="sxs-lookup"><span data-stu-id="c8d04-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="c8d04-173">Pour en savoir plus, voir [utiliser Power bi pour analyser les données de bord](CQD-Power-BI-query-templates.md) .</span><span class="sxs-lookup"><span data-stu-id="c8d04-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c8d04-174">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="c8d04-174">Related topics</span></span>

[<span data-ttu-id="c8d04-175">Améliorer et surveiller la qualité des appels pour teams</span><span class="sxs-lookup"><span data-stu-id="c8d04-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="c8d04-176">Qu’est-ce que bord ?</span><span class="sxs-lookup"><span data-stu-id="c8d04-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="c8d04-177">Télécharger le client et générer des données</span><span class="sxs-lookup"><span data-stu-id="c8d04-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="c8d04-178">Rapports et données bord</span><span class="sxs-lookup"><span data-stu-id="c8d04-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="c8d04-179">Utiliser bord pour gérer la qualité des appels et des réunions</span><span class="sxs-lookup"><span data-stu-id="c8d04-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="c8d04-180">Dimensions et mesures disponibles dans bord</span><span class="sxs-lookup"><span data-stu-id="c8d04-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="c8d04-181">Classification des flux dans bord</span><span class="sxs-lookup"><span data-stu-id="c8d04-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="c8d04-182">Utiliser Power BI pour analyser des données de bord</span><span class="sxs-lookup"><span data-stu-id="c8d04-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
