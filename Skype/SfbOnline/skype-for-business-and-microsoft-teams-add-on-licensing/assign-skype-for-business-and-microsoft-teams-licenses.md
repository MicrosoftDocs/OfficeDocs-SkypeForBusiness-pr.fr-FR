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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: "Apprenez comment affecter des licences Skype Entreprise pour le Système téléphonique, l'Audioconférence, les Plans d'appel et les Crédits de communications. "
ms.openlocfilehash: f1fcece66976d303146a4e173f9e51892ad82282
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2019
ms.locfileid: "30120410"
---
# <a name="assign-skype-for-business-licenses"></a>Attribuer des licences Skype Entreprise

Cet article vous donne des conseils sur l’affectation de licences à vos utilisateurs pour des fonctionnalités telles que l'Audioconférence, le Système téléphonique et les Forfaits d’appels. Il vous fournit également des scripts pour affecter des licences en bloc.

> [!IMPORTANT]
> Voir [Skype pour les licences d’entreprise module complémentaire](skype-for-business-and-microsoft-teams-add-on-licensing.md) pour plus d’informations sur les licences, vous devez acheter et les **Comment acheter** les - selon votre Office 365 planifier - afin que les utilisateurs obtiennent l’audioconférence et la possibilité d’appeler des numéros de téléphone à l’extérieur de numéros gratuits votre entreprise.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences

Ce que vous devez connaître avant d’affecter des licences Audioconférence, Système téléphonique et Forfait d'appels

- **Vous utilisez la connectivité PSTN locale pour les utilisateurs hybrides ?** Dans ce cas, vous devez uniquement attribuer une licence de **Système téléphonique** . Vous devez **pas** assigner un Plan de l’appel.

- **Latence après l’attribution de licences**: en raison de la latence entre Skype pour Business Online et Office 365, il peut éventuellement prendre jusqu'à 24 heures pour un utilisateur à assigner un Plan d’appel une fois que vous attribuez une licence. Si après 24 heures avec l’utilisateur n’est pas affecté à un Plan de l’appel, veuillez [contacter le support technique pour les produits métiers : aide d’administration](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Messages d'erreur**: un message d'erreur s'affiche si vous n'avez pas acheté le nombre correct de licences. Si vous devez acheter des licences supplémentaires de planifier l’appel, cliquez sur **acheter plus**.
    
- **Étapes suivantes**: une fois que vous assignez un appel de planifier les licences à vos utilisateurs, vous devez obtenir vos numéros de téléphone pour votre organisation et l’assigner à ces numéros aux personnes de votre organisation. Pour obtenir des instructions pas à pas, consultez [configurer des Plans de l’appel](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Comment attribuer une licence de système téléphonique et planifier l’appel à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Comment affecter des licences Système téléphonique et Forfait d’appel en volume

1. Installez l' **Assistant de connexion Microsoft Online Services pour les informaticiens RTW**. Le module n'est pas installé ? Voir [Assistant Microsoft Online Services connexion pour les professionnels de l’informatique RTW](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.

2. Installez le **module Windows Azure Active Directory**. Le module n'est pas installé ? Pour des instructions de téléchargement et de la syntaxe de l’applet de commande, voir [Gérer Azure AD à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .

3. Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

   Cet exemple affecte une **licence Entreprise E3**, ainsi qu'une licence **Système téléphonique** et **Forfait d’appels interne**.

   Le nom des licences ou des noms de produits dans le script sont répertoriés dans le texte italique (voir **système téléphonique et appel de planifier les noms de produits ou SKU utilisé pour les scripts**, après l’exemple).

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Système téléphonique et appel des Plans de noms de produits ou des références destinés script

|**Nom du produit**|**Référence**|
|:-----|:-----|
|Entreprise E5 (avec Système téléphonique)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Entreprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Entreprise E1  <br/> |STANDARDPACK  <br/> |
|Plan autonome 2 de Skype Entreprise Online  <br/> |MCOSTANDARD  <br/> |
|Système téléphonique  <br/> |MCOEV  <br/> |
|Plan d’appels internationaux  <br/> |MCOPSTN2  <br/> |
|Forfait d'appels nationaux  <br/> |MCOPSTN1  <br/> |
|Crédits de communication  <br/> |MCOPSTNPP  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Services d’audioconférence : Conseils et des scripts pour l’attribution de licences

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Vous devez connaître avant d’attribution de licences d’audioconférence

- **Fournisseur de services d’audioconférence tiers**: si une personne est déjà configurée pour utiliser un fournisseur de services d’audioconférence tiers, lorsque vous leur attribuez une licence de **Conférence Audio** , ils ne seront modifiés pour utiliser Microsoft en tant que les services d’audioconférence fournisseur de services. Vous pouvez le remplacer par le fournisseur tiers.

- Étapes suivantes : une fois que vous affectez des licences de **Services d’audioconférence** , vous devez lui assigner un fournisseur de services d’audioconférence. Voir [Affecter Microsoft comme fournisseur d'audioconférence].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Comment attribuer une licence de conférence Audio à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Comment attribuer des licences d’audioconférence en bloc

1. Téléchargez et installez [Microsoft Online Services Assistant de connexion pour les professionnels de l’informatique RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Téléchargez et installez le **module Windows Azure Active Directory**. Pour connaître les instructions de téléchargement et la syntaxe des applets de commande, reportez-vous à la rubrique[Gestion d'Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).

    Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

    Le nom des licences ou des produits du script est répertorié dans le texte en italique. Voir [les noms de produits audioconférence ou SKU utilisé pour les scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) pour tous les noms de produits.

    Cet exemple attribue une licence entreprise E3 avec une licence d’audioconférence.

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Les noms de produits de conférence audio ou des références destinés script
<a name="sku"> </a>

|**Nom du produit**|**Référence**|
|:-----|:-----|
|Audioconférence  <br/> |MCOMEETADV  <br/> |
|Plan autonome 2 de Skype Entreprise Online  <br/> |MCOSTANDARD  <br/> |
|Entreprise E1  <br/> |STANDARDPACK  <br/> |
|Entreprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Entreprise E5 (sans Audioconférence)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Entreprise E5 (avec les services d’audioconférence)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Crédits de communication

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Vous devez connaître avant d’attribution de licences crédits Communications

- **Clients Enterprise E5**: même si vos utilisateurs sont affectées des licences Enterprise E5, nous vous recommandons d’affecter les licences **Crédits Communications** .
    
- **Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation. Pour obtenir des instructions pas à pas, consultez [configurer des Plans de l’appel](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Comment attribuer une licence Communications générique à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Comment attribuer des licences Communications crédits en bloc

Jetez un œil à l’exemple de script pour l’attribution de licences de **Conférence Audio** . Mettre à jour avec les informations de l’attribution de licences **Crédits Communications** .

## <a name="related-topics"></a>Rubriques connexes
  
[Configurer des forfaits d'appels](/microsoftteams/set-up-calling-plans)
  
[Ajouter des fonds et gérer les Crédits de Communications](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
