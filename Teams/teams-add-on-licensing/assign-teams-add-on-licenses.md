---
title: Attribution de licences de complément d’équipe aux utilisateurs
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Découvrez comment affecter des licences de complément d’équipe aux utilisateurs pour des fonctionnalités telles que l’audioconférence, le système téléphonique et les offres d’appels.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7faaf2e65330aafd809872ed19b5f2f16afc668
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868581"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="8cb95-103">Attribution de licences de complément d’équipe aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="8cb95-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="8cb95-104">Les licences de compléments sont des licences pour des fonctionnalités d’équipe spécifiques, telles que les conférences audio, le système téléphonique et les offres d’appels.</span><span class="sxs-lookup"><span data-stu-id="8cb95-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="8cb95-105">Cet article décrit comment affecter des licences de complément à des utilisateurs individuels et à des groupes de personnes volumineux en bloc.</span><span class="sxs-lookup"><span data-stu-id="8cb95-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="8cb95-106">Pour plus d’options, voir [licences de complément teams](microsoft-teams-add-on-licensing.md) disponibles avec des licences de compléments.</span><span class="sxs-lookup"><span data-stu-id="8cb95-106">See [Teams add-on licensing](microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="8cb95-107">Vous trouverez également des informations sur les licences que vous devez acheter et sur la manière de les acheter (en fonction de votre plan), de sorte que les utilisateurs puissent obtenir des fonctions telles que les services d’audioconférence, les numéros gratuits et la possibilité d’appeler des numéros de téléphone en dehors de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8cb95-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="8cb95-108">Une fois que vous avez décidé des fonctionnalités que vous voulez pour vos utilisateurs, attribuez-leur des licences.</span><span class="sxs-lookup"><span data-stu-id="8cb95-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="8cb95-109">Vous pouvez utiliser le centre d’administration 365 Microsoft ou PowerShell pour attribuer des licences aux utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8cb95-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="8cb95-110">Vous devez être un administrateur général ou un administrateur de gestion des utilisateurs pour gérer les licences.</span><span class="sxs-lookup"><span data-stu-id="8cb95-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="8cb95-111">Ce que vous devez savoir avant d’affecter des licences de système téléphonique, de plan d’appels et de crédits de communication</span><span class="sxs-lookup"><span data-stu-id="8cb95-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="8cb95-112">Avant de commencer, vérifiez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="8cb95-112">Before you get started, review the following:</span></span>

- <span data-ttu-id="8cb95-113">Si vous utilisez une connectivité de réseau téléphonique commuté (PSTN) locale pour les utilisateurs hybrides, il vous suffit d’affecter une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="8cb95-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="8cb95-114">Ne pas affecter de licence de plan d’appel.</span><span class="sxs-lookup"><span data-stu-id="8cb95-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="8cb95-115">En raison de la latence entre Microsoft 365 et Microsoft Teams, il est possible que l’utilisateur dispose d’une offre de 24 heures après avoir affecté une licence.</span><span class="sxs-lookup"><span data-stu-id="8cb95-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="8cb95-116">Si l’utilisateur ne dispose pas d’un plan d’appels après 24 heures, [Contactez le support technique des produits pour les entreprises-aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="8cb95-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="8cb95-117">Vous recevez un message d’erreur si vous n’avez pas acheté le nombre de licences correct.</span><span class="sxs-lookup"><span data-stu-id="8cb95-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="8cb95-118">Si vous avez besoin d’acheter d’autres licences de plan d’appel, choisissez l’option d’achat.</span><span class="sxs-lookup"><span data-stu-id="8cb95-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="8cb95-119">Même si des licences entreprise E5 ont été affectées à vos utilisateurs, vous devez quand [même affecter des licences aux destinataires](../what-are-communications-credits.md) de vos appels pour passer ou recevoir des appels à partir du RTC.</span><span class="sxs-lookup"><span data-stu-id="8cb95-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="8cb95-120">Dès lors que vous attribuez des licences à vos utilisateurs, vous devez obtenir des numéros de téléphone pour votre organisation, puis affecter ces numéros aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8cb95-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="8cb95-121">Pour obtenir des instructions détaillées, consultez la rubrique [configurer les offres d’appels](../set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="8cb95-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="8cb95-122">Utilisation du centre d’administration Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8cb95-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="8cb95-123">Utilisez le centre d’administration Microsoft 365 pour attribuer des licences à des utilisateurs individuels ou à des groupes d’utilisateurs de petites entreprises à la fois.</span><span class="sxs-lookup"><span data-stu-id="8cb95-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="8cb95-124">Vous pouvez attribuer des licences dans la page **licences** (pour 20 utilisateurs maximum à la fois) ou la page **utilisateurs actifs** .</span><span class="sxs-lookup"><span data-stu-id="8cb95-124">You can assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="8cb95-125">La méthode que vous choisissez dépend de la façon dont vous souhaitez gérer les licences de produits pour des utilisateurs spécifiques ou gérer des licences utilisateur pour des produits spécifiques.</span><span class="sxs-lookup"><span data-stu-id="8cb95-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="8cb95-126">Pour obtenir des instructions détaillées, voir attribuer des [licences à des utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="8cb95-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="8cb95-127">Si vous devez attribuer des licences à un grand nombre d’utilisateurs, par exemple des centaines ou des milliers d’utilisateurs, utilisez PowerShell ou des [licences basées sur le groupe dans Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="8cb95-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="8cb95-128">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cb95-128">Using PowerShell</span></span>

<span data-ttu-id="8cb95-129">Utiliser PowerShell pour attribuer des licences en bloc aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8cb95-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="8cb95-130">Pour en savoir plus, voir [attribuer des licences à des comptes d’utilisateurs avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="8cb95-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="8cb95-131">Exemple de script</span><span class="sxs-lookup"><span data-stu-id="8cb95-131">Example script</span></span>

<span data-ttu-id="8cb95-132">Voici un exemple illustrant comment utiliser un script pour attribuer des licences à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8cb95-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="8cb95-133">Installez la version 64 bits de l' [Assistant de connexion de Microsoft Online Services pour les informaticiens RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="8cb95-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
2. <span data-ttu-id="8cb95-134">Installez le module Microsoft Azure Active Directory pour Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="8cb95-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="8cb95-135">Ouvrez une invite de commandes Windows PowerShell avec élévation de privilèges (exécutez Windows PowerShell en tant qu’administrateur).</span><span class="sxs-lookup"><span data-stu-id="8cb95-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="8cb95-136">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8cb95-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="8cb95-137">Si vous êtes invité à installer le fournisseur NuGet, tapez **o**, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="8cb95-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="8cb95-138">Si vous êtes invité à installer le module à partir de PSGallery, tapez **Y**, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="8cb95-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="8cb95-139">Dans l’invite de commandes Windows PowerShell, exécutez le script suivant pour attribuer des licences à vos utilisateurs, où \<CompanyName:License> est le nom de votre organisation et l’identificateur de la licence que vous voulez attribuer.</span><span class="sxs-lookup"><span data-stu-id="8cb95-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="8cb95-140">Par exemple, litwareinc : MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="8cb95-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="8cb95-141">L’identificateur est différent du nom convivial de la licence.</span><span class="sxs-lookup"><span data-stu-id="8cb95-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="8cb95-142">Par exemple, l’identificateur pour audioconférence est MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="8cb95-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="8cb95-143">Pour en savoir plus, consultez la rubrique [noms des produits et identificateurs UGS pour les licences](#product-names-and-sku-identifiers-for-licensing).</span><span class="sxs-lookup"><span data-stu-id="8cb95-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    <span data-ttu-id="8cb95-144">Par exemple, pour attribuer des licences Microsoft 365 entreprise 1 et audioconférence, utilisez la syntaxe suivante dans le script :</span><span class="sxs-lookup"><span data-stu-id="8cb95-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="8cb95-145">Pour attribuer une licence Microsoft Business Voice (sans plan d’appel), utilisez la syntaxe suivante dans le script :</span><span class="sxs-lookup"><span data-stu-id="8cb95-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="8cb95-146">Noms des produits et identificateurs UGS pour les licences</span><span class="sxs-lookup"><span data-stu-id="8cb95-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="8cb95-147">Voici une liste partielle des noms de produits et des noms de parties SKU correspondants que vous pouvez utiliser en tant que référence lorsque vous utilisez PowerShell pour gérer les licences dans Teams.</span><span class="sxs-lookup"><span data-stu-id="8cb95-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="8cb95-148">Pour en savoir plus, voir [afficher des licences et services avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [noms de produits et identificateurs de plan de service pour la gestion des licences](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)et référence des références [SKU éducation](../sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="8cb95-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="8cb95-149">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="8cb95-149">Product name</span></span>| <span data-ttu-id="8cb95-150">Référence</span><span class="sxs-lookup"><span data-stu-id="8cb95-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="8cb95-151">Microsoft entreprise E5 (avec système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="8cb95-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="8cb95-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="8cb95-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="8cb95-153">Microsoft entreprise E5 (sans conférence audio)</span><span class="sxs-lookup"><span data-stu-id="8cb95-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="8cb95-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="8cb95-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="8cb95-155">Microsoft entreprise E5 (avec audioconférence)</span><span class="sxs-lookup"><span data-stu-id="8cb95-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="8cb95-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="8cb95-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="8cb95-157">Microsoft entreprise E3</span><span class="sxs-lookup"><span data-stu-id="8cb95-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="8cb95-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="8cb95-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="8cb95-159">Microsoft entreprise E1</span><span class="sxs-lookup"><span data-stu-id="8cb95-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="8cb95-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="8cb95-160">STANDARDPACK</span></span> |
| <span data-ttu-id="8cb95-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="8cb95-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="8cb95-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="8cb95-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="8cb95-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="8cb95-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="8cb95-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="8cb95-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="8cb95-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="8cb95-165">Microsoft 365 Business</span></span> | <span data-ttu-id="8cb95-166">SPB</span><span class="sxs-lookup"><span data-stu-id="8cb95-166">SPB</span></span>|
| <span data-ttu-id="8cb95-167">Microsoft Business Voice (Canada)</span><span class="sxs-lookup"><span data-stu-id="8cb95-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="8cb95-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="8cb95-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="8cb95-169">Microsoft Business Voice (Royaume-Uni)</span><span class="sxs-lookup"><span data-stu-id="8cb95-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="8cb95-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="8cb95-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="8cb95-171">Microsoft Business Voice (États-Unis)</span><span class="sxs-lookup"><span data-stu-id="8cb95-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="8cb95-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="8cb95-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="8cb95-173">Microsoft Business Voice (sans plan d’appel)</span><span class="sxs-lookup"><span data-stu-id="8cb95-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="8cb95-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="8cb95-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="8cb95-175">Microsoft Business Voice (sans plan d’appel) pour les États-Unis</span><span class="sxs-lookup"><span data-stu-id="8cb95-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="8cb95-176">_MED BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="8cb95-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="8cb95-177">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="8cb95-177">Audio Conferencing</span></span> | <span data-ttu-id="8cb95-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="8cb95-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="8cb95-179">Payez à la minute (payer au fur et à mesure)</span><span class="sxs-lookup"><span data-stu-id="8cb95-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="8cb95-180">*Le crédit de communications doit être configuré et activé.*</span><span class="sxs-lookup"><span data-stu-id="8cb95-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="8cb95-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="8cb95-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="8cb95-182">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="8cb95-182">Phone System</span></span> | <span data-ttu-id="8cb95-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="8cb95-183">MCOEV</span></span> |
| <span data-ttu-id="8cb95-184">Forfait d’appels nationaux et internationaux</span><span class="sxs-lookup"><span data-stu-id="8cb95-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="8cb95-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="8cb95-185">MCOPSTN2</span></span> |
| <span data-ttu-id="8cb95-186">Forfait d’appels nationaux (3000 minutes par utilisateur/par mois pour les États-Unis/PR/CA, 1200 minutes par utilisateur et par mois pour les pays de l’Union européenne)</span><span class="sxs-lookup"><span data-stu-id="8cb95-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="8cb95-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="8cb95-187">MCOPSTN1</span></span> |
| <span data-ttu-id="8cb95-188">Forfait d’appels nationaux (120 minutes par utilisateur/mois pour chaque pays)</span><span class="sxs-lookup"><span data-stu-id="8cb95-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="8cb95-189">*Ce plan n’est pas disponible aux États-Unis.*</span><span class="sxs-lookup"><span data-stu-id="8cb95-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="8cb95-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="8cb95-190">MCOPSTN5</span></span> |
| <span data-ttu-id="8cb95-191">Forfait d’appels nationaux (240 minutes par utilisateur/mois pour chaque pays)</span><span class="sxs-lookup"><span data-stu-id="8cb95-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="8cb95-192">*Ce plan n’est pas disponible aux États-Unis.*</span><span class="sxs-lookup"><span data-stu-id="8cb95-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="8cb95-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="8cb95-193">MCOPSTN6</span></span> |
| <span data-ttu-id="8cb95-194">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="8cb95-194">Communications Credits</span></span> | <span data-ttu-id="8cb95-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="8cb95-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8cb95-196">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8cb95-196">Related topics</span></span>

- [<span data-ttu-id="8cb95-197">Licences de module complémentaire Teams</span><span class="sxs-lookup"><span data-stu-id="8cb95-197">Teams add-on licensing</span></span>](microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="8cb95-198">Gérer l’accès des utilisateurs à Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cb95-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="8cb95-199">Afficher les licences et services avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cb95-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="8cb95-200">Noms de produits et identificateurs de plans de service pour la gestion des licences</span><span class="sxs-lookup"><span data-stu-id="8cb95-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="8cb95-201">Référence SKU éducation</span><span class="sxs-lookup"><span data-stu-id="8cb95-201">Education SKU reference</span></span>](../sku-reference-edu.md)