---
title: Assigner des licences Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Découvrez comment attribuer des licences aux fonctionnalités telles que l’audioconférence, le système téléphonique et les offres d’appels.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46ae5952d79f3f0ef0a6137b240661550ecead00
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888683"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="6a8a1-103">Attribution de licences Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="6a8a1-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="6a8a1-104">Vous pouvez attribuer des licences à vos utilisateurs pour des fonctionnalités telles que l’audioconférence, le système téléphonique et les offres d’appels.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="6a8a1-105">Cet article explique comment ajouter ces licences en bloc et pour un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6a8a1-106">Pour plus d’informations sur les licences que vous devez acheter et sur la manière de les acheter, reportez-vous à la rubrique [licences de module complémentaire de Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) , en fonction de votre offre Office 365, afin que les utilisateurs obtiennent des conférences audio, des numéros gratuits et la possibilité d’appeler des numéros de téléphone hors de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="6a8a1-107">Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences</span><span class="sxs-lookup"><span data-stu-id="6a8a1-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="6a8a1-108">Voici ce que vous devez savoir avant d’affecter des licences de conférence audio, de système téléphonique et de plan d’appel.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="6a8a1-109">**Vous utilisez la connectivité PSTN locale pour les utilisateurs hybrides ?**</span><span class="sxs-lookup"><span data-stu-id="6a8a1-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="6a8a1-110">Si tel est le cas, il vous suffit d’affecter une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="6a8a1-111">Vous ne devez pas affecter de plan d’appels.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="6a8a1-112">**Latence après l’attribution de licences**: en raison de la latence entre Office 365 et Microsoft Teams, un utilisateur peut être tenu de 24 heures pour pouvoir affecter un plan d’appels après que vous lui avez affecté une licence.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="6a8a1-113">Si, au bout de 24 heures, l’utilisateur ne dispose pas d’un plan d’appels, [Contactez le support technique pour les produits destinés aux entreprises-aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="6a8a1-114">**Messages d'erreur**: un message d'erreur s'affiche si vous n'avez pas acheté le nombre correct de licences.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="6a8a1-115">Si vous avez besoin d’acheter d’autres licences de plan d’appel, sélectionnez **acheter plus**.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="6a8a1-116">**Étapes**suivantes : une fois que vous avez attribué des licences de plan d’appel aux utilisateurs, vous devez obtenir vos numéros de téléphone pour votre organisation, puis affecter ces numéros aux personnes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="6a8a1-117">Pour obtenir des instructions détaillées, consultez la rubrique [configurer les offres d’appels](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="6a8a1-118">Attribution d’un système téléphonique et d’une licence de plan d’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="6a8a1-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="6a8a1-119">Les étapes sont les mêmes que pour affecter un licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="6a8a1-120">Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="6a8a1-121">Affectation de licences de système téléphonique et de plan d’appel en bloc</span><span class="sxs-lookup"><span data-stu-id="6a8a1-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="6a8a1-122">Installez l' Assistant de connexion Microsoft Online Services pour les informaticiens RTW.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="6a8a1-123">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="6a8a1-123">Don't have the module installed?</span></span> <span data-ttu-id="6a8a1-124">Voir [Assistant de connexion de Microsoft Online Services pour les informaticiens RTW](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="6a8a1-125">Installez le module Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="6a8a1-126">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="6a8a1-126">Don't have the module installed?</span></span> <span data-ttu-id="6a8a1-127">Pour plus d’informations sur le téléchargement et la syntaxe de l’applet de cmdlet, voir [gérer Azure ad à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="6a8a1-128">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="6a8a1-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="6a8a1-129">Cet exemple affecte une licence Entreprise E3, ainsi qu'une licence Système téléphonique et Forfait d’appels interne.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="6a8a1-130">Le nom des licences ou des noms de produits figurant dans le script est affiché en italique (voir [système téléphonique et plans d’appel, noms de produits ou références SKU utilisés pour l’écriture de scripts](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), après l’exemple).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

```powershell
#Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline
#Authenticate to MSOLservice.
Connect-MSOLService
#File prompt to select the userlist txt file.
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
$OFD = New-Object System.Windows.Forms.OpenFileDialog
$OFD.filter = "text files (*.*)| *.txt"
$OFD.ShowDialog() | Out-Null
$OFD.filename
If ($OFD.filename -eq '')
{
 Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}
#Create a variable of all users.
$users = Get-Content $OFD.filename
#License each user in the $users variable.
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
International Calling.
for each ($user in $users)
 {
 Write-host "Assigning License: $user"
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
 }

```

## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="6a8a1-131">Système téléphonique et offres d’appels noms de produits ou UGS utilisés pour l’écriture de scripts</span><span class="sxs-lookup"><span data-stu-id="6a8a1-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="6a8a1-132">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="6a8a1-132">Product name</span></span> | <span data-ttu-id="6a8a1-133">Référence</span><span class="sxs-lookup"><span data-stu-id="6a8a1-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="6a8a1-134">Entreprise E5 (avec Système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="6a8a1-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="6a8a1-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="6a8a1-136">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="6a8a1-136">Enterprise E3</span></span> | <span data-ttu-id="6a8a1-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="6a8a1-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="6a8a1-138">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="6a8a1-138">Enterprise E1</span></span> | <span data-ttu-id="6a8a1-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="6a8a1-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="6a8a1-140">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="6a8a1-140">Phone System</span></span> | <span data-ttu-id="6a8a1-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="6a8a1-141">MCOEV</span></span> |
| <span data-ttu-id="6a8a1-142">Forfait d’appels internationaux & international</span><span class="sxs-lookup"><span data-stu-id="6a8a1-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="6a8a1-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="6a8a1-143">MCOPSTN2</span></span> |
| <span data-ttu-id="6a8a1-144">Forfait d’appels nationaux (3000 minutes par utilisateur/par mois pour les États-Unis/PR/CA, 1200 minutes par utilisateur et par mois pour les pays de l’Union européenne)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="6a8a1-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="6a8a1-145">MCOPSTN1</span></span> |
| <span data-ttu-id="6a8a1-146">Forfait d’appels nationaux (120 minutes par utilisateur/mois pour chaque pays)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="6a8a1-147">*Remarque : ce plan n’est pas disponible aux États-Unis*.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="6a8a1-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="6a8a1-148">MCOPSTN5</span></span> |
| <span data-ttu-id="6a8a1-149">Forfait d’appels nationaux (240 minutes par utilisateur/mois pour chaque pays)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="6a8a1-150">*Remarque : ce plan n’est pas disponible aux États-Unis*.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="6a8a1-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="6a8a1-151">MCOPSTN6</span></span> |
| <span data-ttu-id="6a8a1-152">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="6a8a1-152">Communications Credits</span></span> | <span data-ttu-id="6a8a1-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="6a8a1-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="6a8a1-154">Audioconférence : conseils et scripts pour affecter des licences</span><span class="sxs-lookup"><span data-stu-id="6a8a1-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="6a8a1-155">Voici ce que vous devez savoir avant d’affecter des licences de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="6a8a1-156">Fournisseur de services d' **audioconférence tiers**: si une personne est déjà configurée pour utiliser un fournisseur de services d’audioconférence tiers, lorsque vous lui attribuez une licence d’audioconférence, celle-ci est modifiée de manière à utiliser Microsoft comme fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="6a8a1-157">Vous pouvez le remplacer par le fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="6a8a1-158">**Étapes**suivantes : une fois que vous avez attribué des licences de conférence audio, vous devez affecter un fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="6a8a1-159">Voir [affecter Microsoft en tant que fournisseur de](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="6a8a1-160">Affectation d’une licence de conférence audio à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="6a8a1-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="6a8a1-161">Les étapes sont les mêmes que pour affecter un licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="6a8a1-162">Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="6a8a1-163">Affectation de licences de conférence audio en bloc</span><span class="sxs-lookup"><span data-stu-id="6a8a1-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="6a8a1-164">Téléchargez et installez [l’Assistant de connexion de Microsoft Online Services pour les informaticiens RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="6a8a1-165">Téléchargez et installez le module Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="6a8a1-166">Pour plus d’informations sur le téléchargement et la syntaxe de l’applet de cmdlet, voir [gérer Azure ad à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="6a8a1-167">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="6a8a1-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="6a8a1-168">Le nom des licences ou des noms de produits figurant dans le script est affiché en italique.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="6a8a1-169">Voir les noms des produits de l’audioconférence pour l' [écriture de scripts](#audio-conferencing-product-names-or-skus-used-for-scripting) pour l’ensemble des noms de produits.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="6a8a1-170">Cet exemple affecte une licence entreprise E3, ainsi qu’une licence de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

```powershell
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
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
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    }
```

## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="6a8a1-171">Noms des produits de conférence audio ou références (SKU) utilisés pour l’écriture de scripts</span><span class="sxs-lookup"><span data-stu-id="6a8a1-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="6a8a1-172">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="6a8a1-172">Product name</span></span> | <span data-ttu-id="6a8a1-173">Référence</span><span class="sxs-lookup"><span data-stu-id="6a8a1-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="6a8a1-174">Audioconférence (abonnement)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="6a8a1-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="6a8a1-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="6a8a1-176">Payez à la minute (payer au fur et à mesure)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="6a8a1-177">*Remarque : la configuration et l’activation de crédits de communication sont nécessaires*.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="6a8a1-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="6a8a1-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="6a8a1-179">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="6a8a1-179">Enterprise E1</span></span> | <span data-ttu-id="6a8a1-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="6a8a1-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="6a8a1-181">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="6a8a1-181">Enterprise E3</span></span> | <span data-ttu-id="6a8a1-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="6a8a1-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="6a8a1-183">Entreprise E5 (sans Audioconférence)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="6a8a1-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="6a8a1-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="6a8a1-185">Entreprise E5 (avec audioconférence)</span><span class="sxs-lookup"><span data-stu-id="6a8a1-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="6a8a1-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="6a8a1-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="6a8a1-187">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="6a8a1-187">Communications Credits</span></span>

<span data-ttu-id="6a8a1-188">Voici ce que vous devez savoir avant d’affecter des licences de crédits de communication.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="6a8a1-189">**Clients entreprise E5**: même si des licences entreprise E5 ont été affectées à vos utilisateurs, nous vous conseillons de leur affecter des licences de crédits de communication.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="6a8a1-190">**Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="6a8a1-191">Pour obtenir des instructions détaillées, consultez la rubrique [configurer les offres d’appels](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="6a8a1-192">Affectation d’une licence de crédits de communication à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="6a8a1-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="6a8a1-193">Les étapes sont les mêmes que pour affecter un licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="6a8a1-194">Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="6a8a1-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="6a8a1-195">Affectation de licences de crédits de communication en bloc</span><span class="sxs-lookup"><span data-stu-id="6a8a1-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="6a8a1-196">Jetez un coup d’œil à l’exemple de script permettant d’affecter des licences de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="6a8a1-197">Mettez-le à jour avec les informations relatives à l’affectation de licences de crédits de communication.</span><span class="sxs-lookup"><span data-stu-id="6a8a1-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a8a1-198">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6a8a1-198">Related topics</span></span>

[<span data-ttu-id="6a8a1-199">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="6a8a1-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="6a8a1-200">Ajouter des fonds et gérer les Crédits de Communications</span><span class="sxs-lookup"><span data-stu-id="6a8a1-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
