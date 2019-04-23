---
title: Assigner des licences Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: Découvrez comment attribuer des licences pour des fonctionnalités telles que la conférence Audio, système téléphonique, et des plans d’appel.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46966b7cad855ef6336b501564cde89dffd6b2b2
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993628"
---
# <a name="assign-microsoft-teams-licenses"></a>Affecter des licences Microsoft Teams

Vous pouvez attribuer des licences à vos utilisateurs de conférence Audio, système téléphonique et les Plans de l’appel. Cet article explique comment ajouter ces licences en bloc et pour un utilisateur individuel. 

> [!IMPORTANT]
> Voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) pour plus d’informations sur ce que vous devez acheter des licences et comment acheter, en fonction de votre Office 365 plan, afin que les utilisateurs obtiennent l’audioconférence, numéros gratuits et la possibilité d’appeler des numéros de téléphone à l’extérieur de votre entreprise.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences

Voici ce que vous devez connaître avant d’attribution de licences de conférence Audio, système téléphonique et planifier l’appel.

- **Vous utilisez la connectivité PSTN locale pour les utilisateurs hybrides ?** Dans ce cas, vous devez uniquement attribuer une licence de système téléphonique. Vous ne devez affecter un Plan de l’appel.

- **Latence après l’attribution de licences**: en raison de la latence entre Office 365 et Microsoft Teams, elle peut prendre jusqu'à 24 heures pour un utilisateur à assigner un Plan d’appel une fois que vous attribuez une licence. Si après 24 heures avec l’utilisateur n’est pas attribué à un Plan de l’appel, veuillez [contacter le support pour les produits métiers : aide d’administration](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Messages d'erreur**: un message d'erreur s'affiche si vous n'avez pas acheté le nombre correct de licences. Si vous devez acheter des licences supplémentaires de planifier l’appel, cliquez sur **acheter plus**.

- **Étapes suivantes**: une fois que vous assignez un appel de planifier les licences à vos utilisateurs, vous devez obtenir vos numéros de téléphone pour votre organisation et l’assigner à ces numéros aux personnes de votre organisation. Pour obtenir des instructions pas à pas, consultez [configurer des Plans de l’appel](set-up-calling-plans.md).

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Attribuer une licence de système téléphonique et planifier l’appel à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Attribution de licences système téléphonique et planifier l’appel en bloc

1. Installez l' Assistant de connexion Microsoft Online Services pour les informaticiens RTW. Le module n'est pas installé ? Voir [Assistant Microsoft Online Services connexion pour les professionnels de l’informatique RTW](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.

2. Installez le module Windows Azure Active Directory. Le module n'est pas installé ? Pour des instructions de téléchargement et de la syntaxe de l’applet de commande, voir [Gérer Azure AD à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .

3. Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

Cet exemple affecte une licence Entreprise E3, ainsi qu'une licence Système téléphonique et Forfait d’appels interne.

Le nom des licences ou des noms de produits dans le script sont répertoriés en italique (voir [système téléphonique et Plans de l’appel des noms de produits ou SKU utilisé pour les scripts](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), après l’exemple).

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Système téléphonique et appel des Plans de noms de produits ou des références destinés script

| Nom du produit | Référence |
|--------------|---------------|
| Entreprise E5 (avec Système téléphonique) | ENTERPRISEPREMIUM |
| Entreprise E3 | ENTERPRISEPACK | 
| Entreprise E1 | STANDARDPACK | 
| Système téléphonique | MCOEV |
| Plan d’appels internationaux & interne | MCOPSTN2 |
| Intérieur appelant planifier (3000 minutes par utilisateur/mois pour les ÉTATS-UNIS/PR/autorité de certification, 1200 minutes par utilisateur par mois pour l’Union européenne) | MCOPSTN1 |
| Intérieur appelant planifier (120 minutes par utilisateur par mois pour chaque pays) </br>*Remarque : ce plan n’est pas disponible aux États-Unis*. | MCOPSTN5 |
| Intérieur appelant planifier (240 minutes par utilisateur par mois pour chaque pays) </br>*Remarque : ce plan n’est pas disponible aux États-Unis*. | MCOPSTN6 |
| Crédits de communication | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Services d’audioconférence : conseils et des scripts pour l’attribution de licences

Voici ce que vous devez connaître avant d’attribution de licences de conférence Audio.

- **Fournisseur de services d’audioconférence tiers**: si une personne est déjà configurée pour utiliser un fournisseur de services d’audioconférence tiers, lorsque vous leur attribuez une licence de conférence Audio, ils ne seront modifiés pour utiliser Microsoft comme fournisseur de services d’audioconférence. Vous pouvez le remplacer par le fournisseur tiers.

- **Étapes suivantes**: une fois que vous affectez des licences de services d’audioconférence, vous devez lui assigner un fournisseur de services d’audioconférence. Voir [Assigner de Microsoft en tant que le fournisseur de services d’audioconférence](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>Attribuer une licence de conférence Audio à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>Attribution de licences de conférence Audio en bloc

1. Téléchargez et installez [Microsoft Online Services Assistant de connexion pour les professionnels de l’informatique RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Téléchargez et installez le module Windows Azure Active Directory. Pour des instructions de téléchargement et de la syntaxe de l’applet de commande, voir [Gérer Azure AD à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) .

Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

Le nom des licences ou des noms de produits dans le script sont répertoriés en italique. Voir [les noms de produits audioconférence ou SKU utilisé pour les scripts](#audio-conferencing-product-names-or-skus-used-for-scripting) pour tous les noms de produits.

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Les noms de produits de conférence audio ou des références de script

| Nom du produit | Référence |
|--------------|---------------|
| Services d’audioconférence (abonnement) | MCOMEETADV | 
| Audio conférence payer par Minute (retenues)</br>*Remarque : nécessite crédits Communications configuré et activé*. | MCOMEETACPEA |
| Entreprise E1 | STANDARDPACK | 
| Entreprise E3 | ENTERPRISEPACK |
| Entreprise E5 (sans Audioconférence) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Entreprise E5 (avec les services d’audioconférence) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>Crédits de communication

Voici ce que vous devez connaître avant d’attribution de licences crédits Communications.

- **Clients Enterprise E5**: même si vos utilisateurs sont affectées des licences Enterprise E5, nous vous recommandons d’affecter les licences crédits Communications.

- **Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation. Pour obtenir des instructions pas à pas, consultez [configurer des Plans de l’appel](set-up-calling-plans.md).

## <a name="assign-a-communications-credits-license-to-one-user"></a>Attribuer une licence de Communications générique à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-communications-credits-licenses-in-bulk"></a>Attribution de licences Communications crédits en bloc

Jetez un œil à l’exemple de script pour l’attribution de licences de conférence Audio. Mettre à jour avec les informations de l’attribution de licences crédits Communications.

## <a name="related-topics"></a>Rubriques connexes

[Configurer des forfaits d'appels](set-up-calling-plans.md)
</br>
[Ajouter des fonds et gérer les Crédits de Communications](add-funds-and-manage-communications-credits.md)
