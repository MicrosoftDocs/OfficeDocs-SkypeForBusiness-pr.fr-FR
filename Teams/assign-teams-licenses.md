---
title: Assigner des licences Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: Découvrez comment attribuer des licences pour des fonctionnalités telles que la conférence Audio, système téléphonique, et des plans d’appel.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46966b7cad855ef6336b501564cde89dffd6b2b2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198736"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="d1fab-103">Affecter des licences Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1fab-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="d1fab-104">Vous pouvez attribuer des licences à vos utilisateurs de conférence Audio, système téléphonique et les Plans de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d1fab-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="d1fab-105">Cet article explique comment ajouter ces licences en bloc et pour un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="d1fab-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d1fab-106">Voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) pour plus d’informations sur ce que vous devez acheter des licences et comment acheter, en fonction de votre Office 365 plan, afin que les utilisateurs obtiennent l’audioconférence, numéros gratuits et la possibilité d’appeler des numéros de téléphone à l’extérieur de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="d1fab-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="d1fab-107">Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences</span><span class="sxs-lookup"><span data-stu-id="d1fab-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="d1fab-108">Voici ce que vous devez connaître avant d’attribution de licences de conférence Audio, système téléphonique et planifier l’appel.</span><span class="sxs-lookup"><span data-stu-id="d1fab-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="d1fab-109">**Vous utilisez la connectivité PSTN locale pour les utilisateurs hybrides ?**</span><span class="sxs-lookup"><span data-stu-id="d1fab-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="d1fab-110">Dans ce cas, vous devez uniquement attribuer une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="d1fab-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="d1fab-111">Vous ne devez affecter un Plan de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d1fab-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="d1fab-112">**Latence après l’attribution de licences**: en raison de la latence entre Office 365 et Microsoft Teams, elle peut prendre jusqu'à 24 heures pour un utilisateur à assigner un Plan d’appel une fois que vous attribuez une licence.</span><span class="sxs-lookup"><span data-stu-id="d1fab-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="d1fab-113">Si après 24 heures avec l’utilisateur n’est pas attribué à un Plan de l’appel, veuillez [contacter le support pour les produits métiers : aide d’administration](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="d1fab-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="d1fab-114">**Messages d'erreur**: un message d'erreur s'affiche si vous n'avez pas acheté le nombre correct de licences.</span><span class="sxs-lookup"><span data-stu-id="d1fab-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="d1fab-115">Si vous devez acheter des licences supplémentaires de planifier l’appel, cliquez sur **acheter plus**.</span><span class="sxs-lookup"><span data-stu-id="d1fab-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="d1fab-116">**Étapes suivantes**: une fois que vous assignez un appel de planifier les licences à vos utilisateurs, vous devez obtenir vos numéros de téléphone pour votre organisation et l’assigner à ces numéros aux personnes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d1fab-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="d1fab-117">Pour obtenir des instructions pas à pas, consultez [configurer des Plans de l’appel](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="d1fab-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="d1fab-118">Attribuer une licence de système téléphonique et planifier l’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="d1fab-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="d1fab-119">Les étapes sont les mêmes que pour affecter un licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1fab-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="d1fab-120">Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="d1fab-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="d1fab-121">Attribution de licences système téléphonique et planifier l’appel en bloc</span><span class="sxs-lookup"><span data-stu-id="d1fab-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="d1fab-122">Installez l' Assistant de connexion Microsoft Online Services pour les informaticiens RTW.</span><span class="sxs-lookup"><span data-stu-id="d1fab-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="d1fab-123">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="d1fab-123">Don't have the module installed?</span></span> <span data-ttu-id="d1fab-124">Voir [Assistant Microsoft Online Services connexion pour les professionnels de l’informatique RTW](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.</span><span class="sxs-lookup"><span data-stu-id="d1fab-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="d1fab-125">Installez le module Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1fab-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="d1fab-126">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="d1fab-126">Don't have the module installed?</span></span> <span data-ttu-id="d1fab-127">Pour des instructions de téléchargement et de la syntaxe de l’applet de commande, voir [Gérer Azure AD à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .</span><span class="sxs-lookup"><span data-stu-id="d1fab-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="d1fab-128">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="d1fab-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="d1fab-129">Cet exemple affecte une licence Entreprise E3, ainsi qu'une licence Système téléphonique et Forfait d’appels interne.</span><span class="sxs-lookup"><span data-stu-id="d1fab-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="d1fab-130">Le nom des licences ou des noms de produits dans le script sont répertoriés en italique (voir [système téléphonique et Plans de l’appel des noms de produits ou SKU utilisé pour les scripts](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), après l’exemple).</span><span class="sxs-lookup"><span data-stu-id="d1fab-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

```
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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="d1fab-131">Système téléphonique et appel des Plans de noms de produits ou des références destinés script</span><span class="sxs-lookup"><span data-stu-id="d1fab-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="d1fab-132">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d1fab-132">Product name</span></span> | <span data-ttu-id="d1fab-133">Référence</span><span class="sxs-lookup"><span data-stu-id="d1fab-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="d1fab-134">Entreprise E5 (avec Système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="d1fab-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="d1fab-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="d1fab-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="d1fab-136">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="d1fab-136">Enterprise E3</span></span> | <span data-ttu-id="d1fab-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="d1fab-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="d1fab-138">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="d1fab-138">Enterprise E1</span></span> | <span data-ttu-id="d1fab-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="d1fab-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="d1fab-140">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="d1fab-140">Phone System</span></span> | <span data-ttu-id="d1fab-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="d1fab-141">MCOEV</span></span> |
| <span data-ttu-id="d1fab-142">Plan d’appels internationaux & interne</span><span class="sxs-lookup"><span data-stu-id="d1fab-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="d1fab-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="d1fab-143">MCOPSTN2</span></span> |
| <span data-ttu-id="d1fab-144">Intérieur appelant planifier (3000 minutes par utilisateur/mois pour les ÉTATS-UNIS/PR/autorité de certification, 1200 minutes par utilisateur par mois pour l’Union européenne)</span><span class="sxs-lookup"><span data-stu-id="d1fab-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="d1fab-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="d1fab-145">MCOPSTN1</span></span> |
| <span data-ttu-id="d1fab-146">Intérieur appelant planifier (120 minutes par utilisateur par mois pour chaque pays)</span><span class="sxs-lookup"><span data-stu-id="d1fab-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="d1fab-147">*Remarque : ce plan n’est pas disponible aux États-Unis*.</span><span class="sxs-lookup"><span data-stu-id="d1fab-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="d1fab-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="d1fab-148">MCOPSTN5</span></span> |
| <span data-ttu-id="d1fab-149">Intérieur appelant planifier (240 minutes par utilisateur par mois pour chaque pays)</span><span class="sxs-lookup"><span data-stu-id="d1fab-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="d1fab-150">*Remarque : ce plan n’est pas disponible aux États-Unis*.</span><span class="sxs-lookup"><span data-stu-id="d1fab-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="d1fab-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="d1fab-151">MCOPSTN6</span></span> |
| <span data-ttu-id="d1fab-152">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="d1fab-152">Communications Credits</span></span> | <span data-ttu-id="d1fab-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="d1fab-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="d1fab-154">Services d’audioconférence : conseils et des scripts pour l’attribution de licences</span><span class="sxs-lookup"><span data-stu-id="d1fab-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="d1fab-155">Voici ce que vous devez connaître avant d’attribution de licences de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="d1fab-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="d1fab-156">**Fournisseur de services d’audioconférence tiers**: si une personne est déjà configurée pour utiliser un fournisseur de services d’audioconférence tiers, lorsque vous leur attribuez une licence de conférence Audio, ils ne seront modifiés pour utiliser Microsoft comme fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="d1fab-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="d1fab-157">Vous pouvez le remplacer par le fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="d1fab-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="d1fab-158">**Étapes suivantes**: une fois que vous affectez des licences de services d’audioconférence, vous devez lui assigner un fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="d1fab-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="d1fab-159">Voir [Assigner de Microsoft en tant que le fournisseur de services d’audioconférence](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="d1fab-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="d1fab-160">Attribuer une licence de conférence Audio à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="d1fab-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="d1fab-161">Les étapes sont les mêmes que pour affecter un licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1fab-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="d1fab-162">Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="d1fab-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="d1fab-163">Attribution de licences de conférence Audio en bloc</span><span class="sxs-lookup"><span data-stu-id="d1fab-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="d1fab-164">Téléchargez et installez [Microsoft Online Services Assistant de connexion pour les professionnels de l’informatique RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="d1fab-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="d1fab-165">Téléchargez et installez le module Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1fab-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="d1fab-166">Pour des instructions de téléchargement et de la syntaxe de l’applet de commande, voir [Gérer Azure AD à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .</span><span class="sxs-lookup"><span data-stu-id="d1fab-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="d1fab-167">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="d1fab-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="d1fab-168">Le nom des licences ou des noms de produits dans le script sont répertoriés en italique.</span><span class="sxs-lookup"><span data-stu-id="d1fab-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="d1fab-169">Voir [les noms de produits audioconférence ou SKU utilisé pour les scripts](#audio-conferencing-product-names-or-skus-used-for-scripting) pour tous les noms de produits.</span><span class="sxs-lookup"><span data-stu-id="d1fab-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="d1fab-170">Cet exemple attribue une licence entreprise E3 avec une licence d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="d1fab-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

```
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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="d1fab-171">Les noms de produits de conférence audio ou des références de script</span><span class="sxs-lookup"><span data-stu-id="d1fab-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="d1fab-172">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d1fab-172">Product name</span></span> | <span data-ttu-id="d1fab-173">Référence</span><span class="sxs-lookup"><span data-stu-id="d1fab-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="d1fab-174">Services d’audioconférence (abonnement)</span><span class="sxs-lookup"><span data-stu-id="d1fab-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="d1fab-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="d1fab-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="d1fab-176">Audio conférence payer par Minute (retenues)</span><span class="sxs-lookup"><span data-stu-id="d1fab-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="d1fab-177">*Remarque : nécessite crédits Communications configuré et activé*.</span><span class="sxs-lookup"><span data-stu-id="d1fab-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="d1fab-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="d1fab-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="d1fab-179">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="d1fab-179">Enterprise E1</span></span> | <span data-ttu-id="d1fab-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="d1fab-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="d1fab-181">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="d1fab-181">Enterprise E3</span></span> | <span data-ttu-id="d1fab-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="d1fab-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="d1fab-183">Entreprise E5 (sans Audioconférence)</span><span class="sxs-lookup"><span data-stu-id="d1fab-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="d1fab-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="d1fab-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="d1fab-185">Entreprise E5 (avec les services d’audioconférence)</span><span class="sxs-lookup"><span data-stu-id="d1fab-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="d1fab-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="d1fab-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="d1fab-187">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="d1fab-187">Communications Credits</span></span>

<span data-ttu-id="d1fab-188">Voici ce que vous devez connaître avant d’attribution de licences crédits Communications.</span><span class="sxs-lookup"><span data-stu-id="d1fab-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="d1fab-189">**Clients Enterprise E5**: même si vos utilisateurs sont affectées des licences Enterprise E5, nous vous recommandons d’affecter les licences crédits Communications.</span><span class="sxs-lookup"><span data-stu-id="d1fab-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="d1fab-190">**Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d1fab-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="d1fab-191">Pour obtenir des instructions pas à pas, consultez [configurer des Plans de l’appel](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="d1fab-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="d1fab-192">Attribuer une licence de Communications générique à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="d1fab-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="d1fab-193">Les étapes sont les mêmes que pour affecter un licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1fab-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="d1fab-194">Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="d1fab-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="d1fab-195">Attribution de licences Communications crédits en bloc</span><span class="sxs-lookup"><span data-stu-id="d1fab-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="d1fab-196">Jetez un œil à l’exemple de script pour l’attribution de licences de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="d1fab-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="d1fab-197">Mettre à jour avec les informations de l’attribution de licences crédits Communications.</span><span class="sxs-lookup"><span data-stu-id="d1fab-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1fab-198">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d1fab-198">Related topics</span></span>

[<span data-ttu-id="d1fab-199">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="d1fab-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="d1fab-200">Ajouter des fonds et gérer les Crédits de Communications</span><span class="sxs-lookup"><span data-stu-id="d1fab-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
