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
ms.openlocfilehash: 9aa423683160c064b13be140c4226b2327dd9b69
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692519"
---
# <a name="assign-skype-for-business-licenses"></a>Attribuer des licences Skype Entreprise

This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.

> [!IMPORTANT]
> Pour plus d’informations sur les licences que vous devez acheter et sur **la manière de les acheter** , reportez-vous à la rubrique [licences de compléments Skype entreprise](skype-for-business-and-microsoft-teams-add-on-licensing.md) , en fonction de votre plan Office 365, afin que les utilisateurs puissent obtenir des conférences audio, des numéros gratuits et la possibilité d’appeler des numéros de téléphone en dehors de votre entreprise.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences

Ce que vous devez connaître avant d’affecter des licences Audioconférence, Système téléphonique et Forfait d'appels

- **Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.

- **Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.
    
- **Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Attribution d’un système téléphonique et d’une licence de plan d’appel à un utilisateur

The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Comment affecter des licences Système téléphonique et Forfait d’appel en volume

1. Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.

2. Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.

3. Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

   Cet exemple affecte une **licence Entreprise E3**, ainsi qu'une licence **Système téléphonique** et **Forfait d’appels interne**.

   Le nom des licences ou des noms de produits figurant dans le script est affiché en italique (voir le **système téléphonique et les noms des produits de plan d’appel et les références (SKU) utilisées pour l’écriture de scripts**, après l’exemple).

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Système téléphonique et offres d’appels noms de produits ou UGS utilisés pour l’écriture de scripts

|**Nom du produit**|**Référence**|
|:-----|:-----|
|Entreprise E5 (avec Système téléphonique)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Entreprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Entreprise E1  <br/> |STANDARDPACK  <br/> |
|Plan autonome 2 de Skype Entreprise Online  <br/> |MCOSTANDARD  <br/> |
|Système téléphonique  <br/> |MCOEV  <br/> |
|Plan d’appels internationaux  <br/> |MCOPSTN2  <br/> |
|Forfait d’appels nationaux (3000 min US/1200 min Europe)  <br/> |MCOPSTN1  <br/> |
|Forfait d’appels nationaux (forfait d’appels 120 min)  <br/> |MCOPSTN5  <br/> |
|Forfait d’appels nationaux (forfait d’appels 240 min)  <br/> |MCOPSTN6  <br/> |
|Crédits de communication  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audioconférence : conseils et scripts pour affecter des licences

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Ce que vous devez savoir avant d’affecter des licences de conférence audio

- Fournisseur de services d' **audioconférence tiers**: si une personne est déjà configurée pour utiliser un fournisseur de services d’audioconférence tiers, lorsque vous lui attribuez une licence d' **audioconférence** , celle-ci est modifiée de manière à utiliser Microsoft comme fournisseur de services d’audioconférence. Vous pouvez le remplacer par le fournisseur tiers.

- Étapes suivantes : une fois que vous avez attribué des licences de **conférence audio** , vous devez affecter un fournisseur de services d’audioconférence. Voir [Affecter Microsoft comme fournisseur d'audioconférence].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Comment affecter une licence de conférence audio à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Comment affecter des licences de conférence audio en bloc

1. Téléchargez et installez [l’Assistant de connexion de Microsoft Online Services pour les informaticiens RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Téléchargez et installez le **module Windows Azure Active Directory**. Pour connaître les instructions de téléchargement et la syntaxe des applets de commande, reportez-vous à la rubrique[Gestion d'Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).

    Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

    Le nom des licences ou des produits du script est répertorié dans le texte en italique. Voir les noms des produits de l’audioconférence pour l' [écriture de scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) pour l’ensemble des noms de produits.

    Cet exemple affecte une licence entreprise E3, ainsi qu’une licence de conférence audio.

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Noms des produits de conférence audio ou références (SKU) utilisés pour l’écriture de scripts
<a name="sku"> </a>

|**Nom du produit**|**Référence**|
|:-----|:-----|
|Audioconférence,  <br/> |MCOMEETADV  <br/> |
|Plan autonome 2 de Skype Entreprise Online  <br/> |MCOSTANDARD  <br/> |
|Entreprise E1  <br/> |STANDARDPACK  <br/> |
|Entreprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Entreprise E5 (sans Audioconférence)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Entreprise E5 (avec audioconférence)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Crédits de communication

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Ce que vous devez savoir avant d’affecter des licences de crédits de communication

- **Clients entreprise E5**: même si des licences entreprise E5 ont été affectées à vos utilisateurs, nous vous conseillons de leur affecter des licences de **crédits de communication** .
    
- **Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation. Pour obtenir des instructions détaillées, consultez la rubrique [configurer les offres d’appels](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Comment affecter une licence de crédits de communication à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Comment attribuer des crédits de communication en bloc

Jetez un coup d’œil à l’exemple de script permettant d’affecter des licences de **conférence audio** . Mettez-le à jour avec les informations relatives à l’affectation de licences de **crédits de communication** .

## <a name="related-topics"></a>Rubriques connexes
  
[Configurer des forfaits d'appels](/microsoftteams/set-up-calling-plans)
  
[Ajouter des fonds et gérer les Crédits de Communications](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
