---
title: Déploiements de Microsoft 365 Government - GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Conseils pour les professionnels de l’informatique en matière de gestion des déploiements Microsoft 365 au cours d’entités qui gèrent les données soumises à la réglementation du gouvernement américain
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: e40f511aedfed2423e04ece74a9c2c7f370acb74
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085608"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="5e248-103">Planifier les déploiements de Microsoft 365 Government - GCC</span><span class="sxs-lookup"><span data-stu-id="5e248-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="5e248-104">Ces conseils sont adaptés aux professionnels de l’informatique qui sont responsables des déploiements de Microsoft 365 dans l’administration fédérale, l’État, le pays, le gouvernement local ou d’autres entités qui gèrent des données qui sont soumises aux réglementations gouvernementales et aux exigences, où l’utilisation de Microsoft 365 Government - GCC convient pour répondre à ces exigences.</span><span class="sxs-lookup"><span data-stu-id="5e248-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="5e248-105">À partir du 26 mars 2020 : Ne manquez pas notre guide de démarrage rapide téléchargeable [pour le GCC.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)</span><span class="sxs-lookup"><span data-stu-id="5e248-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e248-106">Microsoft Teams connaît un pic considérable dans les appels en ligne et les conférences audio/vidéo en raison du coronavirus (COVID-19).</span><span class="sxs-lookup"><span data-stu-id="5e248-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="5e248-107">En réponse à l’augmentation immédiate du nombre d’appels et à la continuité des appels et à la disponibilité, Microsoft autorise les serveurs audio/vidéo de Microsoft Teams GCC à tirer parti de la capacité de traitement de nos centres de données commerciaux, ainsi que de nos centres de données du secteur public.</span><span class="sxs-lookup"><span data-stu-id="5e248-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="5e248-108">Ces serveurs audio/vidéo résident dans des serveurs limites du haut de Microsoft Azure FedRAMP aux États-Unis et ne stockent aucun contenu client.</span><span class="sxs-lookup"><span data-stu-id="5e248-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="5e248-109">Toutefois, ces serveurs traitent l’audio et la vidéo pour les appels et les conférences et fonctionnent sous l’activité de notre équipe commerciale pendant cette période temporaire.</span><span class="sxs-lookup"><span data-stu-id="5e248-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="5e248-110">Le personnel qualifié et screened surveille ces serveurs pour l’accès potentiel aux données client en examine les éventuelles connexions interactives à ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="5e248-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="5e248-111">Le personnel qualifié répond aux exigences du GCC en matière d’accès au contenu du client.</span><span class="sxs-lookup"><span data-stu-id="5e248-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="5e248-112">Pour plus d’informations sur le filtrage des exigences, voir la [description du service GCC.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)</span><span class="sxs-lookup"><span data-stu-id="5e248-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="5e248-113">Nous vous remercions pour votre soutien car nous prenons des mesures pour nous assurer que nos services restent disponibles et fiables dans ces moments extraordinaires.</span><span class="sxs-lookup"><span data-stu-id="5e248-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="5e248-114">Si votre organisation a déjà satisfait aux conditions d’éligibilité de Microsoft 365 Government - GCC et a demandé et accepté le programme, vous pouvez ignorer les étapes 1 et 2 et passer directement à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="5e248-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="5e248-115">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="5e248-115">Step 1.</span></span> <span data-ttu-id="5e248-116">Déterminez si votre organisation a besoin de Microsoft 365 Government - GCC et répond aux conditions d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="5e248-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="5e248-117">L’environnement Microsoft 365 Government - GCC fournit la conformité avec les exigences du gouvernement américain pour les services cloud, notamment FedRAMP Modéré, et des exigences de justice pénale et de systèmes d’information fiscales fédéraux (types de données CJI et FTI).</span><span class="sxs-lookup"><span data-stu-id="5e248-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="5e248-118">En plus de profiter des fonctionnalités de Microsoft 365, les organisations bénéficient des fonctionnalités suivantes qui sont propres à Microsoft 365 Government - GCC :</span><span class="sxs-lookup"><span data-stu-id="5e248-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="5e248-119">Le contenu client de votre organisation est logiquement isolé du contenu client dans les services Microsoft 365 commerciaux de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5e248-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="5e248-120">Le contenu client de votre organisation est stocké aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="5e248-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="5e248-121">L’accès au contenu client de votre organisation est limité au personnel Microsoft dont l’écran est limité.</span><span class="sxs-lookup"><span data-stu-id="5e248-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="5e248-122">Microsoft 365 Secteur Public - GCC est conforme aux certifications et aux entreprises requises pour les clients du secteur public américain.</span><span class="sxs-lookup"><span data-stu-id="5e248-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="5e248-123">Vous pouvez trouver plus d’informations sur l’offre Microsoft 365 Government - GCC pour les clients du gouvernement américain sur les offres [Microsoft 365 Government,](https://products.office.com/government/compare-office-365-government-plans)y compris sur les conditions [d’éligibilité.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="5e248-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="5e248-124">La [description du service Public Microsoft 365 aux](https://technet.microsoft.com/library/mt774581.aspx) États-Unis décrit les avantages de la plateforme, qui sont centrés autour des conditions de conformité requises aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="5e248-124">The [Microsoft 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="5e248-125">Vous pouvez transférer les tables d’informations de la description du service dans un workbook Excel et ajouter deux colonnes : Pertinentes pour mon organisation **Y/N** et Répondre aux besoins de mon organisation **Y/N.**</span><span class="sxs-lookup"><span data-stu-id="5e248-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="5e248-126">Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5e248-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5e248-128">Points de décision</span><span class="sxs-lookup"><span data-stu-id="5e248-128">Decision points</span></span>|<ul><li><span data-ttu-id="5e248-129">Décidez si Microsoft 365 Government - GCC est approprié pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5e248-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="5e248-130">Confirmez que votre organisation répond aux conditions d’éligibilité requises.</span><span class="sxs-lookup"><span data-stu-id="5e248-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="5e248-131">Microsoft 365 Government - GCC est disponible uniquement aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="5e248-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="5e248-132">Les clients non-us Government peuvent choisir parmi un certain nombre de [plans Microsoft 365 Secteur Secteur.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="5e248-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="5e248-133">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="5e248-133">Step 2.</span></span> <span data-ttu-id="5e248-134">S’appliquer à Microsoft 365 Government - GCC</span><span class="sxs-lookup"><span data-stu-id="5e248-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="5e248-135">Ayant décidé que ce service est exact pour votre organisation, commencez le processus de demande [de ce service ici.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="5e248-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="5e248-136">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="5e248-136">Step 3.</span></span> <span data-ttu-id="5e248-137">Comprendre les paramètres de sécurité par défaut de Microsoft 365 Government - GCC.</span><span class="sxs-lookup"><span data-stu-id="5e248-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="5e248-138">Nous vous conseillons de prendre le temps de passer en revue soigneusement vos [paramètres](enable-features-office-365.md) d’administration et de sécurité avant de les modifier, et de prendre en compte les conséquences sur la conformité avant de modifier les paramètres de sécurité par défaut.</span><span class="sxs-lookup"><span data-stu-id="5e248-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5e248-140">Point de décision</span><span class="sxs-lookup"><span data-stu-id="5e248-140">Decision point</span></span>|<ul><li><span data-ttu-id="5e248-141">Décidez si vous allez modifier les paramètres de sécurité par défaut de Microsoft 365 Government - GCC, en résolvant pour comprendre d’abord l’impact des modifications que vous pourriez apporter.</span><span class="sxs-lookup"><span data-stu-id="5e248-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="5e248-142">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="5e248-142">Step 4.</span></span> <span data-ttu-id="5e248-143">Comprendre les fonctionnalités actuellement indisponibles ou désactivées par défaut.</span><span class="sxs-lookup"><span data-stu-id="5e248-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="5e248-144">Pour répondre aux besoins de nos clients cloud du secteur, il existe quelques différences entre les plans Microsoft 365 Secteur, Cloud et Entreprise.</span><span class="sxs-lookup"><span data-stu-id="5e248-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="5e248-145">Consultez le tableau suivant pour voir quelles fonctionnalités sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="5e248-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="5e248-146">Description du service Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e248-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="5e248-147">Une fois que d’autres charges de travail sont entièrement disponibles dans le cloud gcc, elles deviennent disponibles dans Teams une fois tout le travail d’intégration supplémentaire terminé.</span><span class="sxs-lookup"><span data-stu-id="5e248-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5e248-149">Point de décision</span><span class="sxs-lookup"><span data-stu-id="5e248-149">Decision point</span></span>|<ul><li><span data-ttu-id="5e248-150">Déterminez si l’ensemble des fonctionnalités de Teams répond aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5e248-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="5e248-151">Étape 5.</span><span class="sxs-lookup"><span data-stu-id="5e248-151">Step 5.</span></span> <span data-ttu-id="5e248-152">Plan de gouvernance</span><span class="sxs-lookup"><span data-stu-id="5e248-152">Plan for governance</span></span>

<span data-ttu-id="5e248-153">Déterminez vos exigences de gouvernance et la manière dont vous pouvez les respecter.</span><span class="sxs-lookup"><span data-stu-id="5e248-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="5e248-154">Pour plus [d’informations, voir Planifier la gouvernance dans Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="5e248-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5e248-156">Point de décision</span><span class="sxs-lookup"><span data-stu-id="5e248-156">Decision point</span></span>|<ul><li><span data-ttu-id="5e248-157">Déterminez et consignez vos exigences de gouvernance, en suivant les recommandations de la politique [de gouvernance de Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="5e248-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="5e248-158">Étape 6.</span><span class="sxs-lookup"><span data-stu-id="5e248-158">Step 6.</span></span> <span data-ttu-id="5e248-159">Déployer Teams pour la collaboration</span><span class="sxs-lookup"><span data-stu-id="5e248-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="5e248-160">Après avoir été intégré à Microsoft 365 Government – GCC, suivez la voie de déploiement recommandée décrite dans comment déployer [Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="5e248-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="5e248-161">N’oubliez pas de vous impliquer avec votre équipe Adoption et gestion du changement et les champions Teams.</span><span class="sxs-lookup"><span data-stu-id="5e248-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="5e248-162">Vous pouvez également travailler avec [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour intégrer le service.</span><span class="sxs-lookup"><span data-stu-id="5e248-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="5e248-163">Étape 7.</span><span class="sxs-lookup"><span data-stu-id="5e248-163">Step 7.</span></span> <span data-ttu-id="5e248-164">Déployer Teams pour les réunions et la voix</span><span class="sxs-lookup"><span data-stu-id="5e248-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="5e248-165">C’est également le moment idéal pour utiliser Teams avec l’ensemble des parties prenantes pour commencer à planifier le déploiement de réunions et de [fonctionnalités vocales cloud.](cloud-voice-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="5e248-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

