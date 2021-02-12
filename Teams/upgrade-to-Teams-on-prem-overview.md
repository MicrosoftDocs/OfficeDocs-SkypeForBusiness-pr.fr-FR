---
title: Mise à niveau vers Teams à partir d’un déploiement local de Skype Entreprise - Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578397"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="d15d6-103">Mise à niveau de Skype Entreprise vers Teams &mdash; pour les administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="d15d6-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="d15d6-104">Présentation</span><span class="sxs-lookup"><span data-stu-id="d15d6-104">Overview</span></span>

<span data-ttu-id="d15d6-105">Lors de la mise à niveau de Skype Entreprise vers Teams, certaines organisations nécessitent un déploiement progressif planifié et géré par leurs services informatiques.</span><span class="sxs-lookup"><span data-stu-id="d15d6-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="d15d6-106">Les articles de cette section s’appliquent principalement aux administrateurs informatiques des grandes organisations.</span><span class="sxs-lookup"><span data-stu-id="d15d6-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="d15d6-107">Ces organisations sont généralement locales, mais il peut également s’agit d’organisations Skype Entreprise Online de grande taille.</span><span class="sxs-lookup"><span data-stu-id="d15d6-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="d15d6-108">Avant de lire ces articles, n’oubliez pas de lire les articles [Mise](upgrade-start-here.md) à niveau et À propos de l’infrastructure [de mise à niveau de Teams.](upgrade-framework.md)</span><span class="sxs-lookup"><span data-stu-id="d15d6-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="d15d6-109">Les articles suivants vous guideront tout au long du processus de mise à niveau pour votre organisation :</span><span class="sxs-lookup"><span data-stu-id="d15d6-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="d15d6-110">Méthodes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="d15d6-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="d15d6-111">Outils de gestion de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="d15d6-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="d15d6-112">Autres éléments à prendre en considération pour les organisations avec Skype Entreprise sur site</span><span class="sxs-lookup"><span data-stu-id="d15d6-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="d15d6-113">Implémenter votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="d15d6-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="d15d6-114">Considérations sur le réseau téléphonique commuté (PSTN)</span><span class="sxs-lookup"><span data-stu-id="d15d6-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="d15d6-115">Par ailleurs, les articles suivants décrivent les concepts de mise à niveau et les comportements de coexistence importants :</span><span class="sxs-lookup"><span data-stu-id="d15d6-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="d15d6-116">Coexistence de Teams et de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="d15d6-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="d15d6-117">Modes de coexistence - Référence</span><span class="sxs-lookup"><span data-stu-id="d15d6-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="d15d6-118">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="d15d6-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="d15d6-119">Les articles suivants utilisent les termes Skype Entreprise Online, Skype Entreprise Server en local et Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d15d6-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="d15d6-120">Ce dernier terme fait référence à des versions en ligne et en local.</span><span class="sxs-lookup"><span data-stu-id="d15d6-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="d15d6-121">Avant de commencer, sachez qu’un utilisateur qui a été migré vers Teams n’utilise plus un client Skype Entreprise sauf pour participer à une réunion hébergée dans Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d15d6-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="d15d6-122">Toutes les conversations et appels entrants arrivent dans le client Teams de l’utilisateur, que l’expéditeur utilise Teams ou Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d15d6-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="d15d6-123">Les nouvelles réunions organisées par l’utilisateur migré seront organisées en tant que réunions Teams.</span><span class="sxs-lookup"><span data-stu-id="d15d6-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="d15d6-124">Si l’utilisateur tente d’utiliser le client Skype Entreprise, le démarrage de conversations et d’appels est bloqué.</span><span class="sxs-lookup"><span data-stu-id="d15d6-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="d15d6-125">Toutefois, l’utilisateur peut (et doit) continuer à utiliser le client Skype Entreprise pour participer aux réunions Skype Entreprise à qui il est invité.</span><span class="sxs-lookup"><span data-stu-id="d15d6-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="d15d6-126">(Les anciens clients Skype Entreprise expédiés avant 2017 n’utilisent pas TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="d15d6-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="d15d6-127">Assurez-vous d’utiliser le dernier client Skype Entreprise.)</span><span class="sxs-lookup"><span data-stu-id="d15d6-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="d15d6-128">Vous gérez la transition de vos utilisateurs vers Teams en utilisant le concept de [mode,](migration-interop-guidance-for-teams-with-skype.md)qui est une propriété de [TeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d15d6-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="d15d6-129">Un utilisateur ayant été migré vers Teams comme décrit ci-dessus est en mode « TeamsOnly ».</span><span class="sxs-lookup"><span data-stu-id="d15d6-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="d15d6-130">Pour une organisation qui migre vers Teams, l’objectif ultime est de déplacer tous les utilisateurs en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="d15d6-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

>[!NOTE]
><span data-ttu-id="d15d6-131">Les utilisateurs qui ont un compte Skype Entreprise sur site ne peuvent pas être TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="d15d6-131">Users who have a Skype for Business on-premises account cannot be TeamsOnly.</span></span> <span data-ttu-id="d15d6-132">Bien que ces utilisateurs peuvent utiliser Teams en [mode Îles,](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)cela ne fournit pas l’ensemble complet de la fonctionnalité Teams disponible en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="d15d6-132">Although these users can [use Teams in Islands mode](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), this does not provide the full set of Teams functionality that is available in TeamsOnly mode.</span></span> <span data-ttu-id="d15d6-133">Pour que ces utilisateurs teamsOnly, ils doivent être déplacés vers le cloud à l’aide des `Move-CsUser` outils Skype Entreprise Server locaux.</span><span class="sxs-lookup"><span data-stu-id="d15d6-133">To make these users TeamsOnly, they must be moved to the cloud using `Move-CsUser` in the on-premises Skype for Business Server tools.</span></span>

<span data-ttu-id="d15d6-134">Bien.</span><span class="sxs-lookup"><span data-stu-id="d15d6-134">OK.</span></span> <span data-ttu-id="d15d6-135">Commençons.</span><span class="sxs-lookup"><span data-stu-id="d15d6-135">Let's get started.</span></span>  <span data-ttu-id="d15d6-136">La première étape consiste à comprendre les [méthodes de mise à niveau à votre disposition.](upgrade-to-teams-on-prem-upgrade-methods.md)</span><span class="sxs-lookup"><span data-stu-id="d15d6-136">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="d15d6-137">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="d15d6-137">Related links</span></span>

[<span data-ttu-id="d15d6-138">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="d15d6-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="d15d6-139">Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="d15d6-139">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="d15d6-140">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="d15d6-140">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="d15d6-141">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="d15d6-141">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="d15d6-142">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="d15d6-142">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="d15d6-143">Utilisation du service Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="d15d6-143">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

