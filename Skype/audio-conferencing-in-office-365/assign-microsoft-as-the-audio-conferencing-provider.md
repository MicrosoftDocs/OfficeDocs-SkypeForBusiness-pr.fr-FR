---
title: "Affecter Microsoft comme le fournisseur de conférence audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Audio Conferencing
- Strat_SB_PSTN
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge.
ms.openlocfilehash: c42bf80b456517eb6305a993cbb11c3b9a245c20
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="b0e7b-104">Affecter Microsoft comme le fournisseur de conférence audio</span><span class="sxs-lookup"><span data-stu-id="b0e7b-104">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="b0e7b-105">Un fournisseur de conférence audio fournit le *pont de conférence*.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-105">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="b0e7b-106">Le pont de conférence fournit les numéros de téléphone, broches, les ID de conférence pour les réunions qui sont créées.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-106">The conference bridge provides the dial-in phone numbers, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="b0e7b-107">Vous devrez affecter un fournisseur de conférence audio pour les personnes qui vont planifier ou entraîner Skype pour les réunions d’entreprise ou Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-107">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
<span data-ttu-id="b0e7b-108">Si vous souhaitez être en mesure de voir **que Microsoft** répertorié comme fournisseur audio, vous devez affecter une licence de **Conférence Audio** à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-108">If you want to be able to see **Microsoft** listed as the audio provider, you must assign an **Audio Conferencing** license to the user.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b0e7b-109">Si vous attribuez une licence de **Conférence Audio** à une personne qui ne possède pas un fournisseur de conférence audio de tiers, Microsoft est automatiquement désigné comme le fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-109">If you assign an **Audio Conferencing** license to a person who doesn't have a third-party audio conferencing provider, Microsoft is automatically assigned as the audio conferencing provider.</span></span> <span data-ttu-id="b0e7b-110">Vous pouvez [affecter un tiers que le fournisseur de conférence audio](assign-a-third-party-as-the-audio-conferencing-provider.md) si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-110">You can [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) if needed.</span></span>
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="b0e7b-111">Affecter Microsoft comme le fournisseur de conférence audio</span><span class="sxs-lookup"><span data-stu-id="b0e7b-111">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="using-the-skype-for-business-admin-center"></a><span data-ttu-id="b0e7b-112">Utilisation du centre d'administration Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b0e7b-112">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="b0e7b-113">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b0e7b-114">Lorsque le fournisseur est modifié à partir d’un autre fournisseur pour **Microsoft**, les informations de conférence audio de l’utilisateur (ID de la conférence, numéro payant et numéros d’appel gratuits) seront remplacées.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-114">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="b0e7b-115">Vous devez enregistrer ces informations avant de modifier le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-115">You should save this information before changing the provider.</span></span> 
  
2. <span data-ttu-id="b0e7b-116">Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>
    
3. <span data-ttu-id="b0e7b-117">Dans le volet Action, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-117">In the Action pane, click **Edit**.</span></span>
    
4. <span data-ttu-id="b0e7b-118">Sur la page de propriétés de l’utilisateur, sous **le nom du fournisseur**, sélectionnez **Microsoft** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-118">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b0e7b-119">Dans la mesure où vous utilisez Microsoft comme le fournisseur de conférence audio et il y a plusieurs numéros de téléphone, vous pouvez utiliser la liste déroulante **numéro d’appel payant par défaut** pour sélectionner un numéro d’audio par défaut pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-119">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="b0e7b-120">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-120">Click **Save**.</span></span>
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="b0e7b-121">Utilisation d'un script Windows PowerShell pour un petit nombre d'utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b0e7b-121">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="b0e7b-122">Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser le script PowerShell suivant à configurer Microsoft comme le fournisseur de conférence audio pour un petit nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-122">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e7b-123">Lorsque le fournisseur est modifié à partir d’un autre fournisseur pour **Microsoft**, les informations de conférence audio de l’utilisateur (ID de la conférence, numéro payant et numéros d’appel gratuits) seront remplacées.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-123">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="b0e7b-124">Vous devez enregistrer ces informations avant de modifier le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-124">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="b0e7b-125">Vous pouvez enregistrer un ou plusieurs des scripts suivants comme fichiers de script PowerShell puis les exécuter.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-125">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>
  
<span data-ttu-id="b0e7b-126">Pour modifier le fournisseur de Microsoft pour un petit nombre d’utilisateurs, vous pouvez utiliser le [CsOnlineDialInConferencingUser de l’activer](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span><span class="sxs-lookup"><span data-stu-id="b0e7b-126">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).</span></span>
  
<span data-ttu-id="b0e7b-127">**Exemple 1 :** vous pouvez exécuter ce script en fournissant la liste des utilisateurs que vous souhaitez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-127">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
<span data-ttu-id="b0e7b-128">**Exemple 2 :** vous pouvez exécuter ce script en fournissant un fichier .csv contenant l'adresse électronique (alias) de chaque utilisateur que vous souhaitez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-128">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="b0e7b-129">Utilisation d'un script Windows PowerShell pour un grand nombre d'utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b0e7b-129">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="b0e7b-130">Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser le script PowerShell suivant à configurer Microsoft comme le fournisseur de conférence audio pour un grand nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-130">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="b0e7b-131">Lorsque le fournisseur est modifié à partir d’un autre fournisseur pour **Microsoft**, les informations de conférence audio de l’utilisateur (ID de la conférence, numéro payant et numéros d’appel gratuits) seront remplacées.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-131">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="b0e7b-132">Vous devez enregistrer ces informations avant de modifier le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-132">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="b0e7b-133">Vous pouvez enregistrer un ou plusieurs des scripts suivants comme fichiers de script PowerShell puis les exécuter.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-133">You can save one or more of the following scripts as a PowerShell script file and then run it.</span></span>

<span data-ttu-id="b0e7b-134">**Exemple 1 :** Dans cet exemple, vous pouvez utiliser ce script pour modifier le fournisseur de conférence audio à partir d’Intercall (ou un autre fournisseur) à **Microsoft** pour un grand nombre d’utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-134">**Example 1:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="b0e7b-135">Voici le script :</span><span class="sxs-lookup"><span data-stu-id="b0e7b-135">Here is the script:</span></span>

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
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.counts
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
<span data-ttu-id="b0e7b-136">Pour plus d'informations sur l'utilisation de Windows PowerShell, consultez la rubrique [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="b0e7b-136">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="b0e7b-137">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b0e7b-137">What else should I know?</span></span>

- <span data-ttu-id="b0e7b-138">Un utilisateur peut être affecté à un seul fournisseur de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-138">A user can be assigned only one audio conferencing provider.</span></span>
    
- <span data-ttu-id="b0e7b-139">Vous pouvez modifier le fournisseur de conférence audio de Microsoft, à un fournisseur tiers à tout moment.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-139">You can change the audio conferencing provider from Microsoft to a third-party provider at any time.</span></span> <span data-ttu-id="b0e7b-140">Pour plus d’informations, consultez [affecter un comme fournisseur de conférence audio tiers](assign-a-third-party-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="b0e7b-140">To learn more, see [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="b0e7b-141">Dans votre organisation, vous pouvez avoir certains utilisateurs de Microsoft comme leur fournisseur de conférence audio, les personnes qui utilisent un fournisseur tiers.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-141">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider.</span></span> <span data-ttu-id="b0e7b-142">Mais c’est plus compliqué à configurer et à gérer.</span><span class="sxs-lookup"><span data-stu-id="b0e7b-142">But this is more complicated to set up and manage.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="b0e7b-143">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="b0e7b-143">Related topics</span></span>

[<span data-ttu-id="b0e7b-144">Configurer la conférence Audio pour Skype entreprise et Teams Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0e7b-144">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="b0e7b-145">Configurer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b0e7b-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)