---
title: Affecter Microsoft comme le fournisseur de conférence audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/02/2018
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- Strat_SB_PSTN
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge.
ms.openlocfilehash: d572c9fc61b887679e434e669fc263c746be8bcf
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="a426c-104">Affecter Microsoft comme le fournisseur de conférence audio</span><span class="sxs-lookup"><span data-stu-id="a426c-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="a426c-105">Pour utiliser l’audioconférence dans Office 365 avec Skype pour les entreprises et les Teams de Microsoft, les utilisateurs de votre organisation devront disposer d’une licence d’Audio conférence qui leur sont affectée.</span><span class="sxs-lookup"><span data-stu-id="a426c-105">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="a426c-106">Pour obtenir plus d’informations sur les licences et son coût, reportez-vous à la section [Essayez ou achetez audioconférence dans Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="a426c-106">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="a426c-107">Conférence Audio de Microsoft fournit les numéros de téléphone, des broches et conférence ID qui peut être utilisé par les participants à la réunion à assister aux réunions de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a426c-107">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="a426c-108">Vous devez uniquement affecter Microsoft comme le fournisseur de conférence audio pour les personnes qui vont planifier ou entraîner Skype pour les réunions d’entreprise ou Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a426c-108">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

<span data-ttu-id="a426c-109">Si une licence de **Conférence Audio de Microsoft** est affectée à un utilisateur qui ne possède pas un fournisseur de conférence audio, le fournisseur de l’utilisateur est automatiquement configurée à **Microsoft** et vous n’avez rien à faire.</span><span class="sxs-lookup"><span data-stu-id="a426c-109">If a **Microsoft Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to **Microsoft** and you don't have to do anything else.</span></span> <span data-ttu-id="a426c-110">Si l’utilisateur avait déjà un fournisseur de conférence audio, vous devez modifier le fournisseur de l’utilisateur à Microsoft après l’attribution d’une licence de conférence Audio.</span><span class="sxs-lookup"><span data-stu-id="a426c-110">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an Audio Conferencing license.</span></span>

<span data-ttu-id="a426c-111">Si vous souhaitez être en mesure de voir que Microsoft répertorié comme le fournisseur de conférence audio, vous devez affecter une licence de conférence Audio à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a426c-111">If you want to be able to see Microsoft listed as the audio conferencing provider, you must assign an Audio Conferencing license to the user.</span></span>


  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="a426c-112">Affecter Microsoft comme le fournisseur de conférence audio</span><span class="sxs-lookup"><span data-stu-id="a426c-112">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="a426c-113">Utilisation du centre d'administration Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="a426c-113">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="a426c-114">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="a426c-114">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a426c-115">Lorsque le fournisseur est modifié à partir d’un autre fournisseur pour **Microsoft**, les informations de conférence audio de l’utilisateur (ID de la conférence, numéro payant et numéros d’appel gratuits) seront remplacées.</span><span class="sxs-lookup"><span data-stu-id="a426c-115">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="a426c-116">Enregistrez ces informations avant de changer de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a426c-116">You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="a426c-117">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **l’audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="a426c-117">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a426c-118">Si vous voyez une bannière qui vous avertit qu’il existe des utilisateurs qui ont une **Conférence Audio** licence affectés mais n’avez pas Microsoft défini comme leur fournisseur de conférence audio pour l’instant, cliquez sur **Cliquez ici pour les déplacer**.</span><span class="sxs-lookup"><span data-stu-id="a426c-118">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="a426c-119">Si vous ne voyez pas la bannière, dans le **Skype pour le centre d’administration Business** cliquez sur **utilisateurs**et puis sélectionnez le filtre **prête à être déplacée à l’Audio conférence des utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="a426c-119">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="a426c-120">Sur la page de propriétés de l’utilisateur, sous **le nom du fournisseur**, sélectionnez **Microsoft** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a426c-120">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a426c-121">Dans la mesure où vous utilisez Microsoft comme le fournisseur de conférence audio et il y a plusieurs numéros de téléphone, vous pouvez utiliser la liste déroulante **numéro d’appel payant par défaut** pour sélectionner un numéro d’audio par défaut pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a426c-121">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="a426c-122">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a426c-122">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="a426c-123">Utilisation d'un script Windows PowerShell pour un petit nombre d'utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a426c-123">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="a426c-124">Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser le script PowerShell suivant à configurer Microsoft comme le fournisseur de conférence audio pour un petit nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a426c-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="a426c-125">Lorsque le fournisseur est modifié à partir d’un autre fournisseur pour **Microsoft**, les informations de conférence audio de l’utilisateur (ID de la conférence, numéro payant et numéros d’appel gratuits) seront remplacées.</span><span class="sxs-lookup"><span data-stu-id="a426c-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="a426c-126">Enregistrez ces informations avant de changer de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a426c-126">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="a426c-127">Pour modifier le fournisseur de Microsoft pour un petit nombre d’utilisateurs, vous pouvez utiliser l’applet de commande [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) .</span><span class="sxs-lookup"><span data-stu-id="a426c-127">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="a426c-128">Utilisation d'un script Windows PowerShell pour un grand nombre d'utilisateurs</span><span class="sxs-lookup"><span data-stu-id="a426c-128">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="a426c-129">Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser le script PowerShell suivant à configurer Microsoft comme le fournisseur de conférence audio pour un grand nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a426c-129">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="a426c-130">Lorsque le fournisseur est modifié à partir d’un autre fournisseur pour **Microsoft**, les informations de conférence audio de l’utilisateur (ID de la conférence, numéro payant et numéros d’appel gratuits) seront remplacées.</span><span class="sxs-lookup"><span data-stu-id="a426c-130">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="a426c-131">Enregistrez ces informations avant de changer de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a426c-131">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="a426c-132">Vous pouvez enregistrer le script suivant dans un fichier de script PowerShell et ensuite l’exécuter à l’aide de ses paramètres d’entrée.</span><span class="sxs-lookup"><span data-stu-id="a426c-132">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="a426c-133">**Exemple 1 :** vous pouvez exécuter ce script en fournissant la liste des utilisateurs que vous souhaitez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="a426c-133">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="a426c-134">**Exemple 2 :** vous pouvez exécuter ce script en fournissant un fichier .csv contenant l'adresse électronique (alias) de chaque utilisateur que vous souhaitez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="a426c-134">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="a426c-135">**Exemple 3 :** Dans cet exemple, vous pouvez utiliser ce script pour modifier le fournisseur de conférence audio à partir d’Intercall (ou un autre fournisseur) à **Microsoft** pour un grand nombre d’utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a426c-135">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="a426c-136">Voici le script :</span><span class="sxs-lookup"><span data-stu-id="a426c-136">Here is the script:</span></span>

  ```
  <#
  .SYNOPSIS

  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .DESCRIPTION
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .EXAMPLE
  
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ./Script.ps1 -ACPProviderName ""Intercall""
  #>
  param (
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
   [string]$CsvFile,
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
   [string]$UserList,
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  [string]$ACPProviderName
  )
  if ($CsvFile)
  {
  if(!(Test-Path $CsvFile))
  {
  Write-Error "File does not exist."
  Exit
   }
  $users = Get-Content $CsvFile
  }
  if ($UserList)
  {
  $users = $UserList.Split(",")
  }
  if ($ACPProviderName)
  {
  $supportedACPProviders = Get-csAudioConferencingProvider
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  if ($providerNameMatch -eq $null)
  {
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  $supportedACPProviders      | %{$_.Identity}
  return
  }
  $allUsersInTenant = Get-csOnlineUser
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  }
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.count
  foreach ($user in $users)
  {
  if ($CsvFile -or $UserList)
  {
  try
  {
  $adUser = Get-csOnlineUser -Identity $user
  }
  catch
  {
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  Continue
  }
  }
  else
  {
  $adUser = $user
  }
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  {
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  {
  try
  {
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  Write-Host "The provider of $user has changed to Microsoft."
  $enableUser
  }
  catch
  {
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  continue;
  }
  }
   else
  {
  Write-Warning "The provider of $user is already set to Microsoft."
  }
  }
  else
              {
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  }
  }
  ```
<span data-ttu-id="a426c-137">Pour plus d'informations sur l'utilisation de Windows PowerShell, consultez la rubrique [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="a426c-137">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="a426c-138">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a426c-138">Related topics</span></span>

[<span data-ttu-id="a426c-139">Tester ou acheter l'audioconférence dans Office 365</span><span class="sxs-lookup"><span data-stu-id="a426c-139">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
[<span data-ttu-id="a426c-140">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a426c-140">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

