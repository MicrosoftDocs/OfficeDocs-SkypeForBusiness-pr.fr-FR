---
title: Affecter Microsoft comme fournisseur de services d'audioconférence
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn how to assign Microsoft the dial-in conferencing provider for Skype for Business.
ms.openlocfilehash: 2fd01e38b05615bab79471b60aafeb8d0409c1d4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017124"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Affecter Microsoft comme fournisseur de services d'audioconférence

Pour utiliser l'audioconférence dans Office 365 avec Skype Entreprise et Microsoft Teams, les utilisateurs de votre organisation doivent disposer d'une licence audioconférence. Pour obtenir plus d’informations sur les licences et les tarifs proposés, voir [Essayer ou acheter les services d'audioconférence dans Office 365](try-or-purchase-audio-conferencing-in-office-365.md).

Le service d'audioconférence Microsoft fournit des numéros d'appel, des codes personnels et des ID qui peuvent âtre utilisées par les participants pour rejoindre des réunions au sein de votre organisation. Vous devez uniquement attribuer des Microsoft en tant que le fournisseur de services d’audioconférence aux personnes qui vont planifier ou entraîner Skype pour les réunions Microsoft Teams ou de l’entreprise.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Affecter Microsoft comme fournisseur de services d'audioconférence

### <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Utilisation du centre d'administration Skype Entreprise

1. Accédez au site **équipes & Skype pour le centre d’administration Business** > **portail hérité**.
    
2. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**.
    
3. Si vous voyez une bannière vous avertissant que des utilisateurs disposent d'une licence **Audioconférence** mais n'ont pas affecté Microsoft en tant que fournisseur de service d'audioconférence, cliquez sur **Cliquer ici pour les déplacer**. Si vous ne voyez pas la bannière, dans le **centre d'administration Skype Entreprise** cliquez sur **Utilisateurs**, puis sélectionnez le filtre **Utilisateurs prêts à être déplacés vers Audioconférence** .
    
4. Dans la page Propriétés de l’utilisateur, sous **nom du fournisseur**, sélectionnez **Microsoft** dans la liste déroulante.
    
    > [!NOTE]
    > Étant donné que vous utilisez Microsoft en tant que le fournisseur de services d’audioconférence et il existe plusieurs numéros de téléphone, vous pouvez utiliser la liste déroulante **numéro de téléphone payant par défaut** pour sélectionner un numéro audio par défaut pour l’utilisateur.
  
5. Cliquez sur **Enregistrer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>Utilisation d'un script Windows PowerShell pour un petit nombre d'utilisateurs

Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser le script PowerShell suivant pour définir Microsoft en tant que le fournisseur de services d’audioconférence pour un petit nombre d’utilisateurs.

> [!NOTE]
> Lorsque le fournisseur est modifié à partir d’un autre fournisseur à **Microsoft**, les informations de conférence audio de l’utilisateur (ID de conférence, payant et gratuit) seront remplacées. Enregistrez ces informations avant de changer de fournisseur. 

  
Pour modifier le fournisseur à Microsoft pour un petit nombre d’utilisateurs, vous pouvez utiliser l’applet de commande [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/en-us/library/mt243813.aspx) .
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>Utilisation d'un script Windows PowerShell pour un grand nombre d'utilisateurs
Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser le script PowerShell suivant pour définir Microsoft en tant que le fournisseur de services d’audioconférence pour un grand nombre d’utilisateurs.

Lorsque le fournisseur est modifié à partir d’un autre fournisseur à **Microsoft**, les informations de conférence audio de l’utilisateur (ID de conférence, payant et gratuit) seront remplacées. Enregistrez ces informations avant de changer de fournisseur. 
  
Vous pouvez enregistrer le script suivant dans un fichier script PowerShell et l’exécuter ensuite en utilisant l'un de ses paramètres d’entrée.

**Exemple 1 :** vous pouvez exécuter ce script en fournissant la liste des utilisateurs que vous souhaitez mettre à jour.
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**Exemple 2 :** vous pouvez exécuter ce script en fournissant un fichier .csv contenant l'adresse électronique (alias) de chaque utilisateur que vous souhaitez mettre à jour.
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**L’exemple 3 :** Dans cet exemple, vous pouvez utiliser ce script pour modifier le fournisseur de services d’audioconférence à partir de Intercall (ou un autre fournisseur) à **Microsoft** pour un grand nombre d’utilisateurs dans votre organisation.
    
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
[Essayer ou acheter les services d'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

