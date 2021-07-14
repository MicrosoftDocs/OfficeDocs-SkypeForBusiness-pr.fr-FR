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
ms.openlocfilehash: 97681f4e9306336874ba4d9428a273b1d31519db
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420839"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="26b4c-103">Désactiver votre configuration hybride pour terminer la migration vers Teams uniquement</span><span class="sxs-lookup"><span data-stu-id="26b4c-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="26b4c-104">Cet article explique comment désactiver votre configuration hybride avant de désaffecter votre environnement Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="26b4c-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="26b4c-105">Il s’agit de l’étape 2 des étapes suivantes pour désaffecter votre environnement local :</span><span class="sxs-lookup"><span data-stu-id="26b4c-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="26b4c-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="26b4c-106">Step 1.</span></span> <span data-ttu-id="26b4c-107">[Déplacez tous les utilisateurs requis de l’local vers le site en ligne.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="26b4c-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="26b4c-108">**Étape 2. Désactivez votre configuration hybride.**</span><span class="sxs-lookup"><span data-stu-id="26b4c-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="26b4c-109">(Cet article)</span><span class="sxs-lookup"><span data-stu-id="26b4c-109">(This article)</span></span>

- <span data-ttu-id="26b4c-110">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="26b4c-110">Step 3.</span></span> <span data-ttu-id="26b4c-111">[Migrez les points de terminaison de l’application hybride de l’local vers le mode en ligne.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="26b4c-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="26b4c-112">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="26b4c-112">Step 4.</span></span> <span data-ttu-id="26b4c-113">[Supprimez votre déploiement Skype Entreprise local.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="26b4c-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="26b4c-114">Les étapes 2 et 3 doivent être réalisées dans la même fenêtre de maintenance, car les points de terminaison d’application hybride existants ne seront pas découvrables entre les étapes 2 et la fin de l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="26b4c-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>

## <a name="overview"></a><span data-ttu-id="26b4c-115">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="26b4c-115">Overview</span></span>

<span data-ttu-id="26b4c-116">Une fois que vous avez mis à niveau tous les utilisateurs de Skype Entreprise en local vers Teams Uniquement en Microsoft 365, vous pouvez désaffecter le déploiement Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="26b4c-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="26b4c-117">Avant de désaffecter le déploiement Skype Entreprise local et de supprimer du matériel, vous devez séparer logiquement le déploiement local de Microsoft 365 en désactivant l’hybride.</span><span class="sxs-lookup"><span data-stu-id="26b4c-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="26b4c-118">La désactivation hybride se compose des quatre étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="26b4c-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="26b4c-119">Mettre à jour les enregistrements DNS pour qu'ils pointent vers Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26b4c-119">Update DNS records to point to Microsoft 365.</span></span>

2. <span data-ttu-id="26b4c-120">Modifiez le mode de coexistence de votre organisation Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="26b4c-120">Change the coexistence mode for your organization to Teams Only.</span></span>

3. <span data-ttu-id="26b4c-121">Désactivez l’espace d’adressaie sip partagé (également appelé « domaine fractioné ») dans l Microsoft 365'organisation.</span><span class="sxs-lookup"><span data-stu-id="26b4c-121">Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization.</span></span>

4. <span data-ttu-id="26b4c-122">Désactivez la possibilité en local de communiquer avec les Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26b4c-122">Disable the ability in on-premises to communicate with Microsoft 365.</span></span>

<span data-ttu-id="26b4c-123">Ces étapes séparent logiquement votre déploiement local de Skype Entreprise Server de Microsoft 365 et assurez-vous que votre organisation est entièrement Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="26b4c-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="26b4c-124">Les détails de chaque étape sont fournis dans cet article.</span><span class="sxs-lookup"><span data-stu-id="26b4c-124">Details for each step are provided in this article.</span></span> <span data-ttu-id="26b4c-125">Une fois l’installation terminée, vous pouvez désaffecter votre déploiement local Skype Entreprise à l’aide de l’une des deux méthodes référencés ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="26b4c-125">Once that is complete, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced below.</span></span>

> [!Important] 
> <span data-ttu-id="26b4c-126">Une fois cette séparation logique terminée, les attributs msRTCSIP de votre active Directory local ont toujours des valeurs et continueront à se synchroniser via Azure AD Connecter dans Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26b4c-126">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="26b4c-127">La façon dont vous désaffectez l’environnement local varie selon que vous avez l’intention de laisser ces attributs en place ou de les effacer d’abord de votre environnement Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="26b4c-127">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="26b4c-128">Sachez que l’effacement des attributs msRTCSIP locaux une fois que vous avez migré à partir de l’local peut entraîner une perte de service pour les utilisateurs !</span><span class="sxs-lookup"><span data-stu-id="26b4c-128">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="26b4c-129">Les détails et les compromis des deux approches de désaffectation sont décrits plus loin.</span><span class="sxs-lookup"><span data-stu-id="26b4c-129">Details and tradeoffs of the two decommissioning approaches are described later.</span></span>

## <a name="detailed-steps"></a><span data-ttu-id="26b4c-130">Étapes détaillées</span><span class="sxs-lookup"><span data-stu-id="26b4c-130">Detailed Steps</span></span>

1. <span data-ttu-id="26b4c-131">*Mettez à jour le DNS pour qu’il pointe vers Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="26b4c-131">*Update DNS to point to Microsoft 365.*</span></span> <span data-ttu-id="26b4c-132">Le DNS externe de l’organisation pour l’organisation sur site doit être mis à jour afin que les enregistrements Skype Entreprise pointent vers Microsoft 365 au lieu du déploiement local.</span><span class="sxs-lookup"><span data-stu-id="26b4c-132">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="26b4c-133">Notamment :</span><span class="sxs-lookup"><span data-stu-id="26b4c-133">Specifically:</span></span>

    |<span data-ttu-id="26b4c-134">Type d’enregistrement</span><span class="sxs-lookup"><span data-stu-id="26b4c-134">Record type</span></span>|<span data-ttu-id="26b4c-135">Nom</span><span class="sxs-lookup"><span data-stu-id="26b4c-135">Name</span></span>|<span data-ttu-id="26b4c-136">Durée de vie</span><span class="sxs-lookup"><span data-stu-id="26b4c-136">TTL</span></span>|<span data-ttu-id="26b4c-137">Priorité</span><span class="sxs-lookup"><span data-stu-id="26b4c-137">Priority</span></span>|<span data-ttu-id="26b4c-138">Pondération</span><span class="sxs-lookup"><span data-stu-id="26b4c-138">Weight</span></span>|<span data-ttu-id="26b4c-139">Port</span><span class="sxs-lookup"><span data-stu-id="26b4c-139">Port</span></span>|<span data-ttu-id="26b4c-140">Value (Valeur)</span><span class="sxs-lookup"><span data-stu-id="26b4c-140">Value</span></span>|
    |---|---|---|---|---|---|---|
    |<span data-ttu-id="26b4c-141">SRV</span><span class="sxs-lookup"><span data-stu-id="26b4c-141">SRV</span></span>|<span data-ttu-id="26b4c-142">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="26b4c-142">_sipfederationtls._tcp</span></span>|<span data-ttu-id="26b4c-143">3600</span><span class="sxs-lookup"><span data-stu-id="26b4c-143">3600</span></span>|<span data-ttu-id="26b4c-144">100</span><span class="sxs-lookup"><span data-stu-id="26b4c-144">100</span></span>|<span data-ttu-id="26b4c-145">1</span><span class="sxs-lookup"><span data-stu-id="26b4c-145">1</span></span>|<span data-ttu-id="26b4c-146">5061</span><span class="sxs-lookup"><span data-stu-id="26b4c-146">5061</span></span>|<span data-ttu-id="26b4c-147">sipfed.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="26b4c-147">sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="26b4c-148">SRV</span><span class="sxs-lookup"><span data-stu-id="26b4c-148">SRV</span></span>|<span data-ttu-id="26b4c-149">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="26b4c-149">_sip._tls</span></span>|<span data-ttu-id="26b4c-150">3600</span><span class="sxs-lookup"><span data-stu-id="26b4c-150">3600</span></span>|<span data-ttu-id="26b4c-151">100</span><span class="sxs-lookup"><span data-stu-id="26b4c-151">100</span></span>|<span data-ttu-id="26b4c-152">1</span><span class="sxs-lookup"><span data-stu-id="26b4c-152">1</span></span>|<span data-ttu-id="26b4c-153">443</span><span class="sxs-lookup"><span data-stu-id="26b4c-153">443</span></span>|<span data-ttu-id="26b4c-154">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="26b4c-154">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="26b4c-155">CNAME</span><span class="sxs-lookup"><span data-stu-id="26b4c-155">CNAME</span></span>| <span data-ttu-id="26b4c-156">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="26b4c-156">lyncdiscover</span></span>|   <span data-ttu-id="26b4c-157">3600</span><span class="sxs-lookup"><span data-stu-id="26b4c-157">3600</span></span>| | | |<span data-ttu-id="26b4c-158">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="26b4c-158">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="26b4c-159">CNAME</span><span class="sxs-lookup"><span data-stu-id="26b4c-159">CNAME</span></span>| <span data-ttu-id="26b4c-160">sip</span><span class="sxs-lookup"><span data-stu-id="26b4c-160">sip</span></span>|    <span data-ttu-id="26b4c-161">3600</span><span class="sxs-lookup"><span data-stu-id="26b4c-161">3600</span></span>| | | | <span data-ttu-id="26b4c-162">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="26b4c-162">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="26b4c-163">En outre, les enregistrements CNAME pour la meet ou dialin (le cas présent) peuvent être supprimés.</span><span class="sxs-lookup"><span data-stu-id="26b4c-163">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="26b4c-164">Enfin, tous les enregistrements DNS Skype Entreprise votre réseau interne doivent être supprimés.</span><span class="sxs-lookup"><span data-stu-id="26b4c-164">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="26b4c-165">Dans de rares cas, le fait de changer le DNS de pointage local en Microsoft 365 pour votre organisation peut entraîner l’arrêt de la fédération avec d’autres organisations jusqu’à ce que cette autre organisation met à jour sa configuration de fédération :</span><span class="sxs-lookup"><span data-stu-id="26b4c-165">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="26b4c-166">Toutes les organisations fédérées qui utilisent l’ancien modèle de fédération directe (également appelé serveur partenaire autorisé) doivent mettre à jour leurs entrées de domaine autorisées pour que leur organisation supprime le nom de domaine réservé au proxy.</span><span class="sxs-lookup"><span data-stu-id="26b4c-166">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="26b4c-167">Ce modèle de fédération hérité n’est pas basé sur des enregistrements DNS SRV, de sorte qu’une telle configuration ne sera plus à jour une fois que votre organisation sera installée dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="26b4c-167">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="26b4c-168">Toute organisation fédérée qui n’a pas de fournisseur d’hébergement activé pour sipfed.online.lync. <span> com devra mettre à jour sa configuration pour l’activer.</span><span class="sxs-lookup"><span data-stu-id="26b4c-168">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="26b4c-169">Cette situation n’est possible que si l’organisation fédérée est purement sur site et n’a jamais été fédérée avec un client hybride ou en ligne.</span><span class="sxs-lookup"><span data-stu-id="26b4c-169">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="26b4c-170">Dans ce cas, la fédération avec ces organisations ne fonctionne pas tant qu’elles n’ont pas activé leur fournisseur d’hébergement.</span><span class="sxs-lookup"><span data-stu-id="26b4c-170">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="26b4c-171">Si vous pensez que l’un de vos partenaires fédérés peut utiliser la fédération directe ou n’avoir été fédéré avec aucune organisation en ligne ou hybride, nous vous suggérons de leur envoyer une communication à ce sujet lorsque vous vous préparez à terminer votre migration vers le cloud.</span><span class="sxs-lookup"><span data-stu-id="26b4c-171">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

2.  <span data-ttu-id="26b4c-172">*Modifiez le mode de coexistence de votre organisation Teams uniquement.*</span><span class="sxs-lookup"><span data-stu-id="26b4c-172">*Change the coexistence mode for your organization to Teams Only.*</span></span> <span data-ttu-id="26b4c-173">Cela garantit que tout nouvel utilisateur de votre organisation est toujours créé en tant qu’Teams utilisateur uniquement.</span><span class="sxs-lookup"><span data-stu-id="26b4c-173">This ensures that any new user in your organization is always created as a Teams Only user.</span></span> <span data-ttu-id="26b4c-174">En outre, si vous essayez de modifier le mode client en mode Teams Seul vérifie automatiquement l’existence d’enregistrements DNS locaux qui ont pu être manqués à l’étape 1 et identifie ces enregistrements dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="26b4c-174">In addition,  attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span>  <span data-ttu-id="26b4c-175">Si vous modifiez le mode client Teams seul ne réussira pas tant que tous les enregistrements DNS de votre organizaiton n’auront pas été mis à jour.</span><span class="sxs-lookup"><span data-stu-id="26b4c-175">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organizaiton are updated.</span></span> <span data-ttu-id="26b4c-176">Pour modifier le mode client en mode Teams exécutez uniquement la commande suivante à partir d’Teams fenêtre PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26b4c-176">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
     ```
<span data-ttu-id="26b4c-177">Vous pouvez également utiliser le Centre d’administration Teams pour modifier le mode de coexistence client en TeamsOnly, sous « Paramètres à l’échelle de l’organisation » -> « Mise à niveau Teams client ».</span><span class="sxs-lookup"><span data-stu-id="26b4c-177">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    
    
3.  <span data-ttu-id="26b4c-178">*Désactivez l’espace d’adressaie sip partagé dans Microsoft 365 organisation.*</span><span class="sxs-lookup"><span data-stu-id="26b4c-178">*Disable shared sip address space in Microsoft 365 organization.*</span></span> <span data-ttu-id="26b4c-179">La commande ci-dessous doit être effectuée à partir d’une Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26b4c-179">The command below needs to be done from a Teams PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
4.  <span data-ttu-id="26b4c-180">*Désactivez la possibilité en local de communiquer avec les Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="26b4c-180">*Disable the ability in on-premises to communicate with Microsoft 365.*</span></span> <span data-ttu-id="26b4c-181">La commande ci-dessous doit être effectuée à partir d’une fenêtre PowerShell sur site :</span><span class="sxs-lookup"><span data-stu-id="26b4c-181">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="26b4c-182">Gestion des attributs après le déplacement d’utilisateurs de l’local vers le cloud</span><span class="sxs-lookup"><span data-stu-id="26b4c-182">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="26b4c-183">Par défaut, tous les utilisateurs qui ont été précédemment activés pour Skype Entreprise Server puis déplacés vers le cloud ont toujours des attributs msRTCSIP configurés dans votre annuaire Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="26b4c-183">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="26b4c-184">Ces attributs, en particulier l’adresse sip (msRTCSIP-PrimaryUserAddress) et potentiellement le numéro de téléphone (msRTCSIP-Line), continuent de se synchroniser avec Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26b4c-184">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="26b4c-185">Si des modifications sont requises pour l’un des attributs msRTCSIP, ces modifications doivent être apportées dans l’annuaire Active Directory local, puis synchronisées avec Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26b4c-185">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="26b4c-186">Toutefois, une fois le déploiement Skype Entreprise Server supprimé, les outils Skype Entreprise Server ne seront pas disponibles pour gérer ces attributs.</span><span class="sxs-lookup"><span data-stu-id="26b4c-186">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="26b4c-187">Deux options sont disponibles pour gérer cette situation :</span><span class="sxs-lookup"><span data-stu-id="26b4c-187">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="26b4c-188">Laissez les utilisateurs qui ont été activés pour Skype Entreprise comptes serveur tels qu’ils sont et gérez les attributs msRTCSIP à l’aide des outils Active Directory.</span><span class="sxs-lookup"><span data-stu-id="26b4c-188">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="26b4c-189">Cela garantit l’absence de perte de service pour les utilisateurs migrés et vous permet de supprimer facilement le déploiement Skype Entreprise Server en éliminant (par exemple, la suppression) des serveurs, sans désaffectation complète.</span><span class="sxs-lookup"><span data-stu-id="26b4c-189">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="26b4c-190">Toutefois, les utilisateurs nouvellement titulaires d’une licence n’auront pas ces attributs dans votre annuaire Active Directory local et devront être gérés en ligne.</span><span class="sxs-lookup"><span data-stu-id="26b4c-190">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="26b4c-191">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span><span class="sxs-lookup"><span data-stu-id="26b4c-191">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="26b4c-192">Cette méthode permet une approche de gestion cohérente pour les utilisateurs existants et nouveaux, mais elle peut potentiellement entraîner une perte temporaire de service pendant le processus de mise hors service local.</span><span class="sxs-lookup"><span data-stu-id="26b4c-192">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="26b4c-193">Méthode 1 : gérer les adresses SIP et les numéros de téléphone des utilisateurs dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="26b4c-193">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="26b4c-194">Les administrateurs peuvent gérer les utilisateurs qui ont été précédemment déplacés d’une Skype Entreprise Server sur site vers le cloud, même après la désaffectation du déploiement local.</span><span class="sxs-lookup"><span data-stu-id="26b4c-194">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="26b4c-195">Si vous souhaitez apporter des modifications à l’adresse SIP d’un utilisateur ou au numéro de téléphone d’un utilisateur (et que l’adresse sip ou le numéro de téléphone a déjà une valeur dans l’annuaire Active Directory local), vous devez le faire dans l’annuaire Active Directory local et laisser les valeurs s’écouler jusqu’à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="26b4c-195">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="26b4c-196">Cela ne nécessite PAS de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="26b4c-196">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="26b4c-197">Au lieu de cela, vous pouvez modifier ces attributs directement dans Active Directory local, à l’aide du logiciel en ligne MMC Utilisateurs et ordinateurs Active Directory (comme illustré ci-dessous) ou à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26b4c-197">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="26b4c-198">Si vous utilisez le logiciel en snap-in MMC, ouvrez la page des propriétés de l’utilisateur, cliquez sur l’onglet Éditeur d’attributs et recherchez les attributs appropriés à modifier :</span><span class="sxs-lookup"><span data-stu-id="26b4c-198">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="26b4c-199">Pour modifier l’adresse SIP d’un utilisateur, modifiez le `msRTCSIP-PrimaryUserAddress` .</span><span class="sxs-lookup"><span data-stu-id="26b4c-199">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="26b4c-200">Si `ProxyAddresses` l’attribut contient une adresse SIP, mettez également à jour cette valeur en tant que meilleure pratique.</span><span class="sxs-lookup"><span data-stu-id="26b4c-200">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="26b4c-201">Bien que l’adresse sip dans soit ignorée par O365 si elle est remplie, elle peut être utilisée par d’autres `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` composants locaux.</span><span class="sxs-lookup"><span data-stu-id="26b4c-201">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="26b4c-202">Pour modifier le numéro de téléphone d’un utilisateur, modifiez `msRTCSIP-Line` *s’il a déjà une valeur.*</span><span class="sxs-lookup"><span data-stu-id="26b4c-202">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Outil utilisateurs et ordinateurs Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="26b4c-204">Si l’utilisateur n’avait à l’origine pas de valeur pour l’environnement local avant le déplacement, vous pouvez modifier le numéro de téléphone à l’aide du paramètre - dans `msRTCSIP-Line` l’cmdlet `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) du module Skype Entreprise Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="26b4c-204">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="26b4c-205">Ces étapes ne sont pas nécessaires pour les nouveaux utilisateurs créés après la désactivation de l’hybride, et ces utilisateurs peuvent être gérés directement dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="26b4c-205">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="26b4c-206">Si vous êtes à l’aise avec la combinaison de ces méthodes et si vous souhaitez laisser les attributs msRTCSIP en place dans votre environnement Active Directory local, vous pouvez simplement ré-imager les serveurs Skype Entreprise locaux.</span><span class="sxs-lookup"><span data-stu-id="26b4c-206">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="26b4c-207">Toutefois, si vous préférez effacer tous les attributs msRTCSIP et faire une désinstallation traditionnelle de Skype Entreprise Server, utilisez la méthode 2.</span><span class="sxs-lookup"><span data-stu-id="26b4c-207">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="26b4c-208">Méthode 2 : effacer Skype Entreprise pour tous les utilisateurs locaux dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="26b4c-208">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="26b4c-209">Cette option nécessite des efforts supplémentaires et une planification appropriée, car les utilisateurs qui ont été précédemment déplacés d’un Skype Entreprise Server local vers le cloud doivent être réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="26b4c-209">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="26b4c-210">Ces utilisateurs peuvent être classés dans deux catégories différentes : les utilisateurs sans Système téléphonique et les utilisateurs Système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="26b4c-210">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="26b4c-211">Les utilisateurs Système téléphonique seront temporairement perdus du service téléphonique dans le cadre de la transition du numéro de téléphone de la gestion dans Active Directory local vers le cloud.</span><span class="sxs-lookup"><span data-stu-id="26b4c-211">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="26b4c-212">**Il est recommandé d’effectuer un projet pilote impliquant un petit nombre d’utilisateurs avec Système téléphonique avant de démarrer des opérations utilisateur en bloc.**</span><span class="sxs-lookup"><span data-stu-id="26b4c-212">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="26b4c-213">Pour les déploiements de grande taille, les utilisateurs peuvent être traitées par groupes plus petits dans différentes fenêtres de temps.</span><span class="sxs-lookup"><span data-stu-id="26b4c-213">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="26b4c-214">Ce processus est plus simple pour les utilisateurs qui ont une adresse sip correspondante et UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="26b4c-214">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="26b4c-215">Pour les organisations dont les utilisateurs ont des valeurs non correspondantes dans ces deux attributs, une attention supplémentaire doit être prise comme indiqué ci-dessous pour une transition fluide.</span><span class="sxs-lookup"><span data-stu-id="26b4c-215">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="26b4c-216">Si vous avez configuré des points de terminaison d’application hybride sur site pour les attendants automatiques ou les files d’attente d’appels, veillez à déplacer ces points de terminaison vers Microsoft 365 avant de désaffecter Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="26b4c-216">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="26b4c-217">Confirmez que l’Skype Entreprise cmdlet PowerShell suivante renvoie un résultat vide.</span><span class="sxs-lookup"><span data-stu-id="26b4c-217">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="26b4c-218">Un résultat vide signifie qu’aucun utilisateur n’est installé en local et a été déplacé vers Microsoft 365 ou désactivé :</span><span class="sxs-lookup"><span data-stu-id="26b4c-218">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="26b4c-219">Enregistrez le numéro de téléphone actuel des utilisateurs (LineUri), UserPrincipalName et les informations associées en exécutant l’applet de Skype Entreprise Server PowerShell sur site suivante pour exporter les données utilisateur :</span><span class="sxs-lookup"><span data-stu-id="26b4c-219">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="26b4c-220">Avant de poursuivre lSfbUserSettings.csv fichier et de confirmer que toutes les données utilisateur ont bien été exportées.</span><span class="sxs-lookup"><span data-stu-id="26b4c-220">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="26b4c-221">Il est recommandé de conserver une copie de ce fichier.</span><span class="sxs-lookup"><span data-stu-id="26b4c-221">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="26b4c-222">N’utilisez pas ce fichier dans les étapes suivantes pour traiter les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="26b4c-222">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="26b4c-223">Créez un fichier avec un groupe d’utilisateurs à utiliser dans les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="26b4c-223">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="26b4c-224">Une fois le premier groupe d’utilisateurs terminé, continuez avec le groupe d’utilisateurs suivant.</span><span class="sxs-lookup"><span data-stu-id="26b4c-224">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="26b4c-225">Dans l’exemple ci-dessous, les groupes d’utilisateurs sont sélectionnés par ordre alphabétique, mais vous pouvez filtrer les utilisateurs en fonction de critères qui correspond à la façon dont vous souhaitez traiter les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="26b4c-225">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="26b4c-226">Avant de poursuivre lSfbUsers.csv fichier et de confirmer que les données utilisateur ont bien été exportées.</span><span class="sxs-lookup"><span data-stu-id="26b4c-226">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="26b4c-227">Vous aurez besoin de LineUri (numéro de téléphone), UserPrincipalName, SamAccountName et SipAddress à partir de ce fichier dans une étape ultérieure.</span><span class="sxs-lookup"><span data-stu-id="26b4c-227">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="26b4c-228">Supprimez les informations d’attribut Skype Entreprise Server d’Active Directory pour l’ensemble d’utilisateurs que vous êtes prêt à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="26b4c-228">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="26b4c-229">Ce processus est en deux étapes, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="26b4c-229">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="26b4c-230">Après le cycle de AAD Sync suivant après l’exécution de cette étape, les utilisateurs avec Système téléphonique qui ont été précédemment déplacés d’une Skype Entreprise Server sur site vers le cloud perdront la possibilité d’effectuer et de recevoir des appels jusqu’à ce que l’étape 8 soit correctement terminée et confirmée à l’étape 9.</span><span class="sxs-lookup"><span data-stu-id="26b4c-230">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="26b4c-231">En outre, assurez-vous que vous avez enregistré les numéros de téléphone et les informations connexes de l’utilisateur à l’étape 2, car ces informations sont requises pour cette étape.</span><span class="sxs-lookup"><span data-stu-id="26b4c-231">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="26b4c-232">Ensuite, pour le même ensemble d’utilisateurs, désinsértez la valeur de msRTCSIP-DeploymentLocator à l’aide d’Active Directory PowerShell local :</span><span class="sxs-lookup"><span data-stu-id="26b4c-232">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="26b4c-233">Exécutez le module Active Directory local suivant pour Windows PowerShell cmdlet pour rajouter une valeur d’adresse sip aux adresses proxy Active Directory sur site.</span><span class="sxs-lookup"><span data-stu-id="26b4c-233">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="26b4c-234">Cela permet d’éviter les problèmes d’interopérabilité qui dépendent de cet attribut.</span><span class="sxs-lookup"><span data-stu-id="26b4c-234">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="26b4c-235">Exécuter Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="26b4c-235">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="26b4c-236">Attendez la fin de la mise en service de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="26b4c-236">Wait for user provisioning to complete.</span></span> <span data-ttu-id="26b4c-237">Vous pouvez surveiller la progression de l’approvisionnement des utilisateurs en exécutant la commande PowerShell Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="26b4c-237">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="26b4c-238">La commande Skype Entreprise Online PowerShell renvoie un résultat vide dès que le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="26b4c-238">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="26b4c-239">Exécutez la commande PowerShell Skype Entreprise Online suivante pour affecter des numéros de téléphone et activer les utilisateurs pour Système téléphonique :</span><span class="sxs-lookup"><span data-stu-id="26b4c-239">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="26b4c-240">Si vous avez encore Skype Entreprise points de terminaison (clients Skype ou téléphones tiers), vous devez également définir -HostedVoiceMail sur $true.</span><span class="sxs-lookup"><span data-stu-id="26b4c-240">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="26b4c-241">Si votre organisation utilise uniquement des points Teams pour les utilisateurs à reconnaissance vocale, ce paramètre n’est pas applicable à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="26b4c-241">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="26b4c-242">Confirmez que les utilisateurs Système téléphonique fonctionnalités ont été correctement mis en service.</span><span class="sxs-lookup"><span data-stu-id="26b4c-242">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="26b4c-243">La commande Skype Entreprise Online PowerShell renvoie un résultat vide dès que le processus est terminé.</span><span class="sxs-lookup"><span data-stu-id="26b4c-243">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="26b4c-244">Répétez les étapes 3 à 9 jusqu’à ce que tous les utilisateurs soient traitées.</span><span class="sxs-lookup"><span data-stu-id="26b4c-244">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="26b4c-245">Confirmez que tous les utilisateurs ont été correctement traitées en exécutant les deux commandes PowerShell suivantes.</span><span class="sxs-lookup"><span data-stu-id="26b4c-245">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="26b4c-246">Commande PowerShell Skype Entreprise Server sur site :</span><span class="sxs-lookup"><span data-stu-id="26b4c-246">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="26b4c-247">Skype Entreprise Commande PowerShell en ligne :</span><span class="sxs-lookup"><span data-stu-id="26b4c-247">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="26b4c-248">Après avoir effectué toutes les étapes de la méthode 2, voir Déplacer des points de terminaison [d’application](decommission-move-on-prem-endpoints.md) hybride de l’local vers l’application en ligne et Supprimer votre Skype Entreprise Server sur site pour obtenir des [étapes](decommission-remove-on-prem.md) supplémentaires pour supprimer votre déploiement local Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="26b4c-248">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="26b4c-249">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26b4c-249">See also</span></span>

- [<span data-ttu-id="26b4c-250">Consolidation du cloud pour Teams et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="26b4c-250">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="26b4c-251">Mise hors service de votre environnement Skype pour entreprises sur site</span><span class="sxs-lookup"><span data-stu-id="26b4c-251">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

