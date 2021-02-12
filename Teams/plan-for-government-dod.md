---
title: Déploiements d’Office 365 Service Public - DoD
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Conseils pour les professionnels de l’informatique en matière de gestion des déploiements d’Office 365 au cours d’entités qui gèrent les données soumises à la réglementation du service public américain (DoD).
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
ms.openlocfilehash: 954eb24cd0d6c79ab3fd30e22521660d2afeb08e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909158"
---
# <a name="plan-for-office-365-government---dod-deployments"></a><span data-ttu-id="6934d-103">Planifier les déploiements d’Office 365 pour les administrations publiques</span><span class="sxs-lookup"><span data-stu-id="6934d-103">Plan for Office 365 Government - DoD deployments</span></span>

<span data-ttu-id="6934d-104">Ces conseils sont adaptés aux professionnels de l’informatique qui conduisent des déploiements d’Office 365 dans des entités gouvernementales fédérale aux États-Unis ou d’autres entités qui gèrent des données soumises à des réglementations gouvernementales et des exigences, où l’utilisation d’Office 365 Secteur Public – DoD est appropriée pour répondre à ces exigences.</span><span class="sxs-lookup"><span data-stu-id="6934d-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="6934d-105">Si votre organisation a déjà satisfait aux conditions d’éligibilité d’Office 365 Service Public – DD et a demandé et accepté dans le programme, vous pouvez ignorer les étapes 1 et 2 et passer directement à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="6934d-105">If your organization has already met the Office 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="6934d-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="6934d-106">Step 1.</span></span> <span data-ttu-id="6934d-107">Déterminer si votre organisation a besoin d’Office 365 Service Public - DoD et satisfait aux conditions d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="6934d-107">Determine whether your organization needs Office 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="6934d-108">L’environnement Office 365 Secteur Public - DoD fournit la conformité avec les exigences du gouvernement américain pour les services cloud.</span><span class="sxs-lookup"><span data-stu-id="6934d-108">The Office 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="6934d-109">En plus de profiter des fonctionnalités d’Office 365, les organisations bénéficient des fonctionnalités suivantes qui sont propres à Office 365 Service Public – DoD :</span><span class="sxs-lookup"><span data-stu-id="6934d-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – DoD:</span></span>

- <span data-ttu-id="6934d-110">Le contenu client de votre organisation est logiquement séparé du contenu des clients dans les services Office 365 commerciaux de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6934d-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="6934d-111">Le contenu client de votre organisation est stocké aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="6934d-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="6934d-112">L’accès au contenu client de votre organisation est limité au personnel Microsoft dont l’écran est limité.</span><span class="sxs-lookup"><span data-stu-id="6934d-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="6934d-113">Office 365 Secteur Public – DoD est conforme aux certifications et aux entreprises requises pour les clients du secteur public américain.</span><span class="sxs-lookup"><span data-stu-id="6934d-113">Office 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="6934d-114">Pour plus d’informations sur l’offre Office 365 Service Public – DoD pour les clients du gouvernement américain, voir les offres [Office 365 Government,](https://products.office.com/government/compare-office-365-government-plans)notamment les conditions [d’éligibilité.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="6934d-114">You can find more information about the Office 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="6934d-115">La [description du service Office 365 pour](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) le gouvernement américain décrit les avantages de la plateforme, qui sont centrés sur les conditions de conformité requises aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="6934d-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="6934d-116">Vous pouvez transférer les tables d’informations de la description du service dans un workbook Excel et ajouter deux colonnes : Pertinentes pour mon organisation **Y/N** et Répondre aux besoins de mon organisation **Y/N.**</span><span class="sxs-lookup"><span data-stu-id="6934d-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="6934d-117">Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6934d-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="6934d-119">Points de décision</span><span class="sxs-lookup"><span data-stu-id="6934d-119">Decision points</span></span>|<ul><li><span data-ttu-id="6934d-120">Déterminez si Office 365 Service Public - DoD est approprié pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6934d-120">Decide whether Office 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="6934d-121">Confirmez que votre organisation répond aux conditions d’éligibilité requises.</span><span class="sxs-lookup"><span data-stu-id="6934d-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="6934d-122">Office 365 Service Public - DoD est disponible uniquement aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="6934d-122">Office 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="6934d-123">Les clients non-us Government peuvent choisir parmi un certain nombre d’plans [Office 365 Secteur Public.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="6934d-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---dod"></a><span data-ttu-id="6934d-124">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="6934d-124">Step 2.</span></span> <span data-ttu-id="6934d-125">S’appliquer à Office 365 Service Public - DoD</span><span class="sxs-lookup"><span data-stu-id="6934d-125">Apply for Office 365 Government - DoD</span></span>

<span data-ttu-id="6934d-126">Ayant décidé que ce service est exact pour votre organisation, commencez le processus de demande [de ce service.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="6934d-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a><span data-ttu-id="6934d-127">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="6934d-127">Step 3.</span></span> <span data-ttu-id="6934d-128">Comprendre Office 365 Service Public - Paramètres de sécurité par défaut d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="6934d-128">Understand Office 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="6934d-129">Nous vous conseillons de prendre le temps de passer en revue soigneusement vos [paramètres](enable-features-office-365.md) d’administration et de sécurité avant de les modifier, et de prendre en compte les conséquences sur la conformité avant de modifier les paramètres de sécurité par défaut.</span><span class="sxs-lookup"><span data-stu-id="6934d-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="6934d-131">Point de décision</span><span class="sxs-lookup"><span data-stu-id="6934d-131">Decision point</span></span>|<ul><li><span data-ttu-id="6934d-132">Décidez si vous devez modifier l’un des paramètres de sécurité Office 365 Service Public - DoD par défaut, en résolvant pour comprendre d’abord l’impact des modifications que vous pourriez apporter.</span><span class="sxs-lookup"><span data-stu-id="6934d-132">Decide whether you'll need to modify any of the default Office 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a><span data-ttu-id="6934d-133">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="6934d-133">Step 4.</span></span> <span data-ttu-id="6934d-134">Comprendre les fonctionnalités Teams actuellement disponibles dans Office 365 Service Public - DoD</span><span class="sxs-lookup"><span data-stu-id="6934d-134">Understand which Teams capabilities are currently available in Office 365 Government - DoD</span></span>

<span data-ttu-id="6934d-135">Pour répondre aux besoins de nos clients cloud du secteur public, il existe certaines différences entre Teams dans Office 365 Secteur Public - DoD et Teams dans les plans d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6934d-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="6934d-136">Consultez le tableau suivant pour voir quelles fonctionnalités sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="6934d-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="6934d-137">Description du service Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6934d-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="6934d-138">Étape 5.</span><span class="sxs-lookup"><span data-stu-id="6934d-138">Step 5.</span></span> <span data-ttu-id="6934d-139">Plan de gouvernance</span><span class="sxs-lookup"><span data-stu-id="6934d-139">Plan for governance</span></span>

<span data-ttu-id="6934d-140">Déterminez vos exigences de gouvernance et la manière dont vous pouvez les respecter.</span><span class="sxs-lookup"><span data-stu-id="6934d-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="6934d-141">Pour plus [d’informations, voir Planifier la gouvernance dans Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="6934d-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="6934d-142">Point de décision</span><span class="sxs-lookup"><span data-stu-id="6934d-142">Decision point</span></span> |<ul><li><span data-ttu-id="6934d-143">Déterminez et consignez vos exigences de gouvernance, en suivant les recommandations [de la politique de gouvernance de Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="6934d-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="6934d-144">Étape 6.</span><span class="sxs-lookup"><span data-stu-id="6934d-144">Step 6.</span></span> <span data-ttu-id="6934d-145">Déployer Teams pour la collaboration</span><span class="sxs-lookup"><span data-stu-id="6934d-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="6934d-146">Après avoir été intégré à Office 365 Service Public – DoD, suivez la voie de déploiement recommandée décrite dans comment déployer [Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6934d-146">After you've been onboarded to Office 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="6934d-147">N’oubliez pas de vous impliquer avec votre équipe Adoption et gestion du changement et les champions Teams.</span><span class="sxs-lookup"><span data-stu-id="6934d-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="6934d-148">Vous pouvez également travailler avec [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour intégrer le service.</span><span class="sxs-lookup"><span data-stu-id="6934d-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="6934d-149">Le client Mac Teams pour les environnements DOD n’est pas encore pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6934d-149">The Mac Teams client for DOD environments is not yet supported.</span></span>
