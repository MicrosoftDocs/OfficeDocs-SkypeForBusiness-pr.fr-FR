---
title: Microsoft 365 Government-déploiements de très haute qualité
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Conseils destinés aux professionnels de l’informatique pour piloter les déploiements d’Office 365 dans les entités qui gèrent les données soumises au règlement du gouvernement des États-Unis.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b5111e61f6c545a7311280fa865c762e8498b86
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137809"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a><span data-ttu-id="0b4df-103">Plan pour Microsoft 365 Government-déploiements de niveau supérieur</span><span class="sxs-lookup"><span data-stu-id="0b4df-103">Plan for Microsoft 365 Government - GCC High deployments</span></span>

<span data-ttu-id="0b4df-104">Ce guide est destiné aux professionnels de l’informatique qui pilotent des déploiements d’Office 365 au sein des organisations du secteur public américain ou d’autres entités qui gèrent les données soumises à la réglementation et aux exigences gouvernementales, car l’utilisation de Microsoft 365 Government (GCC High) est appropriée pour répondre à ces exigences.</span><span class="sxs-lookup"><span data-stu-id="0b4df-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="0b4df-105">Si votre organisation a déjà rempli les obligations du ministère de l’éligibilité Microsoft 365 et qu’elle a été acceptée dans le programme, vous pouvez ignorer les étapes 1 et 2, puis passer directement à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="0b4df-105">If your organization has already met the Microsoft 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="0b4df-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="0b4df-106">Step 1.</span></span> <span data-ttu-id="0b4df-107">Déterminez si votre organisation a besoin de Microsoft 365 Government-GCC High et conforme aux exigences d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="0b4df-107">Determine whether your organization needs Microsoft 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="0b4df-108">Le secteur public de Microsoft 365-GCC High fournit une conformité aux exigences de l’administration américaine pour les services Cloud.</span><span class="sxs-lookup"><span data-stu-id="0b4df-108">The Microsoft 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="0b4df-109">En plus des fonctionnalités et des fonctionnalités d’Office 365, les organisations tirent parti des fonctionnalités suivantes qui sont propres à l’administration de Microsoft 365 :</span><span class="sxs-lookup"><span data-stu-id="0b4df-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – GCC High:</span></span>

- <span data-ttu-id="0b4df-110">Le contenu du client de votre organisation est séparé de manière logique du contenu client dans les services Office 365 commerciaux de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0b4df-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="0b4df-111">Le contenu du client de votre organisation est enregistré aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="0b4df-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="0b4df-112">L’accès au contenu du client de votre organisation est limité aux membres du personnel de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0b4df-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="0b4df-113">Microsoft 365 Government-GCC High est conforme aux certifications et aux accréditations requises pour les clients du secteur public américain.</span><span class="sxs-lookup"><span data-stu-id="0b4df-113">Microsoft 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="0b4df-114">Vous pouvez en savoir plus sur le gouvernement Microsoft 365 pour les clients du secteur public d' [Office 365](https://products.office.com/government/compare-office-365-government-plans), y compris sur les [conditions d’éligibilité](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="0b4df-114">You can find more information about the Microsoft 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="0b4df-115">La [Description du service fédéral des États-Unis d’Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) décrit les avantages de la plateforme, qui sont centrés sur les exigences en matière de conformité aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="0b4df-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="0b4df-116">Vous souhaiterez peut-être transférer les tableaux d’informations dans la description du service dans un classeur Excel et ajouter deux colonnes : **approprié pour mon organisation y/n** et **répond aux besoins de mon organisation y/n**.</span><span class="sxs-lookup"><span data-stu-id="0b4df-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="0b4df-117">Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0b4df-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="0b4df-119">Points de décision</span><span class="sxs-lookup"><span data-stu-id="0b4df-119">Decision points</span></span>|<ul><li><span data-ttu-id="0b4df-120">Décidez si le service public de Microsoft 365 est approprié pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="0b4df-120">Decide whether Microsoft 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="0b4df-121">Vérifiez que votre organisation répond aux conditions d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="0b4df-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="0b4df-122">Microsoft 365 Government-GCC High est uniquement disponible aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="0b4df-122">Microsoft 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="0b4df-123">Les clients de l’administration non américaine peuvent opter pour un certain nombre de [forfaits Office 365 Government](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="0b4df-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a><span data-ttu-id="0b4df-124">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="0b4df-124">Step 2.</span></span> <span data-ttu-id="0b4df-125">Demander à Microsoft 365 Government-GCC High</span><span class="sxs-lookup"><span data-stu-id="0b4df-125">Apply for Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="0b4df-126">Après avoir décidé que ce service est approprié pour votre organisation, commencez le processus d' [application pour ce service](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="0b4df-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="0b4df-127">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="0b4df-127">Step 3.</span></span> <span data-ttu-id="0b4df-128">Comprendre les principaux paramètres de sécurité par défaut de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0b4df-128">Understand Microsoft 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="0b4df-129">Nous vous conseillons de prendre le temps de vérifier les paramètres de votre [administrateur et de votre sécurité](enable-features-office-365.md) avant de les modifier, et de réfléchir à la conformité avant de modifier les paramètres de sécurité par défaut.</span><span class="sxs-lookup"><span data-stu-id="0b4df-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="0b4df-131">Point de décision</span><span class="sxs-lookup"><span data-stu-id="0b4df-131">Decision point</span></span>|<ul><li><span data-ttu-id="0b4df-132">Déterminez si vous avez besoin de modifier l’un des paramètres de sécurité du service public Microsoft 365 par défaut et de le résoudre pour tout d’abord comprendre l’impact des modifications que vous pourriez apporter.</span><span class="sxs-lookup"><span data-stu-id="0b4df-132">Decide whether you'll need to modify any of the default Microsoft 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a><span data-ttu-id="0b4df-133">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="0b4df-133">Step 4.</span></span> <span data-ttu-id="0b4df-134">Comprenez quelles sont les fonctionnalités d’équipe actuellement disponibles dans Microsoft 365 Government-GCC High</span><span class="sxs-lookup"><span data-stu-id="0b4df-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="0b4df-135">Pour répondre aux besoins de nos clients du cloud public, il existe quelques différences entre les équipes dans Microsoft 365 Government-GCC High et teams dans les offres de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="0b4df-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="0b4df-136">Pour savoir quelles fonctionnalités sont disponibles, consultez le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="0b4df-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="0b4df-137">Description du service Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="0b4df-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="0b4df-138">Étape 5.</span><span class="sxs-lookup"><span data-stu-id="0b4df-138">Step 5.</span></span> <span data-ttu-id="0b4df-139">Plan de gouvernance</span><span class="sxs-lookup"><span data-stu-id="0b4df-139">Plan for governance</span></span>

<span data-ttu-id="0b4df-140">Déterminez vos besoins en matière de gouvernance et comment vous pouvez les répondre.</span><span class="sxs-lookup"><span data-stu-id="0b4df-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="0b4df-141">Pour plus d’informations, voir [plan de gouvernance dans teams](plan-teams-governance.md) .</span><span class="sxs-lookup"><span data-stu-id="0b4df-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="0b4df-142">Point de décision</span><span class="sxs-lookup"><span data-stu-id="0b4df-142">Decision point</span></span> |<ul><li><span data-ttu-id="0b4df-143">Déterminez et documentez vos exigences de gouvernance conformément aux recommandations en [matière de plan de gouvernance dans teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="0b4df-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="0b4df-144">Étape 6.</span><span class="sxs-lookup"><span data-stu-id="0b4df-144">Step 6.</span></span> <span data-ttu-id="0b4df-145">Déploiement d’équipes pour la collaboration</span><span class="sxs-lookup"><span data-stu-id="0b4df-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="0b4df-146">Une fois que vous avez été intégré au service public Microsoft 365, vous pouvez suivre la procédure de déploiement recommandée décrite dans [la rubrique Comment déployer Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0b4df-146">After you've been onboarded to Microsoft 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="0b4df-147">N’hésitez pas à vous engager avec votre adoption et votre équipe de gestion des changements et des champions.</span><span class="sxs-lookup"><span data-stu-id="0b4df-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="0b4df-148">Vous pouvez également utiliser [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour l’intégration du service.</span><span class="sxs-lookup"><span data-stu-id="0b4df-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

