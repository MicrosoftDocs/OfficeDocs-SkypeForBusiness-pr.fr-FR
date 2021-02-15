---
title: Direct Routing SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
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
description: En savoir plus sur le routage direct, comme la configuration, les décisions de déploiement essentielles nécessaires et les considérations relatives au routage vocal.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fb8812fd025317eb9c6e3c67ce1f5fcea094978
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196488"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="36c10-103">Appliance de branche (SBA) survivable pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="36c10-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="36c10-104">Parfois, un site client utilisant le routage direct pour se connecter à Microsoft Phone System peut être en panne sur Internet.</span><span class="sxs-lookup"><span data-stu-id="36c10-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="36c10-105">Supposons que le site du client (appelé branche) ne puisse pas se connecter temporairement au cloud Microsoft via un routage direct.</span><span class="sxs-lookup"><span data-stu-id="36c10-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="36c10-106">Toutefois, l’intranet à l’intérieur de la branche est toujours pleinement fonctionnel et les utilisateurs peuvent se connecter au contrôleur de session en bordure (SBC) qui fournit la connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="36c10-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="36c10-107">Cet article décrit comment utiliser une appliance de branche permettant de survivre pour permettre à Microsoft Phone System de continuer à passer et à recevoir des appels de réseau téléphonique commuté (PSTN) en cas de panne.</span><span class="sxs-lookup"><span data-stu-id="36c10-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36c10-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="36c10-108">Prerequisites</span></span>

<span data-ttu-id="36c10-109">Le code SBA est fourni par les fournisseurs Microsoft à SBC qui incorporent ensuite le code dans leur microprogramme ou le distribuez séparément pour que SBA soit exécuté sur une version VM ou un matériel distinct.</span><span class="sxs-lookup"><span data-stu-id="36c10-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="36c10-110">Pour obtenir la dernière version du microprogramme du contrôleur de session en bordure avec l’appliance de branche survivable incorporée, contactez votre fournisseur SBC.</span><span class="sxs-lookup"><span data-stu-id="36c10-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="36c10-111">De plus, les suivantes sont obligatoires :</span><span class="sxs-lookup"><span data-stu-id="36c10-111">In addition, the following is required:</span></span>

- <span data-ttu-id="36c10-112">Le SBC doit être configuré pour la dérivation média afin de s’assurer que le client Microsoft Teams sur le site de branche peut faire circuler le média directement avec le SBC.</span><span class="sxs-lookup"><span data-stu-id="36c10-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="36c10-113">TLS1.2 doit être activé sur le système d’exploitation VM SBA.</span><span class="sxs-lookup"><span data-stu-id="36c10-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="36c10-114">Clients Teams pris en charge</span><span class="sxs-lookup"><span data-stu-id="36c10-114">Supported Teams clients</span></span>

<span data-ttu-id="36c10-115">La fonctionnalité SBA est prise en charge sur les clients Microsoft Teams suivants :</span><span class="sxs-lookup"><span data-stu-id="36c10-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="36c10-116">Microsoft Teams pour Bureau Windows</span><span class="sxs-lookup"><span data-stu-id="36c10-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="36c10-117">Bureau Microsoft Teams macOS</span><span class="sxs-lookup"><span data-stu-id="36c10-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="36c10-118">Mode de fonctionnement</span><span class="sxs-lookup"><span data-stu-id="36c10-118">How it works</span></span>

<span data-ttu-id="36c10-119">En cas d’interruption d’Internet, le client Teams doit basculer automatiquement vers le SBA, et les appels en cours doivent continuer sans interruptions.</span><span class="sxs-lookup"><span data-stu-id="36c10-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="36c10-120">Aucune action n’est requise de la part de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="36c10-120">No action is required from the user.</span></span> <span data-ttu-id="36c10-121">Dès que le client Teams détecte qu’Internet est en cours et que tous les appels sortants sont terminés, le client revient en mode d’utilisation normal et se connecte aux autres services Teams.</span><span class="sxs-lookup"><span data-stu-id="36c10-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="36c10-122">Le SBA charge les enregistrements de données d’appel collectés dans le cloud et l’historique des appels est mis à jour de sorte que ces informations soient disponibles pour révision par l’administrateur client.</span><span class="sxs-lookup"><span data-stu-id="36c10-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="36c10-123">Lorsque le client Microsoft Teams est en mode hors connexion, la fonctionnalité d’appel suivante est disponible :</span><span class="sxs-lookup"><span data-stu-id="36c10-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="36c10-124">Passer des appels PSTN via SBA/SBC local avec les médias s’écoule dans le SBC.</span><span class="sxs-lookup"><span data-stu-id="36c10-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="36c10-125">Réception d’appels PSTN via SBA/SBC local, avec trafic de médias par le SBC.</span><span class="sxs-lookup"><span data-stu-id="36c10-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="36c10-126">Appels PSTN en attente et reprise.</span><span class="sxs-lookup"><span data-stu-id="36c10-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="36c10-127">Configuration</span><span class="sxs-lookup"><span data-stu-id="36c10-127">Configuration</span></span>

<span data-ttu-id="36c10-128">Pour que la fonctionnalité SBA fonctionne, le client Teams doit savoir quels SBA sont disponibles sur chaque site de succursale et quels sont affectés aux utilisateurs de ce site.</span><span class="sxs-lookup"><span data-stu-id="36c10-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="36c10-129">Les étapes de configuration sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="36c10-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="36c10-130">Créez les SBA.</span><span class="sxs-lookup"><span data-stu-id="36c10-130">Create the SBAs.</span></span>
2. <span data-ttu-id="36c10-131">Créez la stratégie de survivance de la branche Teams.</span><span class="sxs-lookup"><span data-stu-id="36c10-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="36c10-132">Attribuez la stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="36c10-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="36c10-133">Enregistrez une application pour SBA auprès d’Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="36c10-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="36c10-134">Toute la configuration est effectuée à l’aide des cmdlets PowerShell Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="36c10-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="36c10-135">(Le Centre d’administration Teams ne prend pas encore en charge la fonctionnalité SBA de routage direct.)</span><span class="sxs-lookup"><span data-stu-id="36c10-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="36c10-136">(Pour plus d’informations sur la configuration du SBC, avec des liens vers la documentation du fournisseur SBC, consultez la configuration du contrôleur de session en bordure à la fin de cet article.)</span><span class="sxs-lookup"><span data-stu-id="36c10-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="36c10-137">Créer les SBA</span><span class="sxs-lookup"><span data-stu-id="36c10-137">Create the SBAs</span></span>

<span data-ttu-id="36c10-138">Pour créer les SBA, vous devez utiliser la cmdlet New-CsTeamsSurvivableBranchAppliance'entrée.</span><span class="sxs-lookup"><span data-stu-id="36c10-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="36c10-139">Cette cmdlet a les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="36c10-139">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="36c10-140">Paramètre</span><span class="sxs-lookup"><span data-stu-id="36c10-140">Parameter</span></span>| <span data-ttu-id="36c10-141">Description</span><span class="sxs-lookup"><span data-stu-id="36c10-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="36c10-142">Identity</span><span class="sxs-lookup"><span data-stu-id="36c10-142">Identity</span></span>  | <span data-ttu-id="36c10-143">Identité du SBA</span><span class="sxs-lookup"><span data-stu-id="36c10-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="36c10-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="36c10-144">Fqdn</span></span> | <span data-ttu-id="36c10-145">FQDN du SBA</span><span class="sxs-lookup"><span data-stu-id="36c10-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="36c10-146">Site</span><span class="sxs-lookup"><span data-stu-id="36c10-146">Site</span></span> | <span data-ttu-id="36c10-147">Site TenantNetworkSite où se trouve le site SBA</span><span class="sxs-lookup"><span data-stu-id="36c10-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="36c10-148">Description</span><span class="sxs-lookup"><span data-stu-id="36c10-148">Description</span></span> | <span data-ttu-id="36c10-149">Mise en forme gratuite du texte</span><span class="sxs-lookup"><span data-stu-id="36c10-149">Free format text</span></span> |
|||

<span data-ttu-id="36c10-150">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="36c10-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="36c10-151">Créer la stratégie de survivance de la branche Teams</span><span class="sxs-lookup"><span data-stu-id="36c10-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="36c10-152">Pour créer une stratégie, vous devez utiliser l'New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="36c10-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="36c10-153">Cette cmdlet possède les paramètres suivants.</span><span class="sxs-lookup"><span data-stu-id="36c10-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="36c10-154">Notez que la stratégie peut contenir un ou plusieurs SBA.</span><span class="sxs-lookup"><span data-stu-id="36c10-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="36c10-155">Paramètre</span><span class="sxs-lookup"><span data-stu-id="36c10-155">Parameter</span></span>| <span data-ttu-id="36c10-156">Description</span><span class="sxs-lookup"><span data-stu-id="36c10-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="36c10-157">Identity</span><span class="sxs-lookup"><span data-stu-id="36c10-157">Identity</span></span> | <span data-ttu-id="36c10-158">L’identité de la stratégie</span><span class="sxs-lookup"><span data-stu-id="36c10-158">The identity of the policy</span></span> |
| <span data-ttu-id="36c10-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="36c10-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="36c10-160">FQDN des SBA dans le site</span><span class="sxs-lookup"><span data-stu-id="36c10-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="36c10-161">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="36c10-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="36c10-162">Vous pouvez ajouter ou supprimer des SBE d’une stratégie à l’aide de Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="36c10-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="36c10-163">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="36c10-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="36c10-164">Affecter une stratégie à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="36c10-164">Assign a policy to a user</span></span>

<span data-ttu-id="36c10-165">Pour affecter la stratégie à des utilisateurs individuels, vous devez utiliser l'Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="36c10-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="36c10-166">Cette cmdlet a les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="36c10-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="36c10-167">Paramètre</span><span class="sxs-lookup"><span data-stu-id="36c10-167">Parameter</span></span>| <span data-ttu-id="36c10-168">Description</span><span class="sxs-lookup"><span data-stu-id="36c10-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="36c10-169">Identity</span><span class="sxs-lookup"><span data-stu-id="36c10-169">Identity</span></span> | <span data-ttu-id="36c10-170">Identité de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="36c10-170">The identity of the user</span></span> |
| <span data-ttu-id="36c10-171">PolicyName</span><span class="sxs-lookup"><span data-stu-id="36c10-171">PolicyName</span></span> | <span data-ttu-id="36c10-172">L’identité de la stratégie</span><span class="sxs-lookup"><span data-stu-id="36c10-172">The identity of the policy</span></span> |
||

<span data-ttu-id="36c10-173">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="36c10-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="36c10-174">Vous pouvez supprimer une stratégie d’un utilisateur en accordant la stratégie $Null comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="36c10-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="36c10-175">Enregistrer une application pour SBA auprès d’Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="36c10-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="36c10-176">Pour permettre à différents SBA utilisés au sein de votre client de lire les données requises de Microsoft 365, vous devez inscrire une application pour SBA auprès d’Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="36c10-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="36c10-177">Pour plus d’informations sur l’inscription des applications, voir les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="36c10-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="36c10-178">Développer des applications métier pour Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="36c10-178">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="36c10-179">[Enregistrez une application auprès de la plateforme d’identité Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)</span><span class="sxs-lookup"><span data-stu-id="36c10-179">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="36c10-180">Vous ne devez inscrire qu’une seule application pour être utilisé par tous les SBE de votre client.</span><span class="sxs-lookup"><span data-stu-id="36c10-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="36c10-181">Pour l’inscription SBA, les valeurs suivantes doivent être créées par l’inscription :</span><span class="sxs-lookup"><span data-stu-id="36c10-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="36c10-182">ID d’application (client)</span><span class="sxs-lookup"><span data-stu-id="36c10-182">Application (client) ID</span></span> 
- <span data-ttu-id="36c10-183">Client secret</span><span class="sxs-lookup"><span data-stu-id="36c10-183">Client secret</span></span> 

<span data-ttu-id="36c10-184">Pour l’application SBA, gardez les choses suivantes à l’esprit :</span><span class="sxs-lookup"><span data-stu-id="36c10-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="36c10-185">Le nom peut être ce que vous décidez.</span><span class="sxs-lookup"><span data-stu-id="36c10-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="36c10-186">Types de comptes pris en charge = Compte dans cet annuaire de l’organisation uniquement.</span><span class="sxs-lookup"><span data-stu-id="36c10-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="36c10-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="36c10-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="36c10-188">Jetons d’octroi implicites = jetons Access et ID.</span><span class="sxs-lookup"><span data-stu-id="36c10-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="36c10-189">Autorisations de l’API = Accès des administrateurs client Skype et Teams ->'application -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="36c10-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="36c10-190">Secret client : vous pouvez utiliser n’importe quelle description et expiration.</span><span class="sxs-lookup"><span data-stu-id="36c10-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="36c10-191">N’oubliez pas de copier le secret client immédiatement après l’avoir créé.</span><span class="sxs-lookup"><span data-stu-id="36c10-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="36c10-192">L’ID d’application (client) s’affiche sous l’onglet Vue d’ensemble.</span><span class="sxs-lookup"><span data-stu-id="36c10-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="36c10-193">Ensuite, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="36c10-193">Then follow these steps:</span></span>

1. <span data-ttu-id="36c10-194">Enregistrez l’application.</span><span class="sxs-lookup"><span data-stu-id="36c10-194">Register the application.</span></span>
2. <span data-ttu-id="36c10-195">Définissez les jetons d’octroi implicites.</span><span class="sxs-lookup"><span data-stu-id="36c10-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="36c10-196">Définissez les autorisations de l’API.</span><span class="sxs-lookup"><span data-stu-id="36c10-196">Set the API permissions.</span></span>
4. <span data-ttu-id="36c10-197">Créez le secret client.</span><span class="sxs-lookup"><span data-stu-id="36c10-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="36c10-198">Configuration du contrôleur de session Border</span><span class="sxs-lookup"><span data-stu-id="36c10-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="36c10-199">Pour obtenir une aide étape par étape sur la configuration du contrôleur de session en bordure avec l’appliance de branche utilisable pour la survie, consultez la documentation fournie par votre fournisseur SBC :</span><span class="sxs-lookup"><span data-stu-id="36c10-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="36c10-200">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="36c10-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="36c10-201">Ruban</span><span class="sxs-lookup"><span data-stu-id="36c10-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="36c10-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="36c10-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="36c10-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="36c10-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="36c10-204">Signaler des problèmes</span><span class="sxs-lookup"><span data-stu-id="36c10-204">Reporting issues</span></span>

<span data-ttu-id="36c10-205">Signalez les problèmes à l’organisation de support de votre fournisseur SBC.</span><span class="sxs-lookup"><span data-stu-id="36c10-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="36c10-206">Lorsque vous signalez le problème, indiquez que vous avez une appliance de branche utilisable par la survivable.</span><span class="sxs-lookup"><span data-stu-id="36c10-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="36c10-207">Problèmes connus</span><span class="sxs-lookup"><span data-stu-id="36c10-207">Known issues</span></span>

- <span data-ttu-id="36c10-208">L’ajout de nouveaux équipements de branches survivables peut prendre un certain temps avant de pouvoir les utiliser dans les stratégies d’appliance de branche survivable.</span><span class="sxs-lookup"><span data-stu-id="36c10-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="36c10-209">Lorsque vous affectez une stratégie d’équipement de branche survivable à un utilisateur, l’utilisation de SBA dans la sortie de Get-CsOnlineUser peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="36c10-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="36c10-210">La recherche inversée de nombre par rapport aux contacts Azure AD n’est pas effectuée.</span><span class="sxs-lookup"><span data-stu-id="36c10-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="36c10-211">Le SBA ne prend pas en charge les paramètres de forwardage d’appel.</span><span class="sxs-lookup"><span data-stu-id="36c10-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="36c10-212">La prise en charge d’un appel d’urgence vers un numéro de secours configuré pour les appels d’urgence dynamiques (E911) n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="36c10-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="36c10-213">La sortie de Get-CsOnlineUser montre TeamsBranchSurvivabilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="36c10-213">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
