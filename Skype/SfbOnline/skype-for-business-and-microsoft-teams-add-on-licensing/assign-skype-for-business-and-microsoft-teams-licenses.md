---
title: Affecter Skype pour les licences d’entreprise et Microsoft Teams
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
description: 'Découvrez comment attribuer Skype pour les licences d’entreprise pour système téléphonique, audioconférence, l’appel des Plans et crédits Communications. '
ms.openlocfilehash: 00c80637e4b94a66f63c43e51f0bc3e562d42bea
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="89bb9-103">Affecter Skype pour les licences d’entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="89bb9-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="89bb9-104">Cet article vous donne des conseils sur l’attribution de licences à vos utilisateurs de conférence Audio, système téléphonique et les Plans de l’appel.</span><span class="sxs-lookup"><span data-stu-id="89bb9-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="89bb9-105">Il vous fournit également des scripts pour affecter des licences en bloc.</span><span class="sxs-lookup"><span data-stu-id="89bb9-105">It also provides scripts for assigning licenses in bulk.</span></span>
  
 <span data-ttu-id="89bb9-106">**IMPORTANT**: consultez [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestion des licences](skype-for-business-and-microsoft-teams-add-on-licensing.md) pour plus d’informations sur les licences dont vous avez besoin pour acheter et **Comment acheter** - en fonction de votre plan Office 365 - afin que les utilisateurs obtiennent la conférence Audio, les numéros gratuits, et la possibilité d’appeler des numéros de téléphone à l’extérieur de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="89bb9-106">**IMPORTANT**: See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="89bb9-107">Système et des Plans de l’appel de téléphone : conseils et des scripts pour l’attribution de licences</span><span class="sxs-lookup"><span data-stu-id="89bb9-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="89bb9-108">Ce que vous devez connaître avant d’en affecter l’audioconférence, système téléphonique et appel de planifier les licences</span><span class="sxs-lookup"><span data-stu-id="89bb9-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="89bb9-109">**Vous utilisez la connectivité PSTN locale pour les utilisateurs hybrides ?**</span><span class="sxs-lookup"><span data-stu-id="89bb9-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="89bb9-110">Dans ce cas, vous devez uniquement attribuer une licence de **Système téléphonique** .</span><span class="sxs-lookup"><span data-stu-id="89bb9-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="89bb9-111">Vous devez **pas** assigner un Plan de l’appel.</span><span class="sxs-lookup"><span data-stu-id="89bb9-111">You should **NOT** assign a Calling Plan.</span></span>
    
- <span data-ttu-id="89bb9-112">**Latence après l’attribution de licences**: en raison de la latence entre Skype pour Business Online et Office 365, il peut éventuellement prendre jusqu'à 24 heures pour un utilisateur à assigner un Plan d’appel une fois que vous attribuez une licence.</span><span class="sxs-lookup"><span data-stu-id="89bb9-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="89bb9-113">Si après 24 heures avec l’utilisateur n’est pas affecté à un Plan de l’appel, veuillez [contacter le support technique pour les produits métiers : aide d’administration](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="89bb9-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>
    
- <span data-ttu-id="89bb9-114">**Messages d'erreur**: un message d'erreur s'affiche si vous n'avez pas acheté le nombre correct de licences.</span><span class="sxs-lookup"><span data-stu-id="89bb9-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="89bb9-115">Si vous devez acheter des licences supplémentaires de planifier l’appel, cliquez sur **acheter plus**.</span><span class="sxs-lookup"><span data-stu-id="89bb9-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="89bb9-116">**Étapes suivantes**: une fois que vous assignez un appel de planifier les licences à vos utilisateurs, vous devez obtenir vos numéros de téléphone pour votre organisation et l’assigner à ces numéros aux personnes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="89bb9-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="89bb9-117">Pour obtenir des instructions pas à pas, consultez [configurer des Plans de l’appel](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="89bb9-117">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="89bb9-118">Comment attribuer une licence de système téléphonique et planifier l’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="89bb9-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="89bb9-p106">Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="89bb9-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="89bb9-121">Comment attribuer des licences système téléphonique et planifier l’appel en bloc</span><span class="sxs-lookup"><span data-stu-id="89bb9-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="89bb9-122">Installez l' **Assistant de connexion Microsoft Online Services pour les informaticiens RTW**.</span><span class="sxs-lookup"><span data-stu-id="89bb9-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="89bb9-123">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="89bb9-123">Don't have the module installed?</span></span> <span data-ttu-id="89bb9-124">Voir [Assistant Microsoft Online Services connexion pour les professionnels de l’informatique RTW](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.</span><span class="sxs-lookup"><span data-stu-id="89bb9-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>
    
2. <span data-ttu-id="89bb9-125">Installez le **module Windows Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="89bb9-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="89bb9-126">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="89bb9-126">Don't have the module installed?</span></span> <span data-ttu-id="89bb9-127">Pour des instructions de téléchargement et de la syntaxe de l’applet de commande, voir [Gérer Azure AD à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .</span><span class="sxs-lookup"><span data-stu-id="89bb9-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
3. <span data-ttu-id="89bb9-128">Une fois les modules installés, utilisez l'invite de commandes Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="89bb9-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
  <span data-ttu-id="89bb9-129">Cet exemple attribue une **licence entreprise E3** avec un **Système téléphonique** et une licence de **Planifier l’appel interne** .</span><span class="sxs-lookup"><span data-stu-id="89bb9-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>
    
  <span data-ttu-id="89bb9-130">Le nom des licences ou des noms de produits dans le script sont répertoriés dans le texte italique (voir **système téléphonique et appel de planifier les noms de produits ou SKU utilisé pour les scripts**, après l’exemple).</span><span class="sxs-lookup"><span data-stu-id="89bb9-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>
    
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="89bb9-131">Système téléphonique et appel des Plans de noms de produits ou des références destinés script</span><span class="sxs-lookup"><span data-stu-id="89bb9-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="89bb9-132">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="89bb9-132">**Product name**</span></span>|<span data-ttu-id="89bb9-133">**Référence**</span><span class="sxs-lookup"><span data-stu-id="89bb9-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89bb9-134">Entreprise E5 (avec un système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="89bb9-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="89bb9-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="89bb9-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="89bb9-136">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="89bb9-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="89bb9-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="89bb9-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="89bb9-138">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="89bb9-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="89bb9-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="89bb9-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="89bb9-140">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="89bb9-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="89bb9-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="89bb9-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="89bb9-142">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="89bb9-142">Phone System</span></span>  <br/> |<span data-ttu-id="89bb9-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="89bb9-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="89bb9-144">Plan d’appels internationaux</span><span class="sxs-lookup"><span data-stu-id="89bb9-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="89bb9-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="89bb9-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="89bb9-146">Forfait d'appels nationaux</span><span class="sxs-lookup"><span data-stu-id="89bb9-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="89bb9-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="89bb9-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="89bb9-148">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="89bb9-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="89bb9-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="89bb9-149">MCOPSTNPP</span></span>  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="89bb9-150">Services d’audioconférence : Conseils et des scripts pour l’attribution de licences</span><span class="sxs-lookup"><span data-stu-id="89bb9-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="89bb9-151">Vous devez connaître avant d’attribution de licences d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="89bb9-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="89bb9-152">**Fournisseur de services d’audioconférence tiers**: si une personne est déjà configurée pour utiliser un fournisseur de services d’audioconférence tiers, lorsque vous leur attribuez une licence de **Conférence Audio** , ils ne seront modifiés pour utiliser Microsoft en tant que les services d’audioconférence fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="89bb9-152">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="89bb9-153">Vous pouvez le remplacer par le fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="89bb9-153">You can change them back to the third-party provider.</span></span>
    
- <span data-ttu-id="89bb9-154">Étapes suivantes : une fois que vous affectez des licences de **Services d’audioconférence** , vous devez lui assigner un fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="89bb9-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="89bb9-155">Voir [affecter Microsoft en tant que le fournisseur de services d’audioconférence].</span><span class="sxs-lookup"><span data-stu-id="89bb9-155">See [Assign Microsoft as the audio conferencing provider].</span></span>
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="89bb9-156">Comment attribuer une licence de conférence Audio à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="89bb9-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="89bb9-p111">Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="89bb9-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="89bb9-159">Comment attribuer des licences d’audioconférence en bloc</span><span class="sxs-lookup"><span data-stu-id="89bb9-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="89bb9-160">Téléchargez et installez [Microsoft Online Services Assistant de connexion pour les professionnels de l’informatique RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="89bb9-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>
    
2. <span data-ttu-id="89bb9-p112">Téléchargez et installez le **module Windows Azure Active Directory**. Pour connaître les instructions de téléchargement et la syntaxe des applets de commande, reportez-vous à la rubrique[Gestion d'Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="89bb9-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
    <span data-ttu-id="89bb9-163">Une fois les modules installés, utilisez l'invite de commandes Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="89bb9-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
    <span data-ttu-id="89bb9-164">Les noms de licence ou de produit dans le script sont notés en italique.</span><span class="sxs-lookup"><span data-stu-id="89bb9-164">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="89bb9-165">Voir [les noms de produits audioconférence ou SKU utilisé pour les scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) pour tous les noms de produits.</span><span class="sxs-lookup"><span data-stu-id="89bb9-165">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>
    
    <span data-ttu-id="89bb9-166">Cet exemple attribue une licence entreprise E3 avec une licence d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="89bb9-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>
    
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="89bb9-167">Les noms de produits de conférence audio ou des références destinés script</span><span class="sxs-lookup"><span data-stu-id="89bb9-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="89bb9-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="89bb9-168"></span></span>

|<span data-ttu-id="89bb9-169">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="89bb9-169">**Product name**</span></span>|<span data-ttu-id="89bb9-170">**Référence**</span><span class="sxs-lookup"><span data-stu-id="89bb9-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89bb9-171">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="89bb9-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="89bb9-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="89bb9-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="89bb9-173">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="89bb9-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="89bb9-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="89bb9-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="89bb9-175">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="89bb9-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="89bb9-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="89bb9-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="89bb9-177">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="89bb9-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="89bb9-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="89bb9-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="89bb9-179">Entreprise E5 (sans les services d’audioconférence)</span><span class="sxs-lookup"><span data-stu-id="89bb9-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="89bb9-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="89bb9-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="89bb9-181">Entreprise E5 (avec les services d’audioconférence)</span><span class="sxs-lookup"><span data-stu-id="89bb9-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="89bb9-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="89bb9-182">ENTERPRISEPREMIUM</span></span>  <br/> |
   
## <a name="communications-credits"></a><span data-ttu-id="89bb9-183">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="89bb9-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="89bb9-184">Vous devez connaître avant d’attribution de licences crédits Communications</span><span class="sxs-lookup"><span data-stu-id="89bb9-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="89bb9-185">**Clients Enterprise E5**: même si vos utilisateurs sont affectées des licences Enterprise E5, nous vous recommandons d’affecter les licences **Crédits Communications** .</span><span class="sxs-lookup"><span data-stu-id="89bb9-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="89bb9-186">**Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="89bb9-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="89bb9-187">Pour obtenir des instructions pas à pas, consultez [configurer des Plans de l’appel](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="89bb9-187">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="89bb9-188">Comment attribuer une licence Communications générique à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="89bb9-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="89bb9-p115">Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="89bb9-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="89bb9-191">Comment attribuer des licences Communications crédits en bloc</span><span class="sxs-lookup"><span data-stu-id="89bb9-191">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="89bb9-192">Jetez un œil à l’exemple de script pour l’attribution de licences de **Conférence Audio** .</span><span class="sxs-lookup"><span data-stu-id="89bb9-192">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="89bb9-193">Mettre à jour avec les informations de l’attribution de licences **Crédits Communications** .</span><span class="sxs-lookup"><span data-stu-id="89bb9-193">Update it with the info for assigning **Communications Credits** licenses.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="89bb9-194">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="89bb9-194">Related topics</span></span>
  
[<span data-ttu-id="89bb9-195">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="89bb9-195">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[<span data-ttu-id="89bb9-196">Ajouter des fonds et gérer les crédits de communication</span><span class="sxs-lookup"><span data-stu-id="89bb9-196">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
  
  
 