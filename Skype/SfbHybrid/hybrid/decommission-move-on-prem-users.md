---
title: Déplacer des utilisateurs vers le cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Déplacez les utilisateurs avant de désaffecter un environnement Skype Entreprise local.
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656670"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="3f232-103">Déplacer les utilisateurs requis avant de désaffecter votre environnement local</span><span class="sxs-lookup"><span data-stu-id="3f232-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="3f232-104">Cet article explique comment déplacer les utilisateurs requis vers le cloud Microsoft avant de désaffecter votre environnement Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="3f232-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="3f232-105">Il s’agit de l’étape 1 des étapes suivantes pour désaffecter votre environnement local :</span><span class="sxs-lookup"><span data-stu-id="3f232-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="3f232-106">**Étape 1. Déplacez tous les utilisateurs requis de l’local vers le site en ligne.**</span><span class="sxs-lookup"><span data-stu-id="3f232-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="3f232-107">(Cet article)</span><span class="sxs-lookup"><span data-stu-id="3f232-107">(This article)</span></span>

- <span data-ttu-id="3f232-108">Étape 2.</span><span class="sxs-lookup"><span data-stu-id="3f232-108">Step 2.</span></span> <span data-ttu-id="3f232-109">[Désactivez votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="3f232-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="3f232-110">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="3f232-110">Step 3.</span></span> <span data-ttu-id="3f232-111">[Déplacez les points de terminaison de l’application hybride de l’local vers le mode en ligne.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="3f232-111">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="3f232-112">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="3f232-112">Step 4.</span></span> <span data-ttu-id="3f232-113">[Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="3f232-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="3f232-114">Déplacer tous les utilisateurs requis de l’local vers le cloud</span><span class="sxs-lookup"><span data-stu-id="3f232-114">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="3f232-115">Tous les utilisateurs que vous continuerez à utiliser après avoir effectué la migration doivent d’abord être déplacés de l’local vers le cloud.</span><span class="sxs-lookup"><span data-stu-id="3f232-115">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="3f232-116">Vous déplacez les utilisateurs à l’aide des outils d’administration locaux.</span><span class="sxs-lookup"><span data-stu-id="3f232-116">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="3f232-117">Pour plus d’informations, voir [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="3f232-117">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="3f232-118">Bien qu’il soit possible pour les utilisateurs ayant des comptes Skype Entreprise Server locaux d’utiliser Teams, ces utilisateurs n’ont pas toutes les fonctionnalités de Teams.</span><span class="sxs-lookup"><span data-stu-id="3f232-118">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="3f232-119">Ces utilisateurs ne peuvent pas interopérer ou fédérer avec d’autres utilisateurs qui utilisent encore Skype Entreprise (en ligne ou en local).</span><span class="sxs-lookup"><span data-stu-id="3f232-119">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="3f232-120">Ces utilisateurs ne peuvent pas non plus recevoir d’appels PSTN dans leur client Teams.</span><span class="sxs-lookup"><span data-stu-id="3f232-120">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="3f232-121">Par conséquent, vous devez déplacer ces utilisateurs en ligne.</span><span class="sxs-lookup"><span data-stu-id="3f232-121">Therefore, you must move these users to online.</span></span> <span data-ttu-id="3f232-122">Cette étape garantit également que tous les contacts ou réunions créés dans Skype Entreprise Server sont migrés vers Teams.</span><span class="sxs-lookup"><span data-stu-id="3f232-122">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="3f232-123">Pour vérifier s’il reste des utilisateurs dans votre déploiement local, exécutez l’cmdlet suivante dans une fenêtre PowerShell Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3f232-123">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="3f232-124">Si des utilisateurs sont renvoyés, examinez la sortie pour déterminer si des comptes doivent être déplacés vers le cloud et, pour ces utilisateurs, suivez les étapes [ci-après.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="3f232-124">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="3f232-125">Pour les comptes d’utilisateurs qui ne sont plus nécessaires, exécutez l’cmdlet PowerShell Skype Entreprise Server suivante :</span><span class="sxs-lookup"><span data-stu-id="3f232-125">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="3f232-126">L'Disable-CsUser supprimera tous les attributs Skype Entreprise pour tous les utilisateurs qui ont les critères de filtre.</span><span class="sxs-lookup"><span data-stu-id="3f232-126">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="3f232-127">Avant de continuer, confirmez que ces comptes ne sont plus nécessaires à l’avenir.</span><span class="sxs-lookup"><span data-stu-id="3f232-127">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="3f232-128">Vous êtes maintenant prêt à [désactiver votre configuration hybride.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="3f232-128">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3f232-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3f232-129">See also</span></span>

- [<span data-ttu-id="3f232-130">Mise hors service de votre environnement Skype pour entreprises sur site</span><span class="sxs-lookup"><span data-stu-id="3f232-130">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="3f232-131">Désactiver votre configuration hybride</span><span class="sxs-lookup"><span data-stu-id="3f232-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="3f232-132">Déplacer des points de terminaison d’application hybride de l’local vers le mode en ligne</span><span class="sxs-lookup"><span data-stu-id="3f232-132">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="3f232-133">Supprimez votre déploiement sur site de Skype pour entreprises.</span><span class="sxs-lookup"><span data-stu-id="3f232-133">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




