---
title: Qualité de l’utilisation de l’utilisateur | Microsoft teams | QoS | Qualité des appels
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Tâches et activités requises pour l’analyse de la qualité et de l’utilisation de Microsoft teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e870c6e6561bac991e7b9498ef76162ec1fa2eb9
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706974"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="ce51f-103">Guide d’examen de l’expérience de qualité</span><span class="sxs-lookup"><span data-stu-id="ce51f-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="ce51f-104">![Mise en évidence de l’étape de mise à niveau d’amélioration du diagramme](media/upgrade-banner-op-excellence.png "Étapes du voyage de la mise à niveau, avec mise en évidence de l’étape d’excellence opérationnelle")</span><span class="sxs-lookup"><span data-stu-id="ce51f-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="ce51f-105">Cet article fait partie de l’étape du fonctionnement de votre mise à niveau du fonctionnement de votre mise à niveau, qui commence dès que vous avez terminé la mise à niveau de Skype entreprise vers Teams.</span><span class="sxs-lookup"><span data-stu-id="ce51f-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

<span data-ttu-id="ce51f-106">Le [Guide de vérification de la qualité de l’utilisation](https://aka.ms/qerguide) inclut un ensemble d’activités qui évaluent et fournissent des recommandations en matière de correction dans des domaines clés ayant un impact élevé sur l’amélioration de l’interface utilisateur, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ce51f-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="ce51f-107">![Illustration des principales zones à examiner lors d’une révision.](media/plan-my-service-management-image2.png "Principaux points à examiner lors de la vérification de la qualité de l’utilisation : audio, fiabilité et résultats d’une enquête utilisateur.")</span><span class="sxs-lookup"><span data-stu-id="ce51f-107">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="ce51f-108">En évaluant et en révisant en permanence les zones décrites dans le guide, vous pouvez réduire leur potentiel pour une utilisation négative de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce51f-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="ce51f-109">La plupart des problèmes d'expérience utilisateur rencontrés lors d'un déploiement peuvent être regroupés dans les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="ce51f-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="ce51f-110">Configuration incomplète du pare-feu ou du proxy</span><span class="sxs-lookup"><span data-stu-id="ce51f-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="ce51f-111">Faible couverture Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ce51f-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="ce51f-112">Bande passante insuffisante</span><span class="sxs-lookup"><span data-stu-id="ce51f-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="ce51f-113">VPN</span><span class="sxs-lookup"><span data-stu-id="ce51f-113">VPN</span></span>

- <span data-ttu-id="ce51f-114">Utilisation d'appareils audio non optimisés ou intégrés</span><span class="sxs-lookup"><span data-stu-id="ce51f-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="ce51f-115">Sous-réseaux ou périphériques réseau problématiques</span><span class="sxs-lookup"><span data-stu-id="ce51f-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="ce51f-116">Les recommandations fournies dans le guide sur la qualité de l’utilisation s’intéressent à l’utilisation du tableau de bord de qualité des appels (bord) en ligne comme outil principal permettant de signaler et d’examiner chaque zone décrite, de manière à optimiser l’adoption et l’impact.</span><span class="sxs-lookup"><span data-stu-id="ce51f-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="ce51f-117">Toutes les optimisations apportées au réseau pour améliorer l'expérience audio se traduiront aussi directement par des améliorations dans le partage de la vidéo et du bureau.</span><span class="sxs-lookup"><span data-stu-id="ce51f-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="ce51f-118">Nous vous conseillons vivement de le nommer rapidement.</span><span class="sxs-lookup"><span data-stu-id="ce51f-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="ce51f-119">Ils doivent commencer à se familiariser avec le contenu du guide sur la [qualité de l’utilisation](https://aka.ms/qerguide).</span><span class="sxs-lookup"><span data-stu-id="ce51f-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
