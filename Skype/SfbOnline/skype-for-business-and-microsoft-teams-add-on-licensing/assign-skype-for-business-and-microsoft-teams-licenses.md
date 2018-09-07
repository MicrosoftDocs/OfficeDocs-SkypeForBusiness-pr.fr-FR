---
title: Affecter des licences Skype Entreprise et Microsoft Teams
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Licensing
description: "Apprenez comment affecter des licences Skype Entreprise pour le Système téléphonique, l'Audioconférence, les Plans d'appel et les Crédits de communications. "
ms.openlocfilehash: af2b7357c5dbe9e11b84ac87e0f72721d10a6a30
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856052"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>Affecter des licences Skype Entreprise et Microsoft Teams

Cet article vous donne des conseils sur l’affectation de licences à vos utilisateurs pour des fonctionnalités telles que l'Audioconférence, le Système téléphonique et les Forfaits d’appels. Il vous fournit également des scripts pour affecter des licences en volume.

> [!IMPORTANT]
> Voir [Octroi de licences de compléments Skype Entreprise et Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md) pour plus d’informations sur quelles licences vous devez acheter et **Comment acheter** ces dernières - en fonction de votre plan Office 365 -, de façon à ce que les utilisateurs disposent de l’Audioconférence, de numéros gratuits, et de la possibilité d’appeler des numéros de téléphone à l’extérieur de votre entreprise.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences

Ce que vous devez connaître avant d’affecter des licences Audioconférence, Système téléphonique et Forfait d'appels

- **Utilisation de la connectivité RTC locale pour les utilisateurs hybrides ?** Dans ce cas, vous avez seulement besoin d’affecter une licence de **Système téléphonique**. Vous ne devez **PAS** affecter un Forfait d'appels.

- **Latence après affectation de licences** : en raison de la latence entre Office 365 et Skype Entreprise Online, jusqu'à 24 heures peuvent être nécessaires pour qu'un utilisateur se voie affecter un Plan d'appel après que vous lui avez affecté une licence. Si après 24 heures, l’utilisateur ne se voit pas affecter un Forfait d’appels, veuillez [Contacter le support pour les produits entreprise : aide à l’administration](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Messages d'erreur** : un message d'erreur s'affiche si vous n'avez pas acheté le nombre correct de licences. Si vous devez acheter davantage de licences de Forfait d'appels, choisissez **Acheter plus**.
    
- **Prochaines étapes** : après que vous aurez affecté des licences de Forfaits d'appels à vos utilisateurs, vous aurez besoin d'obtenir les numéros de téléphone de votre organisation, puis de les affecter aux personnes dans votre organisation. Pour des instructions pas à pas, voir [Configurer des Forfaits d'appels](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Comment affecter une licence Système téléphonique et Forfait d’appel à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Comment affecter des licences Système téléphonique et Forfait d’appel en volume

1. Installez l' **Assistant de connexion Microsoft Online Services pour les informaticiens RTW**. Le module n'est pas installé ? Voir [Assistant de connexion Microsoft Online Services pour les professionnels des technologies de l'information RTW](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.

2. Installez le **module Windows Azure Active Directory**. Le module n'est pas installé ? Voir [Gérez Azure AD en utilisant Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) pour les instructions de téléchargement et la syntaxe de cmdlet.

3. Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

  Cet exemple affecte une **licence Entreprise E3**, ainsi qu'une licence **Système téléphonique** et **Forfait d’appels interne**.

  Le nom des licences ou les noms des produits dans le script sont listés en italique dans le texte (reportez-vous à la rubrique **Système téléphonique et noms des produits de Forfaits d’appels RTC ou UGS utilisés pour l’écriture de scripts**, après l’exemple).

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Système téléphonique et noms des produits Forfaits d’appel ou UGS utilisés pour l’écriture de scripts

|**Nom du produit**|**Référence**|
|:-----|:-----|
|Entreprise E5 (avec Système téléphonique)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Entreprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Entreprise E1  <br/> |STANDARDPACK  <br/> |
|Plan autonome 2 de Skype Entreprise Online  <br/> |MCOSTANDARD  <br/> |
|Système téléphonique  <br/> |MCOEV  <br/> |
|Forfait d'appels international  <br/> |MCOPSTN2  <br/> |
|Forfait d'appels nationaux  <br/> |MCOPSTN1  <br/> |
|Crédits de communication  <br/> |MCOPSTNPP  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audioconférence : conseils et scripts pour affecter les licences

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Ce que vous devez savoir avant d'affecter des licences d'Audioconférence

- **Fournisseur de services d’audioconférence tiers** : si des personnes sont déjà configurées pour utiliser un fournisseur de services d’audioconférence tiers, lorsque vous leur affectez une licence d'**Audioconférence**, elles seront modifiées pour utiliser Microsoft comme fournisseur d’audioconférence. Vous pouvez le remplacer par le fournisseur tiers.

- Étapes suivantes : après avoir affecté des licences d'**Audioconférence**, vous devez affecter un fournisseur de services d’audioconférence. Voir [Affecter Microsoft comme fournisseur d'audioconférence].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Comment affecter une licence d’Audioconférence à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Comment affecter des licences d’Audioconférence en volume

1. Téléchargez et installez l’[Assistant de connexion à Microsoft Online Services pour les professionnels des technologies de l’information RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Téléchargez et installez le **module Windows Azure Active Directory**. Pour connaître les instructions de téléchargement et la syntaxe des applets de commande, reportez-vous à la rubrique[Gestion d'Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).

    Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

    Les noms de licence ou de produit dans le script sont notés en italique. Voir [Noms des produits d’Audioconférence ou UGS utilisés pour l’écriture de scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) pour tous les noms de produits.

    Cet exemple affecte une licence Entreprise E3 avec une licence Audioconférence.

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Noms des produits d’Audioconférence ou UGS utilisés pour l’écriture de scripts
<a name="sku"> </a>

|**Nom du produit**|**Référence**|
|:-----|:-----|
|Audioconférence  <br/> |MCOMEETADV  <br/> |
|Plan autonome 2 de Skype Entreprise Online  <br/> |MCOSTANDARD  <br/> |
|Entreprise E1  <br/> |STANDARDPACK  <br/> |
|Entreprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Entreprise E5 (sans Audioconférence)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Entreprise E5 (avec Audioconférence)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Crédits de communication

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Ce que vous devez savoir avant l’affectation de licences de Crédits de communications

- **Clients Entreprise E5** : même si vos utilisateurs se sont vus affecter des licences Enterprise E5, nous vous recommandons néanmoins de leur affecter des licences **Crédits de communication**.
    
- **Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation. Pour des instructions pas à pas, voir [Configurer des Forfaits d’appels](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Comment affecter une licence Crédits de communications à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Comment affecter des licences Crédits de communications en volume

Jetez un coup d'œil à l'exemple de script pour l'affectation des licences d'**Audioconférence**. Mettez-le à jour avec les informations d’affectation de licences **Crédits de communications**.

## <a name="related-topics"></a>Rubriques connexes
  
[Configurer des offres d'appels](/microsoftteams/set-up-calling-plans)
  
[Ajouter des fonds et gérer les crédits de communication](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
