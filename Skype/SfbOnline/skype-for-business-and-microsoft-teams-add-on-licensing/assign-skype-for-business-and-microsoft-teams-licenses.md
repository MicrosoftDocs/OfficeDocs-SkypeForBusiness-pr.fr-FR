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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: "Apprenez comment affecter des licences Skype Entreprise pour le Système téléphonique, l'Audioconférence, les Plans d'appel et les Crédits de communications. "
ms.openlocfilehash: 6917b3d47f29c10bea8b7695cfa69ace60609393
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671820"
---
# <a name="assign-skype-for-business-licenses"></a>Attribuer des licences Skype Entreprise

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cet article vous donne des conseils sur l’affectation de licences à vos utilisateurs pour des fonctionnalités telles que l'Audioconférence, le Système téléphonique et les Forfaits d’appels. Il vous fournit également des scripts pour affecter des licences en bloc.

> [!IMPORTANT]
> Consultez [Skype Entreprise licences de module](skype-for-business-and-microsoft-teams-add-on-licensing.md) complémentaire pour plus d’informations sur les licences que vous devez acheter et **sur la façon** de les acheter , en fonction de votre Microsoft 365 ou de votre plan de Office 365, afin que les utilisateurs obtiennent Audioconférence, des numéros gratuits et la possibilité d’appeler des numéros de téléphone en dehors de votre entreprise.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences

Ce que vous devez connaître avant d’affecter des licences Audioconférence, Système téléphonique et Forfait d'appels

- **Vous utilisez la connectivité PSTN locale pour les utilisateurs hybrides ?** Si c’est le cas, vous devez uniquement attribuer une licence **Système téléphonique**. Vous **ne devez PAS** attribuer de plan d’appel.

- **Latence après l’attribution de licences** : en raison de la latence entre Microsoft 365 ou Office 365 et Skype Entreprise Online, l’attribution d’un plan d’appel à un utilisateur après l’attribution d’une licence peut prendre jusqu’à 24 heures. Si, au bout de 24 heures, l’utilisateur ne reçoit pas de plan d’appel, contactez [le support technique pour les produits professionnels - Administration aide](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Messages d'erreur**: un message d'erreur s'affiche si vous n'avez pas acheté le nombre correct de licences. Si vous avez besoin d’acheter d’autres licences de forfait d’appels, **choisissez Acheter plus**.
    
- **Étapes suivantes** : après avoir attribué des licences de forfait d’appels à vos utilisateurs, vous devez obtenir vos numéros de téléphone pour votre organisation, puis affecter ces numéros aux personnes de votre organisation. Pour obtenir des instructions pas à pas, consultez [Configurer les forfaits d’appels](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Comment attribuer une licence Système téléphonique et forfait d’appels à un utilisateur

Les étapes sont identiques à l’attribution d’une licence Microsoft 365 ou Office 365. Consultez [Attribuer ou supprimer des licences pour Microsoft 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Comment affecter des licences Système téléphonique et Forfait d’appel en volume

1. Installez l' **Assistant de connexion Microsoft Online Services pour les informaticiens RTW**. Le module n'est pas installé ? Consultez [Microsoft Online Services Sign-In Assistant pour les professionnels de l’informatique RTW](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.

2. Installez le **module Windows Azure Active Directory**. Le module n'est pas installé ? Consultez [Gérer Azure AD à l’aide de Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) pour obtenir des instructions de téléchargement et la syntaxe de l’applet de commande.

3. Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

   Cet exemple affecte une **licence Entreprise E3**, ainsi qu'une licence **Système téléphonique** et **Forfait d’appels interne**.

   Le nom des licences ou des noms de produits dans le script est répertorié en italique (voir **Système téléphonique et les noms de produits ou références SKU du plan d’appel utilisés pour l’écriture de scripts**, après l’exemple).

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Système téléphonique et les noms de produits ou références SKU des plans d’appel utilisés pour l’écriture de scripts

|**Nom du produit**|**Référence**|
|:-----|:-----|
|Entreprise E5 (avec Système téléphonique)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Entreprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Entreprise E1  <br/> |STANDARDPACK  <br/> |
|Plan autonome 2 de Skype Entreprise Online  <br/> |MCOSTANDARD  <br/> |
|Système téléphonique  <br/> |MCOEV  <br/> |
|Plan d’appels internationaux  <br/> |MCOPSTN2  <br/> |
|Forfait d’appels nationaux (3000 min US / 1200 min plans de l’UE)  <br/> |MCOPSTN1  <br/> |
|Forfait d’appels nationaux (forfait d’appels de 120 minutes)  <br/> |MCOPSTN5  <br/> |
|Forfait d’appels nationaux (forfait d’appels de 240 minutes)  <br/> |MCOPSTN6  <br/> |
|Crédits de communication  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Audioconférence : Astuces et scripts pour l’attribution de licences

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Ce que vous devez savoir avant d’attribuer des licences Audioconférence

- **Fournisseur d’audioconférence tiers** : si une personne est déjà configurée pour utiliser un fournisseur d’audioconférence tiers, lorsque vous lui attribuez une licence **Audioconférence**, elle est modifiée pour utiliser Microsoft comme fournisseur d’audioconférence. Vous pouvez le remplacer par le fournisseur tiers.

- Étapes suivantes : après avoir attribué **Audioconférence** licences, vous devez affecter un fournisseur d’audioconférence. Voir [Affecter Microsoft comme fournisseur d'audioconférence].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Comment attribuer une licence Audioconférence à un utilisateur

Les étapes sont identiques à l’attribution d’une licence Microsoft 365 ou Office 365. Consultez [Attribuer ou supprimer des licences pour Microsoft 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Comment attribuer des licences Audioconférence en bloc

1. Téléchargez et installez [Microsoft Online Services Sign-In Assistant pour les professionnels de l’informatique RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Téléchargez et installez le **module Windows Azure Active Directory**. Pour connaître les instructions de téléchargement et la syntaxe des applets de commande, reportez-vous à la rubrique[Gestion d'Azure AD à l'aide de Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)).

   Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

   Le nom des licences ou des produits du script est répertorié dans le texte en italique. Consultez [Audioconférence noms de produits ou références SKU utilisés pour l’écriture de scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) pour tous les noms de produits.

   Cet exemple montre comment attribuer une licence Enterprise E3 avec une licence Audioconférence.

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Audioconférence noms de produits ou références SKU utilisés pour l’écriture de scripts
<a name="sku"> </a>

|**Nom du produit**|**Référence**|
|:-----|:-----|
|Audioconférence  <br/> |MCOMEETADV  <br/> |
|Plan autonome 2 de Skype Entreprise Online  <br/> |MCOSTANDARD  <br/> |
|Entreprise E1  <br/> |STANDARDPACK  <br/> |
|Entreprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Entreprise E5 (sans Audioconférence)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5 (avec Audioconférence)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Crédits de communication

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Ce que vous devez savoir avant d’attribuer des licences de crédits de communication

- **Enterprise clients E5** : même si des licences Enterprise E5 sont attribuées à vos utilisateurs, nous vous recommandons toujours de leur attribuer des licences **de crédits de communication**.
    
- **Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation. Pour obtenir des instructions pas à pas, consultez [Configurer les forfaits d’appels](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Comment attribuer une licence de crédits de communication à un utilisateur

Les étapes sont identiques à l’attribution d’une licence Microsoft 365 ou Office 365. Consultez [Attribuer ou supprimer des licences pour Microsoft 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Comment attribuer des licences de crédits de communication en bloc

Examinez l’exemple de script pour l’attribution de licences **Audioconférence**. Mettez-le à jour avec les informations relatives à l’attribution de licences **de crédits de communication** .

## <a name="related-topics"></a>Voir aussi
  
[Configurer des forfaits d'appels](/microsoftteams/set-up-calling-plans)
  
[Ajouter des fonds et gérer les Crédits de Communications](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
