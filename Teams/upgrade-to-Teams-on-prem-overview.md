---
title: Effectuer une mise à niveau vers teams à partir d’un déploiement local de Skype entreprise-Microsoft teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa87941300f87abb320ddad7e8bc1311c62addf0
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940574"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="f3f31-103">Mise à niveau de Skype entreprise vers teams &mdash; pour les administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="f3f31-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="f3f31-104">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="f3f31-104">Overview</span></span>

<span data-ttu-id="f3f31-105">Lorsque vous procédez à la mise à niveau de Skype entreprise vers équipes, certaines organisations requièrent un lancement progressif qui est planifié et géré par leurs services informatiques.</span><span class="sxs-lookup"><span data-stu-id="f3f31-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="f3f31-106">Les Articles de cette section s’appliquent principalement aux administrateurs informatiques au sein d’organisations de grande envergure.</span><span class="sxs-lookup"><span data-stu-id="f3f31-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="f3f31-107">Ces organisations sont généralement locales, mais peuvent également être des organisations Skype entreprise Online de grande envergure.</span><span class="sxs-lookup"><span data-stu-id="f3f31-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="f3f31-108">Avant de lire cet article, assurez-vous de lire la [mise à niveau de votre équipe](upgrade-start-here.md) et de [l’infrastructure de mise à niveau](upgrade-framework.md).</span><span class="sxs-lookup"><span data-stu-id="f3f31-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="f3f31-109">Les articles suivants vous guident tout au long du processus de mise à niveau de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="f3f31-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="f3f31-110">Méthodes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f3f31-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="f3f31-111">Outils de gestion de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f3f31-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="f3f31-112">Autres considérations concernant les organisations avec Skype entreprise en local</span><span class="sxs-lookup"><span data-stu-id="f3f31-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="f3f31-113">Implémenter votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f3f31-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="f3f31-114">Considérations relatives au réseau téléphonique public commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="f3f31-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="f3f31-115">De plus, les articles suivants décrivent des concepts importants de mise à niveau et des comportements de coexistence :</span><span class="sxs-lookup"><span data-stu-id="f3f31-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="f3f31-116">Coexistence des équipes et de Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="f3f31-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="f3f31-117">Modes de coexistence-référence</span><span class="sxs-lookup"><span data-stu-id="f3f31-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="f3f31-118">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="f3f31-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="f3f31-119">Les articles suivants utilisent les termes Skype entreprise Online, Skype entreprise Server en local et Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="f3f31-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="f3f31-120">Ce terme fait référence à des versions en ligne et locales.</span><span class="sxs-lookup"><span data-stu-id="f3f31-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="f3f31-121">Avant de commencer, sachez qu’un utilisateur qui a migré vers teams n’utilise plus un client Skype entreprise, à l’exception de la participation à une réunion hébergée dans Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="f3f31-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="f3f31-122">Toutes les conversations et les appels entrants dans le client teams de l’utilisateur, que l’expéditeur utilise teams ou Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="f3f31-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="f3f31-123">Toutes les nouvelles réunions organisées par l’utilisateur migré seront planifiées en tant que réunions d’équipes.</span><span class="sxs-lookup"><span data-stu-id="f3f31-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="f3f31-124">Si l’utilisateur tente d’utiliser le client Skype entreprise, l’ouverture de conversations et d’appels est bloquée.</span><span class="sxs-lookup"><span data-stu-id="f3f31-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="f3f31-125">Toutefois, l’utilisateur peut (et doit) toujours utiliser le client Skype entreprise pour participer aux réunions Skype entreprise auxquelles il est invité.</span><span class="sxs-lookup"><span data-stu-id="f3f31-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="f3f31-126">(Les anciens clients Skype entreprise livrés avant 2017 ne respectent pas TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="f3f31-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="f3f31-127">Vérifiez que vous utilisez la dernière version du client Skype entreprise.)</span><span class="sxs-lookup"><span data-stu-id="f3f31-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="f3f31-128">Vous gérez la transition de votre utilisateur vers teams à l’aide du concept de [mode](migration-interop-guidance-for-teams-with-skype.md), qui est une propriété de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f3f31-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="f3f31-129">Un utilisateur qui a été migré vers teams comme décrit ci-dessus est en mode « TeamsOnly ».</span><span class="sxs-lookup"><span data-stu-id="f3f31-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="f3f31-130">Dans le cas d’une organisation migrant vers Teams, l’objectif ultime consiste à déplacer tous les utilisateurs vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="f3f31-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

<span data-ttu-id="f3f31-131">Bien.</span><span class="sxs-lookup"><span data-stu-id="f3f31-131">OK.</span></span> <span data-ttu-id="f3f31-132">Commençons.</span><span class="sxs-lookup"><span data-stu-id="f3f31-132">Let's get started.</span></span>  <span data-ttu-id="f3f31-133">La première étape consiste à comprendre les [méthodes de mise à niveau disponibles](upgrade-to-teams-on-prem-upgrade-methods.md).</span><span class="sxs-lookup"><span data-stu-id="f3f31-133">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="f3f31-134">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="f3f31-134">Related links</span></span>

[<span data-ttu-id="f3f31-135">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="f3f31-135">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="f3f31-136">Configurer une connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="f3f31-136">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="f3f31-137">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="f3f31-137">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="f3f31-138">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="f3f31-138">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="f3f31-139">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f3f31-139">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="f3f31-140">Utiliser le service de migration de réunion (MMS)</span><span class="sxs-lookup"><span data-stu-id="f3f31-140">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

