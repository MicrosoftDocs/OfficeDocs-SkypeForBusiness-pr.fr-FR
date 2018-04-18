---
title: Affecter Microsoft comme le fournisseur de conférence audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 2ccb2b9a2b0a611d46056a8369dcb92d294c081f
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Affecter Microsoft comme le fournisseur de conférence audio

Pour utiliser l’audioconférence dans Office 365 avec Skype pour les entreprises et les Teams de Microsoft, les utilisateurs de votre organisation devront disposer d’une licence d’Audio conférence qui leur sont affectée. Pour obtenir plus d’informations sur les licences et son coût, reportez-vous à la section [Essayez ou achetez audioconférence dans Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .

Conférence Audio de Microsoft fournit les numéros de téléphone, des broches et conférence ID qui peut être utilisé par les participants à la réunion à assister aux réunions de votre organisation. Vous devez uniquement affecter Microsoft comme le fournisseur de conférence audio pour les personnes qui vont planifier ou entraîner Skype pour les réunions d’entreprise ou Teams de Microsoft.
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Affecter Microsoft comme le fournisseur de conférence audio

### <a name="using-the-skype-for-business-admin-center"></a>Utilisation du centre d'administration Skype Entreprise

1. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
2. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **l’audioconférence**.
    
3. Si vous voyez une bannière qui vous avertit qu’il existe des utilisateurs qui ont une **Conférence Audio** licence affectés mais n’avez pas Microsoft défini comme leur fournisseur de conférence audio pour l’instant, cliquez sur **Cliquez ici pour les déplacer**. Si vous ne voyez pas la bannière, dans le **Skype pour le centre d’administration Business** cliquez sur **utilisateurs**et puis sélectionnez le filtre **prête à être déplacée à l’Audio conférence des utilisateurs** .
    
4. Sur la page de propriétés de l’utilisateur, sous **le nom du fournisseur**, sélectionnez **Microsoft** dans la liste déroulante.
    
    > [!NOTE]
    > Dans la mesure où vous utilisez Microsoft comme le fournisseur de conférence audio et il y a plusieurs numéros de téléphone, vous pouvez utiliser la liste déroulante **numéro d’appel payant par défaut** pour sélectionner un numéro d’audio par défaut pour l’utilisateur.
  
5. Cliquez sur **Enregistrer**.
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Utilisation d'un script Windows PowerShell pour un petit nombre d'utilisateurs

Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser le script PowerShell suivant à configurer Microsoft comme le fournisseur de conférence audio pour un petit nombre d’utilisateurs.

> [!NOTE]
> Lorsque le fournisseur est modifié à partir d’un autre fournisseur pour **Microsoft**, les informations de conférence audio de l’utilisateur (ID de la conférence, numéro payant et numéros d’appel gratuits) seront remplacées. Enregistrez ces informations avant de changer de fournisseur. 

  
Pour modifier le fournisseur de Microsoft pour un petit nombre d’utilisateurs, vous pouvez utiliser l’applet de commande [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) .
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Utilisation d'un script Windows PowerShell pour un grand nombre d'utilisateurs
Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser le script PowerShell suivant à configurer Microsoft comme le fournisseur de conférence audio pour un grand nombre d’utilisateurs.

Lorsque le fournisseur est modifié à partir d’un autre fournisseur pour **Microsoft**, les informations de conférence audio de l’utilisateur (ID de la conférence, numéro payant et numéros d’appel gratuits) seront remplacées. Enregistrez ces informations avant de changer de fournisseur. 
  
Vous pouvez enregistrer le script suivant dans un fichier de script PowerShell et ensuite l’exécuter à l’aide de ses paramètres d’entrée.

**Exemple 1 :** vous pouvez exécuter ce script en fournissant la liste des utilisateurs que vous souhaitez mettre à jour.
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com,    user02@contoso.com, user03@contoso.com"
  ```

**Exemple 2 :** vous pouvez exécuter ce script en fournissant un fichier .csv contenant l'adresse électronique (alias) de chaque utilisateur que vous souhaitez mettre à jour.
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**Exemple 3 :** Dans cet exemple, vous pouvez utiliser ce script pour modifier le fournisseur de conférence audio à partir d’Intercall (ou un autre fournisseur) à **Microsoft** pour un grand nombre d’utilisateurs dans votre organisation.
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Voici le script :

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
Pour plus d'informations sur l'utilisation de Windows PowerShell, consultez la rubrique [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## <a name="related-topics"></a>Rubriques connexes
[Essayez ou achetez audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[paramétrer Skype pour professionnels en ligne](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

