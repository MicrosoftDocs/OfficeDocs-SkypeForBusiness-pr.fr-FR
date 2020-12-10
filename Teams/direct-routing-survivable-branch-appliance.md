---
title: Service de routage direct SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: En savoir plus sur le routage direct, tel que la configuration, les décisions de déploiement principales nécessaires et les considérations en matière de routage vocal.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b30f8a435f256edc816ebeea075425fddeaf8bb
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611788"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="ceaa2-103">Appareil de branchement survivant (SBA) pour le routage direct-Aperçu public</span><span class="sxs-lookup"><span data-stu-id="ceaa2-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="ceaa2-104">Il s’agit d’une version bêta publique.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-104">This is a public preview release.</span></span>

<span data-ttu-id="ceaa2-105">Occasionnellement, un site client utilisant le routage direct pour se connecter au système Microsoft Phone peut rencontrer une panne Internet.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="ceaa2-106">Supposez que le site du client (appelé succursale) ne peut pas se connecter à Microsoft Cloud par le biais du routage direct.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="ceaa2-107">Toutefois, l’intranet au sein de la succursale reste entièrement fonctionnel et les utilisateurs peuvent se connecter au contrôleur de bordure de session (SBC) fournissant une connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="ceaa2-108">Cet article décrit comment utiliser une application de branchement Survivable (SBA) pour permettre au système Microsoft Phone de continuer à passer et à recevoir des appels de réseau téléphonique commuté (PSTN) en cas de panne.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ceaa2-109">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="ceaa2-109">Prerequisites</span></span>

<span data-ttu-id="ceaa2-110">Le code de l’erreur SBA est fourni par Microsoft aux fournisseurs de SBC qui incorporent ensuite le code dans le microprogramme de leur SBCs.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed the code into the firmware of their SBCs.</span></span> 

<span data-ttu-id="ceaa2-111">Pour obtenir le dernier microprogramme de contrôleur de bordure de session avec l’appareil de branchement Survivable intégré, contactez votre fournisseur de SBC.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="ceaa2-112">Par ailleurs, les informations suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-112">In addition, the following is required:</span></span>

- <span data-ttu-id="ceaa2-113">L’élément SBC doit être configuré pour la dérivation de média pour s’assurer que le client Microsoft teams dans le site de succursale peut mettre le contenu multimédia en flux direct avec l’SBC.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="ceaa2-114">TLS 1.2 doit être activé sur le système d’exploitation de l’ordinateur virtuel SBA.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="ceaa2-115">Clients équipes pris en charge</span><span class="sxs-lookup"><span data-stu-id="ceaa2-115">Supported Teams clients</span></span>

<span data-ttu-id="ceaa2-116">La fonction SBA est prise en charge sur les clients Microsoft teams suivants :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="ceaa2-117">Bureau Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="ceaa2-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="ceaa2-118">Bureau Microsoft teams macOS</span><span class="sxs-lookup"><span data-stu-id="ceaa2-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="ceaa2-119">Mode de fonctionnement</span><span class="sxs-lookup"><span data-stu-id="ceaa2-119">How it works</span></span>

<span data-ttu-id="ceaa2-120">Au cours d’une panne d’Internet, le client teams doit basculer vers le SBA automatiquement et les appels en cours continuent sans interruption.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="ceaa2-121">Aucune action n’est requise de la part de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-121">No action is required from the user.</span></span> <span data-ttu-id="ceaa2-122">Dès que le client teams a détecté que la connexion à Internet fonctionne et que tous les appels sortants sont terminés, le client revient au mode de fonctionnement normal et se connecte à d’autres services Teams.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="ceaa2-123">Le SBA télécharge les enregistrements de données d’appel collectés vers le Cloud et l’historique des appels sera mis à jour de manière à ce que ces informations puissent être consultées par l’administrateur client.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="ceaa2-124">Lorsque le client Microsoft teams est en mode hors connexion, les fonctionnalités d’appel suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="ceaa2-125">Appels RTC par le biais d’un réseau local SBA/SBC avec les contenus multimédias acheminés par l’intermédiaire de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="ceaa2-126">Réception d’appels RTC par le biais d’un réseau local SBA/SBC avec média passant par le SBC.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="ceaa2-127">Mise en attente et reprise d’appels RTC.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="ceaa2-128">Configuration</span><span class="sxs-lookup"><span data-stu-id="ceaa2-128">Configuration</span></span>

<span data-ttu-id="ceaa2-129">Pour que la fonctionnalité SBA fonctionne, le client teams doit savoir quels SBAs sont disponibles dans chaque site de filiale et quels SBAs sont attribués aux utilisateurs de ce site.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="ceaa2-130">Les étapes de configuration sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="ceaa2-131">Créez l’SBAs.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-131">Create the SBAs.</span></span>
2. <span data-ttu-id="ceaa2-132">Créer la stratégie de survie de la succursale Teams.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="ceaa2-133">Affectez la stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="ceaa2-134">Enregistrez une application pour le SBA avec Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="ceaa2-135">La configuration est terminée en utilisant les cmdlets PowerShell de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="ceaa2-136">(Le centre d’administration Teams ne prend pas encore en charge la fonctionnalité de routage directe SBA.)</span><span class="sxs-lookup"><span data-stu-id="ceaa2-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="ceaa2-137">(Pour plus d’informations sur la configuration de l’SBC, avec des liens vers la documentation du fournisseur SBC, voir Configuration de contrôleur de bordure de session à la fin de cet article.)</span><span class="sxs-lookup"><span data-stu-id="ceaa2-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="ceaa2-138">Créer le SBAs</span><span class="sxs-lookup"><span data-stu-id="ceaa2-138">Create the SBAs</span></span>

<span data-ttu-id="ceaa2-139">Pour créer le SBAs, vous devez utiliser l’applet de passe New-CsTeamsSurvivableBranchAppliance.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="ceaa2-140">Cette applet de commande a les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="ceaa2-141">Paramètre</span><span class="sxs-lookup"><span data-stu-id="ceaa2-141">Parameter</span></span>| <span data-ttu-id="ceaa2-142">Description</span><span class="sxs-lookup"><span data-stu-id="ceaa2-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="ceaa2-143">Identity</span><span class="sxs-lookup"><span data-stu-id="ceaa2-143">Identity</span></span>  | <span data-ttu-id="ceaa2-144">Identité de l’SBA</span><span class="sxs-lookup"><span data-stu-id="ceaa2-144">The identity of the SBA</span></span>  |
| <span data-ttu-id="ceaa2-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="ceaa2-145">Fqdn</span></span> | <span data-ttu-id="ceaa2-146">Nom de domaine complet du SBA</span><span class="sxs-lookup"><span data-stu-id="ceaa2-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="ceaa2-147">Site</span><span class="sxs-lookup"><span data-stu-id="ceaa2-147">Site</span></span> | <span data-ttu-id="ceaa2-148">Le TenantNetworkSite dans lequel se trouve l’SBA</span><span class="sxs-lookup"><span data-stu-id="ceaa2-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="ceaa2-149">Description</span><span class="sxs-lookup"><span data-stu-id="ceaa2-149">Description</span></span> | <span data-ttu-id="ceaa2-150">Mettre en forme du texte libre</span><span class="sxs-lookup"><span data-stu-id="ceaa2-150">Free format text</span></span> |
|||

<span data-ttu-id="ceaa2-151">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="ceaa2-152">Créer la stratégie de survie de la succursale teams</span><span class="sxs-lookup"><span data-stu-id="ceaa2-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="ceaa2-153">Pour créer une stratégie, vous devez utiliser l’applet de New-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="ceaa2-154">Ce cmdlet a les paramètres suivants.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="ceaa2-155">Notez que la stratégie peut contenir au moins un SBAs.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="ceaa2-156">Paramètre</span><span class="sxs-lookup"><span data-stu-id="ceaa2-156">Parameter</span></span>| <span data-ttu-id="ceaa2-157">Description</span><span class="sxs-lookup"><span data-stu-id="ceaa2-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="ceaa2-158">Identity</span><span class="sxs-lookup"><span data-stu-id="ceaa2-158">Identity</span></span> | <span data-ttu-id="ceaa2-159">Identité de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-159">The identity of the policy</span></span> |
| <span data-ttu-id="ceaa2-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="ceaa2-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="ceaa2-161">Nom de domaine complet (FQDN) du site</span><span class="sxs-lookup"><span data-stu-id="ceaa2-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="ceaa2-162">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="ceaa2-163">Vous pouvez ajouter ou supprimer SBAs d’une stratégie à l’aide de l’applet de Set-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="ceaa2-164">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="ceaa2-165">Attribuer une stratégie à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="ceaa2-165">Assign a policy to a user</span></span>

<span data-ttu-id="ceaa2-166">Pour affecter la stratégie à des utilisateurs individuels, vous devez utiliser l’applet de Grant-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="ceaa2-167">Ce cmdlet comporte les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="ceaa2-168">Paramètre</span><span class="sxs-lookup"><span data-stu-id="ceaa2-168">Parameter</span></span>| <span data-ttu-id="ceaa2-169">Description</span><span class="sxs-lookup"><span data-stu-id="ceaa2-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="ceaa2-170">Identity</span><span class="sxs-lookup"><span data-stu-id="ceaa2-170">Identity</span></span> | <span data-ttu-id="ceaa2-171">Identité de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-171">The identity of the user</span></span> |
| <span data-ttu-id="ceaa2-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="ceaa2-172">PolicyName</span></span> | <span data-ttu-id="ceaa2-173">Identité de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-173">The identity of the policy</span></span> |
||

<span data-ttu-id="ceaa2-174">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="ceaa2-175">Vous pouvez supprimer une stratégie d’un utilisateur en autorisant la stratégie de $Null comme le montre l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="ceaa2-176">Inscrire une application pour l’SBA auprès d’Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ceaa2-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="ceaa2-177">Pour permettre à différentes SBAs d’être utilisés dans votre client pour lire les données requises de Microsoft 365, vous devez inscrire une application pour l’SBA auprès d’Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="ceaa2-178">Pour plus d’informations sur l’inscription des applications, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="ceaa2-179">Développer des applications métier pour Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ceaa2-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="ceaa2-180">[Enregistrez une application à l’aide de la plateforme d’identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="ceaa2-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="ceaa2-181">Il vous suffit d’inscrire une seule application pour pouvoir l’utiliser dans tous les SBAs de votre client.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="ceaa2-182">Pour l’inscription SBA, vous avez besoin des valeurs suivantes créées par l’inscription :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="ceaa2-183">ID de l’application (client)</span><span class="sxs-lookup"><span data-stu-id="ceaa2-183">Application (client) ID</span></span> 
- <span data-ttu-id="ceaa2-184">Clé secrète client</span><span class="sxs-lookup"><span data-stu-id="ceaa2-184">Client secret</span></span> 

<span data-ttu-id="ceaa2-185">Pour l’application SBA, gardez les points suivants à l’esprit :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="ceaa2-186">Il peut s’agir du nom de votre choix.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="ceaa2-187">Types de comptes pris en charge = compte uniquement dans cet annuaire d’organisation.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="ceaa2-188">URI de redirection Web = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="ceaa2-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="ceaa2-189">Jetons d’attribution implicite = jetons d’accès et jetons d’ID.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="ceaa2-190">Autorisations d’API = autorisation d’accès de l’administrateur client de Skype et teams-> > application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="ceaa2-191">Clé secrète client : vous pouvez utiliser n’importe quelle description et votre date d’expiration.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="ceaa2-192">N’oubliez pas de copier la clé secrète du client immédiatement après l’avoir créée.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="ceaa2-193">L’ID de l’application (client) est affiché dans l’onglet vue d’ensemble.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="ceaa2-194">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-194">Then follow these steps:</span></span>

1. <span data-ttu-id="ceaa2-195">Enregistrez l’application.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-195">Register the application.</span></span>
2. <span data-ttu-id="ceaa2-196">Définissez les jetons d’attribution implicite.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="ceaa2-197">Définissez les autorisations d’API.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-197">Set the API permissions.</span></span>
4. <span data-ttu-id="ceaa2-198">Créez la clé secrète client.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="ceaa2-199">Configuration du contrôleur de bordure de session</span><span class="sxs-lookup"><span data-stu-id="ceaa2-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="ceaa2-200">Pour obtenir des instructions détaillées sur la configuration de votre contrôleur de bordure de session avec l’appareil de branche Survivable intégré, voir la documentation fournie par votre fournisseur de SBC :</span><span class="sxs-lookup"><span data-stu-id="ceaa2-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="ceaa2-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="ceaa2-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="ceaa2-202">»</span><span class="sxs-lookup"><span data-stu-id="ceaa2-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="ceaa2-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="ceaa2-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="ceaa2-204">TE-systèmes</span><span class="sxs-lookup"><span data-stu-id="ceaa2-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="ceaa2-205">Signalement de problèmes</span><span class="sxs-lookup"><span data-stu-id="ceaa2-205">Reporting issues</span></span>

<span data-ttu-id="ceaa2-206">Signaler les problèmes à l’organisation du support technique de votre fournisseur de SBC.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="ceaa2-207">Lorsque vous signalez le problème, indiquez que vous disposez d’une unité de branchement survivant configurée.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ceaa2-208">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="ceaa2-208">Known issues</span></span>

- <span data-ttu-id="ceaa2-209">Lorsque vous ajoutez de nouvelles applications de succursales survivant, il est possible que vous deviez prendre un peu de temps pour pouvoir les utiliser dans les stratégies de l’appareil de branchement Survivables.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="ceaa2-210">Lorsque vous attribuez une stratégie d’appareil de succursale Survivable à un utilisateur, l’affichage de la stratégie Get-CsOnlineUser peut prendre un peu de temps.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="ceaa2-211">La recherche de numéro inversée des contacts Azure AD n’est pas effectuée.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="ceaa2-212">Le SBA ne prend pas en charge les paramètres de transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="ceaa2-213">Les appels d’urgence vers un numéro d’urgence configuré pour les appels d’urgence dynamiques (E911) ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="ceaa2-214">La sortie de Get-CsOnlineUser montre TeamsBranchSurvivabilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="ceaa2-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
