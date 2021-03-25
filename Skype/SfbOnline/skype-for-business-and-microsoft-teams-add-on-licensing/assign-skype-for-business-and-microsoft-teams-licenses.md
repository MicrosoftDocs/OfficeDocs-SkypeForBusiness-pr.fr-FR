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
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: "Apprenez comment affecter des licences Skype Entreprise pour le Système téléphonique, l'Audioconférence, les Plans d'appel et les Crédits de communications. "
ms.openlocfilehash: beb4fa46133aa7a09ce3d0de0a08392dbf2d2591
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106490"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="3b804-103">Attribuer des licences Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="3b804-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="3b804-104">Cet article vous donne des conseils sur l’affectation de licences à vos utilisateurs pour des fonctionnalités telles que l'Audioconférence, le Système téléphonique et les Forfaits d’appels.</span><span class="sxs-lookup"><span data-stu-id="3b804-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="3b804-105">Il vous fournit également des scripts pour affecter des licences en bloc.</span><span class="sxs-lookup"><span data-stu-id="3b804-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b804-106">Pour plus d’informations sur les licences à acheter  et leur achat (selon votre offre Microsoft 365 ou Office 365), consultez la fonction de licences des modules complémentaires [Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md) Entreprise, afin que les utilisateurs obtiennent des services d’audioconférence, des numéros gratuits et la possibilité d’appeler des numéros de téléphone en dehors de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="3b804-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Microsoft 365 or Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="3b804-107">Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences</span><span class="sxs-lookup"><span data-stu-id="3b804-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="3b804-108">Ce que vous devez connaître avant d’affecter des licences Audioconférence, Système téléphonique et Forfait d'appels</span><span class="sxs-lookup"><span data-stu-id="3b804-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="3b804-109">**Vous utilisez la connectivité PSTN locale pour les utilisateurs hybrides ?**</span><span class="sxs-lookup"><span data-stu-id="3b804-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="3b804-110">Si c’est le cas, vous devez uniquement affecter une **licence Phone System.**</span><span class="sxs-lookup"><span data-stu-id="3b804-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="3b804-111">Vous ne devez **PAS** affecter de forfait d’appels.</span><span class="sxs-lookup"><span data-stu-id="3b804-111">You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="3b804-112">**Latence** après l’attribution de licences : en raison de la latence entre Microsoft 365 ou Office 365 et Skype Entreprise Online, jusqu’à 24 heures peuvent être nécessaire pour qu’un utilisateur soit affecté à un plan d’appel une fois une licence affectée.</span><span class="sxs-lookup"><span data-stu-id="3b804-112">**Latency after assigning licenses**: Because of the latency between Microsoft 365 or Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="3b804-113">Si au bout de 24 heures l’utilisateur n’a pas de forfait d’appels, contactez le support pour les produits pour les entreprises [- Aide de l’administrateur.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="3b804-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="3b804-114">**Messages d'erreur**: un message d'erreur s'affiche si vous n'avez pas acheté le nombre correct de licences.</span><span class="sxs-lookup"><span data-stu-id="3b804-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="3b804-115">Si vous devez acheter d’autres licences forfait d’appels, choisissez **Acheter plus.**</span><span class="sxs-lookup"><span data-stu-id="3b804-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="3b804-116">**Prochaines étapes**: après avoir attribué des licences Forfait d’appels à vos utilisateurs, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3b804-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="3b804-117">Pour obtenir des instructions détaillées, voir [Configurer les forfaits d’appels.](/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="3b804-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="3b804-118">Comment affecter une licence de système téléphonique et de plan d’appel à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="3b804-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="3b804-119">Les étapes sont identiques à l’attribution d’une licence Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b804-119">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="3b804-120">Voir [Attribuer ou supprimer des licences pour Microsoft 365 pour les entreprises.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="3b804-120">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="3b804-121">Comment affecter des licences Système téléphonique et Forfait d’appel en volume</span><span class="sxs-lookup"><span data-stu-id="3b804-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="3b804-122">Installez l' **Assistant de connexion Microsoft Online Services pour les informaticiens RTW**.</span><span class="sxs-lookup"><span data-stu-id="3b804-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="3b804-123">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="3b804-123">Don't have the module installed?</span></span> <span data-ttu-id="3b804-124">Consultez Microsoft Online Services Sign-In Assistant de téléchargement pour les professionnels de l’informatique [RTW.](https://go.microsoft.com/fwlink/?LinkId=625123)</span><span class="sxs-lookup"><span data-stu-id="3b804-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="3b804-125">Installez le **module Windows Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3b804-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="3b804-126">Le module n'est pas installé ?</span><span class="sxs-lookup"><span data-stu-id="3b804-126">Don't have the module installed?</span></span> <span data-ttu-id="3b804-127">Pour consulter des instructions de téléchargement et la syntaxe [de l’Windows PowerShell,](/previous-versions/azure/jj151815(v=azure.100)) voir Gérer Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3b804-127">See [Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="3b804-128">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="3b804-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="3b804-129">Cet exemple affecte une **licence Entreprise E3**, ainsi qu'une licence **Système téléphonique** et **Forfait d’appels interne**.</span><span class="sxs-lookup"><span data-stu-id="3b804-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="3b804-130">Le nom des licences ou des produits du script est répertorié dans le texte en italique (voir les noms des produits ou des plans d’appels téléphoniques utilisés pour l’écriture de **scripts,** après l’exemple).</span><span class="sxs-lookup"><span data-stu-id="3b804-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="3b804-131">Nom ou nom des produits du système téléphonique et du plan d’appel utilisé pour l’écriture de scripts</span><span class="sxs-lookup"><span data-stu-id="3b804-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="3b804-132">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="3b804-132">**Product name**</span></span>|<span data-ttu-id="3b804-133">**Référence**</span><span class="sxs-lookup"><span data-stu-id="3b804-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3b804-134">Entreprise E5 (avec Système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="3b804-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="3b804-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="3b804-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="3b804-136">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="3b804-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="3b804-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="3b804-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="3b804-138">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="3b804-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="3b804-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="3b804-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="3b804-140">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3b804-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="3b804-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="3b804-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="3b804-142">Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="3b804-142">Phone System</span></span>  <br/> |<span data-ttu-id="3b804-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="3b804-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="3b804-144">Plan d’appels internationaux</span><span class="sxs-lookup"><span data-stu-id="3b804-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="3b804-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="3b804-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="3b804-146">Forfait d’appels nationaux (plans de 3 000 min pour les États-Unis / 1 200 min pour l’UE)</span><span class="sxs-lookup"><span data-stu-id="3b804-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="3b804-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="3b804-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="3b804-148">Forfait d’appels nationaux (forfait d’appels de 120 minutes)</span><span class="sxs-lookup"><span data-stu-id="3b804-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="3b804-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="3b804-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="3b804-150">Forfait d’appels nationaux (forfait d’appels de 240 min)</span><span class="sxs-lookup"><span data-stu-id="3b804-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="3b804-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="3b804-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="3b804-152">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="3b804-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="3b804-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="3b804-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="3b804-154">Audioconférence : conseils et scripts pour affecter des licences</span><span class="sxs-lookup"><span data-stu-id="3b804-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="3b804-155">Ce que vous devez savoir avant d’affecter des licences d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="3b804-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="3b804-156">Fournisseur de services d’audioconférence tiers : si un fournisseur de services d’audioconférence tiers est déjà utilisé, lorsque vous lui affectez une licence **d’audioconférence,** microsoft est utilisé comme fournisseur de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="3b804-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="3b804-157">Vous pouvez le remplacer par le fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="3b804-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="3b804-158">Prochaines étapes : après avoir attribué des licences d’audioconférence, vous devez affecter un fournisseur de services d’audioconférence. </span><span class="sxs-lookup"><span data-stu-id="3b804-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="3b804-159">Voir [Affecter Microsoft comme fournisseur d'audioconférence].</span><span class="sxs-lookup"><span data-stu-id="3b804-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="3b804-160">Comment affecter une licence d’audioconférence à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="3b804-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="3b804-161">Les étapes sont identiques à l’attribution d’une licence Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b804-161">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="3b804-162">Voir [Attribuer ou supprimer des licences pour Microsoft 365 pour les entreprises.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="3b804-162">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="3b804-163">Comment affecter des licences d’audioconférence en bloc</span><span class="sxs-lookup"><span data-stu-id="3b804-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="3b804-164">Téléchargez et installez [l’Assistant Microsoft Online Services Sign-In pour les professionnels de l’informatique RTW.](https://go.microsoft.com/fwlink/?LinkId=625123)</span><span class="sxs-lookup"><span data-stu-id="3b804-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="3b804-p112">Téléchargez et installez le **module Windows Azure Active Directory**. Pour connaître les instructions de téléchargement et la syntaxe des applets de commande, reportez-vous à la rubrique [Gestion d'Azure AD à l'aide de Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="3b804-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="3b804-167">Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="3b804-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="3b804-168">Le nom des licences ou des produits du script est répertorié dans le texte en italique.</span><span class="sxs-lookup"><span data-stu-id="3b804-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="3b804-169">Consultez les références ou noms des produits de l’audioconférence utilisés pour l’écriture [de scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) pour tous les noms de produit.</span><span class="sxs-lookup"><span data-stu-id="3b804-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="3b804-170">Cet exemple affecte une licence Entreprise E3, ainsi qu’une licence Audioconférence.</span><span class="sxs-lookup"><span data-stu-id="3b804-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="3b804-171">Référence ou nom des produits de l’audioconférence pour l’écriture de scripts</span><span class="sxs-lookup"><span data-stu-id="3b804-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="3b804-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="3b804-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="3b804-173">**Nom du produit**</span><span class="sxs-lookup"><span data-stu-id="3b804-173">**Product name**</span></span>|<span data-ttu-id="3b804-174">**Référence**</span><span class="sxs-lookup"><span data-stu-id="3b804-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3b804-175">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="3b804-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="3b804-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="3b804-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="3b804-177">Plan autonome 2 de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="3b804-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="3b804-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="3b804-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="3b804-179">Entreprise E1</span><span class="sxs-lookup"><span data-stu-id="3b804-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="3b804-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="3b804-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="3b804-181">Entreprise E3</span><span class="sxs-lookup"><span data-stu-id="3b804-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="3b804-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="3b804-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="3b804-183">Entreprise E5 (sans Audioconférence)</span><span class="sxs-lookup"><span data-stu-id="3b804-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="3b804-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="3b804-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="3b804-185">Entreprise E5 (avec audioconférence)</span><span class="sxs-lookup"><span data-stu-id="3b804-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="3b804-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="3b804-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="3b804-187">Crédits de communication</span><span class="sxs-lookup"><span data-stu-id="3b804-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="3b804-188">Ce que vous devez savoir avant d’affecter des licences de crédits de communication</span><span class="sxs-lookup"><span data-stu-id="3b804-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="3b804-189">**Clients Entreprise E5**: Même si des licences Entreprise E5 sont attribuées à vos utilisateurs, nous vous recommandons de leur attribuer des **licences de crédits de** communication.</span><span class="sxs-lookup"><span data-stu-id="3b804-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="3b804-190">**Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3b804-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="3b804-191">Pour obtenir des instructions détaillées, voir [Configurer les forfaits d’appels.](/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="3b804-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="3b804-192">Comment affecter une licence Crédits de communication à un utilisateur</span><span class="sxs-lookup"><span data-stu-id="3b804-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="3b804-193">Les étapes sont identiques à l’attribution d’une licence Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b804-193">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="3b804-194">Voir [Attribuer ou supprimer des licences pour Microsoft 365 pour les entreprises.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="3b804-194">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="3b804-195">Comment affecter des licences de crédits de communication en bloc</span><span class="sxs-lookup"><span data-stu-id="3b804-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="3b804-196">Jetez un coup d’œil à l’exemple de script pour affecter des licences **d’audioconférence.**</span><span class="sxs-lookup"><span data-stu-id="3b804-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="3b804-197">Mettez-le à jour avec les informations pour affecter des **licences de crédits** de communication.</span><span class="sxs-lookup"><span data-stu-id="3b804-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3b804-198">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="3b804-198">Related topics</span></span>
  
[<span data-ttu-id="3b804-199">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="3b804-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="3b804-200">Ajouter des fonds et gérer les Crédits de Communications</span><span class="sxs-lookup"><span data-stu-id="3b804-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
