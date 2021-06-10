---
title: Attribuer Teams licences de modules add-on aux utilisateurs
author: cichur
ms.author: v-cichur
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
description: Découvrez comment affecter des Teams de modules supplémentaires aux utilisateurs pour des fonctionnalités telles que l’audioconférence, les Système téléphonique et les plans d’appel.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240672b125190492a036bc9dfa3f7a42070e8320
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116932"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="b4624-103">Attribuer Teams licences de modules add-on aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b4624-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="b4624-104">Les licences de modules supplémentaires sont des licences Teams de fonctionnalités spécifiques telles que l’audioconférence, les Système téléphonique et les plans d’appel.</span><span class="sxs-lookup"><span data-stu-id="b4624-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="b4624-105">Cet article explique comment attribuer des licences d’ajout à des utilisateurs individuels et à de grands ensembles d’utilisateurs en bloc.</span><span class="sxs-lookup"><span data-stu-id="b4624-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="b4624-106">Consultez [Teams licences de modules](./microsoft-teams-add-on-licensing.md) Teams fonctionnalités disponibles avec des licences de modules supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="b4624-106">See [Teams add-on licensing](./microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="b4624-107">Vous trouverez également des informations sur les licences que vous devez acheter et sur la manière de les acheter (selon votre offre), afin que les utilisateurs disposent de fonctionnalités telles que l’audioconférence, les numéros gratuits et la possibilité d’appeler des numéros de téléphone en dehors de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b4624-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="b4624-108">Après avoir décidé des fonctionnalités que vous souhaitez pour vos utilisateurs, attribuez-leur les licences.</span><span class="sxs-lookup"><span data-stu-id="b4624-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="b4624-109">Vous pouvez utiliser le Centre Microsoft 365'administration de l’entreprise ou PowerShell pour attribuer des licences aux utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b4624-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="b4624-110">Pour gérer les licences, vous devez être administrateur global ou administrateur de gestion des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b4624-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="b4624-111">Ce que vous devez savoir avant d’affecter Système téléphonique licences pour le plan d’appel et les crédits de communication</span><span class="sxs-lookup"><span data-stu-id="b4624-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="b4624-112">Avant de commencer, examinez les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4624-112">Before you get started, review the following requirements:</span></span>

- <span data-ttu-id="b4624-113">Si vous utilisez une connectivité de réseau téléphonique public commuté (RST) sur site pour des utilisateurs hybrides, vous devez seulement affecter une licence Système téléphonique public.</span><span class="sxs-lookup"><span data-stu-id="b4624-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="b4624-114">N’affectez PAS de licence Forfait d’appels.</span><span class="sxs-lookup"><span data-stu-id="b4624-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="b4624-115">En raison de la latence entre Microsoft 365 et Microsoft Teams, l’attribution d’un plan d’appels à un utilisateur peut prendre jusqu’à 24 heures après l’attribution d’une licence.</span><span class="sxs-lookup"><span data-stu-id="b4624-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="b4624-116">Si l’utilisateur n’a pas accès à un plan d’appels au bout de 24 heures, contactez le support technique pour les produits pour les entreprises - Aide [de l’administrateur.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="b4624-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="b4624-117">Vous recevrez un message d’erreur si vous n’avez pas acheté le nombre correct de licences.</span><span class="sxs-lookup"><span data-stu-id="b4624-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="b4624-118">Si vous avez besoin d’acheter d’autres licences de forfait d’appels, choisissez l’option d’achat.</span><span class="sxs-lookup"><span data-stu-id="b4624-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="b4624-119">Même si vos utilisateurs reçoivent Enterprise licences E5, vous devez leur attribuer des licences de [crédits](../what-are-communications-credits.md) de communication s’ils souhaitent appeler ou recevoir des appels du réseau PSTN.</span><span class="sxs-lookup"><span data-stu-id="b4624-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want to make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="b4624-120">Après avoir attribué des licences de plan d’appel ou de crédit de communication à vos utilisateurs, vous devrez obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b4624-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="b4624-121">Pour obtenir des instructions détaillées, [consultez Configurer les forfaits d’appels.](../set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="b4624-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="b4624-122">Utilisation du Microsoft 365 d’administration</span><span class="sxs-lookup"><span data-stu-id="b4624-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="b4624-123">Utilisez le Microsoft 365 d’administration pour attribuer des licences à des utilisateurs individuels ou à de petits ensembles d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="b4624-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="b4624-124">Vous attribuez des **licences** dans la page Licences (jusqu’à 20 utilisateurs à la fois) ou la **page** Utilisateurs actifs.</span><span class="sxs-lookup"><span data-stu-id="b4624-124">You assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="b4624-125">La méthode que vous choisissez dépend de la gestion des licences de produits pour des utilisateurs spécifiques ou de la gestion des licences utilisateur de produits spécifiques.</span><span class="sxs-lookup"><span data-stu-id="b4624-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="b4624-126">Pour obtenir des instructions détaillées, voir [Attribuer des licences aux utilisateurs.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="b4624-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="b4624-127">Si vous devez attribuer des licences à un grand nombre d’utilisateurs(par exemple, des centaines ou des milliers d’utilisateurs), utilisez PowerShell ou des licences basées sur les groupes [dans Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="b4624-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="b4624-128">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4624-128">Using PowerShell</span></span>

<span data-ttu-id="b4624-129">Utilisez PowerShell pour attribuer des licences aux utilisateurs en bloc.</span><span class="sxs-lookup"><span data-stu-id="b4624-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="b4624-130">Pour en savoir plus, voir [Attribuer des licences à des comptes d’utilisateurs avec PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="b4624-130">To learn more, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="b4624-131">Exemple de script</span><span class="sxs-lookup"><span data-stu-id="b4624-131">Example script</span></span>

<span data-ttu-id="b4624-132">Voici un exemple de l’utilisation d’un script pour attribuer des licences à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b4624-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="b4624-133">Installez la version 64 bits de l’Assistant de Microsoft Online Services [de l’it professionals RTW.](/collaborate/connect-redirect?DownloadID=59185)</span><span class="sxs-lookup"><span data-stu-id="b4624-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](/collaborate/connect-redirect?DownloadID=59185).</span></span>
2. <span data-ttu-id="b4624-134">Installez le module Microsoft Azure Active Directory de l’Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="b4624-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="b4624-135">Ouvrir une invite de commandes avec Windows PowerShell avec élévation de privilèges (exécuter Windows PowerShell en tant qu’administrateur).</span><span class="sxs-lookup"><span data-stu-id="b4624-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="b4624-136">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b4624-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="b4624-137">Si vous êtes invité à installer le fournisseur de NuGet, tapez **Y,** puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="b4624-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="b4624-138">Si vous êtes invité à installer le module à partir de PSGallery, tapez **Y,** puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="b4624-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="b4624-139">À l’invite de commandes Windows PowerShell, exécutez le script suivant pour attribuer des licences à vos utilisateurs, à savoir le nom de votre organisation et l’identificateur de la licence que vous \<CompanyName:License> voulez attribuer.</span><span class="sxs-lookup"><span data-stu-id="b4624-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="b4624-140">Par exemple, litwareinc:MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="b4624-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="b4624-141">L’identificateur est différent du nom convivial de la licence.</span><span class="sxs-lookup"><span data-stu-id="b4624-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="b4624-142">Par exemple, l’identificateur de l’audioconférence est MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="b4624-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="b4624-143">Pour en savoir plus, consultez [les noms des produits et les identificateurs de référence (SKU) pour les licences.](#product-names-and-sku-identifiers-for-licensing)</span><span class="sxs-lookup"><span data-stu-id="b4624-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

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

    <span data-ttu-id="b4624-144">Par exemple, pour affecter Microsoft 365 Entreprise 1 et Audioconférence, utilisez la syntaxe suivante dans le script :</span><span class="sxs-lookup"><span data-stu-id="b4624-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="b4624-145">Pour affecter une licence Microsoft Business Voice (sans forfait d’appels), utilisez la syntaxe suivante dans le script :</span><span class="sxs-lookup"><span data-stu-id="b4624-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="b4624-146">Noms de produits et identificateurs de référence SKU pour les licences</span><span class="sxs-lookup"><span data-stu-id="b4624-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="b4624-147">Voici une liste partielle des noms de produits et de leurs références SKU correspondantes que vous pouvez utiliser comme référence lorsque vous utilisez PowerShell pour gérer les licences Teams.</span><span class="sxs-lookup"><span data-stu-id="b4624-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="b4624-148">Pour en savoir plus, consultez Afficher les licences et services avec [PowerShell,](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)les noms des produits et les identificateurs de plan de service pour les [licences](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)et la [référence SKU Éducation.](../sku-reference-edu.md)</span><span class="sxs-lookup"><span data-stu-id="b4624-148">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="b4624-149">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b4624-149">Product name</span></span>| <span data-ttu-id="b4624-150">Référence</span><span class="sxs-lookup"><span data-stu-id="b4624-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="b4624-151">Microsoft Enterprise E5 (avec Système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="b4624-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="b4624-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b4624-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="b4624-153">Microsoft Enterprise E5 (sans Audioconférence)</span><span class="sxs-lookup"><span data-stu-id="b4624-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="b4624-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="b4624-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="b4624-155">Microsoft Enterprise E5 (avec audioconférence)</span><span class="sxs-lookup"><span data-stu-id="b4624-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="b4624-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b4624-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="b4624-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="b4624-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="b4624-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b4624-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="b4624-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="b4624-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="b4624-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b4624-160">STANDARDPACK</span></span> |
| <span data-ttu-id="b4624-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="b4624-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="b4624-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="b4624-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="b4624-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="b4624-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="b4624-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="b4624-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="b4624-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b4624-165">Microsoft 365 Business</span></span> | <span data-ttu-id="b4624-166">SPB</span><span class="sxs-lookup"><span data-stu-id="b4624-166">SPB</span></span>|
| <span data-ttu-id="b4624-167">Microsoft Business Voice (Canada)</span><span class="sxs-lookup"><span data-stu-id="b4624-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="b4624-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="b4624-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="b4624-169">Microsoft Business Voice (Royaume-Uni)</span><span class="sxs-lookup"><span data-stu-id="b4624-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="b4624-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="b4624-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="b4624-171">Microsoft Business Voice (États-Unis)</span><span class="sxs-lookup"><span data-stu-id="b4624-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="b4624-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="b4624-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="b4624-173">Microsoft Business Voice (sans forfait d’appels)</span><span class="sxs-lookup"><span data-stu-id="b4624-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="b4624-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="b4624-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="b4624-175">Microsoft Business Voice (sans forfait d’appels) pour les États-Unis</span><span class="sxs-lookup"><span data-stu-id="b4624-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="b4624-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="b4624-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="b4624-177">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="b4624-177">Audio Conferencing</span></span> | <span data-ttu-id="b4624-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="b4624-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="b4624-179">Audioconférence - Paiement à la minute (paiement à la ligne)</span><span class="sxs-lookup"><span data-stu-id="b4624-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="b4624-180">*Il est nécessaire de configurer et d’activer les crédits de communication.*</span><span class="sxs-lookup"><span data-stu-id="b4624-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="b4624-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="b4624-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="b4624-182">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="b4624-182">Phone System</span></span> | <span data-ttu-id="b4624-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="b4624-183">MCOEV</span></span> |
| <span data-ttu-id="b4624-184">Forfait d’appels nationaux et internationaux</span><span class="sxs-lookup"><span data-stu-id="b4624-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="b4624-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="b4624-185">MCOPSTN2</span></span> |
| <span data-ttu-id="b4624-186">Forfait d’appels nationaux (3 000 minutes par utilisateur/mois pour les états-Unis/les relations publiques/ca, 1 200 minutes par utilisateur/mois pour les pays de l’UE)</span><span class="sxs-lookup"><span data-stu-id="b4624-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="b4624-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="b4624-187">MCOPSTN1</span></span> |
| <span data-ttu-id="b4624-188">Forfait d’appels nationaux (120 minutes par utilisateur/mois pour chaque pays)</span><span class="sxs-lookup"><span data-stu-id="b4624-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="b4624-189">*Cette offre n’est pas disponible aux États-Unis.*</span><span class="sxs-lookup"><span data-stu-id="b4624-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="b4624-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="b4624-190">MCOPSTN5</span></span> |
| <span data-ttu-id="b4624-191">Forfait d’appels nationaux (240 minutes par utilisateur/mois pour chaque pays)</span><span class="sxs-lookup"><span data-stu-id="b4624-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="b4624-192">*Cette offre n’est pas disponible aux États-Unis.*</span><span class="sxs-lookup"><span data-stu-id="b4624-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="b4624-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="b4624-193">MCOPSTN6</span></span> |
| <span data-ttu-id="b4624-194">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="b4624-194">Communications Credits</span></span> | <span data-ttu-id="b4624-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="b4624-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b4624-196">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="b4624-196">Related topics</span></span>

- [<span data-ttu-id="b4624-197">Licences de module complémentaire Teams</span><span class="sxs-lookup"><span data-stu-id="b4624-197">Teams add-on licensing</span></span>](./microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="b4624-198">Gérer l’accès des utilisateurs à Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4624-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="b4624-199">Afficher les licences et services avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4624-199">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="b4624-200">Noms de produits et identificateurs de plans de service pour la gestion des licences</span><span class="sxs-lookup"><span data-stu-id="b4624-200">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="b4624-201">Référence SKU pour l’éducation</span><span class="sxs-lookup"><span data-stu-id="b4624-201">Education SKU reference</span></span>](../sku-reference-edu.md)