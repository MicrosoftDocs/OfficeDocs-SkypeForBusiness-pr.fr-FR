---
title: Office 365 gouvernementale-déploiements de GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Conseils destinés aux professionnels de l’informatique pour piloter les déploiements d' 365 Office
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
ms.openlocfilehash: 2fb916b30a26694debf8d699fc05cc3fcc8c8c77
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581245"
---
# <a name="plan-for-office-365-government---gcc-deployments"></a><span data-ttu-id="44bf3-103">Plan pour Office 365 Government-déploiements de GCC</span><span class="sxs-lookup"><span data-stu-id="44bf3-103">Plan for Office 365 Government - GCC deployments</span></span>

<span data-ttu-id="44bf3-104">Ce guide est destiné aux professionnels de l’informatique qui pilotent des déploiements d’Office 365 aux États-Unis, aux États-Unis, aux États-Unis, tribal ou d’autres entités du gouvernement territorial ou d’autres entités qui gèrent les données soumises aux lois et exigences gouvernementales, lorsque l’utilisation d’Office 365 Government-GCC est appropriée pour respecter ces exigences.</span><span class="sxs-lookup"><span data-stu-id="44bf3-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="44bf3-105">Nouveau 26 mars, 2020 : ne manquez pas notre [Guide de démarrage rapide](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)téléchargeable pour la mise en route de GCC.</span><span class="sxs-lookup"><span data-stu-id="44bf3-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44bf3-106">Microsoft teams est confronté à un énorme pic dans les appels en ligne et les conférences audio/vidéo à l’aide de coronavirus (COVID-19) Pandemic.</span><span class="sxs-lookup"><span data-stu-id="44bf3-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="44bf3-107">En réponse à une augmentation sans précédent des appels et à des fins de continuité et de disponibilité, Microsoft est en mesure de faire en sorte que les serveurs de contenus audio et vidéo Microsoft teams se chargent de la capacité de traitement de nos centres de données commerciaux et de nos centres de données du secteur public.</span><span class="sxs-lookup"><span data-stu-id="44bf3-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="44bf3-108">Ces serveurs audio/vidéo résident dans les serveurs de limite d’acforte accréditation Microsoft Azure FedRAMP aux États-Unis et ne stockent aucun contenu de client.</span><span class="sxs-lookup"><span data-stu-id="44bf3-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="44bf3-109">Toutefois, ces serveurs traitent l’audio et la vidéo pour les appels et les conférences et sont soumis à la même équipe commerciale pendant cette période intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="44bf3-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="44bf3-110">Les membres qualifiés et dotés d’une capture d’écran analysent ces serveurs pour un accès potentiel aux données du client en passant en revue les éléments de journal interactifs de ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="44bf3-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="44bf3-111">Le personnel qualifié répond à la configuration requise pour l’accès au contenu du client.</span><span class="sxs-lookup"><span data-stu-id="44bf3-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="44bf3-112">Pour plus d’informations sur la configuration requise pour le filtrage, voir la [Description du service GCC](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span><span class="sxs-lookup"><span data-stu-id="44bf3-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="44bf3-113">Nous vous remercions d’avoir pris le temps de nous assurer que nos services restent disponibles et fiables dans ces temps exceptionnels.</span><span class="sxs-lookup"><span data-stu-id="44bf3-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="44bf3-114">Si votre organisation a déjà satisfait au service public d’Office 365, et qu’elle l’a appliquée et qu’elle a été acceptée dans le programme, vous pouvez passer directement à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="44bf3-114">If your organization has already met the Office 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="44bf3-115">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="44bf3-115">Step 1.</span></span> <span data-ttu-id="44bf3-116">Déterminez si votre organisation a besoin d’Office 365 Government-GCC et répond aux exigences d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="44bf3-116">Determine whether your organization needs Office 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="44bf3-117">L’environnement Office 365 Government-GCC fournit une conformité aux exigences de l’administration américaine pour les services de Cloud Computing, y compris le FedRAMP modéré et la configuration requise pour les systèmes de données CJI et FTI.</span><span class="sxs-lookup"><span data-stu-id="44bf3-117">The Office 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="44bf3-118">Outre les fonctionnalités et les fonctionnalités d’Office 365, les organisations disposent des fonctionnalités suivantes qui sont propres à Office 365 Government :</span><span class="sxs-lookup"><span data-stu-id="44bf3-118">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government - GCC:</span></span>

-   <span data-ttu-id="44bf3-119">Le contenu du client de votre organisation est séparé de manière logique du contenu client dans les services Office 365 commerciaux de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44bf3-119">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="44bf3-120">Le contenu du client de votre organisation est enregistré aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="44bf3-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="44bf3-121">L’accès au contenu du client de votre organisation est limité aux membres du personnel de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44bf3-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="44bf3-122">Office 365 Government-GCC est conforme aux certifications et aux accréditations requises pour les clients du secteur public américain.</span><span class="sxs-lookup"><span data-stu-id="44bf3-122">Office 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="44bf3-123">Vous trouverez des informations supplémentaires sur l’offre Office 365 Government-GCC pour les clients du secteur public dans [office 365 Government](https://products.office.com/government/compare-office-365-government-plans) [.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="44bf3-123">You can find more information about the Office 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="44bf3-124">La [Description du service fédéral des États-Unis d’Office 365](https://technet.microsoft.com/library/mt774581.aspx) décrit les avantages de la plateforme, qui sont centrés sur les exigences en matière de conformité aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="44bf3-124">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="44bf3-125">Vous souhaiterez peut-être transférer les tableaux d’informations dans la description du service dans un classeur Excel et ajouter deux colonnes : **approprié pour mon organisation y/n** et **répond aux besoins de mon organisation y/n**.</span><span class="sxs-lookup"><span data-stu-id="44bf3-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="44bf3-126">Vous pouvez ensuite consulter cette liste avec vos collègues pour vérifier que ce service répond aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="44bf3-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="44bf3-128">Points de décision</span><span class="sxs-lookup"><span data-stu-id="44bf3-128">Decision points</span></span>|<ul><li><span data-ttu-id="44bf3-129">Déterminez si Office 365 Government-GCC est approprié pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="44bf3-129">Decide whether Office 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="44bf3-130">Vérifiez que votre organisation répond aux conditions d’éligibilité.</span><span class="sxs-lookup"><span data-stu-id="44bf3-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="44bf3-131">Office 365 Government-GCC est uniquement disponible aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="44bf3-131">Office 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="44bf3-132">Les clients de l’administration non américaine peuvent opter pour un certain nombre de [forfaits Office 365 Government](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="44bf3-132">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-office-365-government---gcc"></a><span data-ttu-id="44bf3-133">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="44bf3-133">Step 2.</span></span> <span data-ttu-id="44bf3-134">Demander à Office 365 Government-GCC</span><span class="sxs-lookup"><span data-stu-id="44bf3-134">Apply for Office 365 Government - GCC</span></span>

<span data-ttu-id="44bf3-135">Après avoir décidé que ce service est approprié pour votre organisation, commencez le processus d' [application de ce service ici](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="44bf3-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-office-365-government---gcc-default-security-settings"></a><span data-ttu-id="44bf3-136">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="44bf3-136">Step 3.</span></span> <span data-ttu-id="44bf3-137">Comprendre le gouvernement d’Office 365-paramètres de sécurité par défaut de GCC.</span><span class="sxs-lookup"><span data-stu-id="44bf3-137">Understand Office 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="44bf3-138">Nous vous conseillons de prendre le temps de vérifier les paramètres de votre [administrateur et de votre sécurité](enable-features-office-365.md) avant de les modifier, et de réfléchir à la conformité avant de modifier les paramètres de sécurité par défaut.</span><span class="sxs-lookup"><span data-stu-id="44bf3-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="44bf3-140">Point de décision</span><span class="sxs-lookup"><span data-stu-id="44bf3-140">Decision point</span></span>|<ul><li><span data-ttu-id="44bf3-141">Déterminez si vous souhaitez modifier l’un des paramètres de sécurité par défaut du service d’administration de la sécurité d’Office 365, puis résolvez les problèmes liés aux modifications que vous pourriez apporter.</span><span class="sxs-lookup"><span data-stu-id="44bf3-141">Decide whether you'll modify any of the default Office 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="44bf3-142">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="44bf3-142">Step 4.</span></span> <span data-ttu-id="44bf3-143">Comprenez quelles fonctionnalités sont actuellement indisponibles ou désactivées par défaut.</span><span class="sxs-lookup"><span data-stu-id="44bf3-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="44bf3-144">Pour répondre aux besoins de nos clients du cloud public, il existe quelques différences entre le gouvernement d’Office 365 et les plans de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="44bf3-144">To accommodate the requirements of our government cloud customers, there are some differences between Office 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="44bf3-145">Pour savoir quelles fonctionnalités sont disponibles, consultez le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="44bf3-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="44bf3-146">Description du service Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="44bf3-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="44bf3-147">Une fois les autres charges de travail entièrement disponibles dans le Cloud de GCC, celles-ci deviennent disponibles dans teams lorsque la totalité du travail d’intégration supplémentaire est effectuée.</span><span class="sxs-lookup"><span data-stu-id="44bf3-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="44bf3-149">Point de décision</span><span class="sxs-lookup"><span data-stu-id="44bf3-149">Decision point</span></span>|<ul><li><span data-ttu-id="44bf3-150">Déterminez si l’ensemble des fonctionnalités d’équipe répond aux besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="44bf3-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="44bf3-151">Étape 5.</span><span class="sxs-lookup"><span data-stu-id="44bf3-151">Step 5.</span></span> <span data-ttu-id="44bf3-152">Plan de gouvernance</span><span class="sxs-lookup"><span data-stu-id="44bf3-152">Plan for governance</span></span>

<span data-ttu-id="44bf3-153">Déterminez vos besoins en matière de gouvernance et comment vous pouvez les répondre.</span><span class="sxs-lookup"><span data-stu-id="44bf3-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="44bf3-154">Pour plus d’informations, voir [plan de gouvernance dans teams](plan-teams-governance.md) .</span><span class="sxs-lookup"><span data-stu-id="44bf3-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="44bf3-156">Point de décision</span><span class="sxs-lookup"><span data-stu-id="44bf3-156">Decision point</span></span>|<ul><li><span data-ttu-id="44bf3-157">Déterminez et documentez vos exigences de gouvernance conformément aux recommandations en [matière de plan de gouvernance dans teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="44bf3-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="44bf3-158">Étape 6.</span><span class="sxs-lookup"><span data-stu-id="44bf3-158">Step 6.</span></span> <span data-ttu-id="44bf3-159">Déploiement d’équipes pour la collaboration</span><span class="sxs-lookup"><span data-stu-id="44bf3-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="44bf3-160">Une fois que vous avez été intégré au service public d’Office 365, vous pouvez suivre la procédure de déploiement recommandée décrite dans [la rubrique Comment déployer Microsoft teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="44bf3-160">After you've been onboarded to Office 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="44bf3-161">N’hésitez pas à vous engager avec votre adoption et votre équipe de gestion des changements et des champions.</span><span class="sxs-lookup"><span data-stu-id="44bf3-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="44bf3-162">Vous pouvez également utiliser [FastTrack](https://www.microsoft.com/fasttrack) ou le partenaire que vous avez choisi pour l’intégration du service.</span><span class="sxs-lookup"><span data-stu-id="44bf3-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="44bf3-163">Étape 7.</span><span class="sxs-lookup"><span data-stu-id="44bf3-163">Step 7.</span></span> <span data-ttu-id="44bf3-164">Déploiement d’équipes pour les réunions et la voix</span><span class="sxs-lookup"><span data-stu-id="44bf3-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="44bf3-165">C’est également le moment idéal pour organiser des réunions et des [fonctionnalités vocales](cloud-voice-deployment.md)dans le Cloud et commencer à utiliser Teams.</span><span class="sxs-lookup"><span data-stu-id="44bf3-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

