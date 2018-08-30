---
title: Affecter des licences Skype Entreprise et Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Licensing
description: "Apprenez comment affecter des licences Skype Entreprise pour le Système téléphonique, l'Audioconférence, les Plans d'appel et les Crédits de communications. "
ms.openlocfilehash: 8b83286ef854518197d3b04c23f49bc00ceca2ba
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23253445"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="e5999-103">Affecter des licences Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e5999-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="e5999-104">Cet article vous donne des conseils sur l’affectation de licences à vos utilisateurs pour des fonctionnalités telles que l'Audioconférence, le Système téléphonique et les Forfaits d’appels.</span><span class="sxs-lookup"><span data-stu-id="e5999-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="e5999-105">Il vous fournit également des scripts pour affecter des licences en bloc.</span><span class="sxs-lookup"><span data-stu-id="e5999-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5999-106">Voir [Licence des compléments Skype Entreprise et Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md) pour plus d’informations sur quelles licences vous devez acheter et **Comment acheter** ces dernières - en fonction de votre plan Office 365 -, de façon à ce que les utilisateurs disposent de l’Audioconférence, des numéros gratuits, et de la possibilité d'appeler des numéros de téléphone à l’extérieur de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="e5999-106">[IMPORTANT](skype-for-business-and-microsoft-teams-add-on-licensing.md): See**Skype for Business add-on licensing** for information about what licenses you need to buy and how to buy them - depending on your Office 365 plan - so users get dial-in conferencing, toll free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="e5999-107">Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences</span><span class="sxs-lookup"><span data-stu-id="e5999-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="e5999-108">Ce que vous devez connaître avant d’affecter des licences Audioconférence, Système téléphonique et Forfait d'appels</span><span class="sxs-lookup"><span data-stu-id="e5999-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="e5999-109">**Utilisation de la connectivité RTC locale pour les utilisateurs hybrides ?**</span><span class="sxs-lookup"><span data-stu-id="e5999-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="e5999-110">Dans ce cas, vous avez seulement besoin d'affecter une licence de **Système téléphonique**.</span><span class="sxs-lookup"><span data-stu-id="e5999-110">If so, you only need to assign a Skype for Business Cloud PBX license.</span></span> <span data-ttu-id="e5999-111">Vous NE devriez **PAS** affecter un Forfait d'appels.</span><span class="sxs-lookup"><span data-stu-id="e5999-111">You should **NOT** assign a PSTN Calling plan.</span></span>

- <span data-ttu-id="e5999-112">**Latence après affectation de licences** : en raison de la latence entre Office 365 et Skype Entreprise Online, jusqu'à 24 heures peuvent être nécessaires pour qu'un utilisateur se voie affecter un Plan d'appel après que vous avez affecté une licence.</span><span class="sxs-lookup"><span data-stu-id="e5999-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be enabled for PSTN Calling after you assign a license.</span></span> <span data-ttu-id="e5999-113">Si après 24 heures, l’utilisateur ne se voit pas affecter un Forfait d’appels, veuillez [Contacter le support pour les produits métiers : aide d’administration](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="e5999-113">If after 24 hours, the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="e5999-114">**Messages d'erreur** : vous recevrez un message d'erreur si vous n'avez pas acheté le nombre correct de licences.</span><span class="sxs-lookup"><span data-stu-id="e5999-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="e5999-115">Si vous devez acheter davantage de licences de Forfaits d'appels, choisissez **Acheter plus**.</span><span class="sxs-lookup"><span data-stu-id="e5999-115">If you need to buy more licenses to enable this user for PSTN Calling, choose **Buy more**.</span></span>

- <span data-ttu-id="e5999-116">**Prochaines étapes** : après que vous aurez affecté des licences de Forfaits d'appels à vos utilisateurs, vous aurez besoin d'obtenir les numéros de téléphone de votre organisation, puis de les affecter aux personnes dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e5999-116">**Next steps**: After you assign PSTN Calling plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="e5999-117">Pour des instructions pas à pas, voir [Configurer des Forfaits d'appels](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="e5999-117">For step-by-step setup instructions, see Set up Calling Plans.</span></span>

### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="e5999-118">Comment affecter une licence Système téléphonique et Forfait d’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="e5999-118">How to assign a Cloud PBX and PSTN Calling license to one user</span></span>

<span data-ttu-id="e5999-p106">Les étapes sont les mêmes que l'affectation d'une licence Office 365. Voir [Affecter ou retirer des licences pour Office 365 Entreprise](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="e5999-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="e5999-121">Comment affecter des licences Système téléphonique et Forfait d’appel en volume</span><span class="sxs-lookup"><span data-stu-id="e5999-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="e5999-122">Installez l'**Assistant de connexion à Microsoft Online Services pour les professionnels des technologies de l'information RTW**.</span><span class="sxs-lookup"><span data-stu-id="e5999-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="e5999-123">Vous n'avez pas le module installé ?</span><span class="sxs-lookup"><span data-stu-id="e5999-123">Don't have the module installed?</span></span> <span data-ttu-id="e5999-124">Voir [Assistant de connexion Microsoft Online Services pour les professionnels des technologies de l'information RTW](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.</span><span class="sxs-lookup"><span data-stu-id="e5999-124">See[Microsoft Online Services Sign-In Assistant for IT Professionals RTW ](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="e5999-125">Installez le **Module Windows Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="e5999-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="e5999-126">Vous n'avez pas le module installé ?</span><span class="sxs-lookup"><span data-stu-id="e5999-126">Don't have the module installed?</span></span> <span data-ttu-id="e5999-127">Voir [Gérez Azure AD en utilisant Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) pour les instructions de téléchargement and la syntaxe des cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e5999-127">See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="e5999-128">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="e5999-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

  <span data-ttu-id="e5999-129">Cet exemple affecte une **licence Entreprise E3**, ainsi qu'une licence **Système téléphonique** et **Forfait d’appels interne**.</span><span class="sxs-lookup"><span data-stu-id="e5999-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

  <span data-ttu-id="e5999-130">Le nom des licences ou les noms des produits dans le script sont listés en italique dans le texte (reportez-vous à la rubrique **Système téléphonique et noms des produits de Forfaits d'appels RTC ou SKU utilisés pour l'écriture de scripts**, après l'exemple).</span><span class="sxs-lookup"><span data-stu-id="e5999-130">The name of the licenses or product names in the script are listed in italics text (see **Cloud PBX and PSTN Calling product names or SKUs used for scripting**, after the example).</span></span>

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="e5999-131">Système téléphonique et noms des produits Forfaits d'appel ou SKU utilisés pour l'écriture de scripts</span><span class="sxs-lookup"><span data-stu-id="e5999-131">Cloud PBX and PSTN Calling product names or SKUs used for scripting</span></span>

|<span data-ttu-id="e5999-132">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="e5999-132">**Product name**</span></span>|<span data-ttu-id="e5999-133">**Nom d'élément UGS**</span><span class="sxs-lookup"><span data-stu-id="e5999-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e5999-134">Entreprise E5 (avec Système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="e5999-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="e5999-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e5999-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="e5999-136">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="e5999-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="e5999-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="e5999-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="e5999-138">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="e5999-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="e5999-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="e5999-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="e5999-140">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e5999-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="e5999-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="e5999-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="e5999-142">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="e5999-142">Phone System</span></span>  <br/> |<span data-ttu-id="e5999-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="e5999-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="e5999-144">Forfait d'appels international</span><span class="sxs-lookup"><span data-stu-id="e5999-144">International and Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="e5999-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="e5999-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="e5999-146">Forfait d'appels local</span><span class="sxs-lookup"><span data-stu-id="e5999-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="e5999-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="e5999-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="e5999-148">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="e5999-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="e5999-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="e5999-149">MCOPSTNPP</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="e5999-150">Audioconférence : conseils et scripts pour affecter les licences</span><span class="sxs-lookup"><span data-stu-id="e5999-150">PSTN conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="e5999-151">Ce que vous devez savoir avant d'affecter des licences d'Audioconférence</span><span class="sxs-lookup"><span data-stu-id="e5999-151">What you need to know before assigning PSTN conferencing licenses</span></span>

- <span data-ttu-id="e5999-152">**Fournisseur de services d’audioconférence tiers** : si des personnes sont déjà configurées pour utiliser un fournisseur de services d’audioconférence tiers, lorsque vous leur affectez une licence d'**Audioconférence**, elles seront modifiées pour utiliser Microsoft comme fournisseur d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e5999-152">**Third-party conferencing provider**: If someone is already set up to use a third-party dial-in conferencing provider, when you assign them a **Skype for Business PSTN Conferencing** license, they will be changed to use Microsoft as the dial-in conferencing provider.</span></span> <span data-ttu-id="e5999-153">Vous pouvez les réaffecter au fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="e5999-153">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="e5999-154">Étapes suivantes : après que vous avez affecté des licences d'**Audioconférence**, vous devez lui affecter un fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e5999-154">Next steps: After you assign PSTN conferencing licenses, you need to assign a dial-in conferencing provider.</span></span> <span data-ttu-id="e5999-155">Voir [Affecter Microsoft comme fournisseur d'audioconférence].</span><span class="sxs-lookup"><span data-stu-id="e5999-155">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="e5999-156">Comment affecter une licence d'Audioconférence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="e5999-156">How to assign a PSTN Conferencing license to one user</span></span>

<span data-ttu-id="e5999-p111">Les étapes sont les mêmes que l'affectation d'une licence Office 365. Voir [Affecter ou retirer des licences pour Office 365 Entreprise](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="e5999-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="e5999-159">Comment affecter des licences d'Audioconférence en volume</span><span class="sxs-lookup"><span data-stu-id="e5999-159">How to assign PSTN conferencing licenses in bulk</span></span>

1. <span data-ttu-id="e5999-160">Téléchargez et installez l'[Assistant de connexion à Microsoft Online Services pour les professionnels des technologies de l'information RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="e5999-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="e5999-p112">Téléchargez et installez le **module Windows Azure Active Directory**. Voir [Gérez Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) pour les instructions de téléchargement et la syntaxe des cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e5999-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="e5999-163">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="e5999-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="e5999-164">Le nom des licences ou les noms de produits dans le script sont listés en italique.</span><span class="sxs-lookup"><span data-stu-id="e5999-164">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="e5999-165">Voir [Noms des produits d'Audioconférence ou SKU l'écriture de scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) pour tous les noms de produits.</span><span class="sxs-lookup"><span data-stu-id="e5999-165">See [Dial-in conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="e5999-166">Cet exemple affecte une licence Entreprise E3, ainsi qu'une licence Audioconférence.</span><span class="sxs-lookup"><span data-stu-id="e5999-166">This example assigns an Enterprise E3 license along with a PSTN Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="e5999-167">Noms des produits d'Audioconférence ou UGS utilisés pour l'écriture de scripts</span><span class="sxs-lookup"><span data-stu-id="e5999-167">Dial-in conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="e5999-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="e5999-168"></span></span>

|<span data-ttu-id="e5999-169">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="e5999-169">**Product name**</span></span>|<span data-ttu-id="e5999-170">**Nom d'élément UGS**</span><span class="sxs-lookup"><span data-stu-id="e5999-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e5999-171">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="e5999-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="e5999-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="e5999-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="e5999-173">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="e5999-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="e5999-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="e5999-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="e5999-175">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="e5999-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="e5999-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="e5999-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="e5999-177">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="e5999-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="e5999-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="e5999-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="e5999-179">Entreprise E5 (sans Audioconférence)</span><span class="sxs-lookup"><span data-stu-id="e5999-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="e5999-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="e5999-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="e5999-181">Entreprise E5 (avec Audioconférence)</span><span class="sxs-lookup"><span data-stu-id="e5999-181">Enterprise E5 (with dial-in conferencing)</span></span>  <br/> |<span data-ttu-id="e5999-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e5999-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="e5999-183">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="e5999-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="e5999-184">Ce que vous devez connaître avant l’affecttion de licences de Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="e5999-184">What you need to know before assigning PSTN Consumption licenses</span></span>

- <span data-ttu-id="e5999-185">**Clients Entreprise E5** : même si vos utilisateurs se sont vu affecter des licences Enterprise E5, nous vous recommandons néanmoins de leur affecter des licences **Crédits de communication**.</span><span class="sxs-lookup"><span data-stu-id="e5999-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Skype for Business PSTN Consumption** licenses.</span></span>

- <span data-ttu-id="e5999-186">**Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e5999-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="e5999-187">Pour des instructions pas à pas, voir [Configurer des Forfaits d'appels](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="e5999-187">For step-by-step setup instructions, see Set up Calling Plans.</span></span>

### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="e5999-188">Comment affecter une licence Crédits de communication à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="e5999-188">How to assign a PSTN Conferencing license to one user</span></span>

<span data-ttu-id="e5999-p115">Les étapes sont les mêmes que l'affectation d'une licence Office 365. Voir [Affecter ou retirer des licences pour Office 365 Entreprise](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="e5999-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="e5999-191">Comment affecter des licences Crédits de communications en volume</span><span class="sxs-lookup"><span data-stu-id="e5999-191">How to assign PSTN conferencing licenses in bulk</span></span>

<span data-ttu-id="e5999-192">Jetez un coup d'œil à l'exemple de script pour l'affectation des licences d'**Audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="e5999-192">Take a look at the sample script for assigning PSTN Conferencing licenses.</span></span> <span data-ttu-id="e5999-193">Mettez-la à jour avec les informations d’affectation de licences **Crédits de communication**.</span><span class="sxs-lookup"><span data-stu-id="e5999-193">Update it with the info for assigning PSTN Consumption licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5999-194">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="e5999-194">Related topics</span></span>

[<span data-ttu-id="e5999-195">Configurer des Forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="e5999-195">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)

[<span data-ttu-id="e5999-196">Ajouter des fonds et gérer les Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="e5999-196">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)


