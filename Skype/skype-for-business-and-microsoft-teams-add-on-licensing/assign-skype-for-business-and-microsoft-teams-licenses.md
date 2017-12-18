---
title: "Attribuez Skype pour les entreprises et Microsoft Teams des licences"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/20/2017
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
description: "Learn how to assign Skype for Business licenses for Cloud PBX, PSTN Conferencing, PSTN Calling, and PSTN Consumption. "
---

# Attribuez Skype pour les entreprises et Microsoft Teams des licences

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Cet article vous donne des conseils sur l'attribution de licences à vos utilisateurs pour les fonctionnalités telles que les conférences Audio, système téléphonique et l'appel d'offre. Il fournit également des scripts permettant d'affecter des licences en bloc.
  
 **IMPORTANT**: voir[Skype pour les entreprises et Microsoft Teams module complémentaire licences](skype-for-business-and-microsoft-teams-add-on-licensing.md) pour plus d'informations sur les licences dont vous avez besoin pour acheter et **Comment acheter** - en fonction de votre plan Office 365 - afin que les utilisateurs reçoivent audioconférence, numéros gratuits, et la possibilité d'appeler des numéros de téléphone à l'extérieur de votre entreprise.
  
## Système et l'appel d'offre de téléphone : conseils et les scripts permettant d'affecter des licences

### Ce que vous devez savoir avant de l'assigner audioconférence, système téléphonique et appelant planifier des licences

- **IMPORTANT**: pour que l'option **Voix** apparaisse dans le volet de navigation gauche du Centre d'administration Skype Entreprise, vous devez d'abord acheter au moins une **licence Entreprise E5**, une licence de composant additionnel **Système téléphonique**, ou une licence de composant additionnel **Audioconférence**.
    
- **à l'aide de la connectivité PSTN en local pour les utilisateurs hybride ?** Si c'est le cas, il vous suffit d'attribuer une licence **Système téléphonique**. Vous devez attribuer **pas** un Plan de l'appel.
    
- **Latence après l'attribution de licences**: en raison de la latence entre Office 365 et Skype Entreprise Online, il peut prendre éventuellement jusqu'à 24 heures pour un utilisateur à affecter un Plan d'appel après avoir affecté une licence. Si après 24 heures, l'utilisateur n'est pas affecté un Plan de l'appel, veuillez[Contacter le support Office 365 pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    
- **Messages d'erreur**: vous obtenez un message d'erreur si vous n'avez pas acheté le nombre de licences correct. Si vous avez besoin acheter davantage de licences appelant planifier, choisissez **acheter d'autres**.
    
- **Étapes suivantes**: après avoir affecté appelant planifier des licences à vos utilisateurs, vous devrez obtenir vos numéros de téléphone pour votre organisation et puis affecter des numéros aux personnes de votre organisation. Pour obtenir des instructions étape par étape, voir[Configurer l'appel d'offre](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Comment attribuer une licence système téléphonique et planifier l'appel à un utilisateur

Les étapes sont identique à l'affectation d'une licence Office 365. Voir [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Comment attribuer des licences système téléphonique et planifier l'appel en bloc

1. Installez l' **Assistant Microsoft Online Services se connecter pour les informaticiens RTW**. Vous n'avez installé le module ? Voir[Assistant Microsoft Online Services se connecter pour RTW de professionnels de l'informatique](https://go.microsoft.com/fwlink/?LinkId=625123) pour la télécharger.
    
2. Installer le **Module Windows Azure Active Directory.** Vous n'avez installé le module ? Pour les instructions de téléchargement et la syntaxe de l'applet de commande, consultez[Gérer Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .
    
3. Une fois les modules installés, utilisez l'invite de commandes Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :
    
    Cet exemple attribue une **licence entreprise E3** ainsi qu'un **Système téléphonique** et d'une licence **Appels nationaux planifier de l'appel**.
    
    Le nom des licences ou les noms de produits dans le script sont répertoriés dans le texte en italique (voir **système téléphonique et appelant planifier les noms de produits ou références SKU utilisé pour l'écriture de script**, après l'exemple).
    
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
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and International Calling.
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 

  ```

### Les noms de produits système téléphonique et d'appel d'offre ou références SKU utilisé pour l'écriture de script

|**Nom du produit**|**Référence**|
|:-----|:-----|
|Entreprise E5 (avec le système téléphonique)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Entreprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Entreprise E1  <br/> |STANDARDPACK  <br/> |
|Plan autonome 2 de Skype Entreprise Online  <br/> |MCOSTANDARD  <br/> |
|Système téléphonique  <br/> |MCOEV  <br/> |
|Forfait d'appels internationaux  <br/> |MCOPSTN2  <br/> |
|Forfait d'appels nationaux  <br/> |MCOPSTN1  <br/> |
|Crédits de communication  <br/> |MCOPSTNPP  <br/> |
   
## Services d'audioconférence : Conseils et des scripts permettant d'affecter des licences

### Ce que vous devez savoir avant d'attribution de licences d'audioconférence

- **Fournisseur de services d'audioconférence tiers**: si une personne a déjà étée configurée pour utiliser un fournisseur de services d'audioconférence tiers, les affecter une licence de **Conférence Audio**, ils ne seront modifiés pour utiliser Microsoft comme les services d'audioconférence fournisseur. Vous pouvez modifier les revenir au fournisseur de services tiers.
    
- Étapes suivantes : une fois que vous attribuez des licences de **Services d'audioconférence**, vous devez affecter un fournisseur de services d'audioconférence. Effectuez l'une des opérations suivantes :
    
  - [Affecter Microsoft comme fournisseur de services d'audioconférence](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - Ou, [Affecter un tiers comme fournisseur de services d'audioconférence](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### Comment attribuer une licence de conférence Audio à un utilisateur

Les étapes sont identique à l'affectation d'une licence Office 365. Voir [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Comment attribuer des licences d'audioconférence en bloc

1. Téléchargez et installez [Assistant Microsoft Online Services se connecter pour RTW de professionnels de l'informatique](https://go.microsoft.com/fwlink/?LinkId=625123).
    
2. Téléchargez et installez le **Module Windows Azure Active Directory.** Pour les instructions de téléchargement et la syntaxe de l'applet de commande, consultez[Gérer Azure AD à l'aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .
    
    Une fois les modules installés, utilisez l'invite de commandes Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :
    
    Le nom des licences ou les noms de produits dans le script sont répertoriés dans le texte en italique. Voir [Les noms de produits de conférence audio ou références SKU utilisé pour l'écriture de script](fd41934d-f2eb-4a1b-89d8-32cb37702b33.md#sku) pour tous les noms de produits.
    
    Cet exemple attribue une licence entreprise E3 ainsi qu'une licence de conférence Audio.
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### Les noms de produits de conférence audio ou références SKU utilisé pour l'écriture de script
<a name="sku"> </a>

|**Nom du produit**|**Référence**|
|:-----|:-----|
|Audioconférence  <br/> |MCOMEETADV  <br/> |
|Plan autonome 2 de Skype Entreprise Online  <br/> |MCOSTANDARD  <br/> |
|Entreprise E1  <br/> | STANDARDPACK <br/> |
|Entreprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Entreprise E5 (sans services d'audioconférence)  <br/> |ENTERPRISEPREMIUM_NONRPCCONF  <br/> |
|Entreprise E5 (avec les services d'audioconférence)  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## Crédits de communication

### Ce que vous devez savoir avant d'attribution de licences Communications crédits

- **Clients entreprise E5**: même si vos utilisateurs sont affectées des licences Enterprise E5, nous recommandons que vous leur attribuer des licences **Crédits Communications**.
    
- **Étapes suivantes**: après avoir affecté ces licences, vous devrez obtenir vos numéros de téléphone pour votre organisation et puis affecter des numéros aux personnes de votre organisation. Pour obtenir des instructions étape par étape, voir[Configurer l'appel d'offre](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Comment attribuer une licence Communications crédits à un utilisateur

Les étapes sont identique à l'affectation d'une licence Office 365. Voir [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Comment attribuer des licences Communications crédits en bloc

Examinons l'exemple de script permettant d'affecter des licences **d'Audioconférence**. Mettre à jour avec les informations pour l'attribution de licences **Crédits Communications**.
  
## Articles connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Configurer l'appel d'offre](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[Ajouter des fonds et gérer des Communications crédits](add-funds-and-manage-communications-credits.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

