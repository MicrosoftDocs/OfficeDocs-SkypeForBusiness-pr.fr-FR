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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: "Apprenez comment affecter des licences Skype Entreprise pour le Système téléphonique, l'Audioconférence, les Plans d'appel et les Crédits de communications. "
ms.openlocfilehash: e81c4c4d2fc11202ac114912ca309d93b00f2062
ms.sourcegitcommit: f9a9a7e4b7f6c821a3372f7dcb966a8a6d458752
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2019
ms.locfileid: "30952464"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="f2a95-103">Attribuer des licences Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="f2a95-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="f2a95-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="f2a95-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2a95-106">Voir [Skype pour les licences d’entreprise module complémentaire](skype-for-business-and-microsoft-teams-add-on-licensing.md) pour plus d’informations sur les licences, vous devez acheter et les **Comment acheter** les - selon votre Office 365 planifier - afin que les utilisateurs obtiennent l’audioconférence et la possibilité d’appeler des numéros de téléphone à l’extérieur de numéros gratuits votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="f2a95-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="f2a95-107">Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences</span><span class="sxs-lookup"><span data-stu-id="f2a95-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="f2a95-108">Ce que vous devez connaître avant d’affecter des licences Audioconférence, Système téléphonique et Forfait d'appels</span><span class="sxs-lookup"><span data-stu-id="f2a95-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="f2a95-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="f2a95-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="f2a95-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="f2a95-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="f2a95-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span><span class="sxs-lookup"><span data-stu-id="f2a95-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="f2a95-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="f2a95-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="f2a95-118">Comment attribuer une licence de système téléphonique et planifier l’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="f2a95-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="f2a95-119">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="f2a95-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="f2a95-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="f2a95-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="f2a95-121">Comment affecter des licences Système téléphonique et Forfait d’appel en volume</span><span class="sxs-lookup"><span data-stu-id="f2a95-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="f2a95-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="f2a95-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="f2a95-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="f2a95-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="f2a95-128">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="f2a95-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="f2a95-129">Cet exemple affecte une **licence Entreprise E3**, ainsi qu'une licence **Système téléphonique** et **Forfait d’appels interne**.</span><span class="sxs-lookup"><span data-stu-id="f2a95-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="f2a95-130">Le nom des licences ou des noms de produits dans le script sont répertoriés dans le texte italique (voir **système téléphonique et appel de planifier les noms de produits ou SKU utilisé pour les scripts**, après l’exemple).</span><span class="sxs-lookup"><span data-stu-id="f2a95-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="f2a95-131">Système téléphonique et appel des Plans de noms de produits ou des références destinés script</span><span class="sxs-lookup"><span data-stu-id="f2a95-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="f2a95-132">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="f2a95-132">**Product name**</span></span>|<span data-ttu-id="f2a95-133">**Référence**</span><span class="sxs-lookup"><span data-stu-id="f2a95-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f2a95-134">Entreprise E5 (avec Système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="f2a95-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="f2a95-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="f2a95-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="f2a95-136">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="f2a95-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="f2a95-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="f2a95-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="f2a95-138">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="f2a95-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="f2a95-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="f2a95-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="f2a95-140">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f2a95-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="f2a95-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="f2a95-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="f2a95-142">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="f2a95-142">Phone System</span></span>  <br/> |<span data-ttu-id="f2a95-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="f2a95-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="f2a95-144">Plan d’appels internationaux</span><span class="sxs-lookup"><span data-stu-id="f2a95-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="f2a95-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="f2a95-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="f2a95-146">Forfait d'appels nationaux</span><span class="sxs-lookup"><span data-stu-id="f2a95-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="f2a95-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="f2a95-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="f2a95-148">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="f2a95-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="f2a95-149">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="f2a95-149">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="f2a95-150">Services d’audioconférence : Conseils et des scripts pour l’attribution de licences</span><span class="sxs-lookup"><span data-stu-id="f2a95-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="f2a95-151">Vous devez connaître avant d’attribution de licences d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="f2a95-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="f2a95-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span><span class="sxs-lookup"><span data-stu-id="f2a95-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="f2a95-p110">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. See [Assign Microsoft as the audio conferencing provider].</span><span class="sxs-lookup"><span data-stu-id="f2a95-p110">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="f2a95-156">Comment attribuer une licence de conférence Audio à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="f2a95-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="f2a95-157">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="f2a95-157">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="f2a95-158">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="f2a95-158">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="f2a95-159">Comment attribuer des licences d’audioconférence en bloc</span><span class="sxs-lookup"><span data-stu-id="f2a95-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="f2a95-160">Téléchargez et installez [Microsoft Online Services Assistant de connexion pour les professionnels de l’informatique RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="f2a95-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="f2a95-p112">Téléchargez et installez le **module Windows Azure Active Directory**. Pour connaître les instructions de téléchargement et la syntaxe des applets de commande, reportez-vous à la rubrique[Gestion d'Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="f2a95-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="f2a95-163">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="f2a95-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="f2a95-p113">The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span><span class="sxs-lookup"><span data-stu-id="f2a95-p113">The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="f2a95-166">Cet exemple attribue une licence entreprise E3 avec une licence d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="f2a95-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="f2a95-167">Les noms de produits de conférence audio ou des références destinés script</span><span class="sxs-lookup"><span data-stu-id="f2a95-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="f2a95-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="f2a95-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="f2a95-169">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="f2a95-169">**Product name**</span></span>|<span data-ttu-id="f2a95-170">**Référence**</span><span class="sxs-lookup"><span data-stu-id="f2a95-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f2a95-171">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="f2a95-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="f2a95-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="f2a95-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="f2a95-173">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f2a95-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="f2a95-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="f2a95-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="f2a95-175">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="f2a95-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="f2a95-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="f2a95-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="f2a95-177">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="f2a95-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="f2a95-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="f2a95-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="f2a95-179">Entreprise E5 (sans Audioconférence)</span><span class="sxs-lookup"><span data-stu-id="f2a95-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="f2a95-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="f2a95-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="f2a95-181">Entreprise E5 (avec les services d’audioconférence)</span><span class="sxs-lookup"><span data-stu-id="f2a95-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="f2a95-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="f2a95-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="f2a95-183">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="f2a95-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="f2a95-184">Vous devez connaître avant d’attribution de licences crédits Communications</span><span class="sxs-lookup"><span data-stu-id="f2a95-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="f2a95-185">**Clients Enterprise E5**: même si vos utilisateurs sont affectées des licences Enterprise E5, nous vous recommandons d’affecter les licences **Crédits Communications** .</span><span class="sxs-lookup"><span data-stu-id="f2a95-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="f2a95-p114">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="f2a95-p114">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="f2a95-188">Comment attribuer une licence Communications générique à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="f2a95-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="f2a95-189">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="f2a95-189">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="f2a95-190">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="f2a95-190">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="f2a95-191">Comment attribuer des licences Communications crédits en bloc</span><span class="sxs-lookup"><span data-stu-id="f2a95-191">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="f2a95-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span><span class="sxs-lookup"><span data-stu-id="f2a95-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2a95-194">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="f2a95-194">Related topics</span></span>
  
[<span data-ttu-id="f2a95-195">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="f2a95-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="f2a95-196">Ajouter des fonds et gérer les Crédits de Communications</span><span class="sxs-lookup"><span data-stu-id="f2a95-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
