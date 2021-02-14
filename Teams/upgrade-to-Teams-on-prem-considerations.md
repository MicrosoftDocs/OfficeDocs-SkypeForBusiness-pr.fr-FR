---
title: Mise à niveau vers Teams à partir d’un déploiement local de Skype Entreprise - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533591"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="53311-103">Considérations en cas de mise à niveau pour les organisations avec Skype Entreprise Server sur site &mdash; pour les administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="53311-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="53311-104">Cet article décrit des considérations supplémentaires pour les organisations qui utilisent Skype Entreprise Server en local.</span><span class="sxs-lookup"><span data-stu-id="53311-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="53311-105">Cet article est le quatrième de ceux qui décrivent les concepts de mise à niveau et d’implémentation pour les administrateurs informatiques.</span><span class="sxs-lookup"><span data-stu-id="53311-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="53311-106">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="53311-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="53311-107">Méthodes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="53311-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="53311-108">Outils de gestion de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="53311-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="53311-109">**Considérations supplémentaires pour les organisations avec Skype Entreprise en local** (cet article)</span><span class="sxs-lookup"><span data-stu-id="53311-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="53311-110">Mise en œuvre de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="53311-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="53311-111">Considérations sur le réseau téléphonique commuté (PSTN)</span><span class="sxs-lookup"><span data-stu-id="53311-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="53311-112">De plus, les articles suivants décrivent les concepts de mise à niveau et les comportements de coexistence importants :</span><span class="sxs-lookup"><span data-stu-id="53311-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="53311-113">Coexistence de Teams et de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="53311-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="53311-114">Modes de coexistence - Référence</span><span class="sxs-lookup"><span data-stu-id="53311-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="53311-115">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="53311-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="53311-116">Considérations pour les organisations avec Skype Entreprise Server en local</span><span class="sxs-lookup"><span data-stu-id="53311-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="53311-117">La configuration de Skype Entreprise hybride est une condition préalable pour migrer vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="53311-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="53311-118">S’il est possible d’utiliser Teams en mode Îles sans utiliser le mode hybride, la transition vers le mode TeamsOnly ne peut pas être réalisée tant que l’utilisateur n’a pas été déplacé de Skype Entreprise en local vers Skype Entreprise Online (à l’aide de [Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="53311-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="53311-119">Pour plus d’informations, [voir Configurer la connectivité hybride.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="53311-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="53311-120">Si votre organisation dispose de Skype Entreprise Server et que vous n’avez pas configuré de connectivité hybride, mais que vous souhaitez continuer à utiliser Teams, pour gérer la fonctionnalité Teams, vous devez utiliser un compte d’administration avec un domaine .onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="53311-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="53311-121">Les utilisateurs de Teams qui ont un compte Skype Entreprise en local (autrement dit, ils n’ont pas encore été déplacés vers le cloud à l’aide de Move-CsUser) ne peuvent pas interopérables avec les utilisateurs Skype Entreprise et ne peuvent pas se fédérer avec des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="53311-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="53311-122">Cette fonctionnalité n’est disponible que lorsque les utilisateurs sont déplacés vers le cloud (soit en mode Îles, soit en tant qu’utilisateurs de TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="53311-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="53311-123">Si des utilisateurs ont des comptes Skype Entreprise en local, vous ne pouvez pas affecter le mode TeamsOnly au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="53311-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="53311-124">Vous devez d’abord déplacer tous les utilisateurs utilisant des comptes Skype Entreprise locaux vers le cloud, puis désactiver la migration hybride vers `Move-CsUser` [le cloud.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)</span><span class="sxs-lookup"><span data-stu-id="53311-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="53311-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` ne fonctionne pas au niveau du client si un enregistrement DNS lyncdiscover est détecté qui pointe vers un emplacement autre qu’Office 365.</span><span class="sxs-lookup"><span data-stu-id="53311-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="53311-126">Vous devez vous assurer que vos utilisateurs sont correctement synchronisés dans Azure AD avec les attributs Skype Entreprise appropriés.</span><span class="sxs-lookup"><span data-stu-id="53311-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="53311-127">Ces attributs sont tous des préfixes avec « msRTCSIP- ».</span><span class="sxs-lookup"><span data-stu-id="53311-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="53311-128">Si les utilisateurs ne sont pas correctement synchronisés avec Azure AD, les outils de gestion dans Teams ne pourront pas gérer ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="53311-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="53311-129">(Par exemple, vous ne pourrez pas affecter de stratégies Teams à des utilisateurs locaux, sauf si vous synchronisez correctement ces attributs.) Pour plus d’informations, [consultez Configurer Azure AD Connect pour Teams et Skype Entreprise.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)</span><span class="sxs-lookup"><span data-stu-id="53311-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="53311-130">Pour créer un utilisateur TeamsOnly ou Skype Entreprise Online dans une organisation hybride, vous devez d’abord activer l’utilisateur dans Skype Entreprise *Server* sur site, puis le déplacer de l’utilisateur de l’environnement local vers le cloud à l’aide de Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="53311-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="53311-131">La création de l’utilisateur sur site garantit d’abord que tout autre utilisateur de Skype Entreprise local restant pourra router vers l’utilisateur nouvellement créé.</span><span class="sxs-lookup"><span data-stu-id="53311-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="53311-132">Une fois tous les utilisateurs déplacés en ligne, il n’est plus nécessaire d’activer les utilisateurs en local.</span><span class="sxs-lookup"><span data-stu-id="53311-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="53311-133">Lorsqu’un utilisateur est déplacé du cloud en local, les réunions organisées par cet utilisateur sont déplacées vers Skype Entreprise Online ou Teams, selon que le commutateur -MoveToTeams est spécifié ou non.</span><span class="sxs-lookup"><span data-stu-id="53311-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="53311-134">Si vous souhaitez afficher les notifications dans le client Skype Entreprise pour les utilisateurs locaux, vous devez utiliser TeamsUpgradePolicy dans le groupe d’outils local.</span><span class="sxs-lookup"><span data-stu-id="53311-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="53311-135">Seul le paramètre NotifySfbUsers est pertinent pour les utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="53311-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="53311-136">Les utilisateurs sur site reçoivent leur mode depuis les instances en ligne de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="53311-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="53311-137">Consultez les notes [dans Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="53311-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="53311-138">Les nouveaux clients créés après le 3 septembre 2019 sont créés en tant que clients TeamsOnly, sauf si l’organisation dispose déjà d’un déploiement local de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="53311-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="53311-139">Microsoft utilise les enregistrements DNS pour identifier les organisations Skype Entreprise Server locales.</span><span class="sxs-lookup"><span data-stu-id="53311-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="53311-140">Si votre organisation a un serveur Skype Entreprise local sans entrée DNS publique, vous devez appeler le Support Microsoft pour que votre nouveau client soit rétrogradé.</span><span class="sxs-lookup"><span data-stu-id="53311-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="53311-141">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="53311-141">Related links</span></span>

[<span data-ttu-id="53311-142">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="53311-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="53311-143">Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="53311-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="53311-144">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="53311-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="53311-145">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="53311-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="53311-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="53311-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="53311-147">Utilisation du service Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="53311-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

