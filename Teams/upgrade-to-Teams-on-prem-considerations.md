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
ms.openlocfilehash: 8c359b39707b57a653f35e75497672d306209ccd
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328213"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="ec929-103">Considérations en matière de mise à niveau pour les organisations avec Skype entreprise Server en local &mdash; pour les administrateurs informatiques</span><span class="sxs-lookup"><span data-stu-id="ec929-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="ec929-104">Cet article décrit des considérations supplémentaires pour les organisations avec Skype entreprise Server en local.</span><span class="sxs-lookup"><span data-stu-id="ec929-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="ec929-105">Cet article est le quatrième d’une description de la mise à niveau et de l’implémentation pour les administrateurs informatiques.</span><span class="sxs-lookup"><span data-stu-id="ec929-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="ec929-106">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="ec929-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="ec929-107">Méthodes de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ec929-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="ec929-108">Outils de gestion de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ec929-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="ec929-109">**Remarques supplémentaires pour les organisations avec Skype entreprise local** (cet article)</span><span class="sxs-lookup"><span data-stu-id="ec929-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="ec929-110">Implémentation de votre mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ec929-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="ec929-111">Considérations relatives au réseau téléphonique public commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="ec929-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="ec929-112">De plus, les articles suivants décrivent des concepts importants de mise à niveau et des comportements de coexistence :</span><span class="sxs-lookup"><span data-stu-id="ec929-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="ec929-113">Coexistence des équipes et de Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="ec929-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="ec929-114">Modes de coexistence-référence</span><span class="sxs-lookup"><span data-stu-id="ec929-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="ec929-115">Expérience client Teams et conformité aux modes coexistence</span><span class="sxs-lookup"><span data-stu-id="ec929-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="ec929-116">Remarques concernant les organisations avec Skype entreprise Server en local</span><span class="sxs-lookup"><span data-stu-id="ec929-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="ec929-117">La configuration de Skype entreprise hybride est une condition préalable à la migration vers le mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ec929-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="ec929-118">Même s’il est possible d’utiliser les équipes en mode d’îlot sans qu’elles soient hybrides, la transition vers le mode TeamsOnly ne peut pas être effectuée tant que l’utilisateur n’est pas transféré de Skype entreprise sur site à Skype entreprise Online (via [Move-Csuser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span><span class="sxs-lookup"><span data-stu-id="ec929-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="ec929-119">Pour plus d’informations, voir [configurer une connectivité hybride](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="ec929-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="ec929-120">Si votre organisation possède Skype entreprise Server et que vous n’avez pas configuré une connectivité hybride, mais que vous voulez toujours utiliser Teams, vous devez utiliser un compte administratif doté d’un domaine. onmicrosoft.com pour gérer les fonctionnalités d’équipe.</span><span class="sxs-lookup"><span data-stu-id="ec929-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="ec929-121">Les utilisateurs teams disposant d’un compte Skype entreprise local (autrement dit, ils n’ont pas encore été déplacés vers le Cloud à l’aide de Move-CsUser) ne peuvent pas interagir avec des utilisateurs de Skype entreprise, et ne peuvent pas être fédérer avec des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="ec929-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="ec929-122">Cette fonctionnalité n’est disponible que lorsque les utilisateurs sont déplacés vers le Cloud (en mode îlot ou en tant qu’utilisateurs TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="ec929-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="ec929-123">Si vous avez des utilisateurs avec des comptes Skype entreprise en local, vous ne pouvez pas affecter le mode TeamsOnly au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="ec929-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="ec929-124">Vous devez tout d’abord déplacer tous les utilisateurs disposant d’un compte Skype entreprise local dans le Cloud à l’aide de `Move-CsUser` , puis [désactiver l’environnement hybride pour terminer la migration vers le Cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span><span class="sxs-lookup"><span data-stu-id="ec929-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="ec929-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` ne fonctionnera pas au niveau du client si un enregistrement DNS lyncdiscover est détecté et pointe vers un emplacement autre qu’Office 365.</span><span class="sxs-lookup"><span data-stu-id="ec929-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="ec929-126">Vous devez vous assurer que vos utilisateurs sont correctement synchronisés avec Azure AD avec les attributs Skype entreprise appropriés.</span><span class="sxs-lookup"><span data-stu-id="ec929-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="ec929-127">Ces attributs sont des préfixes avec « msRTCSIP- ».</span><span class="sxs-lookup"><span data-stu-id="ec929-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="ec929-128">Si les utilisateurs ne sont pas synchronisés correctement avec Azure AD, les outils de gestion dans Teams ne seront pas en mesure de gérer ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ec929-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="ec929-129">Par exemple, vous ne serez pas en mesure d’affecter des stratégies d’équipe aux utilisateurs locaux, sauf si vous synchronisez correctement ces attributs. Pour plus d’informations, reportez-vous à la rubrique [configuration d’Azure ad Connect pour les équipes et Skype entreprise](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="ec929-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="ec929-130">Pour créer un nouveau TeamsOnly ou un utilisateur de Skype entreprise Online au sein d’une organisation hybride, *vous devez d’abord activer l’utilisateur dans Skype entreprise Server en local*, puis déplacer l’utilisateur de local vers le Cloud à l’aide de Move-Csuser.</span><span class="sxs-lookup"><span data-stu-id="ec929-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="ec929-131">La création de l’utilisateur sur site permet de s’assurer que tous les autres utilisateurs Skype entreprise restants pourront diriger vers l’utilisateur nouvellement créé.</span><span class="sxs-lookup"><span data-stu-id="ec929-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="ec929-132">Une fois tous les utilisateurs déplacés en ligne, il n’est plus nécessaire d’activer d’abord les utilisateurs en local.</span><span class="sxs-lookup"><span data-stu-id="ec929-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="ec929-133">Lorsque l’utilisateur passe du Cloud local, les réunions organisées par cet utilisateur sont déplacées vers Skype entreprise Online ou Teams, selon que le commutateur-MoveToTeams est ou non spécifié.</span><span class="sxs-lookup"><span data-stu-id="ec929-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="ec929-134">Si vous souhaitez afficher les notifications dans le client Skype entreprise pour les utilisateurs locaux, vous devez utiliser TeamsUpgradePolicy dans l’ensemble d’outils local.</span><span class="sxs-lookup"><span data-stu-id="ec929-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="ec929-135">Seul le paramètre NotifySfbUsers est pertinent pour les utilisateurs locaux.</span><span class="sxs-lookup"><span data-stu-id="ec929-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="ec929-136">Les utilisateurs sur site reçoivent leur mode provenant des instances en ligne d’TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="ec929-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="ec929-137">Voir les remarques dans [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ec929-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="ec929-138">Tout nouveau client créé après le 3 septembre 2019 est créé en tant que client TeamsOnly, sauf si l’organisation a déjà un déploiement local de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ec929-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="ec929-139">Microsoft utilise des enregistrements DNS pour identifier les organisations serveur Skype entreprise locales.</span><span class="sxs-lookup"><span data-stu-id="ec929-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="ec929-140">Si votre organisation possède un serveur Skype entreprise local sans aucune entrée DNS publique, vous devrez appeler le support Microsoft pour que votre nouveau client soit mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="ec929-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="ec929-141">Liens connexes</span><span class="sxs-lookup"><span data-stu-id="ec929-141">Related links</span></span>

[<span data-ttu-id="ec929-142">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="ec929-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="ec929-143">Configurer une connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="ec929-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="ec929-144">Déplacer des utilisateurs entre l’environnement local et le cloud</span><span class="sxs-lookup"><span data-stu-id="ec929-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="ec929-145">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="ec929-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="ec929-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="ec929-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="ec929-147">Utiliser le service de migration de réunion (MMS)</span><span class="sxs-lookup"><span data-stu-id="ec929-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

