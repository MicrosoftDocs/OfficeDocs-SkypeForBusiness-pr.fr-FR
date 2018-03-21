---
title: "Affecter Skype pour les licences d’entreprise et Microsoft Teams"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: "Comment attribuer des Skype pour les licences commerciales pour système téléphonique, audioconférence, Plans d’appel et les crédits de Communications. "
ms.openlocfilehash: a5cbc36d1b5ce5a7d79587df369b2d3bf3caacd6
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="5a61c-103">Affecter Skype pour les licences d’entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a61c-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="5a61c-104">Cet article vous donne des conseils sur l’attribution des licences aux utilisateurs pour des fonctionnalités telles que les conférences Audio, système téléphonique et Plans d’appel.</span><span class="sxs-lookup"><span data-stu-id="5a61c-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="5a61c-105">Il vous fournit également des scripts pour affecter des licences en bloc.</span><span class="sxs-lookup"><span data-stu-id="5a61c-105">It also provides scripts for assigning licenses in bulk.</span></span>
  
 <span data-ttu-id="5a61c-106">**IMPORTANT**: voir [Skype pour les licences de modules complémentaires professionnels et les équipes de Microsoft](skype-for-business-and-microsoft-teams-add-on-licensing.md) pour plus d’informations sur les licences dont vous avez besoin pour acheter et **Comment acheter** - en fonction de votre plan Office 365 - afin que les utilisateurs obtiennent la conférence Audio, numéros de téléphone gratuits, et la possibilité d’appeler des numéros de téléphone à l’extérieur de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="5a61c-106">**IMPORTANT**: See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="5a61c-107">Système et les Plans d’appel de téléphone : conseils et les scripts d’attribution des licences</span><span class="sxs-lookup"><span data-stu-id="5a61c-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="5a61c-108">Ce que vous devez savoir avant d’assigner l’audioconférence, système téléphonique et l’appel de planifier les licences</span><span class="sxs-lookup"><span data-stu-id="5a61c-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="5a61c-109">**Vous utilisez la connectivité PSTN locale pour les utilisateurs hybrides ?**</span><span class="sxs-lookup"><span data-stu-id="5a61c-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="5a61c-110">Dans ce cas, il vous suffit d’attribuer une licence de **Système téléphonique** .</span><span class="sxs-lookup"><span data-stu-id="5a61c-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="5a61c-111">Vous devez **pas** les attribuer un Plan d’appel.</span><span class="sxs-lookup"><span data-stu-id="5a61c-111">You should **NOT** assign a Calling Plan.</span></span>
    
- <span data-ttu-id="5a61c-112">**Latence après l’affectation licences**: en raison de la latence entre Office 365 et Skype pour professionnels en ligne, il peut éventuellement prendre jusqu'à 24 heures à disposer d’un Plan d’appel après avoir attribué une licence pour un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5a61c-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="5a61c-113">Si après 24 heures n’est pas affecté à l’utilisateur un Plan d’appel, veuillez [contacter le support technique pour les produits d’entreprise - aide de l’administrateur](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="5a61c-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>
    
- <span data-ttu-id="5a61c-114">**Messages d'erreur**: un message d'erreur s'affiche si vous n'avez pas acheté le nombre correct de licences.</span><span class="sxs-lookup"><span data-stu-id="5a61c-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="5a61c-115">Si vous avez besoin acheter d’autres licences de l’appel de Plan, cliquez sur **acheter d’autres**.</span><span class="sxs-lookup"><span data-stu-id="5a61c-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="5a61c-116">**Prochaines étapes**: après avoir affecté des licences de l’appel de Plan à vos utilisateurs, vous devrez obtenir vos numéros de téléphone pour votre organisation et ensuite affecter des numéros aux personnes de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5a61c-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="5a61c-117">Pour obtenir des instructions pas à pas, consultez [définir les Plans d’appel](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="5a61c-117">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="5a61c-118">Comment attribuer une licence de système téléphonique et le Plan de l’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="5a61c-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="5a61c-p106">Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="5a61c-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="5a61c-121">Comment attribuer des licences de système téléphonique et l’appel de Plan en vrac</span><span class="sxs-lookup"><span data-stu-id="5a61c-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="5a61c-122">Installez l' **Assistant de connexion Microsoft Online Services pour les informaticiens RTW**.</span><span class="sxs-lookup"><span data-stu-id="5a61c-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="5a61c-123">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="5a61c-123">Don't have the module installed?</span></span> <span data-ttu-id="5a61c-124">Voir l' [Assistant Microsoft Online Services-In pour RTW de professionnels de l’informatique](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.</span><span class="sxs-lookup"><span data-stu-id="5a61c-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>
    
2. <span data-ttu-id="5a61c-125">Installez le **module Windows Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5a61c-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="5a61c-126">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="5a61c-126">Don't have the module installed?</span></span> <span data-ttu-id="5a61c-127">Pour les instructions de téléchargement et de la syntaxe de l’applet de commande, voir la rubrique [Manage AD Azure à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .</span><span class="sxs-lookup"><span data-stu-id="5a61c-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
3. <span data-ttu-id="5a61c-128">Une fois les modules installés, utilisez l'invite de commandes Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="5a61c-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
  <span data-ttu-id="5a61c-129">Cet exemple assigne une **licence d’entreprise E3** avec un **Système téléphonique** et une licence **Nationale appel de Plan** .</span><span class="sxs-lookup"><span data-stu-id="5a61c-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>
    
  <span data-ttu-id="5a61c-130">Le nom des licences ou des noms de produit dans le script sont répertoriés dans le texte de l’italique (voir **système téléphonique et appel de planifier les noms de produit ou les références destinés script**, après l’exemple).</span><span class="sxs-lookup"><span data-stu-id="5a61c-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>
    
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="5a61c-131">Système téléphonique et les Plans d’appel de noms de produits ou de références destinés script</span><span class="sxs-lookup"><span data-stu-id="5a61c-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="5a61c-132">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="5a61c-132">**Product name**</span></span>|<span data-ttu-id="5a61c-133">**Référence**</span><span class="sxs-lookup"><span data-stu-id="5a61c-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5a61c-134">E5 d’entreprise (avec un système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="5a61c-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="5a61c-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="5a61c-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="5a61c-136">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="5a61c-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="5a61c-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="5a61c-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="5a61c-138">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="5a61c-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="5a61c-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="5a61c-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="5a61c-140">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="5a61c-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="5a61c-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="5a61c-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="5a61c-142">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="5a61c-142">Phone System</span></span>  <br/> |<span data-ttu-id="5a61c-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="5a61c-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="5a61c-144">Plan d’appel international</span><span class="sxs-lookup"><span data-stu-id="5a61c-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="5a61c-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="5a61c-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="5a61c-146">Forfait d'appels nationaux</span><span class="sxs-lookup"><span data-stu-id="5a61c-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="5a61c-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="5a61c-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="5a61c-148">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="5a61c-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="5a61c-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="5a61c-149">MCOPSTNPP</span></span>  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="5a61c-150">Téléconférence audio : Conseils et les scripts d’attribution des licences</span><span class="sxs-lookup"><span data-stu-id="5a61c-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="5a61c-151">Ce que vous devez savoir avant d’attribuer des licences d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="5a61c-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="5a61c-152">**Fournisseur de conférence audio tiers**: si une personne est déjà configurée pour utiliser un fournisseur de conférence audio de tiers, lorsque vous les attribuez une licence de **Conférence Audio** , ils ne seront modifiés pour utiliser Microsoft comme la conférence audio fournisseur.</span><span class="sxs-lookup"><span data-stu-id="5a61c-152">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="5a61c-153">Vous pouvez le remplacer par le fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="5a61c-153">You can change them back to the third-party provider.</span></span>
    
- <span data-ttu-id="5a61c-154">Étapes suivantes : après avoir affecté des licences de **Conférence Audio** , vous devez affecter un fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="5a61c-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="5a61c-155">Procédez selon l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="5a61c-155">Do one of the following:</span></span>
    
  - [<span data-ttu-id="5a61c-156">Affecter Microsoft comme fournisseur de services d'audioconférence</span><span class="sxs-lookup"><span data-stu-id="5a61c-156">Assign Microsoft as the audio conferencing provider</span></span>](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - <span data-ttu-id="5a61c-157">Ou, [attribuer un tiers que le fournisseur de conférence audio](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span><span class="sxs-lookup"><span data-stu-id="5a61c-157">Or, [Assign a third-party as the audio conferencing provider](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span></span>
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="5a61c-158">Comment attribuer une licence audioconférence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="5a61c-158">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="5a61c-p111">Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="5a61c-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="5a61c-161">Comment attribuer des licences d’Audio conférence en vrac</span><span class="sxs-lookup"><span data-stu-id="5a61c-161">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="5a61c-162">Téléchargez et installez [Microsoft Online Services Assistant de connexion pour RTW de professionnels de l’informatique](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="5a61c-162">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>
    
2. <span data-ttu-id="5a61c-p112">Téléchargez et installez le **module Windows Azure Active Directory**. Pour connaître les instructions de téléchargement et la syntaxe des applets de commande, reportez-vous à la rubrique[Gestion d'Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="5a61c-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
    <span data-ttu-id="5a61c-165">Une fois les modules installés, utilisez l'invite de commandes Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="5a61c-165">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
    <span data-ttu-id="5a61c-166">Les noms de licence ou de produit dans le script sont notés en italique.</span><span class="sxs-lookup"><span data-stu-id="5a61c-166">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="5a61c-167">Voir [les noms de produits Audio conférence ou des points de stock utilisés pour les scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) pour tous les noms de produits.</span><span class="sxs-lookup"><span data-stu-id="5a61c-167">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>
    
    <span data-ttu-id="5a61c-168">Cet exemple assigne une licence Enterprise E3 avec une licence d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="5a61c-168">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>
    
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="5a61c-169">Les noms de produits de conférence audio ou des références destinés script</span><span class="sxs-lookup"><span data-stu-id="5a61c-169">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="5a61c-170"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="5a61c-170"></span></span>

|<span data-ttu-id="5a61c-171">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="5a61c-171">**Product name**</span></span>|<span data-ttu-id="5a61c-172">**Référence**</span><span class="sxs-lookup"><span data-stu-id="5a61c-172">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5a61c-173">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="5a61c-173">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="5a61c-174">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="5a61c-174">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="5a61c-175">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="5a61c-175">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="5a61c-176">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="5a61c-176">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="5a61c-177">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="5a61c-177">Enterprise E1</span></span>  <br/> |<span data-ttu-id="5a61c-178">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="5a61c-178">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="5a61c-179">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="5a61c-179">Enterprise E3</span></span>  <br/> |<span data-ttu-id="5a61c-180">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="5a61c-180">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="5a61c-181">E5 Enterprise (sans audioconférence)</span><span class="sxs-lookup"><span data-stu-id="5a61c-181">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="5a61c-182">ENTERPRISEPREMIUM_NONRPCCONF</span><span class="sxs-lookup"><span data-stu-id="5a61c-182">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="5a61c-183">E5 d’entreprise (avec la fonction d’audioconférence)</span><span class="sxs-lookup"><span data-stu-id="5a61c-183">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="5a61c-184">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="5a61c-184">ENTERPRISEPREMIUM</span></span>  <br/> |
   
## <a name="communications-credits"></a><span data-ttu-id="5a61c-185">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="5a61c-185">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="5a61c-186">Ce que vous devez savoir avant d’attribuer des licences de crédits de Communications</span><span class="sxs-lookup"><span data-stu-id="5a61c-186">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="5a61c-187">**Les clients entreprise E5**: même si les utilisateurs sont affectés des licences Enterprise E5, nous recommandons quand même d’attribuer les licences de **Crédits de Communications** .</span><span class="sxs-lookup"><span data-stu-id="5a61c-187">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="5a61c-188">**Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="5a61c-188">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="5a61c-189">Pour obtenir des instructions pas à pas, consultez [définir les Plans d’appel](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="5a61c-189">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="5a61c-190">Comment attribuer une licence de crédits de Communications à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="5a61c-190">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="5a61c-p115">Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="5a61c-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="5a61c-193">Comment attribuer des licences de crédits de Communications en vrac</span><span class="sxs-lookup"><span data-stu-id="5a61c-193">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="5a61c-194">Examinons l’exemple de script pour l’attribution des licences **d’Audioconférence** .</span><span class="sxs-lookup"><span data-stu-id="5a61c-194">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="5a61c-195">Mettre à jour avec les informations d’attribution de licences de **Crédits de Communications** .</span><span class="sxs-lookup"><span data-stu-id="5a61c-195">Update it with the info for assigning **Communications Credits** licenses.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5a61c-196">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="5a61c-196">Related topics</span></span>

[<span data-ttu-id="5a61c-197">Configurer la conférence Audio pour Skype entreprise et Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="5a61c-197">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[<span data-ttu-id="5a61c-198">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="5a61c-198">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[<span data-ttu-id="5a61c-199">Ajouter des fonds et gérer les crédits de communication</span><span class="sxs-lookup"><span data-stu-id="5a61c-199">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
  