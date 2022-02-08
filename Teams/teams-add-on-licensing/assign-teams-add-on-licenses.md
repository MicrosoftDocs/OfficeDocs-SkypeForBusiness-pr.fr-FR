---
title: Attribuer Teams licences de modules add-on aux utilisateurs
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Découvrez comment affecter des Teams de modules supplémentaires aux utilisateurs pour des fonctionnalités telles que l’audioconférence, les Système téléphonique et les plans d’appel.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0a83c30a4ea0fd4f907fd192b3f6dac455fc4d1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387592"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Attribuer Teams licences de modules add-on aux utilisateurs

Les licences de modules supplémentaires sont des licences Teams de fonctionnalités spécifiques telles que l’audioconférence, les Système téléphonique et les plans d’appel. Cet article décrit comment attribuer des licences d’ajout à des utilisateurs individuels et à de grands ensembles d’utilisateurs en bloc.

> [!NOTE]
> [Consultez Teams licences de modules](./microsoft-teams-add-on-licensing.md) Teams fonctionnalités disponibles avec les licences de modules supplémentaires. Vous trouverez également des informations sur les licences que vous devez acheter et sur la manière de les acheter (selon votre offre), afin que les utilisateurs disposent de fonctionnalités telles que l’audioconférence, les numéros gratuits et la possibilité d’appeler des numéros de téléphone en dehors de votre organisation. Après avoir décidé des fonctionnalités que vous souhaitez pour vos utilisateurs, attribuez-leur les licences.

Vous pouvez utiliser l’Centre d'administration Microsoft 365 ou PowerShell pour attribuer des licences aux utilisateurs de votre organisation. Pour gérer les licences, vous devez être administrateur global ou administrateur de gestion des utilisateurs.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Ce que vous devez savoir avant d’affecter des licences Système téléphonique, de plan d’appel et de crédits de communication

Avant de commencer, examinez les conditions suivantes :

- Si vous utilisez une connectivité réseau téléphonique public commuté (RST) sur site pour des utilisateurs hybrides, il vous suffit d’affecter Système téléphonique licence. N’affectez PAS de licence Forfait d’appels.

- En raison de la latence entre Microsoft 365 et Microsoft Teams, l’attribution d’un plan d’appels à un utilisateur peut prendre jusqu’à 24 heures après l’attribution d’une licence. Si l’utilisateur n’a pas accès à un plan d’appels au bout de 24 heures, contactez le support technique pour les produits pour les entreprises [- Aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Vous recevrez un message d’erreur si vous n’avez pas acheté le nombre correct de licences. Si vous avez besoin d’acheter d’autres licences de forfait d’appels, choisissez l’option d’achat.

- Même si vos utilisateurs reçoivent Enterprise licences E5, vous devez leur attribuer des [licences de crédits](../what-are-communications-credits.md) de communication s’ils souhaitent appeler ou recevoir des appels du réseau PSTN.

- Après avoir attribué des licences de plan d’appel ou de crédit de communication à vos utilisateurs, vous devrez obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs. Pour obtenir des instructions détaillées, voir [Configurer les forfaits d’appels](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Utilisation de la Centre d'administration Microsoft 365

Utilisez l’Centre d'administration Microsoft 365 pour attribuer des licences à des utilisateurs individuels ou à de petits ensembles d’utilisateurs à la fois. Vous attribuez des licences sur la page Licences (jusqu’à 20 utilisateurs à la fois) ou sur **la page** Utilisateurs actifs (jusqu’à 40 **utilisateurs** à la fois). La méthode que vous choisissez dépend de la gestion des licences de produits pour des utilisateurs spécifiques ou de la gestion des licences utilisateur de produits spécifiques.

Pour obtenir des instructions détaillées, voir [Attribuer des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users).

Si vous devez attribuer des licences à un grand nombre d’utilisateurs(par exemple, des centaines ou des milliers d’utilisateurs), utilisez PowerShell ou des licences basées sur les groupes [dans Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)  

## <a name="using-powershell"></a>Utiliser PowerShell

Utilisez PowerShell pour attribuer des licences aux utilisateurs en bloc.  Pour en savoir plus, voir [Attribuer des licences à des comptes d’utilisateurs avec PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Exemple de script

Voici un exemple de l’utilisation d’un script pour attribuer des licences à vos utilisateurs.

1. Installez la version 64 bits de [l’Assistant Microsoft Online Services de sign-in pour les professionnels de](/collaborate/connect-redirect?DownloadID=59185) l’informatique RTW.
2. Installez le module Microsoft Azure Active Directory de l’Windows PowerShell :
    1. Ouvrir une invite de commandes avec Windows PowerShell avec élévation de privilèges (exécuter Windows PowerShell en tant qu’administrateur).
    2. Exécutez la commande suivante :
        ```powershell
        Install-Module MSOnline
        ```
    3. Si vous êtes invité à installer le fournisseur de NuGet, tapez **O**, puis appuyez sur Entrée.
    4. Si vous êtes invité à installer le module à partir de PSGallery, tapez **O**, puis appuyez sur Entrée.
3. À l’invite de commandes Windows PowerShell, exécutez le script suivant pour attribuer des licences à vos utilisateurs, \<CompanyName:License> à savoir le nom de votre organisation et l’identificateur de la licence que vous voulez attribuer. Par exemple, litwareinc:MCOMEETADV.

    L’identificateur est différent du nom convivial de la licence. Par exemple, l’identificateur de l’audioconférence est MCOMEETADV. Pour en savoir plus, consultez [les noms des produits et les identificateurs de référence (SKU) pour les licences](#product-names-and-sku-identifiers-for-licensing).

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    Par exemple, pour affecter Microsoft 365 Entreprise 1 et Audioconférence, utilisez la syntaxe suivante dans le script :

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Pour affecter une licence Microsoft Business Voice (sans forfait d’appels), utilisez la syntaxe suivante dans le script :

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Noms de produits et identificateurs de référence SKU pour les licences

Voici une liste partielle des noms de produits et de leurs références SKU correspondantes que vous pouvez utiliser comme référence lorsque vous utilisez PowerShell pour gérer les licences Teams.

Pour plus d’informations, voir [Afficher les licences et services avec PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), les noms des produits et les identificateurs de plan de service pour les [licences](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) et la référence [SKU Éducation](../sku-reference-edu.md).

| Nom du produit| Référence |
|--------------|---------------|
| Microsoft Enterprise E5 (avec Système téléphonique) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (sans Audioconférence) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (avec audioconférence) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Microsoft Business Voice (Canada)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Royaume-Uni) | BUSINESS_VOICE  |
| Microsoft Business Voice (États-Unis) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (sans forfait d’appels) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (sans forfait d’appels) pour les États-Unis| BUSINESS_VOICE_DIRECTROUTING _MED |
| Audioconférence | MCOMEETADV | 
| Audioconférence - Paiement à la minute (paiement à la minute)</br>*Il est nécessaire de configurer et d’activer les crédits de communication.* | MCOMEETACPEA |
| Système téléphonique | MCOEV |
| Forfait d’appels nationaux et internationaux | MCOPSTN2 |
| Forfait d’appels nationaux (3 000 minutes par utilisateur/mois pour les états-Unis/les relations publiques/ca, 1 200 minutes par utilisateur/mois pour les pays de l’UE) | MCOPSTN1 |
| Forfait d’appels nationaux (120 minutes par utilisateur/mois pour chaque pays) </br>*Cette offre n’est pas disponible aux États-Unis.* | MCOPSTN5 |
| Forfait d’appels nationaux (240 minutes par utilisateur/mois pour chaque pays) </br>*Cette offre n’est pas disponible aux États-Unis.* | MCOPSTN6 |
| Crédits de communication | MCOPSTNPP |

## <a name="related-topics"></a>Voir aussi

- [Licences de module complémentaire Teams](./microsoft-teams-add-on-licensing.md)
- [Gérer l’accès des utilisateurs à Microsoft Teams](../user-access.md)
- [Afficher les licences et services avec PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Noms de produits et identificateurs de plans de service pour la gestion des licences](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Référence SKU pour l’éducation](../sku-reference-edu.md)
