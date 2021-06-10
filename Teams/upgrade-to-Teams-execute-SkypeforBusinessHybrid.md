---
title: Mettre à Skype Entreprise niveau vers un déploiement hybride Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Découvrez comment mettre à niveau votre organisation vers un déploiement Microsoft Teams un déploiement Skype Entreprise hybride.
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
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104020"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="08a0d-103">Mettre à niveau à partir d Skype Entreprise déploiement hybride vers un déploiement Teams</span><span class="sxs-lookup"><span data-stu-id="08a0d-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="08a0d-104">![Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation")</span><span class="sxs-lookup"><span data-stu-id="08a0d-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="08a0d-105">Cet article fait partie de la phase déploiement et implémentation de votre voyage de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="08a0d-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="08a0d-106">Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="08a0d-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="08a0d-107">Demandez aux parties prenantes de votre projet</span><span class="sxs-lookup"><span data-stu-id="08a0d-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="08a0d-108">Étendue définie de votre projet</span><span class="sxs-lookup"><span data-stu-id="08a0d-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="08a0d-109">Coexistence et interopérabilité comprises entre les systèmes Skype Entreprise et Teams</span><span class="sxs-lookup"><span data-stu-id="08a0d-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="08a0d-110">Nous avons choisi votre chemin de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="08a0d-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="08a0d-111">Préparé votre environnement</span><span class="sxs-lookup"><span data-stu-id="08a0d-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="08a0d-112">Préparé votre organisation</span><span class="sxs-lookup"><span data-stu-id="08a0d-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="08a0d-113">Conduite d’un pilote</span><span class="sxs-lookup"><span data-stu-id="08a0d-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="08a0d-114">Suivez les instructions de cet article si vous avez déployé Skype Entreprise ou Microsoft Lync en local et que vous l’avez configuré dans un déploiement hybride avec votre organisation Microsoft 365 ou Office 365 et que votre organisation souhaite mettre à niveau vers Teams de manière sélective (en utilisant plusieurs modes de coexistence) ou tous les membres.</span><span class="sxs-lookup"><span data-stu-id="08a0d-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="08a0d-115">Pour une mise à niveau, vous devez déplacer vos utilisateurs vers Skype Entreprise Online (s’ils ne sont pas encore domicile domicile) et leur attribuer le mode de coexistence et de mise à niveau approprié.</span><span class="sxs-lookup"><span data-stu-id="08a0d-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="08a0d-116">Étape 1 : déplacer des utilisateurs vers Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="08a0d-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="08a0d-117">Cette étape s’applique aux utilisateurs actuellement domiciles sur site.</span><span class="sxs-lookup"><span data-stu-id="08a0d-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="08a0d-118">Pour plus d’informations sur le déplacement de ces utilisateurs vers Skype Entreprise Online, voir Déplacer les utilisateurs d’un site [local vers Skype Entreprise Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="08a0d-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="08a0d-119">Étape 2 : attribuer une coexistence et un mode de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="08a0d-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="08a0d-120">Une fois que vous avez déplacé vos utilisateurs vers Skype Entreprise Online, vous pouvez leur attribuer le mode de coexistence approprié, en fonction du parcours de mise à niveau que votre organisation a choisi.</span><span class="sxs-lookup"><span data-stu-id="08a0d-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="08a0d-121">Pour plus d’informations, voir Définir vos paramètres de [coexistence](./setting-your-coexistence-and-upgrade-settings.md) et de mise à niveau et [TeamsUpgradePolicy :](upgrade-to-teams-on-prem-tools.md)gestion de la migration et de la coexistence.</span><span class="sxs-lookup"><span data-stu-id="08a0d-121">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="08a0d-122">Avec Skype Entreprise Server 2019 et une prochaine mise à jour cumulative de Skype Entreprise Server 2015, vous serez en mesure d’effectuer les étapes 1 (déplacement des utilisateurs vers Skype Entreprise Online) et étape 2 (mise à niveau des utilisateurs vers Teams) en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="08a0d-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="08a0d-123">Des informations supplémentaires seront fournies après Skype Entreprise Server publication de 2019.</span><span class="sxs-lookup"><span data-stu-id="08a0d-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="08a0d-124">Système téléphonique mise à Teams niveau</span><span class="sxs-lookup"><span data-stu-id="08a0d-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="08a0d-125">Si vous effectuez la transition de votre déploiement hybride Skype Entreprise vers Système téléphonique avec les forfaits d’appels, Microsoft sera votre fournisseur de réseau téléphonique commuté (PSTN) et, en supposant que vous avez effectué le transfert de numéro de téléphone, la mise à niveau de vos utilisateurs vers Teams fera automatiquement passer les appels PSTN entrants vers Teams.</span><span class="sxs-lookup"><span data-stu-id="08a0d-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="08a0d-126">Si les forfaits d’appels ne sont pas disponibles ou si vous avez l’intention d’utiliser votre fournisseur de connectivité PSTN existant, vous devez transition votre déploiement voix d’entreprise, ou déploiement vocal hybride qui utilise votre déploiement local existant ou la version Cloud Connector, vers le routage direct du système Téléphone Microsoft.</span><span class="sxs-lookup"><span data-stu-id="08a0d-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="08a0d-127">Pour mettre à niveau vos utilisateurs vers Teams, consultez les autres éléments à prendre en [compte pour Système téléphonique routage direct.](./direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="08a0d-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span>