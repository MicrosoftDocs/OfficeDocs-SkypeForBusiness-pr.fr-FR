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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 360d580b57ca9528eddf96d80b773c04c71c361b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727713"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Affectation de Microsoft en tant que fournisseur d’audioconférence

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Pour utiliser l’audioconférence dans Microsoft 365 ou Office 365 avec Skype Entreprise et Microsoft Teams, les utilisateurs de votre organisation doivent avoir une licence d’audioconférence. Pour [plus d’informations](try-or-purchase-audio-conferencing-in-office-365.md) sur les licences et leur coût, voir Tester ou acheter l’audioconférence Microsoft 365 ou Office 365 d’informations sur les licences et leur prix.

Le service d'audioconférence Microsoft fournit des numéros d'appel, des codes personnels et des ID qui peuvent âtre utilisées par les participants pour rejoindre des réunions au sein de votre organisation. Vous devez seulement affecter Microsoft comme fournisseur de services d’audioconférence aux personnes qui vont planifier ou diriger Skype Entreprise ou Microsoft Teams réunions.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Affectation de Microsoft en tant que fournisseur d’audioconférence

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png) Utilisation du centre d'administration Skype Entreprise

1. Go to the **Microsoft Teams admin center** Legacy  >  **portal.**
    
2. Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez à **l’audioconférence.**
    
3. Si vous voyez une bannière vous avertissant que des utilisateurs disposent d'une licence **Audioconférence** mais n'ont pas affecté Microsoft en tant que fournisseur de service d'audioconférence, cliquez sur **Cliquer ici pour les déplacer**. Si vous ne voyez pas la bannière, dans le **centre d'administration Skype Entreprise** cliquez sur **Utilisateurs**, puis sélectionnez le filtre **Utilisateurs prêts à être déplacés vers Audioconférence** .
    
4. Dans la page des propriétés de l’utilisateur, sous **Nom du fournisseur,** **sélectionnez Microsoft** dans la liste de listes de liste.
    
    > [!NOTE]
    > Étant donné que vous utilisez Microsoft comme fournisseur de services d’audioconférence et qu’il existe plusieurs numéros de téléphone, vous pouvez utiliser la liste de listes des numéros gratuits par défaut pour sélectionner un numéro audio par défaut pour l’utilisateur. 
  
5. Cliquez sur **Enregistrer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Utilisation d'un script Windows PowerShell pour un petit nombre d'utilisateurs

Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser le script PowerShell suivant pour définir Microsoft comme fournisseur de services d’audioconférence pour un petit nombre d’utilisateurs.

> [!NOTE]
> Lorsque le fournisseur est remplacé par **Microsoft,** les informations de conférence audio de l’utilisateur (ID de conférence, numéros gratuits et gratuits) sont remplacées. Enregistrez ces informations avant de changer de fournisseur. 

  
Pour changer de fournisseur et utiliser Microsoft pour un petit nombre d’utilisateurs, vous pouvez utiliser l’cmdlet [Enable-CsOnlineDialInConferencingUser.](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser)
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Utilisation d'un script Windows PowerShell pour un grand nombre d'utilisateurs
Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser le script PowerShell suivant pour définir Microsoft comme fournisseur de services d’audioconférence pour un grand nombre d’utilisateurs.

Lorsque le fournisseur est remplacé par **Microsoft,** les informations de conférence audio de l’utilisateur (ID de conférence, numéros gratuits et gratuits) sont remplacées. Enregistrez ces informations avant de changer de fournisseur. 
  
Vous pouvez enregistrer le script suivant dans un fichier script PowerShell et l’exécuter ensuite en utilisant l'un de ses paramètres d’entrée.

**Exemple 1 :** vous pouvez exécuter ce script en fournissant la liste des utilisateurs que vous souhaitez mettre à jour.
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**Exemple 2 :** vous pouvez exécuter ce script en fournissant un fichier .csv contenant l'adresse électronique (alias) de chaque utilisateur que vous souhaitez mettre à jour.
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**Exemple 3 :** Dans cet exemple, vous pouvez utiliser ce script pour changer le fournisseur de services d’audioconférence d’Intercall (ou autre fournisseur) en **Microsoft** pour un grand nombre d’utilisateurs dans votre organisation.
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  Voici le script :

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
Pour plus d'informations sur l'utilisation de Windows PowerShell, consultez la rubrique [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="related-topics"></a>Sujets associés
[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 
 [Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
