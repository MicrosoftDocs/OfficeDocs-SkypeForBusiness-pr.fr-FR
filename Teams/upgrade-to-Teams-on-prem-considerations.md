---
title: Effectuer une mise à niveau vers teams à partir d’un déploiement local de Skype entreprise-Microsoft teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
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
ms.openlocfilehash: e16e651004148645789f5e8e55df6fbbfa1dea9c
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955911"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="87974-103">Considérations en matière de mise à niveau pour les organisations avec Skype entreprise Server en local &mdash; pour les administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="87974-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="87974-104">Cet article décrit des considérations supplémentaires pour les organisations avec Skype entreprise Server en local.</span><span class="sxs-lookup"><span data-stu-id="87974-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="87974-105">Cet article est le quatrième d’une description de la mise à niveau et de l’implémentation pour les administrateurs informatiques.</span><span class="sxs-lookup"><span data-stu-id="87974-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="87974-106">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="87974-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="87974-107">Méthodes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="87974-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="87974-108">Outils de gestion de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="87974-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="87974-109">**Remarques supplémentaires pour les organisations avec Skype entreprise local** (cet article)</span><span class="sxs-lookup"><span data-stu-id="87974-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="87974-110">Implémentation de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="87974-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="87974-111">Considérations relatives au réseau téléphonique public commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="87974-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="87974-112">De plus, les articles suivants décrivent des concepts importants de mise à niveau et des comportements de coexistence :</span><span class="sxs-lookup"><span data-stu-id="87974-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="87974-113">Coexistence des équipes et de Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="87974-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="87974-114">Modes de coexistence-référence</span><span class="sxs-lookup"><span data-stu-id="87974-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="87974-115">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="87974-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="87974-116">Remarques concernant les organisations avec Skype entreprise Server en local</span><span class="sxs-lookup"><span data-stu-id="87974-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="87974-117">La configuration de Skype entreprise hybride est une condition préalable à la migration vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="87974-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="87974-118">Même s’il est possible d’utiliser les équipes en mode d’îlot sans qu’elles soient hybrides, la transition vers le mode TeamsOnly ne peut pas être effectuée tant que l’utilisateur n’est pas transféré de Skype entreprise sur site à Skype entreprise Online (via [Move-Csuser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span><span class="sxs-lookup"><span data-stu-id="87974-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="87974-119">Pour plus d’informations, voir [configurer une connectivité hybride](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="87974-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="87974-120">Si votre organisation possède Skype entreprise Server et que vous n’avez pas configuré une connectivité hybride, mais que vous voulez toujours utiliser Teams, vous devez utiliser un compte administratif doté d’un domaine. onmicrosoft.com pour gérer les fonctionnalités d’équipe.</span><span class="sxs-lookup"><span data-stu-id="87974-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="87974-121">Les utilisateurs teams disposant d’un compte Skype entreprise local (autrement dit, ils n’ont pas encore été déplacés vers le Cloud à l’aide de Move-CsUser) ne peuvent pas interagir avec des utilisateurs de Skype entreprise, et ne peuvent pas être fédérer avec des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="87974-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="87974-122">Cette fonctionnalité n’est disponible que lorsque les utilisateurs sont déplacés vers le Cloud (en mode îlot ou en tant qu’utilisateurs TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="87974-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="87974-123">Si vos utilisateurs disposent d’un compte Skype entreprise local, vous ne devez pas affecter le mode TeamsOnly au niveau du client, sauf si vous affectez explicitement un autre mode à tous les utilisateurs disposant de comptes Skype entreprise locaux.</span><span class="sxs-lookup"><span data-stu-id="87974-123">If you have any users with Skype for Business accounts on-premises, you must not assign TeamsOnly mode at the tenant level, unless you explicitly assign some other mode to all users with on-premises Skype for Business accounts.</span></span> 

- <span data-ttu-id="87974-124">Vous devez vous assurer que vos utilisateurs sont correctement synchronisés avec Azure AD avec les attributs Skype entreprise appropriés.</span><span class="sxs-lookup"><span data-stu-id="87974-124">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="87974-125">Ces attributs sont des préfixes avec « msRTCSIP- ».</span><span class="sxs-lookup"><span data-stu-id="87974-125">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="87974-126">Si les utilisateurs ne sont pas synchronisés correctement avec Azure AD, les outils de gestion dans Teams ne seront pas en mesure de gérer ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="87974-126">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="87974-127">Par exemple, vous ne serez pas en mesure d’affecter des stratégies d’équipe aux utilisateurs locaux, sauf si vous synchronisez correctement ces attributs. Pour plus d’informations, reportez-vous à la rubrique [configuration d’Azure ad Connect pour les équipes et Skype entreprise](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="87974-127">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="87974-128">Pour créer un nouveau TeamsOnly ou un utilisateur de Skype entreprise Online au sein d’une organisation hybride, *vous devez d’abord activer l’utilisateur dans Skype entreprise Server en local*, puis déplacer l’utilisateur de local vers le Cloud à l’aide de Move-Csuser.</span><span class="sxs-lookup"><span data-stu-id="87974-128">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="87974-129">La création de l’utilisateur sur site permet de s’assurer que tous les autres utilisateurs Skype entreprise restants pourront diriger vers l’utilisateur nouvellement créé.</span><span class="sxs-lookup"><span data-stu-id="87974-129">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="87974-130">Une fois tous les utilisateurs déplacés en ligne, il n’est plus nécessaire d’activer d’abord les utilisateurs en local.</span><span class="sxs-lookup"><span data-stu-id="87974-130">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="87974-131">Lorsque l’utilisateur passe du Cloud local, les réunions organisées par cet utilisateur sont déplacées vers Skype entreprise Online ou Teams, selon que le commutateur-MoveToTeams est ou non spécifié.</span><span class="sxs-lookup"><span data-stu-id="87974-131">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="87974-132">Si vous souhaitez afficher les notifications dans le client Skype entreprise pour les utilisateurs locaux, vous devez utiliser TeamsUpgradePolicy dans l’ensemble d’outils local.</span><span class="sxs-lookup"><span data-stu-id="87974-132">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="87974-133">Seul le paramètre NotifySfbUsers est pertinent pour les utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="87974-133">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="87974-134">Les utilisateurs sur site reçoivent leur mode provenant des instances en ligne d’TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="87974-134">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="87974-135">Voir les remarques dans [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="87974-135">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="87974-136">Tout nouveau client créé après le 3 septembre 2019 est créé en tant que client TeamsOnly, sauf si l’organisation a déjà un déploiement local de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="87974-136">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="87974-137">Microsoft utilise des enregistrements DNS pour identifier les organisations serveur Skype entreprise locales.</span><span class="sxs-lookup"><span data-stu-id="87974-137">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="87974-138">Si votre organisation possède un serveur Skype entreprise local sans aucune entrée DNS publique, vous devrez appeler le support Microsoft pour que votre nouveau client soit mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="87974-138">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 



















## <a name="related-links"></a><span data-ttu-id="87974-139">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="87974-139">Related links</span></span>

[<span data-ttu-id="87974-140">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="87974-140">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="87974-141">Configurer une connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="87974-141">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="87974-142">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="87974-142">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="87974-143">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="87974-143">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="87974-144">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="87974-144">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="87974-145">Utiliser le service de migration de réunion (MMS)</span><span class="sxs-lookup"><span data-stu-id="87974-145">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
