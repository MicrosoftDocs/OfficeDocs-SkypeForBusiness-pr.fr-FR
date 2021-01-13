---
title: Qualité de l’expérience utilisateur | Microsoft Teams | QoS | Qualité de l’appel
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Les administrateurs peuvent en savoir plus sur les tâches et les activités requises pour surveiller la qualité et l’utilisation de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d57f01887961ad0c458b13db20ba79023272bcdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808994"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="00383-103">Guide d’examen de l’expérience de qualité</span><span class="sxs-lookup"><span data-stu-id="00383-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="00383-104">![Diagramme mettant en évidence l’excellence opérationnelle lors de la phase de mise à niveau](media/upgrade-banner-op-excellence.png "Étapes du voyage de mise à niveau, avec l’accentuation sur la phase d’excellence opérationnelle")</span><span class="sxs-lookup"><span data-stu-id="00383-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="00383-105">Cet article fait partie de la phase d’excellence opérationnelle de votre parcours de mise à niveau qui commence dès que vous avez terminé la mise à niveau de Skype Entreprise vers Teams.</span><span class="sxs-lookup"><span data-stu-id="00383-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="00383-106">Améliorer et surveiller la qualité des appels</span><span class="sxs-lookup"><span data-stu-id="00383-106">Improve and monitor call quality</span></span>

<span data-ttu-id="00383-107">L’amélioration et le suivi de la qualité des appels pour [Teams](monitor-call-quality-qos.md) incluent un ensemble d’activités qui évaluent et fournissent des recommandations de correction dans les domaines clés qui ont le plus fort impact sur l’amélioration de l’expérience utilisateur, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="00383-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="00383-108">![Illustration des principales zones à examiner lors d’une révision.](media/plan-my-service-management-image2.png "Principaux aspects à examiner lors d’une révision de la qualité de l’expérience : audio, fiabilité et résultats des enquêtes effectués par les utilisateurs.")</span><span class="sxs-lookup"><span data-stu-id="00383-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="00383-109">En evaluant et en réstant les aspects décrits dans le guide, vous pouvez réduire leur risque d’affecter négativement l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="00383-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="00383-110">La plupart des problèmes d'expérience utilisateur rencontrés lors d'un déploiement peuvent être regroupés dans les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="00383-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="00383-111">Configuration incomplète du pare-feu ou du proxy</span><span class="sxs-lookup"><span data-stu-id="00383-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="00383-112">Faible couverture Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="00383-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="00383-113">Bande passante insuffisante</span><span class="sxs-lookup"><span data-stu-id="00383-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="00383-114">VPN</span><span class="sxs-lookup"><span data-stu-id="00383-114">VPN</span></span>

- <span data-ttu-id="00383-115">Utilisation d'appareils audio non optimisés ou intégrés</span><span class="sxs-lookup"><span data-stu-id="00383-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="00383-116">Sous-réseaux ou périphériques réseau problématiques</span><span class="sxs-lookup"><span data-stu-id="00383-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="00383-117">Les conseils fournis dans Améliorer et surveiller la qualité des appels pour [Teams](monitor-call-quality-qos.md) se concentrent sur l’utilisation du tableau de bord de qualité des appels online comme outil principal pour signaler et examiner chaque zone décrite, avec un focus sur l’audio afin d’optimiser l’adoption et l’impact.</span><span class="sxs-lookup"><span data-stu-id="00383-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="00383-118">Toutes les optimisations apportées au réseau pour améliorer l'expérience audio se traduiront aussi directement par des améliorations dans le partage de la vidéo et du bureau.</span><span class="sxs-lookup"><span data-stu-id="00383-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="00383-119">Il est vivement recommandé de désigner le champion de la qualité rapidement.</span><span class="sxs-lookup"><span data-stu-id="00383-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="00383-120">Une fois qu’ils ont été désignés, ils doivent commencer à se familiariser avec le contenu dans Améliorer et surveiller la qualité des [appels pour Teams.](monitor-call-quality-qos.md)</span><span class="sxs-lookup"><span data-stu-id="00383-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
