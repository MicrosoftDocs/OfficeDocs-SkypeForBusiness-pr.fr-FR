---
title: Attribuer des licences Skype Entreprise
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: "Apprenez comment affecter des licences Skype Entreprise pour le Système téléphonique, l'Audioconférence, les Plans d'appel et les Crédits de communications. "
ms.openlocfilehash: 997cffce5b98ed992371a0f43e701b2efc1ae128
ms.sourcegitcommit: 6d5f09acdcdc8d5a36f7ac785349209e7496f17d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2019
ms.locfileid: "34768774"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="b4b0b-103">Attribuer des licences Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b4b0b-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="b4b0b-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4b0b-106">Pour plus d’informations sur les licences que vous devez acheter et sur **la manière de les acheter** , reportez-vous à la rubrique [licences de compléments Skype entreprise](skype-for-business-and-microsoft-teams-add-on-licensing.md) , en fonction de votre plan Office 365, afin que les utilisateurs obtiennent des conférences audio, des numéros gratuits et la possibilité d’appeler des numéros de téléphone en dehors de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="b4b0b-107">Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences</span><span class="sxs-lookup"><span data-stu-id="b4b0b-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="b4b0b-108">Ce que vous devez connaître avant d’affecter des licences Audioconférence, Système téléphonique et Forfait d'appels</span><span class="sxs-lookup"><span data-stu-id="b4b0b-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="b4b0b-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="b4b0b-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="b4b0b-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="b4b0b-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="b4b0b-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="b4b0b-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="b4b0b-118">Attribution d’un système téléphonique et d’une licence de plan d’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="b4b0b-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="b4b0b-119">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="b4b0b-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="b4b0b-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="b4b0b-121">Comment affecter des licences Système téléphonique et Forfait d’appel en volume</span><span class="sxs-lookup"><span data-stu-id="b4b0b-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="b4b0b-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="b4b0b-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="b4b0b-128">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="b4b0b-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="b4b0b-129">Cet exemple affecte une **licence Entreprise E3**, ainsi qu'une licence **Système téléphonique** et **Forfait d’appels interne**.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="b4b0b-130">Le nom des licences ou des noms de produits figurant dans le script est affiché en italique (voir le **système téléphonique et les noms des produits de plan d’appel et les références (SKU) utilisées pour l’écriture de scripts**, après l’exemple).</span><span class="sxs-lookup"><span data-stu-id="b4b0b-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="b4b0b-131">Système téléphonique et offres d’appels noms de produits ou UGS utilisés pour l’écriture de scripts</span><span class="sxs-lookup"><span data-stu-id="b4b0b-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="b4b0b-132">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="b4b0b-132">**Product name**</span></span>|<span data-ttu-id="b4b0b-133">**Référence**</span><span class="sxs-lookup"><span data-stu-id="b4b0b-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4b0b-134">Entreprise E5 (avec Système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="b4b0b-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="b4b0b-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b4b0b-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="b4b0b-136">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="b4b0b-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="b4b0b-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b4b0b-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="b4b0b-138">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="b4b0b-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="b4b0b-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b4b0b-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="b4b0b-140">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b4b0b-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="b4b0b-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="b4b0b-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="b4b0b-142">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="b4b0b-142">Phone System</span></span>  <br/> |<span data-ttu-id="b4b0b-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="b4b0b-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="b4b0b-144">Forfait d’appels internationaux</span><span class="sxs-lookup"><span data-stu-id="b4b0b-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="b4b0b-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="b4b0b-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="b4b0b-146">Forfait d’appels nationaux (3000 min US/1200 min Europe)</span><span class="sxs-lookup"><span data-stu-id="b4b0b-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="b4b0b-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="b4b0b-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="b4b0b-148">Forfait d’appels nationaux (forfait d’appels 120 min)</span><span class="sxs-lookup"><span data-stu-id="b4b0b-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="b4b0b-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="b4b0b-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="b4b0b-150">Forfait d’appels nationaux (forfait d’appels 240 min)</span><span class="sxs-lookup"><span data-stu-id="b4b0b-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="b4b0b-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="b4b0b-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="b4b0b-152">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="b4b0b-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="b4b0b-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="b4b0b-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="b4b0b-154">Audioconférence: conseils et scripts pour affecter des licences</span><span class="sxs-lookup"><span data-stu-id="b4b0b-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="b4b0b-155">Ce que vous devez savoir avant d’affecter des licences de conférence audio</span><span class="sxs-lookup"><span data-stu-id="b4b0b-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="b4b0b-156">Fournisseur de services d' **audioconférence tiers**: si une personne est déjà configurée pour utiliser un fournisseur de services d’audioconférence tiers, lorsque vous lui attribuez une licence d' **audioconférence** , elle est modifiée de manière à utiliser Microsoft comme audioconférence. fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="b4b0b-157">Vous pouvez le remplacer par le fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="b4b0b-158">Étapes suivantes: une fois que vous avez attribué des licences de **conférence audio** , vous devez affecter un fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="b4b0b-159">Voir [Affecter Microsoft comme fournisseur d'audioconférence].</span><span class="sxs-lookup"><span data-stu-id="b4b0b-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="b4b0b-160">Comment affecter une licence de conférence audio à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="b4b0b-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="b4b0b-161">Les étapes sont les mêmes que pour affecter un licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="b4b0b-162">Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="b4b0b-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="b4b0b-163">Comment affecter des licences de conférence audio en bloc</span><span class="sxs-lookup"><span data-stu-id="b4b0b-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="b4b0b-164">Téléchargez et installez [l’Assistant de connexion de Microsoft Online Services pour les informaticiens RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="b4b0b-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="b4b0b-p112">Téléchargez et installez le **module Windows Azure Active Directory**. Pour connaître les instructions de téléchargement et la syntaxe des applets de commande, reportez-vous à la rubrique[Gestion d'Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="b4b0b-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="b4b0b-167">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="b4b0b-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="b4b0b-168">Le nom des licences ou des produits du script est répertorié dans le texte en italique.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="b4b0b-169">Voir les noms des produits de l’audioconférence pour l' [écriture de scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) pour l’ensemble des noms de produits.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="b4b0b-170">Cet exemple affecte une licence entreprise E3, ainsi qu’une licence de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="b4b0b-171">Noms des produits de conférence audio ou références (SKU) utilisés pour l’écriture de scripts</span><span class="sxs-lookup"><span data-stu-id="b4b0b-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="b4b0b-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="b4b0b-172"></span></span>

|<span data-ttu-id="b4b0b-173">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="b4b0b-173">**Product name**</span></span>|<span data-ttu-id="b4b0b-174">**Référence**</span><span class="sxs-lookup"><span data-stu-id="b4b0b-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4b0b-175">Audioconférence,</span><span class="sxs-lookup"><span data-stu-id="b4b0b-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="b4b0b-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="b4b0b-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="b4b0b-177">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b4b0b-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="b4b0b-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="b4b0b-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="b4b0b-179">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="b4b0b-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="b4b0b-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="b4b0b-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="b4b0b-181">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="b4b0b-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="b4b0b-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="b4b0b-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="b4b0b-183">Entreprise E5 (sans Audioconférence)</span><span class="sxs-lookup"><span data-stu-id="b4b0b-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="b4b0b-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="b4b0b-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="b4b0b-185">Entreprise E5 (avec audioconférence)</span><span class="sxs-lookup"><span data-stu-id="b4b0b-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="b4b0b-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="b4b0b-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="b4b0b-187">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="b4b0b-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="b4b0b-188">Ce que vous devez savoir avant d’affecter des licences de crédits de communication</span><span class="sxs-lookup"><span data-stu-id="b4b0b-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="b4b0b-189">**Clients entreprise E5**: même si des licences entreprise E5 ont été affectées à vos utilisateurs, nous vous conseillons de leur affecter des licences de **crédits de communication** .</span><span class="sxs-lookup"><span data-stu-id="b4b0b-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="b4b0b-190">**Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="b4b0b-191">Pour obtenir des instructions détaillées, consultez la rubrique [configurer les offres d’appels](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="b4b0b-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="b4b0b-192">Comment affecter une licence de crédits de communication à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="b4b0b-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="b4b0b-193">Les étapes sont les mêmes que pour affecter un licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4b0b-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="b4b0b-194">Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="b4b0b-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="b4b0b-195">Comment attribuer des crédits de communication en bloc</span><span class="sxs-lookup"><span data-stu-id="b4b0b-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="b4b0b-196">Jetez un coup d’œil à l’exemple de script permettant d’affecter des licences de **conférence audio** .</span><span class="sxs-lookup"><span data-stu-id="b4b0b-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="b4b0b-197">Mettez-le à jour avec les informations relatives à l’affectation de licences de **crédits de communication** .</span><span class="sxs-lookup"><span data-stu-id="b4b0b-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b4b0b-198">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b4b0b-198">Related topics</span></span>
  
[<span data-ttu-id="b4b0b-199">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="b4b0b-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="b4b0b-200">Ajouter des fonds et gérer les Crédits de Communications</span><span class="sxs-lookup"><span data-stu-id="b4b0b-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
