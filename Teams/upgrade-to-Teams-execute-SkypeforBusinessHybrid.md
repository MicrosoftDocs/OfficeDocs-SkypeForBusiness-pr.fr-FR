---
title: Mettre à niveau le déploiement hybride de Skype entreprise vers teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez comment mettre à niveau votre organisation vers Microsoft teams à partir d’un déploiement hybride Skype entreprise.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9cc76313bb65a79241e26ab70a38d8698f27e7c
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523437"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="3404d-103">Mise à niveau d’un déploiement hybride Skype entreprise vers teams</span><span class="sxs-lookup"><span data-stu-id="3404d-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="3404d-104">![Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de déploiement et d’implémentation")</span><span class="sxs-lookup"><span data-stu-id="3404d-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="3404d-105">Cet article fait partie de l’étape de déploiement et d’implémentation de votre parcours de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="3404d-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="3404d-106">Avant de continuer, confirmez que vous avez terminé les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="3404d-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="3404d-107">Inscription des parties prenantes du projet</span><span class="sxs-lookup"><span data-stu-id="3404d-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="3404d-108">Définition de l’objectif de votre projet</span><span class="sxs-lookup"><span data-stu-id="3404d-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="3404d-109">Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes</span><span class="sxs-lookup"><span data-stu-id="3404d-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="3404d-110">Choix de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="3404d-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="3404d-111">Préparé votre environnement</span><span class="sxs-lookup"><span data-stu-id="3404d-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="3404d-112">Préparé votre organisation</span><span class="sxs-lookup"><span data-stu-id="3404d-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="3404d-113">A mené une pilote</span><span class="sxs-lookup"><span data-stu-id="3404d-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="3404d-114">Suivez les recommandations de cet article si vous avez déployé Skype entreprise ou Microsoft Lync en local et l’avez configuré dans un déploiement hybride avec votre organisation Office 365 et que votre organisation souhaite effectuer une mise à niveau vers des équipes de manière sélective, à l’aide de plusieurs modes de coexistence, ou tout-en-un.</span><span class="sxs-lookup"><span data-stu-id="3404d-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="3404d-115">Pour chaque mise à niveau, vous devez déplacer vos utilisateurs vers Skype entreprise Online (s’ils ne sont pas encore hébergés en ligne), puis leur affecter le mode de coexistence et de mise à niveau appropriés.</span><span class="sxs-lookup"><span data-stu-id="3404d-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="3404d-116">Étape 1 : déplacer des utilisateurs vers Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3404d-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="3404d-117">Cette étape s’applique aux utilisateurs actuellement hébergés sur site.</span><span class="sxs-lookup"><span data-stu-id="3404d-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="3404d-118">Pour plus d’informations sur le déplacement de ces utilisateurs dans Skype entreprise Online, reportez-vous à la rubrique [déplacer des utilisateurs de local vers Skype entreprise Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="3404d-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="3404d-119">Étape 2 : affecter une coexistence et un mode de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="3404d-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="3404d-120">Après avoir déplacé vos utilisateurs vers Skype entreprise Online, vous pouvez leur affecter le mode de coexistence approprié en fonction du parcours de mise à niveau choisi par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3404d-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="3404d-121">Pour plus d’informations, reportez-vous à [définition de votre coexistence et de vos paramètres de mise à](https://aka.ms/SkypeToTeams-SetCoexistence) [TeamsUpgradePolicy : gestion de la migration et de la coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="3404d-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="3404d-122">Avec Skype entreprise Server 2019 et une prochaine mise à jour cumulative de Skype entreprise Server 2015, vous serez en mesure de passer à l’étape 1 (déplacer les utilisateurs vers Skype entreprise Online) et étape 2 (mettre à niveau les utilisateurs vers Teams) en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="3404d-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="3404d-123">Des informations supplémentaires seront fournies après le lancement de Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3404d-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="3404d-124">Mise à niveau du système téléphonique et des équipes</span><span class="sxs-lookup"><span data-stu-id="3404d-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="3404d-125">Si vous migrez votre déploiement hybride Skype entreprise vers votre système téléphonique avec des plans d’appels et que Microsoft sera votre fournisseur de réseaux téléphoniques commutés (RTC), et en supposant que vous avez terminé le transfert du numéro de téléphone, la mise à niveau de vos utilisateurs vers teams transmettra automatiquement les appels RTC entrants vers Teams.</span><span class="sxs-lookup"><span data-stu-id="3404d-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="3404d-126">Si les offres d’appels ne sont pas disponibles ou si vous envisagez d’utiliser votre fournisseur de connectivité RTC, vous devez migrer votre déploiement voix entreprise (ou un déploiement VoIP hybride qui utilise votre déploiement local ou édition Cloud Connector) vers le routage direct du système Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="3404d-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="3404d-127">Pour mettre à niveau vos utilisateurs vers Teams, reportez-vous à la rubrique [Considérations supplémentaires sur le routage direct du système téléphonique](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="3404d-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
