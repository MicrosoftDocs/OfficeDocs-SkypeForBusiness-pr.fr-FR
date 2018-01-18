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
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Affecter Microsoft comme le fournisseur de conférence audio

Un fournisseur de conférence audio fournit le *pont de conférence*. Le pont de conférence fournit les numéros de téléphone, broches, les ID de conférence pour les réunions qui sont créées. Vous devrez affecter un fournisseur de conférence audio pour les personnes qui vont planifier ou entraîner Skype pour les réunions d’entreprise ou Teams de Microsoft.
  
Si vous souhaitez être en mesure de voir **que Microsoft** répertorié comme fournisseur audio, vous devez affecter une licence de **Conférence Audio** à l’utilisateur.
  
> [!NOTE]
> Si vous attribuez une licence de **Conférence Audio** à une personne qui ne possède pas un fournisseur de conférence audio de tiers, Microsoft est automatiquement désigné comme le fournisseur de conférence audio. Vous pouvez [affecter un tiers que le fournisseur de conférence audio](assign-a-third-party-as-the-audio-conferencing-provider.md) si nécessaire.
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Affecter Microsoft comme le fournisseur de conférence audio

### <a name="using-the-skype-for-business-admin-center"></a>Utilisation du centre d'administration Skype Entreprise

1. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
    > [!NOTE]
    > Lorsque le fournisseur est modifié à partir d’un autre fournisseur pour **Microsoft**, les informations de conférence audio de l’utilisateur (ID de la conférence, numéro payant et numéros d’appel gratuits) seront remplacées. Vous devez enregistrer ces informations avant de modifier le fournisseur. 
  
2. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.
    
3. Dans le volet Action, cliquez sur **Modifier**.
    
4. Sur la page de propriétés de l’utilisateur, sous **le nom du fournisseur**, sélectionnez **Microsoft** dans la liste déroulante.
    
    > [!NOTE]
    > Dans la mesure où vous utilisez Microsoft comme le fournisseur de conférence audio et il y a plusieurs numéros de téléphone, vous pouvez utiliser la liste déroulante **numéro d’appel payant par défaut** pour sélectionner un numéro d’audio par défaut pour l’utilisateur.
  
5. Cliquez sur **Enregistrer**.
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Utilisation d'un script Windows PowerShell pour un petit nombre d'utilisateurs

Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser le script PowerShell suivant à configurer Microsoft comme le fournisseur de conférence audio pour un petit nombre d’utilisateurs.

> [!NOTE]
> Lorsque le fournisseur est modifié à partir d’un autre fournisseur pour **Microsoft**, les informations de conférence audio de l’utilisateur (ID de la conférence, numéro payant et numéros d’appel gratuits) seront remplacées. Vous devez enregistrer ces informations avant de modifier le fournisseur. 
  
Vous pouvez enregistrer un ou plusieurs des scripts suivants comme fichiers de script PowerShell puis les exécuter.
  
Pour modifier le fournisseur de Microsoft pour un petit nombre d’utilisateurs, vous pouvez utiliser le [CsOnlineDialInConferencingUser de l’activer](https://technet.microsoft.com/en-us/library/mt243813.aspx).
  
**Exemple 1 :** vous pouvez exécuter ce script en fournissant la liste des utilisateurs que vous souhaitez mettre à jour.
> 
  ```
  Script.ps1 -UserList <List of users>
  ./Script.ps1 -UserList "user01@constoso.com,   user02@contoso.com, user03@contoso.com"
  ```
**Exemple 2 :** vous pouvez exécuter ce script en fournissant un fichier .csv contenant l'adresse électronique (alias) de chaque utilisateur que vous souhaitez mettre à jour.  
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```
### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Utilisation d'un script Windows PowerShell pour un grand nombre d'utilisateurs
Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser le script PowerShell suivant à configurer Microsoft comme le fournisseur de conférence audio pour un grand nombre d’utilisateurs.

Lorsque le fournisseur est modifié à partir d’un autre fournisseur pour **Microsoft**, les informations de conférence audio de l’utilisateur (ID de la conférence, numéro payant et numéros d’appel gratuits) seront remplacées. Vous devez enregistrer ces informations avant de modifier le fournisseur. 
  
Vous pouvez enregistrer un ou plusieurs des scripts suivants comme fichiers de script PowerShell puis les exécuter.

**Exemple 1 :** Dans cet exemple, vous pouvez utiliser ce script pour modifier le fournisseur de conférence audio à partir d’Intercall (ou un autre fournisseur) à **Microsoft** pour un grand nombre d’utilisateurs dans votre organisation.
    
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
Pour plus d'informations sur l'utilisation de Windows PowerShell, consultez la rubrique [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Un utilisateur peut être affecté à un seul fournisseur de conférence audio.
    
- Vous pouvez modifier le fournisseur de conférence audio de Microsoft, à un fournisseur tiers à tout moment. Pour plus d’informations, consultez [affecter un comme fournisseur de conférence audio tiers](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
- Dans votre organisation, vous pouvez avoir certains utilisateurs de Microsoft comme leur fournisseur de conférence audio, les personnes qui utilisent un fournisseur tiers. Mais c’est plus compliqué à configurer et à gérer.
    
## <a name="related-topics"></a>Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing.md)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)