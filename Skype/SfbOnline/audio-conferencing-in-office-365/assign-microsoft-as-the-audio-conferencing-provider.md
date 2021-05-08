---
title: Affectation de Microsoft en tant que fournisseur d’audioconférence
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 74469a7686855d1bb17627282a9f2e5378a0d59e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237760"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="c24d5-103">Affectation de Microsoft en tant que fournisseur d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="c24d5-103">Assign Microsoft as the audio conferencing provider</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="c24d5-104">Pour utiliser l’audioconférence dans Microsoft 365 ou Office 365 avec Skype Entreprise et Microsoft Teams, les utilisateurs de votre organisation doivent avoir une licence d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="c24d5-104">To use Audio Conferencing in Microsoft 365 or Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="c24d5-105">Pour [plus d’informations](try-or-purchase-audio-conferencing-in-office-365.md) sur les licences et leur coût, voir Tester ou acheter l’audioconférence Microsoft 365 ou Office 365 d’informations sur les licences et leur prix.</span><span class="sxs-lookup"><span data-stu-id="c24d5-105">See [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="c24d5-106">Le service d'audioconférence Microsoft fournit des numéros d'appel, des codes personnels et des ID qui peuvent âtre utilisées par les participants pour rejoindre des réunions au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c24d5-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="c24d5-107">Vous devez seulement affecter Microsoft comme fournisseur de services d’audioconférence aux personnes qui vont planifier ou diriger Skype Entreprise ou Microsoft Teams réunions.</span><span class="sxs-lookup"><span data-stu-id="c24d5-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="c24d5-108">Affectation de Microsoft en tant que fournisseur d’audioconférence</span><span class="sxs-lookup"><span data-stu-id="c24d5-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Icône représentant le logo Skype Entreprise’affichage](../images/sfb-logo-30x30.png) <span data-ttu-id="c24d5-110">Utilisation du centre d'administration Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="c24d5-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="c24d5-111">Go to the **Microsoft Teams admin center** Legacy  >  **portal.**</span><span class="sxs-lookup"><span data-stu-id="c24d5-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="c24d5-112">Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez à **l’audioconférence.**</span><span class="sxs-lookup"><span data-stu-id="c24d5-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c24d5-113">Si vous voyez une bannière vous avertissant que des utilisateurs disposent d'une licence **Audioconférence** mais n'ont pas affecté Microsoft en tant que fournisseur de service d'audioconférence, cliquez sur **Cliquer ici pour les déplacer**.</span><span class="sxs-lookup"><span data-stu-id="c24d5-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="c24d5-114">Si vous ne voyez pas la bannière, dans le **centre d'administration Skype Entreprise** cliquez sur **Utilisateurs**, puis sélectionnez le filtre **Utilisateurs prêts à être déplacés vers Audioconférence** .</span><span class="sxs-lookup"><span data-stu-id="c24d5-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="c24d5-115">Dans la page des propriétés de l’utilisateur, sous **Nom du fournisseur,** **sélectionnez Microsoft** dans la liste de listes de liste.</span><span class="sxs-lookup"><span data-stu-id="c24d5-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c24d5-116">Étant donné que vous utilisez Microsoft comme fournisseur de services d’audioconférence et qu’il existe plusieurs numéros de téléphone, vous pouvez utiliser la liste de listes des numéros gratuits par défaut pour sélectionner un numéro audio par défaut pour l’utilisateur. </span><span class="sxs-lookup"><span data-stu-id="c24d5-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="c24d5-117">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c24d5-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="c24d5-118">Utilisation d'un script Windows PowerShell pour un petit nombre d'utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c24d5-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="c24d5-119">Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser le script PowerShell suivant pour définir Microsoft comme fournisseur de services d’audioconférence pour un petit nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c24d5-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="c24d5-120">Lorsque le fournisseur est remplacé par **Microsoft,** les informations de conférence audio de l’utilisateur (ID de conférence, numéros gratuits et gratuits) sont remplacées.</span><span class="sxs-lookup"><span data-stu-id="c24d5-120">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="c24d5-121">Enregistrez ces informations avant de changer de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c24d5-121">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="c24d5-122">Pour changer de fournisseur et utiliser Microsoft pour un petit nombre d’utilisateurs, vous pouvez utiliser l’cmdlet [Enable-CsOnlineDialInConferencingUser.](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser)</span><span class="sxs-lookup"><span data-stu-id="c24d5-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="c24d5-123">Utilisation d'un script Windows PowerShell pour un grand nombre d'utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c24d5-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="c24d5-124">Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser le script PowerShell suivant pour définir Microsoft comme fournisseur de services d’audioconférence pour un grand nombre d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c24d5-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="c24d5-125">Lorsque le fournisseur est remplacé par **Microsoft,** les informations de conférence audio de l’utilisateur (ID de conférence, numéros gratuits et gratuits) sont remplacées.</span><span class="sxs-lookup"><span data-stu-id="c24d5-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="c24d5-126">Enregistrez ces informations avant de changer de fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c24d5-126">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="c24d5-127">Vous pouvez enregistrer le script suivant dans un fichier script PowerShell et l’exécuter ensuite en utilisant l'un de ses paramètres d’entrée.</span><span class="sxs-lookup"><span data-stu-id="c24d5-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="c24d5-128">**Exemple 1 :** vous pouvez exécuter ce script en fournissant la liste des utilisateurs que vous souhaitez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="c24d5-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="c24d5-129">**Exemple 2 :** vous pouvez exécuter ce script en fournissant un fichier .csv contenant l'adresse électronique (alias) de chaque utilisateur que vous souhaitez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="c24d5-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="c24d5-130">**Exemple 3 :** Dans cet exemple, vous pouvez utiliser ce script pour changer le fournisseur de services d’audioconférence d’Intercall (ou autre fournisseur) en **Microsoft** pour un grand nombre d’utilisateurs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c24d5-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="c24d5-131">Voici le script :</span><span class="sxs-lookup"><span data-stu-id="c24d5-131">Here is the script:</span></span>

  ```PowerShell
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
<span data-ttu-id="c24d5-132">Pour plus d'informations sur l'utilisation de Windows PowerShell, consultez la rubrique [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c24d5-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c24d5-133">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c24d5-133">Related topics</span></span>
<span data-ttu-id="c24d5-134">[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
 [Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="c24d5-134">[Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>
