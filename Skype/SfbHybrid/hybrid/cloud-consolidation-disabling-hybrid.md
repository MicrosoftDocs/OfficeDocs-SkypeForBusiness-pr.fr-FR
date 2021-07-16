---
title: Désactiver l’hybride pour terminer la migration vers Teams uniquement
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cet article comprend des étapes détaillées pour la désactivation de l’hybride dans le cadre de la consolidation du cloud pour Teams et Skype Entreprise.
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453643"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="59b9e-103">Désactiver votre configuration hybride pour terminer la migration vers Teams uniquement</span><span class="sxs-lookup"><span data-stu-id="59b9e-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="59b9e-104">Cet article explique comment désactiver votre configuration hybride avant de désaffecter votre environnement Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="59b9e-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="59b9e-105">Il s’agit de l’étape 2 des étapes suivantes pour désaffecter votre environnement local :</span><span class="sxs-lookup"><span data-stu-id="59b9e-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="59b9e-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="59b9e-106">Step 1.</span></span> <span data-ttu-id="59b9e-107">[Déplacez tous les utilisateurs requis de l’local vers le site en ligne.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="59b9e-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="59b9e-108">**Étape 2. Désactivez votre configuration hybride.**</span><span class="sxs-lookup"><span data-stu-id="59b9e-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="59b9e-109">(Cet article)</span><span class="sxs-lookup"><span data-stu-id="59b9e-109">(This article)</span></span>

- <span data-ttu-id="59b9e-110">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="59b9e-110">Step 3.</span></span> <span data-ttu-id="59b9e-111">[Migrez les points de terminaison de l’application hybride de l’local vers le mode en ligne.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="59b9e-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="59b9e-112">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="59b9e-112">Step 4.</span></span> <span data-ttu-id="59b9e-113">[Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="59b9e-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="59b9e-114">Les étapes 2 et 3 doivent être réalisées dans la même fenêtre de maintenance, car les points de terminaison d’application hybride existants ne seront pas découvrables entre les étapes 2 et la fin de l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="59b9e-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>


## <a name="summary"></a><span data-ttu-id="59b9e-115">Résumé</span><span class="sxs-lookup"><span data-stu-id="59b9e-115">Summary</span></span>

<span data-ttu-id="59b9e-116">Une fois que vous avez mis à niveau tous les utilisateurs de Skype Entreprise en local vers Teams Uniquement en Microsoft 365, vous pouvez désaffecter le déploiement Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="59b9e-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span>

<span data-ttu-id="59b9e-117">Avant de désaffecter le déploiement Skype Entreprise local et de supprimer du matériel, vous devez séparer logiquement le déploiement local de Microsoft 365 en désactivant l’hybride.</span><span class="sxs-lookup"><span data-stu-id="59b9e-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="59b9e-118">La désactivation hybride se compose des quatre étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="59b9e-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="59b9e-119">[Mettez à jour les enregistrements DNS pour qu’ils pointent vers Microsoft 365](#update-dns-to-point-to-microsoft-365).</span><span class="sxs-lookup"><span data-stu-id="59b9e-119">[Update DNS records to point to Microsoft 365](#update-dns-to-point-to-microsoft-365).</span></span>

2. <span data-ttu-id="59b9e-120">[Modifiez le mode de coexistence de votre](#change-the-coexistence-mode-for-your-organization-to-teams-only)organisation en Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="59b9e-120">[Change the coexistence mode for your organization to Teams Only](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span></span>

3. <span data-ttu-id="59b9e-121">[Désactivez l’espace d’adressaie sip partagé (également](#disable-shared-sip-address-space-in-microsoft-365-organization)appelé « domaine fractioné ») dans l’Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59b9e-121">[Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization](#disable-shared-sip-address-space-in-microsoft-365-organization).</span></span>

4. [<span data-ttu-id="59b9e-122">Désactiver la communication entre les locaux et les Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59b9e-122">Disable communication between on-premises and Microsoft 365</span></span>](#disable-communication-between-on-premises-and-microsoft-365)

<span data-ttu-id="59b9e-123">Ces étapes séparent logiquement votre déploiement local de Skype Entreprise Server de Microsoft 365 et assurez-vous que votre organisation est entièrement Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="59b9e-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="59b9e-124">Une fois ces étapes terminées, vous pouvez désaffecter votre déploiement Skype Entreprise local à l’aide de l’une des deux méthodes référencés dans [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="59b9e-124">After you've completed these steps, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

> [!Important] 
> <span data-ttu-id="59b9e-125">Une fois cette séparation logique terminée, les attributs msRTCSIP de votre active Directory local ont toujours des valeurs et continueront à se synchroniser via Azure AD Connecter dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="59b9e-125">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="59b9e-126">La façon dont vous désaffectez l’environnement local varie selon que vous avez l’intention de laisser ces attributs en place ou de les effacer d’abord de votre environnement Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="59b9e-126">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="59b9e-127">Sachez que l’effacement des attributs msRTCSIP locaux une fois que vous avez migré à partir de l’local peut entraîner une perte de service pour les utilisateurs !</span><span class="sxs-lookup"><span data-stu-id="59b9e-127">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="59b9e-128">Les détails et les compromis des deux approches de désaffectation sont décrits dans [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="59b9e-128">Details and tradeoffs of the two decommissioning approaches are described in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

## <a name="update-dns-to-point-to-microsoft-365"></a><span data-ttu-id="59b9e-129">Mettre à jour le DNS pour qu’il pointe vers Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59b9e-129">Update DNS to point to Microsoft 365</span></span>

<span data-ttu-id="59b9e-130">Le DNS externe de l’organisation pour l’organisation sur site doit être mis à jour afin que les enregistrements Skype Entreprise pointent vers Microsoft 365 au lieu du déploiement local.</span><span class="sxs-lookup"><span data-stu-id="59b9e-130">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> 

<span data-ttu-id="59b9e-131">En outre, les enregistrements CNAME pour la meet ou dialin (le cas présent) peuvent être supprimés.</span><span class="sxs-lookup"><span data-stu-id="59b9e-131">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="59b9e-132">Enfin, tous les enregistrements DNS Skype Entreprise votre réseau interne doivent être supprimés.</span><span class="sxs-lookup"><span data-stu-id="59b9e-132">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

<span data-ttu-id="59b9e-133">Pour plus d’informations sur la mise à jour des enregistrements DNS, voir Mettre à jour les entrées [DNS](decommission-manage-dns-entries.md)pour permettre à votre organisation d’être Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="59b9e-133">For details about updating DNS records, see [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).</span></span>

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a><span data-ttu-id="59b9e-134">Modifier le mode de coexistence de votre organisation en mode Teams uniquement</span><span class="sxs-lookup"><span data-stu-id="59b9e-134">Change the coexistence mode for your organization to Teams Only</span></span>

<span data-ttu-id="59b9e-135">Cette étape garantit que tout nouvel utilisateur de votre organisation est toujours créé en tant qu’Teams utilisateur uniquement.</span><span class="sxs-lookup"><span data-stu-id="59b9e-135">This step ensures that any new user in your organization is always created as a Teams Only user.</span></span> 

<span data-ttu-id="59b9e-136">Si vous tentez de modifier le mode client en mode Teams Seul vérifie automatiquement l’existence d’enregistrements DNS locaux qui ont pu être manqués à l’étape 1 et identifie ces enregistrements dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="59b9e-136">Attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span> <span data-ttu-id="59b9e-137">Si vous modifiez le mode client Teams seul ne réussira pas tant que tous les enregistrements DNS de votre organisation n’auront pas été mis à jour.</span><span class="sxs-lookup"><span data-stu-id="59b9e-137">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organization are updated.</span></span> 

<span data-ttu-id="59b9e-138">Pour modifier le mode client en mode Teams exécutez uniquement la commande suivante à partir d’Teams fenêtre PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59b9e-138">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

<span data-ttu-id="59b9e-139">Vous pouvez également utiliser le Centre d’administration Teams pour modifier le mode de coexistence client en TeamsOnly, sous « Paramètres à l’échelle de l’organisation » -> « Mise à niveau Teams client ».</span><span class="sxs-lookup"><span data-stu-id="59b9e-139">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a><span data-ttu-id="59b9e-140">Désactiver l’espace d’adressaie sip partagé dans Microsoft 365 organisation</span><span class="sxs-lookup"><span data-stu-id="59b9e-140">Disable shared sip address space in Microsoft 365 organization</span></span>
    
<span data-ttu-id="59b9e-141">Pour désactiver l’espace d’adressale sip partagé, exécutez la commande suivante à partir d’Teams fenêtre PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59b9e-141">To disable shared sip address space, run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a><span data-ttu-id="59b9e-142">Désactiver la communication entre les locaux et les Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="59b9e-142">Disable communication between on-premises and Microsoft 365</span></span>

<span data-ttu-id="59b9e-143">Pour désactiver la communication entre l’environnement local et Microsoft 365, exécutez la commande suivante à partir d’une fenêtre PowerShell sur site :</span><span class="sxs-lookup"><span data-stu-id="59b9e-143">To disable communication between the on-premises environment and Microsoft 365, run the following command from an on-premises PowerShell window:</span></span>

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a><span data-ttu-id="59b9e-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="59b9e-144">See also</span></span>

- [<span data-ttu-id="59b9e-145">Consolidation du cloud pour Teams et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="59b9e-145">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="59b9e-146">Mise hors service de votre environnement Skype pour entreprises sur site</span><span class="sxs-lookup"><span data-stu-id="59b9e-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

