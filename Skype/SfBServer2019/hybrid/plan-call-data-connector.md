---
title: Planifier le connecteur de données d’appel
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Présentation de l’utilisation de Skype pour Business Online outils de télémétrie pour surveiller une implémentation sur site dans un scénario hybride.
ms.openlocfilehash: 2c491a217f02af77a25f362697e6f89aceb9470c
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "25030699"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="5ff03-103">Planifier le connecteur de données d’appel</span><span class="sxs-lookup"><span data-stu-id="5ff03-103">Plan Call Data Connector</span></span>

[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a><span data-ttu-id="5ff03-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="5ff03-104">Overview</span></span>
<span data-ttu-id="5ff03-105">Cette rubrique décrit les avantages, considérations relatives à la planification et configuration requise pour l’implémentation de Skype Business Server appeler connecteur de données.</span><span class="sxs-lookup"><span data-stu-id="5ff03-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="5ff03-106">Pour plus d’informations sur la configuration de connecteur de données d’appel, voir [Configurer appeler un connecteur de données](configure-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5ff03-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5ff03-107">Version d’évaluation, tableau de bord Analytique appeler uniquement est disponible.</span><span class="sxs-lookup"><span data-stu-id="5ff03-107">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="5ff03-108">Connecteur de données d’appel simplifie grandement la surveillance de l’appel dans un environnement hybride, car vous n’avez plus besoin d’utiliser différentes sur site et les outils en ligne pour contrôler l’ensemble de vos utilisateurs la qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="5ff03-108">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="5ff03-109">Si vos utilisateurs sont hébergés sur site ou en ligne, vous pouvez choisir d’afficher la qualité des appels pour votre organisation en ligne.</span><span class="sxs-lookup"><span data-stu-id="5ff03-109">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="5ff03-110">Avec le connecteur de données d’appel, vous pouvez effectuer les tâches suivantes à l’aide d’un seul ensemble d’outils :</span><span class="sxs-lookup"><span data-stu-id="5ff03-110">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="5ff03-111">Surveiller votre expérience utilisateur dans Microsoft Teams, Skype pour Business Online et Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="5ff03-111">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="5ff03-112">Afficher et résoudre les problèmes de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="5ff03-112">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="5ff03-113">Assigner des rôles de support technique et administrateur appeler Analytique, afin que vous donner des travailleurs de support technique pour afficher et résoudre les problèmes de leurs domaines de responsabilité.</span><span class="sxs-lookup"><span data-stu-id="5ff03-113">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span> 

<span data-ttu-id="5ff03-114">Avec le connecteur de données d’appel, le Skype pour Business Server envoie les données d’appel au service cloud afin que vous pouvez tirer parti de la Skype pour les outils professionnels en ligne appel Analytique (CA) et du tableau de bord de la qualité des appels (CQD), comme illustré dans le diagramme suivant :</span><span class="sxs-lookup"><span data-stu-id="5ff03-114">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![Messagerie vocale SfB Cloud](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="5ff03-116">Le serveur envoie la qualité de l’expérience (QoE) et les données d’appel d’enregistrement des détails au service en ligne.</span><span class="sxs-lookup"><span data-stu-id="5ff03-116">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="5ff03-117">Les outils CQD Analytique d’appel permettent de surveiller la qualité des appels et de résoudre les problèmes de connexion avec Microsoft Teams et Skype pour les services comme suit :</span><span class="sxs-lookup"><span data-stu-id="5ff03-117">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="5ff03-118">Appeler se concentre Analytique sur des problèmes de qualité avec les appels spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5ff03-118">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="5ff03-119">Il affiche des informations détaillées sur les appels et les réunions pour chaque utilisateur dans un Skype pour un compte professionnel.</span><span class="sxs-lookup"><span data-stu-id="5ff03-119">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="5ff03-120">Avec appel Analytique, vous pouvez affecter des autorisations à un opérateur de support technique qui peut puis surveiller les appels sans avoir accès au reste du Skype pour le centre d’administration Business.</span><span class="sxs-lookup"><span data-stu-id="5ff03-120">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="5ff03-121">Tableau de bord qualité appel se concentre sur les performances réseau et problèmes à travers une organisation.</span><span class="sxs-lookup"><span data-stu-id="5ff03-121">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="5ff03-122">Skype pour les administrateurs et les ingénieurs réseau utiliser cet outil pour résoudre les problèmes et optimiser les performances réseau.</span><span class="sxs-lookup"><span data-stu-id="5ff03-122">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="5ff03-123">Pour plus d’informations, voir [Analytique d’appel et appel du tableau de bord qualité](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="5ff03-123">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="5ff03-124">Bien sûr, vous pouvez souhaiter conserver des données de qualité d’appel sur site.</span><span class="sxs-lookup"><span data-stu-id="5ff03-124">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="5ff03-125">Ce peut être le cas, par exemple, si vous utilisez une solution tierce avec flux de travail et des rapports personnalisés.</span><span class="sxs-lookup"><span data-stu-id="5ff03-125">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="5ff03-126">Connecteur de données d’appel permet de configurer le service online envoie des données tout en gardant une copie des données sur votre serveur local, comme illustré dans le diagramme suivant :</span><span class="sxs-lookup"><span data-stu-id="5ff03-126">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![Messagerie vocale SfB Cloud](../../sfbserver2019/media/call-data-connector-plan-2.png)


## <a name="requirements"></a><span data-ttu-id="5ff03-128">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="5ff03-128">Requirements</span></span>

<span data-ttu-id="5ff03-129">Les conditions suivantes supposent que vous avez déjà Skype pour Business Server déployé dans une topologie prise en charge.</span><span class="sxs-lookup"><span data-stu-id="5ff03-129">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="5ff03-130">Pour plus d’informations sur le déploiement de Skype pour Business Server et les topologies prises en charge, voir [Les concepts de topologie](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span><span class="sxs-lookup"><span data-stu-id="5ff03-130">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span></span>

- <span data-ttu-id="5ff03-131">Connectivité hybride.</span><span class="sxs-lookup"><span data-stu-id="5ff03-131">Hybrid connectivity.</span></span> <span data-ttu-id="5ff03-132">Si vous avez déjà Skype pour Business Server est déployé et que vous souhaitez activer le connecteur de données d’appel, vous devez vous assurer que vous disposez de connectivité hybride entre votre organisation locale et environnements en ligne.</span><span class="sxs-lookup"><span data-stu-id="5ff03-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="5ff03-133">Il est parfois appelée une configuration de domaine fractionné.</span><span class="sxs-lookup"><span data-stu-id="5ff03-133">This is sometimes called a split domain configuration.</span></span> 

   <span data-ttu-id="5ff03-134">Pour plus d’informations, voir [planification de la connectivité hybride entre Skype pour Business Server et Office 365](plan-hybrid-connectivity.md) et de [configurer la connectivité hybride entre Skype pour Business Server et Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="5ff03-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="5ff03-135">Pour configurer le connecteur de données d’appel, vous devez s’authentifient auprès de votre client Office 365 et vérifiez que les rôles suivants activés :</span><span class="sxs-lookup"><span data-stu-id="5ff03-135">To configure Call Data Connector, you must authenticate to your Office 365 tenant and ensure that you have the following roles enabled:</span></span>

   - <span data-ttu-id="5ff03-136">Administrateur du serveur pour les professionnels de Skype</span><span class="sxs-lookup"><span data-stu-id="5ff03-136">Skype for Business Server Administrator</span></span> 
   - <span data-ttu-id="5ff03-137">Administrateur Global d’Office 365</span><span class="sxs-lookup"><span data-stu-id="5ff03-137">Office 365 Global Administrator</span></span> 

- <span data-ttu-id="5ff03-138">Si vous n’avez pas déjà fait, allumez appel du tableau de bord qualité comme décrit dans la [mise sous tension et à l’aide d’appels de tableau de bord qualité pour les équipes Microsoft et Skype pour Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="5ff03-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="5ff03-139">Rapports de comparaison des locaux et en ligne du tableau de bord de la qualité des appels (CQD)</span><span class="sxs-lookup"><span data-stu-id="5ff03-139">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="5ff03-140">Rapports de fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="5ff03-140">Feature reports</span></span> | <span data-ttu-id="5ff03-141">Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="5ff03-141">Skype for Business Online</span></span> | <span data-ttu-id="5ff03-142">Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5ff03-142">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="5ff03-143">Mesure de partage d’application</span><span class="sxs-lookup"><span data-stu-id="5ff03-143">Application sharing metric</span></span> |<span data-ttu-id="5ff03-144">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-144">Yes</span></span> | <span data-ttu-id="5ff03-145">Limitée</span><span class="sxs-lookup"><span data-stu-id="5ff03-145">Limited</span></span> |
| <span data-ttu-id="5ff03-146">Informations de création de client</span><span class="sxs-lookup"><span data-stu-id="5ff03-146">Customer building information</span></span>| <span data-ttu-id="5ff03-147">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-147">Yes</span></span> | <span data-ttu-id="5ff03-148">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-148">Yes</span></span> |
| <span data-ttu-id="5ff03-149">Exploration analytique</span><span class="sxs-lookup"><span data-stu-id="5ff03-149">Drill-down analytics</span></span> | <span data-ttu-id="5ff03-150">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-150">Yes</span></span> | <span data-ttu-id="5ff03-151">Non</span><span class="sxs-lookup"><span data-stu-id="5ff03-151">No</span></span> |
| <span data-ttu-id="5ff03-152">Mesures de la fiabilité du média</span><span class="sxs-lookup"><span data-stu-id="5ff03-152">Media reliability metrics</span></span> | <span data-ttu-id="5ff03-153">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-153">Yes</span></span> | <span data-ttu-id="5ff03-154">Limitée</span><span class="sxs-lookup"><span data-stu-id="5ff03-154">Limited</span></span> |
| <span data-ttu-id="5ff03-155">Rapports out-of-the-box</span><span class="sxs-lookup"><span data-stu-id="5ff03-155">Out-of-the-box reports</span></span> | <span data-ttu-id="5ff03-156">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-156">Yes</span></span> | <span data-ttu-id="5ff03-157">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-157">Yes</span></span> |
| <span data-ttu-id="5ff03-158">Vue d’ensemble des rapports</span><span class="sxs-lookup"><span data-stu-id="5ff03-158">Overview reports</span></span> | <span data-ttu-id="5ff03-159">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-159">Yes</span></span> | <span data-ttu-id="5ff03-160">Non</span><span class="sxs-lookup"><span data-stu-id="5ff03-160">No</span></span> |
| <span data-ttu-id="5ff03-161">Par rapports utilisateur</span><span class="sxs-lookup"><span data-stu-id="5ff03-161">Per user reports</span></span> | <span data-ttu-id="5ff03-162">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-162">Yes</span></span> | <span data-ttu-id="5ff03-163">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-163">Yes</span></span> |
| <span data-ttu-id="5ff03-164">Personnalisation de rapports</span><span class="sxs-lookup"><span data-stu-id="5ff03-164">Report set customization</span></span> <br> <span data-ttu-id="5ff03-165">(ajouter, supprimer, modifier des rapports)</span><span class="sxs-lookup"><span data-stu-id="5ff03-165">(add, delete, modify reports)</span></span> | <span data-ttu-id="5ff03-166">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-166">Yes</span></span> | <span data-ttu-id="5ff03-167">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-167">Yes</span></span> |
| <span data-ttu-id="5ff03-168">Partage des mesures d’écran vidéo</span><span class="sxs-lookup"><span data-stu-id="5ff03-168">Video-based screen sharing metrics</span></span> | <span data-ttu-id="5ff03-169">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-169">Yes</span></span> | <span data-ttu-id="5ff03-170">Non</span><span class="sxs-lookup"><span data-stu-id="5ff03-170">No</span></span> |
| <span data-ttu-id="5ff03-171">API de données pour l’accès par programme</span><span class="sxs-lookup"><span data-stu-id="5ff03-171">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="5ff03-172">pour CQD</span><span class="sxs-lookup"><span data-stu-id="5ff03-172">to CQD</span></span> | <span data-ttu-id="5ff03-173">Non</span><span class="sxs-lookup"><span data-stu-id="5ff03-173">No</span></span> | <span data-ttu-id="5ff03-174">Oui</span><span class="sxs-lookup"><span data-stu-id="5ff03-174">Yes</span></span> |



















