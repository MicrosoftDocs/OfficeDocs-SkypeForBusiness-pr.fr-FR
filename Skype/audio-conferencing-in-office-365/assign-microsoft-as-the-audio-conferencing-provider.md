---
title: "Affecter Microsoft comme fournisseur de services d'audioconférence"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
description: "Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business. Conferencing bridge."
---

# Affecter Microsoft comme fournisseur de services d'audioconférence

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](d935a90d-ea61-433d-a820-b400ed9c1f5d.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/d935a90d-ea61-433d-a820-b400ed9c1f5d). 
  
Un fournisseur de services d'audioconférence fournit le  *pont de conférence*  . Le pont de conférence fournit les numéros de téléphone, des codes confidentiels et identifiants de conférence pour les réunions sont créés. Vous devez uniquement affecter un fournisseur de services d'audioconférence aux personnes qui vont planifier ou prospect Skype Entreprise ou Teams Microsoft réunions.
  
Si vous voulez être en mesure de voir **que Microsoft** soit répertorié comme fournisseur d'audio, vous devez attribuer une licence de ** Conférence Audio** à l'utilisateur.
  
> [!NOTE]
> Si vous attribuez une licence de **Conférence Audio** à une personne qui n'a pas un fournisseur de services d'audioconférence tiers, Microsoft est automatiquement affecté comme fournisseur de services d'audioconférence. Vous pouvez[Affecter un tiers comme fournisseur de services d'audioconférence](assign-a-third-party-as-the-audio-conferencing-provider.md) si nécessaire.
  
## Affecter Microsoft comme fournisseur de services d'audioconférence

### Utilisation du centre d'administration Skype Entreprise

1. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
    > [!NOTE]
    > Lorsque le fournisseur est modifié à partir d'un autre fournisseur à **Microsoft**, les informations de services d'audioconférence pour l'utilisateur (ID de conférence, numéro payant et numéros gratuits) seront remplacées. Vous devez enregistrer ces informations avant de modifier le fournisseur. 
  
2. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **utilisateurs** et sélectionnez l'utilisateur dans la liste des utilisateurs disponibles.
    
3. Dans le volet Action, cliquez sur **Modifier**.
    
4. Dans la page Propriétés de l'utilisateur, sous **nom du fournisseur**, sélectionnez **Microsoft** dans la liste déroulante.
    
    > [!NOTE]
    > Étant donné que vous utilisez Microsoft comme fournisseur de services d'audioconférence et qu'il existe plusieurs numéros de téléphone, vous pouvez utiliser la liste déroulante **numéro payant par défaut** pour sélectionner un numéro audio par défaut pour l'utilisateur.
  
5. Cliquez sur **Enregistrer**.
    
### À l'aide d'un script Windows PowerShell pour un petit nombre d'utilisateurs

Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser le script PowerShell suivant à configurer Microsoft comme fournisseur de services d'audioconférence pour un petit nombre d'utilisateurs.
  
> [!NOTE]
> Lorsque le fournisseur est modifié à partir d'un autre fournisseur à **Microsoft**, les informations de services d'audioconférence pour l'utilisateur (ID de conférence, numéro payant et numéros gratuits) seront remplacées. Vous devez enregistrer ces informations avant de modifier le fournisseur. 
  
Vous pouvez enregistrer un ou plusieurs des scripts suivants comme fichiers de script PowerShell puis les exécuter.
  
Pour remplacer le fournisseur par Microsoft pour un petit nombre d'utilisateurs, vous pouvez utiliser le script [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx).
  
> **Exemple 1 :** vous pouvez exécuter ce script en fournissant la liste des utilisateurs que vous souhaitez mettre à jour.
    
> 
  ```
  Script.ps1 -UserList <List of users>
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> **Exemple 2 :** vous pouvez exécuter ce script en fournissant un fichier .csv contenant l'adresse électronique (alias) de chaque utilisateur que vous souhaitez mettre à jour.
    
> 
  ```
  Script.ps1 -CsvFile <Path of the csv file>
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

### Utilisation d'un script Windows PowerShell pour un grand nombre d'utilisateurs

Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser le script PowerShell suivant à configurer Microsoft comme fournisseur de services d'audioconférence pour un grand nombre d'utilisateurs.
  
> [!NOTE]
> Lorsque le fournisseur est modifié à partir d'un autre fournisseur à **Microsoft**, les informations de services d'audioconférence pour l'utilisateur (ID de conférence, numéro payant et numéros gratuits) seront remplacées. Vous devez enregistrer ces informations avant de modifier le fournisseur. 
  
Vous pouvez enregistrer un ou plusieurs des scripts suivants comme fichiers de script PowerShell puis les exécuter.
  
> **Exemple 1 :** Dans cet exemple, vous pouvez utiliser ce script pour modifier le fournisseur de services d'audioconférence à partir de Intercall (ou un autre fournisseur) à **Microsoft** pour un grand nombre d'utilisateurs de votre organisation.
    
> 
  ```
  Script.ps1 -ACPProviderName <Provider>
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName "Intercall"
  ```

    **Le script est le suivant :**
    
> 

> 
  ```
  <#
  ```

> 
  ```
  .SYNOPSIS

  ```

  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .DESCRIPTION
  ```

> 
  ```
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.
  ```

> 
  ```
  .EXAMPLE
  ```

> 
  ```
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

> 
  ```
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

> 
  ```
  ./Script.ps1 -ACPProviderName ""Intercall""
  ```

> 
  ```
  #>
  ```

> 
  ```
  param (
  ```

> 
  ```
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
  ```

> 
  ```
   [string]$CsvFile,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
  ```

> 
  ```
   [string]$UserList,
  ```

> 
  ```
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  ```

> 
  ```
  [string]$ACPProviderName
  ```

> 
  ```
  )
  ```

> 
  ```
  if ($CsvFile)
  ```

> 
  ```
  {
  ```

> 
  ```
  if(!(Test-Path $CsvFile))
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "File does not exist."
  ```

> 
  ```
  Exit
  ```

> 
  ```
   }
  ```

> 
  ```
  $users = Get-Content $CsvFile
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  $users = $UserList.Split(",")
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($ACPProviderName)
  ```

> 
  ```
  {
  ```

> 
  ```
  $supportedACPProviders = Get-csAudioConferencingProvider
  ```

> 
  ```
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  ```

> 
  ```
  if ($providerNameMatch -eq $null)
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  ```

> 
  ```
  $supportedACPProviders      | %{$_.Identity}
  ```

> 
  ```
  return
  ```

> 
  ```
  }
  ```

> 
  ```
  $allUsersInTenant = Get-csOnlineUser
  ```

> 
  ```
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  ```

> 
  ```
  }
  ```

> 
  ```
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.counts
  ```

> 
  ```
  foreach ($user in $users)
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($CsvFile -or $UserList)
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = Get-csOnlineUser -Identity $user
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  ```

> 
  ```
  Continue
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
  {
  ```

> 
  ```
  $adUser = $user
  ```

> 
  ```
  }
  ```

> 
  ```
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  ```

> 
  ```
  {
  ```

> 
  ```
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  ```

> 
  ```
  {
  ```

> 
  ```
  try
  ```

> 
  ```
  {
  ```

> 
  ```
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  ```

> 
  ```
  Write-Host "The provider of $user has changed to Microsoft."
  ```

> 
  ```
  $enableUser
  ```

> 
  ```
  }
  ```

> 
  ```
  catch
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  ```

> 
  ```
  continue;
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
   else
  ```

> 
  ```
  {
  ```

> 
  ```
  Write-Warning "The provider of $user is already set to Microsoft."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

> 
  ```
  else
  ```

> 
  ```
              {
  ```

> 
  ```
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  ```

> 
  ```
  }
  ```

> 
  ```
  }
  ```

Pour plus d'informations sur l'utilisation de Windows PowerShell, consultez la rubrique [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise](https://go.microsoft.com/fwlink/?LinkId=525038).
  
## Informations supplémentaires

- Un utilisateur peut être affecté qu'un seul fournisseur de services d'audioconférence.
    
- Vous pouvez modifier le fournisseur de services d'audioconférence auprès de Microsoft à un fournisseur tiers à tout moment. Pour plus d'informations, voir [Affecter un tiers comme fournisseur de services d'audioconférence](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
- Dans votre organisation, vous pouvez avoir certaines personnes qui utilisent Microsoft comme leur fournisseur de services d'audioconférence et autres personnes qui utilisent un fournisseur tiers. Mais ce n'est plus complexe à configurer et gérer.
    
## Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

