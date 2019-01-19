---
title: Qualité de l’expérience utilisateur | Les équipes Microsoft | QoS | Qualité des appels
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Tâches et activités requises pour la surveillance de la qualité et l’utilisation de Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59acafa7555b793555b504b1555b0d6969a12b4b
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349318"
---
<span data-ttu-id="d5bbc-103">![Étapes du voyage mise à niveau, en insistant sur la phase d’Excellence opérationnelle] (media/upgrade-banner-op-excellence.png "Étapes du voyage mise à niveau, en insistant sur la phase d’Excellence opérationnelle")</span><span class="sxs-lookup"><span data-stu-id="d5bbc-103">![Stages of the upgrade journey, with emphasis on the Operational Excellence stage](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="d5bbc-104">Cet article fait partie de la phase d’Excellence opérationnelle de votre parcours de mise à niveau, qui démarre dès que vous avez terminé votre mise à niveau à partir de Skype pour les entreprises aux équipes.</span><span class="sxs-lookup"><span data-stu-id="d5bbc-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="d5bbc-105">Qualité de consulter le Guide de l’expérience</span><span class="sxs-lookup"><span data-stu-id="d5bbc-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="d5bbc-106">La [Qualité d’expérience consulter le Guide](https://aka.ms/qerguide) inclut un ensemble d’activités évaluer et fournissent des instructions de mise à jour dans les zones clés qui ont le plus grand impact sur l’amélioration de l’expérience utilisateur, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d5bbc-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="d5bbc-107">![Les zones clés pour examiner durant un examen de la qualité de l’expérience : audio, la fiabilité et les résultats du sondage.] (media/plan-my-service-management-image2.png "Les zones clés pour examiner durant un examen de la qualité de l’expérience : audio, la fiabilité et les résultats du sondage.")</span><span class="sxs-lookup"><span data-stu-id="d5bbc-107">![The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="d5bbc-108">En continuellement évaluer et de corriger les zones décrites dans le guide, vous pouvez réduire leur potentiel pour un impact négatif sur l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d5bbc-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="d5bbc-109">La plupart des problèmes d’expérience utilisateur dans un déploiement peuvent être regroupées dans les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="d5bbc-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="d5bbc-110">Configuration de pare-feu ou proxy incomplète</span><span class="sxs-lookup"><span data-stu-id="d5bbc-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="d5bbc-111">Une mauvaise couverture Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d5bbc-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="d5bbc-112">Bande passante insuffisante</span><span class="sxs-lookup"><span data-stu-id="d5bbc-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="d5bbc-113">VPN</span><span class="sxs-lookup"><span data-stu-id="d5bbc-113">VPN</span></span>

- <span data-ttu-id="d5bbc-114">Utilisation de périphériques audio non optimisées ou intégrés</span><span class="sxs-lookup"><span data-stu-id="d5bbc-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="d5bbc-115">Sous-réseaux problématiques ou périphériques réseau</span><span class="sxs-lookup"><span data-stu-id="d5bbc-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="d5bbc-116">Les instructions fournies dans le Guide Quality of Experience passer en revue les se concentre sur l’utilisation en ligne de tableau de bord de la qualité des appels (CQD) comme le principal outil d’examiner chaque zone décrite, en mettant l’accent sur l’audio à optimiser l’impact d’adoption et de signaler.</span><span class="sxs-lookup"><span data-stu-id="d5bbc-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="d5bbc-117">Les optimisations apportées au réseau pour améliorer l’expérience audio auront également directement des améliorations dans le partage du bureau et vidéo.</span><span class="sxs-lookup"><span data-stu-id="d5bbc-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="d5bbc-118">Nous vous recommandons de vous désigner le poids lourd qualité dès le début.</span><span class="sxs-lookup"><span data-stu-id="d5bbc-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="d5bbc-119">Après être désignés, ils doivent commencer à se familiariser avec le contenu dans le [Guide Quality of Experience révision](https://aka.ms/qerguide).</span><span class="sxs-lookup"><span data-stu-id="d5bbc-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->