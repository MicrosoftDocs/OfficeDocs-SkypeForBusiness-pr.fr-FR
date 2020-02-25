---
title: Assigner des licences Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Découvrez comment attribuer des licences aux fonctionnalités telles que l’audioconférence, le système téléphonique et les offres d’appels.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9d75201b7be82337898d4e9fe4feafb4de1155a9
ms.sourcegitcommit: 73518a589db1a9883fc97827f0ddb9132995fbfa
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42236834"
---
# <a name="assign-microsoft-teams-licenses"></a>Attribution de licences Microsoft teams

Vous pouvez attribuer des licences à vos utilisateurs pour des fonctionnalités telles que l’audioconférence, le système téléphonique et les offres d’appels. Cet article explique comment ajouter ces licences en bloc et pour un utilisateur individuel. 

> [!IMPORTANT]
> Pour plus d’informations sur les licences que vous devez acheter et sur la manière de les acheter, reportez-vous à la rubrique [licences de module complémentaire de Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) , en fonction de votre offre Office 365, afin que les utilisateurs obtiennent des conférences audio, des numéros gratuits et la possibilité d’appeler des numéros de téléphone hors de votre entreprise.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Système téléphonique et Forfaits d’appels : conseils et scripts pour l’attribution des licences

Voici ce que vous devez savoir avant d’affecter des licences de conférence audio, de système téléphonique et de plan d’appel.

- **Vous utilisez la connectivité PSTN locale pour les utilisateurs hybrides ?** Si tel est le cas, il vous suffit d’affecter une licence de système téléphonique. Vous ne devez pas affecter de plan d’appels.

- **Latence après l’attribution de licences**: en raison de la latence entre Office 365 et Microsoft Teams, un utilisateur peut être tenu de 24 heures pour pouvoir affecter un plan d’appels après que vous lui avez affecté une licence. Si, au bout de 24 heures, l’utilisateur ne dispose pas d’un plan d’appels, [Contactez le support technique pour les produits destinés aux entreprises-aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Messages d'erreur**: un message d'erreur s'affiche si vous n'avez pas acheté le nombre correct de licences. Si vous avez besoin d’acheter d’autres licences de plan d’appel, sélectionnez **acheter plus**.

- **Étapes**suivantes : une fois que vous avez attribué des licences de plan d’appel aux utilisateurs, vous devez obtenir vos numéros de téléphone pour votre organisation, puis affecter ces numéros aux personnes de votre organisation. Pour obtenir des instructions détaillées, consultez la rubrique [configurer les offres d’appels](set-up-calling-plans.md).

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Attribution d’un système téléphonique et d’une licence de plan d’appel à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Affectation de licences de système téléphonique et de plan d’appel en bloc

1. Installez l' Assistant de connexion Microsoft Online Services pour les informaticiens RTW. Le module n'est pas installé ? Voir [Assistant de connexion de Microsoft Online Services pour les informaticiens RTW](https://go.microsoft.com/fwlink/?LinkId=625123) pour le télécharger.

2. Installez le module Windows Azure Active Directory. Le module n'est pas installé ? Pour plus d’informations sur le téléchargement et la syntaxe de l’applet de cmdlet, voir [gérer Azure ad à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628)

3. Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

Cet exemple affecte une licence Entreprise E3, ainsi qu'une licence Système téléphonique et Forfait d’appels interne.

Le nom des licences ou des noms de produits figurant dans le script est affiché en italique (voir [système téléphonique et plans d’appel, noms de produits ou références SKU utilisés pour l’écriture de scripts](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), après l’exemple).

```powershell
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

## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Système téléphonique et offres d’appels noms de produits ou UGS utilisés pour l’écriture de scripts

| Nom du produit | Référence |
|--------------|---------------|
| Entreprise E5 (avec Système téléphonique) | ENTERPRISEPREMIUM |
| Entreprise E3 | ENTERPRISEPACK | 
| Entreprise E1 | STANDARDPACK | 
| Système téléphonique | MCOEV |
| Forfait d’appels internationaux & international | MCOPSTN2 |
| Forfait d’appels nationaux (3000 minutes par utilisateur/par mois pour les États-Unis/PR/CA, 1200 minutes par utilisateur et par mois pour les pays de l’Union européenne) | MCOPSTN1 |
| Forfait d’appels nationaux (120 minutes par utilisateur/mois pour chaque pays) </br>*Remarque : ce plan n’est pas disponible aux États-Unis*. | MCOPSTN5 |
| Forfait d’appels nationaux (240 minutes par utilisateur/mois pour chaque pays) </br>*Remarque : ce plan n’est pas disponible aux États-Unis*. | MCOPSTN6 |
| Crédits de communication | MCOPSTNPP | 

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>Affectation d’une licence de conférence audio à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>Affectation de licences de conférence audio en bloc

1. Téléchargez et installez [l’Assistant de connexion de Microsoft Online Services pour les informaticiens RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Téléchargez et installez le module Windows Azure Active Directory. Pour plus d’informations sur le téléchargement et la syntaxe de l’applet de cmdlet, voir [gérer Azure ad à l’aide de Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628)

Une fois les modules installés, utilisez l'invite de commande Windows PowerShell et la syntaxe suivante pour affecter les licences à vos utilisateurs :

Le nom des licences ou des noms de produits figurant dans le script est affiché en italique. Voir les noms des produits de l’audioconférence pour l' [écriture de scripts](#audio-conferencing-product-names-or-skus-used-for-scripting) pour l’ensemble des noms de produits.

Cet exemple affecte une licence entreprise E3, ainsi qu’une licence de conférence audio.

```powershell
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

## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Noms des produits de conférence audio ou références (SKU) utilisés pour l’écriture de scripts

| Nom du produit | Référence |
|--------------|---------------|
| Audioconférence (abonnement) | MCOMEETADV | 
| Payez à la minute (payer au fur et à mesure)</br>*Remarque : la configuration et l’activation de crédits de communication sont nécessaires*. | MCOMEETACPEA |
| Entreprise E1 | STANDARDPACK | 
| Entreprise E3 | ENTERPRISEPACK |
| Entreprise E5 (sans Audioconférence) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Entreprise E5 (avec audioconférence) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>Crédits de communication

Voici ce que vous devez savoir avant d’affecter des licences de crédits de communication.

- **Clients entreprise E5**: même si des licences entreprise E5 ont été affectées à vos utilisateurs, nous vous conseillons de leur affecter des licences de crédits de communication.

- **Prochaines étapes**: après avoir affecté ces licences, vous devrez également obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs dans votre organisation. Pour obtenir des instructions détaillées, consultez la rubrique [configurer les offres d’appels](set-up-calling-plans.md).

## <a name="assign-a-communications-credits-license-to-one-user"></a>Affectation d’une licence de crédits de communication à un utilisateur

Les étapes sont les mêmes que pour affecter un licence Office 365. Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-communications-credits-licenses-in-bulk"></a>Affectation de licences de crédits de communication en bloc

Jetez un coup d’œil à l’exemple de script permettant d’affecter des licences de conférence audio. Mettez-le à jour avec les informations relatives à l’affectation de licences de crédits de communication.

## <a name="related-topics"></a>Rubriques connexes

[Configurer des forfaits d'appels](set-up-calling-plans.md)
</br>
[Ajouter des fonds et gérer les Crédits de Communications](add-funds-and-manage-communications-credits.md)
