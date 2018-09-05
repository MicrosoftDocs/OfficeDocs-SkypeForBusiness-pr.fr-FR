---
title: Attribuer des licences Skype Entreprise et Microsoft Teams
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
ms.openlocfilehash: fef4bea3971f2984e46de7a3592b1a157076c879
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780666"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="c9d65-103">Attribuer des licences Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9d65-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="c9d65-104">Cet article vous donne des conseils sur l’affectation de licences à vos utilisateurs pour des fonctionnalités telles que l'Audioconférence, le Système téléphonique et les Forfaits d’appels.</span><span class="sxs-lookup"><span data-stu-id="c9d65-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="c9d65-105">Il vous fournit également des scripts pour affecter des licences en bloc.</span><span class="sxs-lookup"><span data-stu-id="c9d65-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9d65-106">Voir [Octroi de licences de compléments Skype Entreprise et Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md) pour plus d’informations sur quelles licences vous devez acheter et **Comment acheter** ces dernières - en fonction de votre plan Office 365 -, de façon à ce que les utilisateurs disposent de l’Audioconférence, de numéros gratuits, et de la possibilité d’appeler des numéros de téléphone à l’extérieur de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="c9d65-106">IMPORTANT: See[Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get dial-in conferencing, toll free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="c9d65-107">Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences</span><span class="sxs-lookup"><span data-stu-id="c9d65-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="c9d65-108">Ce que vous devez connaître avant d’affecter des licences Audioconférence, Système téléphonique et Forfait d'appels</span><span class="sxs-lookup"><span data-stu-id="c9d65-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="c9d65-109">**Vous utilisez la connectivité PSTN locale pour les utilisateurs hybrides ?**</span><span class="sxs-lookup"><span data-stu-id="c9d65-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="c9d65-110">Dans ce cas, vous avez seulement besoin d’affecter une licence de **Système téléphonique**.</span><span class="sxs-lookup"><span data-stu-id="c9d65-110">If so, you only need to assign a Skype for Business Cloud PBX license.</span></span> <span data-ttu-id="c9d65-111">Vous ne devez **PAS** affecter un Forfait d'appels.</span><span class="sxs-lookup"><span data-stu-id="c9d65-111">You should **NOT** assign a PSTN Calling plan.</span></span>

- <span data-ttu-id="c9d65-112">**Latence après affectation de licences** : en raison de la latence entre Office 365 et Skype Entreprise Online, jusqu'à 24 heures peuvent être nécessaires pour qu'un utilisateur se voie affecter un Plan d'appel après que vous lui avez affecté une licence.</span><span class="sxs-lookup"><span data-stu-id="c9d65-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be enabled for PSTN Calling after you assign a license.</span></span> <span data-ttu-id="c9d65-113">Si après 24 heures, l’utilisateur ne se voit pas affecter un Forfait d’appels, veuillez [Contacter le support pour les produits entreprise : aide à l’administration](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="c9d65-113">If after 24 hours, the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="c9d65-114">**Messages d'erreur** : un message d'erreur s'affiche si vous n'avez pas acheté le nombre correct de licences.</span><span class="sxs-lookup"><span data-stu-id="c9d65-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="c9d65-115">Si vous devez acheter davantage de licences de Forfait d'appels, choisissez **Acheter plus**.</span><span class="sxs-lookup"><span data-stu-id="c9d65-115">If you need to buy more licenses to enable this user for PSTN Calling, choose **Buy more**.</span></span>
    
- <span data-ttu-id="c9d65-116">**Prochaines étapes** : après que vous aurez affecté des licences de Forfaits d'appels à vos utilisateurs, vous aurez besoin d'obtenir les numéros de téléphone de votre organisation, puis de les affecter aux personnes dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c9d65-116">**Next steps**: After you assign PSTN Calling plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="c9d65-117">Pour des instructions pas à pas, voir [Configurer des Forfaits d'appels](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="c9d65-117">For step-by-step setup instructions, see Set up Calling Plans.</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="c9d65-118">Comment affecter une licence Système téléphonique et Forfait d’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c9d65-118">How to assign a Cloud PBX and PSTN Calling license to one user</span></span>

<span data-ttu-id="c9d65-p106">Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c9d65-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="c9d65-121">Comment affecter des licences Système téléphonique et Forfait d’appel en volume</span><span class="sxs-lookup"><span data-stu-id="c9d65-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="c9d65-122">Installez l' **Assistant de connexion Microsoft Online Services pour les informaticiens RTW**.</span><span class="sxs-lookup"><span data-stu-id="c9d65-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="c9d65-123">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="c9d65-123">Don't have the module installed?</span></span> <span data-ttu-id="c9d65-124">Voir [Assistant de connexion Microsoft Online Services pour les professionnels des technologies de l'information RTW](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.</span><span class="sxs-lookup"><span data-stu-id="c9d65-124">See[Microsoft Online Services Sign-In Assistant for IT Professionals RTW ](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="c9d65-125">Installez le **module Windows Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c9d65-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="c9d65-126">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="c9d65-126">Don't have the module installed?</span></span> <span data-ttu-id="c9d65-127">Voir [Gérez Azure AD en utilisant Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) pour les instructions de téléchargement et la syntaxe de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c9d65-127">See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="c9d65-128">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="c9d65-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

  <span data-ttu-id="c9d65-129">Cet exemple affecte une **licence Entreprise E3**, ainsi qu'une licence **Système téléphonique** et **Forfait d’appels interne**.</span><span class="sxs-lookup"><span data-stu-id="c9d65-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

  <span data-ttu-id="c9d65-130">Le nom des licences ou les noms des produits dans le script sont listés en italique dans le texte (reportez-vous à la rubrique **Système téléphonique et noms des produits de Forfaits d’appels RTC ou UGS utilisés pour l’écriture de scripts**, après l’exemple).</span><span class="sxs-lookup"><span data-stu-id="c9d65-130">The name of the licenses or product names in the script are listed in italics text (see **Cloud PBX and PSTN Calling product names or SKUs used for scripting**, after the example).</span></span>

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="c9d65-131">Système téléphonique et noms des produits Forfaits d’appel ou UGS utilisés pour l’écriture de scripts</span><span class="sxs-lookup"><span data-stu-id="c9d65-131">Cloud PBX and PSTN Calling product names or SKUs used for scripting</span></span>

|<span data-ttu-id="c9d65-132">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="c9d65-132">**Product name**</span></span>|<span data-ttu-id="c9d65-133">**Référence**</span><span class="sxs-lookup"><span data-stu-id="c9d65-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9d65-134">Entreprise E5 (avec Système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="c9d65-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="c9d65-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c9d65-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="c9d65-136">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="c9d65-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="c9d65-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="c9d65-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="c9d65-138">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="c9d65-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="c9d65-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="c9d65-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="c9d65-140">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c9d65-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="c9d65-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="c9d65-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="c9d65-142">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="c9d65-142">Phone System</span></span>  <br/> |<span data-ttu-id="c9d65-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="c9d65-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="c9d65-144">Forfait d'appels international</span><span class="sxs-lookup"><span data-stu-id="c9d65-144">International and Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="c9d65-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="c9d65-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="c9d65-146">Forfait d'appels nationaux</span><span class="sxs-lookup"><span data-stu-id="c9d65-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="c9d65-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="c9d65-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="c9d65-148">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="c9d65-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="c9d65-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="c9d65-149">MCOPSTNPP</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="c9d65-150">Audioconférence : conseils et scripts pour affecter les licences</span><span class="sxs-lookup"><span data-stu-id="c9d65-150">PSTN conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="c9d65-151">Ce que vous devez savoir avant d'affecter des licences d'Audioconférence</span><span class="sxs-lookup"><span data-stu-id="c9d65-151">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="c9d65-152">**Fournisseur de services d’audioconférence tiers** : si des personnes sont déjà configurées pour utiliser un fournisseur de services d’audioconférence tiers, lorsque vous leur affectez une licence d'**Audioconférence**, elles seront modifiées pour utiliser Microsoft comme fournisseur d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="c9d65-152">**Third-party conferencing provider**: If someone is already set up to use a third-party dial-in conferencing provider, when you assign them a **Skype for Business PSTN Conferencing** license, they will be changed to use Microsoft as the dial-in conferencing provider.</span></span> <span data-ttu-id="c9d65-153">Vous pouvez le remplacer par le fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="c9d65-153">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="c9d65-154">Étapes suivantes : après avoir affecté des licences d'**Audioconférence**, vous devez affecter un fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="c9d65-154">Next steps: After you assign PSTN conferencing licenses, you need to assign a dial-in conferencing provider.</span></span> <span data-ttu-id="c9d65-155">Voir [Affecter Microsoft comme fournisseur d'audioconférence].</span><span class="sxs-lookup"><span data-stu-id="c9d65-155">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="c9d65-156">Comment affecter une licence d’Audioconférence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c9d65-156">How to assign a PSTN Conferencing license to one user</span></span>

<span data-ttu-id="c9d65-p111">Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c9d65-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="c9d65-159">Comment affecter des licences d’Audioconférence en volume</span><span class="sxs-lookup"><span data-stu-id="c9d65-159">How to assign PSTN conferencing licenses in bulk</span></span>

1. <span data-ttu-id="c9d65-160">Téléchargez et installez l’[Assistant de connexion à Microsoft Online Services pour les professionnels des technologies de l’information RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="c9d65-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="c9d65-p112">Téléchargez et installez le **module Windows Azure Active Directory**. Pour connaître les instructions de téléchargement et la syntaxe des applets de commande, reportez-vous à la rubrique[Gestion d'Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="c9d65-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="c9d65-163">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="c9d65-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="c9d65-164">Les noms de licence ou de produit dans le script sont notés en italique.</span><span class="sxs-lookup"><span data-stu-id="c9d65-164">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="c9d65-165">Voir [Noms des produits d’Audioconférence ou UGS utilisés pour l’écriture de scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) pour tous les noms de produits.</span><span class="sxs-lookup"><span data-stu-id="c9d65-165">See [Dial-in conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="c9d65-166">Cet exemple affecte une licence Entreprise E3 avec une licence Audioconférence.</span><span class="sxs-lookup"><span data-stu-id="c9d65-166">This example assigns an Enterprise E3 license along with a PSTN Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="c9d65-167">Noms des produits d’Audioconférence ou UGS utilisés pour l’écriture de scripts</span><span class="sxs-lookup"><span data-stu-id="c9d65-167">Dial-in conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="c9d65-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="c9d65-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="c9d65-169">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="c9d65-169">**Product name**</span></span>|<span data-ttu-id="c9d65-170">**Référence**</span><span class="sxs-lookup"><span data-stu-id="c9d65-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9d65-171">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="c9d65-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="c9d65-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="c9d65-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="c9d65-173">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="c9d65-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="c9d65-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="c9d65-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="c9d65-175">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="c9d65-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="c9d65-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="c9d65-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="c9d65-177">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="c9d65-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="c9d65-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="c9d65-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="c9d65-179">Entreprise E5 (sans Audioconférence)</span><span class="sxs-lookup"><span data-stu-id="c9d65-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="c9d65-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="c9d65-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="c9d65-181">Entreprise E5 (avec Audioconférence)</span><span class="sxs-lookup"><span data-stu-id="c9d65-181">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="c9d65-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c9d65-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="c9d65-183">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="c9d65-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="c9d65-184">Ce que vous devez savoir avant l’affectation de licences de Crédits de communications</span><span class="sxs-lookup"><span data-stu-id="c9d65-184">What you need to know before assigning PSTN Consumption licenses</span></span>

- <span data-ttu-id="c9d65-185">**Clients Entreprise E5** : même si vos utilisateurs se sont vus affecter des licences Enterprise E5, nous vous recommandons néanmoins de leur affecter des licences **Crédits de communication**.</span><span class="sxs-lookup"><span data-stu-id="c9d65-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Skype for Business PSTN Consumption** licenses.</span></span>
    
- <span data-ttu-id="c9d65-186">**Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c9d65-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="c9d65-187">Pour des instructions pas à pas, voir [Configurer des Forfaits d’appels](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="c9d65-187">For step-by-step setup instructions, see Set up Calling Plans.</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="c9d65-188">Comment affecter une licence Crédits de communications à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="c9d65-188">How to assign a PSTN Conferencing license to one user</span></span>

<span data-ttu-id="c9d65-p115">Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c9d65-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="c9d65-191">Comment affecter des licences Crédits de communications en volume</span><span class="sxs-lookup"><span data-stu-id="c9d65-191">How to assign PSTN conferencing licenses in bulk</span></span>

<span data-ttu-id="c9d65-192">Jetez un coup d'œil à l'exemple de script pour l'affectation des licences d'**Audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="c9d65-192">Take a look at the sample script for assigning PSTN Conferencing licenses.</span></span> <span data-ttu-id="c9d65-193">Mettez-le à jour avec les informations d’affectation de licences **Crédits de communications**.</span><span class="sxs-lookup"><span data-stu-id="c9d65-193">Update it with the info for assigning PSTN Consumption licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c9d65-194">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c9d65-194">Related topics</span></span>
  
[<span data-ttu-id="c9d65-195">Configurer des offres d'appels</span><span class="sxs-lookup"><span data-stu-id="c9d65-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="c9d65-196">Ajouter des fonds et gérer les crédits de communication</span><span class="sxs-lookup"><span data-stu-id="c9d65-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
