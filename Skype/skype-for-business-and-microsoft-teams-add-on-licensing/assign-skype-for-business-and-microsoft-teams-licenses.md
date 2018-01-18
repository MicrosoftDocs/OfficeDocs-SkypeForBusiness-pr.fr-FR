---
title: "Affecter Skype pour les licences d’entreprise et Microsoft Teams"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: "Comment attribuer des Skype pour les licences commerciales pour système téléphonique, audioconférence, Plans d’appel et les crédits de Communications. "
ms.openlocfilehash: d60d637d3b904b98ee8600647c57062927fe9afc
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>Affecter Skype pour les licences d’entreprise et Microsoft Teams

Cet article vous donne des conseils sur l’attribution des licences aux utilisateurs pour des fonctionnalités telles que les conférences Audio, système téléphonique et Plans d’appel. Il fournit également des scripts d’attribution des licences en vrac.
  
 **IMPORTANT**: voir [Skype pour les licences de modules complémentaires professionnels et les équipes de Microsoft](skype-for-business-and-microsoft-teams-add-on-licensing.md) pour plus d’informations sur les licences dont vous avez besoin pour acheter et **Comment acheter** - en fonction de votre plan Office 365 - afin que les utilisateurs obtiennent la conférence Audio, numéros de téléphone gratuits, et la possibilité d’appeler des numéros de téléphone à l’extérieur de votre entreprise.
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Système et les Plans d’appel de téléphone : conseils et les scripts d’attribution des licences

Ce que vous devez savoir avant d’assigner l’audioconférence, système téléphonique et l’appel de planifier les licences

- **À l’aide de locaux connectivité RTPC pour les utilisateurs de hybride ?** Dans ce cas, il vous suffit d’attribuer une licence de **Système téléphonique** . Vous devez **pas** les attribuer un Plan d’appel.
    
- **Latence après l’affectation licences**: en raison de la latence entre Office 365 et Skype pour professionnels en ligne, il peut éventuellement prendre jusqu'à 24 heures à disposer d’un Plan d’appel après avoir attribué une licence pour un utilisateur. Si après 24 heures n’est pas affecté à l’utilisateur un Plan d’appel, veuillez [contacter le support technique pour les produits d’entreprise - aide de l’administrateur](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    
- **Messages d’erreur**: vous obtiendrez un message d’erreur si vous n’avez pas acheté le nombre approprié de licences. Si vous avez besoin acheter d’autres licences de l’appel de Plan, cliquez sur **acheter d’autres**.
    
- **Prochaines étapes**: après avoir affecté des licences de l’appel de Plan à vos utilisateurs, vous devrez obtenir vos numéros de téléphone pour votre organisation et ensuite affecter des numéros aux personnes de votre organisation. Pour obtenir des instructions pas à pas, consultez [définir les Plans d’appel](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Comment attribuer une licence de système téléphonique et le Plan de l’appel à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Comment attribuer des licences de système téléphonique et l’appel de Plan en vrac

1. Installez le **Microsoft Online Services - Assistant de connexion pour les professionnels de l’informatique RTW**. N’avez pas installé le module ? Voir l' [Assistant Microsoft Online Services-In pour RTW de professionnels de l’informatique](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.
    
2. Installer le **Module de Active Directory de Windows Azure.** N’avez pas installé le module ? Pour les instructions de téléchargement et de la syntaxe de l’applet de commande, voir la rubrique [Manage AD Azure à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .
    
3. Une fois les modules installés, utilisez l'invite de commandes Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :
    
  Cet exemple assigne une **licence d’entreprise E3** avec un **Système téléphonique** et une licence **Nationale appel de Plan** .
    
  Le nom des licences ou des noms de produit dans le script sont répertoriés dans le texte de l’italique (voir **système téléphonique et appel de planifier les noms de produit ou les références destinés script**, après l’exemple).
    
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Système téléphonique et les Plans d’appel de noms de produits ou de références destinés script

|**Nom du produit**|**Référence**|
|:-----|:-----|
|E5 d’entreprise (avec un système téléphonique)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Entreprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Entreprise E1  <br/> |STANDARDPACK  <br/> |
|Plan autonome 2 de Skype Entreprise Online  <br/> |MCOSTANDARD  <br/> |
|Système de téléphone  <br/> |MCOEV  <br/> |
|Plan d’appel international  <br/> |MCOPSTN2  <br/> |
|Forfait d'appels nationaux  <br/> |MCOPSTN1  <br/> |
|Crédits de communication  <br/> |MCOPSTNPP  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Téléconférence audio : Conseils et les scripts d’attribution des licences

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Ce que vous devez savoir avant d’attribuer des licences d’audioconférence

- **Fournisseur de conférence audio tiers**: si une personne est déjà configurée pour utiliser un fournisseur de conférence audio de tiers, lorsque vous les attribuez une licence de **Conférence Audio** , ils ne seront modifiés pour utiliser Microsoft comme la conférence audio fournisseur. Vous pouvez les modifier au fournisseur tiers.
    
- Étapes suivantes : après avoir affecté des licences de **Conférence Audio** , vous devez affecter un fournisseur de conférence audio. Effectuez l’une des actions suivantes :
    
  - [Affecter Microsoft comme le fournisseur de conférence audio](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - Ou, [attribuer un tiers que le fournisseur de conférence audio](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Comment attribuer une licence audioconférence à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Comment attribuer des licences d’Audio conférence en vrac

1. Téléchargez et installez [Microsoft Online Services Assistant de connexion pour RTW de professionnels de l’informatique](https://go.microsoft.com/fwlink/?LinkId=625123).
    
2. Téléchargez et installez le **module Windows Azure Active Directory**. Pour connaître les instructions de téléchargement et la syntaxe des applets de commande, reportez-vous à la rubrique[Gestion d'Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).
    
    Une fois les modules installés, utilisez l'invite de commandes Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :
    
    Le nom des licences ou des noms de produit dans le script sont répertoriés dans le texte de l’italique. Voir [les noms de produits Audio conférence ou des points de stock utilisés pour les scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) pour tous les noms de produits.
    
    Cet exemple assigne une licence Enterprise E3 avec une licence d’audioconférence.
    
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
|E5 Enterprise (sans audioconférence)  <br/> |ENTERPRISEPREMIUM_NONRPCCONF  <br/> |
|E5 d’entreprise (avec la fonction d’audioconférence)  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## <a name="communications-credits"></a>Crédits de communication

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Ce que vous devez savoir avant d’attribuer des licences de crédits de Communications

- **Les clients entreprise E5**: même si les utilisateurs sont affectés des licences Enterprise E5, nous recommandons quand même d’attribuer les licences de **Crédits de Communications** .
    
- **Prochaines étapes**: une fois que vous affectez ces licences, vous devrez obtenir vos numéros de téléphone pour votre organisation et ensuite affecter des numéros aux personnes de votre organisation. Pour obtenir des instructions pas à pas, consultez [définir les Plans d’appel](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Comment attribuer une licence de crédits de Communications à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Comment attribuer des licences de crédits de Communications en vrac

Examinons l’exemple de script pour l’attribution des licences **d’Audioconférence** . Mettre à jour avec les informations d’attribution de licences de **Crédits de Communications** .
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[Configurer des forfaits d'appels](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[Ajouter des fonds et la gestion des crédits de Communications](add-funds-and-manage-communications-credits.md)
  