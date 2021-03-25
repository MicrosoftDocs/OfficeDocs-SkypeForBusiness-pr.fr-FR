---
title: Mise à niveau de Skype Entreprise local vers Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez comment faire passer votre organisation à Microsoft Teams à partir d’un déploiement local de Skype Entreprise.
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115552"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="196da-103">Mettre à niveau à partir d’un déploiement Skype Entreprise local vers Teams</span><span class="sxs-lookup"><span data-stu-id="196da-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="196da-104">![Étapes du parcours de mise à niveau, avec l’accentuation sur l’étape déploiement et implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accentuation sur l’étape déploiement et implémentation")</span><span class="sxs-lookup"><span data-stu-id="196da-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="196da-105">Cet article fait partie de la phase déploiement et implémentation de votre parcours vers la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="196da-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="196da-106">Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="196da-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="196da-107">Demandez aux parties prenantes de votre projet</span><span class="sxs-lookup"><span data-stu-id="196da-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="196da-108">Étendue définie de votre projet</span><span class="sxs-lookup"><span data-stu-id="196da-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="196da-109">Coexistence et interopérabilité comprises de Skype Entreprise et Teams</span><span class="sxs-lookup"><span data-stu-id="196da-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="196da-110">Nous avons choisi votre chemin de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="196da-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="196da-111">Préparé votre environnement</span><span class="sxs-lookup"><span data-stu-id="196da-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="196da-112">Préparé votre organisation</span><span class="sxs-lookup"><span data-stu-id="196da-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="196da-113">Conduite d’un pilote</span><span class="sxs-lookup"><span data-stu-id="196da-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="196da-114">Si vous avez déployé Skype Entreprise ou Microsoft Lync en local et que votre organisation souhaite mettre à niveau vers Microsoft Teams de manière sélective (à l’aide de plusieurs modes de coexistence), suivez les instructions de cet article.</span><span class="sxs-lookup"><span data-stu-id="196da-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="196da-115">Étape 1 : déployer la connectivité hybride</span><span class="sxs-lookup"><span data-stu-id="196da-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="196da-116">La principale condition préalable pour la mise à niveau de vos utilisateurs vers Teams consiste à déployer la connectivité hybride.</span><span class="sxs-lookup"><span data-stu-id="196da-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="196da-117">Pour plus d’informations, [voir Déployer la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="196da-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="196da-118">Étape 2 : mettre en œuvre le chemin de mise à niveau que vous avez choisi pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="196da-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="196da-119">Une fois que vous avez terminé votre configuration hybride, vous pouvez planifier le déplacement de vos utilisateurs vers Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="196da-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="196da-120">Pour plus d’informations, consultez :</span><span class="sxs-lookup"><span data-stu-id="196da-120">For more information, see:</span></span>

- <span data-ttu-id="196da-121">[TeamsUpgradePolicy : gestion de la migration et de la coexistence.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="196da-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="196da-122">[Déplacer les utilisateurs du site vers Skype Entreprise Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="196da-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="196da-123">Mise à niveau de Phone System et Teams</span><span class="sxs-lookup"><span data-stu-id="196da-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="196da-124">La transition des systèmes téléphoniques locaux vers Teams vous permet de tirer parti du routage direct du système téléphonique (« Routage direct ») ou des plans d’appels fournis par Microsoft pour Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="196da-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="196da-125">Si vous n’utilisez pas de forfaits d’appels, vous devez transition votre déploiement vocal d’entreprise vers le routage direct du système téléphonique dans le cadre de votre mise à niveau vers Teams.</span><span class="sxs-lookup"><span data-stu-id="196da-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="196da-126">Pour plus d’informations, voir [d’autres considérations concernant le routage direct du](./direct-routing-landing-page.md)système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="196da-126">For more information, see [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span> <span data-ttu-id="196da-127">Si vous envisagez d’utiliser des forfaits d’appels, consultez nos recommandations pour le transfert de vos numéros [de téléphone vers Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="196da-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>