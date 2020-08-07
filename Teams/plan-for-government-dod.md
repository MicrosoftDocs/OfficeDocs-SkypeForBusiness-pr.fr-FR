---
title: Office 365 gouvernementale-déploiements DoD
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Conseils destinés aux professionnels de l’informatique pour piloter les déploiements d’Office 365 dans les entités qui gèrent les données soumises aux règlements du ministère des États-Unis.
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
ms.openlocfilehash: 04b0833f453ffac96e9fe2c9cef1b0f2a0797ca2
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581255"
---
# <a name="plan-for-office-365-government---dod-deployments"></a><span data-ttu-id="2490d-103">Plan pour les déploiements Office 365 Government-DoD</span><span class="sxs-lookup"><span data-stu-id="2490d-103">Plan for Office 365 Government - DoD deployments</span></span>

<span data-ttu-id="2490d-104">Ce guide est destiné aux professionnels de l’informatique qui pilotent des déploiements d’Office 365 dans les organisations du secteur public américain ou d’autres entités qui gèrent les données soumises à des réglementations et exigences gouvernementales, lorsque l’utilisation d’Office 365 Government-DoD est appropriée pour ces exigences.</span><span class="sxs-lookup"><span data-stu-id="2490d-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="2490d-105">Si votre organisation a déjà satisfait au service public d’Office 365, et qu’elle a été acceptée pour le programme, vous pouvez passer directement à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="2490d-105">If your organization has already met the Office 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="2490d-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="2490d-106">Step 1.</span></span> <span data-ttu-id="2490d-107">Déterminez si votre organisation a besoin d’Office 365 Government-DoD et répond aux exigences d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="2490d-107">Determine whether your organization needs Office 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="2490d-108">L’environnement Office 365 Government-DoD fournit une conformité avec les exigences de l’administration américaine pour les services Cloud.</span><span class="sxs-lookup"><span data-stu-id="2490d-108">The Office 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="2490d-109">En plus des fonctionnalités et des fonctionnalités d’Office 365, les organisations profitent des fonctionnalités suivantes qui sont propres à Office 365 secteur public – DoD :</span><span class="sxs-lookup"><span data-stu-id="2490d-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – DoD:</span></span>

- <span data-ttu-id="2490d-110">Le contenu du client de votre organisation est séparé de manière logique du contenu client dans les services Office 365 commerciaux de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2490d-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="2490d-111">Le contenu du client de votre organisation est enregistré aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="2490d-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="2490d-112">L’accès au contenu du client de votre organisation est limité aux membres du personnel de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2490d-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="2490d-113">Office 365 Government-DoD est conforme aux certifications et acversions nécessaires pour les clients du secteur public américain.</span><span class="sxs-lookup"><span data-stu-id="2490d-113">Office 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="2490d-114">Vous trouverez des informations supplémentaires sur l’offre Office 365 Government-DoD pour les clients du secteur public dans [office 365 Government](https://products.office.com/government/compare-office-365-government-plans), y compris sur les [conditions d’éligibilité](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="2490d-114">You can find more information about the Office 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="2490d-115">La [Description du service fédéral des États-Unis d’Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) décrit les avantages de la plateforme, qui sont centrés sur les exigences en matière de conformité aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="2490d-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="2490d-116">Vous souhaiterez peut-être transférer les tableaux d’informations dans la description du service dans un classeur Excel et ajouter deux colonnes : **approprié pour mon organisation y/n** et **répond aux besoins de mon organisation y/n**.</span><span class="sxs-lookup"><span data-stu-id="2490d-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="2490d-117">Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2490d-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2490d-119">Points de décision</span><span class="sxs-lookup"><span data-stu-id="2490d-119">Decision points</span></span>|<ul><li><span data-ttu-id="2490d-120">Déterminez si Office 365 Government-DoD est approprié pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2490d-120">Decide whether Office 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="2490d-121">Vérifiez que votre organisation répond aux conditions d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="2490d-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="2490d-122">Office 365 Government-DoD est uniquement disponible aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="2490d-122">Office 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="2490d-123">Les clients de l’administration non américaine peuvent opter pour un certain nombre de [forfaits Office 365 Government](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="2490d-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---dod"></a><span data-ttu-id="2490d-124">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="2490d-124">Step 2.</span></span> <span data-ttu-id="2490d-125">Demander à Office 365 pour le gouvernement-DoD</span><span class="sxs-lookup"><span data-stu-id="2490d-125">Apply for Office 365 Government - DoD</span></span>

<span data-ttu-id="2490d-126">Après avoir décidé que ce service est approprié pour votre organisation, commencez le processus d' [application pour ce service](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="2490d-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a><span data-ttu-id="2490d-127">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="2490d-127">Step 3.</span></span> <span data-ttu-id="2490d-128">Comprendre les paramètres de sécurité par défaut d’Office 365 pour le gouvernement-DoD.</span><span class="sxs-lookup"><span data-stu-id="2490d-128">Understand Office 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="2490d-129">Nous vous conseillons de prendre le temps de vérifier les paramètres de votre [administrateur et de votre sécurité](enable-features-office-365.md) avant de les modifier, et de réfléchir à la conformité avant de modifier les paramètres de sécurité par défaut.</span><span class="sxs-lookup"><span data-stu-id="2490d-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2490d-131">Point de décision</span><span class="sxs-lookup"><span data-stu-id="2490d-131">Decision point</span></span>|<ul><li><span data-ttu-id="2490d-132">Déterminez si vous avez besoin de modifier les paramètres de sécurité par défaut du service public-DoD Office 365, puis de le résoudre pour tout d’abord comprendre l’impact des modifications que vous pourriez apporter.</span><span class="sxs-lookup"><span data-stu-id="2490d-132">Decide whether you'll need to modify any of the default Office 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a><span data-ttu-id="2490d-133">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="2490d-133">Step 4.</span></span> <span data-ttu-id="2490d-134">Découvrir les fonctionnalités d’équipe actuellement disponibles dans Office 365 Government-DoD</span><span class="sxs-lookup"><span data-stu-id="2490d-134">Understand which Teams capabilities are currently available in Office 365 Government - DoD</span></span>

<span data-ttu-id="2490d-135">Pour répondre aux besoins de nos clients du cloud public, il existe quelques différences entre teams dans Office 365 Government-DoD et équipes dans les plans de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="2490d-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="2490d-136">Pour savoir quelles fonctionnalités sont disponibles, consultez le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="2490d-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="2490d-137">Description du service Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="2490d-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="2490d-138">Étape 5.</span><span class="sxs-lookup"><span data-stu-id="2490d-138">Step 5.</span></span> <span data-ttu-id="2490d-139">Plan de gouvernance</span><span class="sxs-lookup"><span data-stu-id="2490d-139">Plan for governance</span></span>

<span data-ttu-id="2490d-140">Déterminez vos besoins en matière de gouvernance et comment vous pouvez les répondre.</span><span class="sxs-lookup"><span data-stu-id="2490d-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="2490d-141">Pour plus d’informations, voir [plan de gouvernance dans teams](plan-teams-governance.md) .</span><span class="sxs-lookup"><span data-stu-id="2490d-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="2490d-142">Point de décision</span><span class="sxs-lookup"><span data-stu-id="2490d-142">Decision point</span></span> |<ul><li><span data-ttu-id="2490d-143">Déterminez et documentez vos exigences de gouvernance conformément aux recommandations en [matière de plan de gouvernance dans teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="2490d-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="2490d-144">Étape 6.</span><span class="sxs-lookup"><span data-stu-id="2490d-144">Step 6.</span></span> <span data-ttu-id="2490d-145">Déploiement d’équipes pour la collaboration</span><span class="sxs-lookup"><span data-stu-id="2490d-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="2490d-146">Après avoir été intégré à Office 365 Government-DoD, suivez le chemin de déploiement recommandé décrit dans [la rubrique Comment déployer Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2490d-146">After you've been onboarded to Office 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="2490d-147">N’hésitez pas à vous engager avec votre adoption et votre équipe de gestion des changements et des champions.</span><span class="sxs-lookup"><span data-stu-id="2490d-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="2490d-148">Vous pouvez également utiliser [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour l’intégration du service.</span><span class="sxs-lookup"><span data-stu-id="2490d-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
