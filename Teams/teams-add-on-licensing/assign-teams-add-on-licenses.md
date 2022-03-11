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
description: Découvrez comment affecter des Teams de modules à des utilisateurs pour des fonctionnalités telles que l’audioconférence, les Système téléphonique et les plans d’appel.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8668b31caf0dc10e8585a518a9c4c9be890d1d0d
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435838"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Attribuer Teams licences de modules add-on aux utilisateurs

Les licences de modules add-on sont des licences Teams fonctionnalités spécifiques telles que l’audioconférence, la Système téléphonique et les plans d’appel. Cet article explique comment attribuer des licences d’ajout à des utilisateurs individuels et à de grands ensembles d’utilisateurs en bloc.

> [!NOTE]
> [Consultez Teams licences de modules](./microsoft-teams-add-on-licensing.md) Teams fonctionnalités disponibles avec les licences de modules ajoutés. Selon votre offre, vous trouverez également des informations sur les licences à acheter et leur achat. Après avoir décidé des fonctionnalités que vous souhaitez pour vos utilisateurs, attribuez-leur les licences.

Vous pouvez utiliser l’Centre d'administration Microsoft 365 powershell pour attribuer des licences aux utilisateurs de votre organisation. Pour gérer les licences, vous devez être administrateur global ou administrateur de gestion des utilisateurs.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Ce que vous devez savoir avant d’affecter Système téléphonique licences pour le plan d’appel et les crédits de communication

Avant de commencer, examinez les conditions suivantes :

- Si vous utilisez une connectivité réseau téléphonique public commuté (RST) sur site pour les utilisateurs, il vous suffit d’affecter une licence Teams Téléphone Standard. N’affectez PAS de licence Forfait d’appels.

- Après avoir attribué un plan d’appel Microsoft à un utilisateur, jusqu’à 24 heures peuvent s’ouvrir avant que le pavé de numérotation ne s’Teams client. Si le pavé de numérotation n’est pas affiché dans les 24 heures, vérifiez la [configuration du pavé de numérotation](../dial-pad-configuration.md). Si nécessaire, vous pouvez également [contacter le support.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- Vous recevrez un message d’erreur si vous n’avez pas acheté le nombre correct de licences. Si vous avez besoin d’acheter d’autres licences de forfait d’appels, choisissez l’option d’achat.

- Même si vos utilisateurs ont Enterprise licences E5, vous devez quand même les connecter au réseau PSTN. Vous avez plusieurs [options](../pstn-connectivity.md) de connectivité R MICROSOFT TEAMS, notamment des plans d’appel, un routage direct ou des Connecter.

- Après avoir attribué des licences de plan d’appel ou de crédit de communication à vos utilisateurs, vous devrez obtenir les numéros de téléphone pour votre organisation, puis les affecter aux utilisateurs. Pour obtenir des instructions détaillées, voir [Configurer les forfaits d’appels](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Utilisation de la Centre d'administration Microsoft 365

Utilisez l’Centre d'administration Microsoft 365 pour attribuer des licences à des utilisateurs individuels ou à de petits ensembles d’utilisateurs à la fois.

Vous attribuez des licences sur la page Licences (jusqu’à 20 utilisateurs à la fois) ou sur **la page** Utilisateurs actifs (jusqu’à 40 **utilisateurs** à la fois). La méthode que vous choisissez dépend de la gestion des licences de produits pour des utilisateurs spécifiques ou de la gestion des licences utilisateur de produits spécifiques.

Pour obtenir des instructions détaillées, voir [Attribuer des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users).

Si vous devez attribuer des licences à un grand nombre d’utilisateurs(par exemple, des centaines ou des milliers d’utilisateurs), utilisez PowerShell ou des licences basées sur les groupes [dans Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)

## <a name="using-powershell"></a>Utiliser PowerShell

Utilisez PowerShell pour attribuer des licences aux utilisateurs en bloc. Pour en savoir plus, voir [Attribuer des licences à des comptes d’utilisateurs avec PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Exemple de script

Voici un exemple de l’utilisation d’un script pour attribuer des licences à vos utilisateurs.

1. Installez la version 64 bits de [l’Assistant Microsoft Online Services de sign-in pour les professionnels de](/collaborate/connect-redirect?DownloadID=59185) l’informatique RTW.
2. Installez le module Microsoft Azure Active Directory de l’Windows PowerShell :
    1. Ouvrez une invite de commandes avec Windows PowerShell avec élévation de privilèges (exécutez Windows PowerShell en tant qu’administrateur).
    2. Exécutez la commande suivante :
        ```powershell
        Install-Module MSOnline
        ```
    3. Si vous êtes invité à installer le fournisseur de NuGet, tapez **O**, puis appuyez sur Entrée.
    4. Si vous êtes invité à installer le module à partir de PSGallery, tapez **O**, puis appuyez sur Entrée.
3. À l’invite Windows PowerShell, exécutez le script suivant pour attribuer des licences à vos utilisateurs, \<CompanyName:License> à savoir le nom de votre organisation et l’identificateur de la licence que vous voulez attribuer. Par exemple, litwareinc:MCOMEETADV.

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

    Par exemple, pour affecter Microsoft 365 Entreprise licences E1 et Audioconférence, utilisez la syntaxe suivante dans le script :

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Pour affecter une Teams Téléphone licence Forfait d’appels, utilisez la syntaxe suivante dans le script :

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Noms de produits et identificateurs de référence SKU pour les licences

Voici une liste partielle des noms de produits et de leurs références SKU correspondantes que vous pouvez référencer lorsque vous utilisez PowerShell pour gérer les licences Teams.

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
| Audioconférence | MCOMEETADV |
| L’audioconférence avec paiement à la minute (paiement à la minute) nécessite la mise en place et l’activé des crédits de communication.* | MCOMEETACPEA |
| Teams Téléphone Standard | MCOEV |
| Téléphone Teams avec forfait d'appel | MCOTEAMS_ESSENTIALS |
| Forfait d’appels nationaux et internationaux | MCOPSTN2 |
| Forfait d’appels nationaux (3 000 minutes par utilisateur/mois pour les états-Unis/les relations publiques/ca, 1 200 minutes par utilisateur/mois pour les pays de l’UE) | MCOPSTN1 |
| Forfait d’appels nationaux (120 minutes par utilisateur/mois pour chaque pays) </br>*Cette offre n’est pas disponible aux États-Unis.* | MCOPSTN5 |
| Forfait d’appels nationaux (240 minutes par utilisateur/mois pour chaque pays) </br>*Cette offre n’est pas disponible aux États-Unis.* | MCOPSTN6 |
| Crédits de communication | MCOPSTNPP |

## <a name="related-content"></a>Contenu associé

- [Licences de module complémentaire Teams](./microsoft-teams-add-on-licensing.md)
- [Gérer l’accès des utilisateurs à Microsoft Teams](../user-access.md)
- [Afficher les licences et services avec PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Noms de produits et identificateurs de plans de service pour la gestion des licences](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Référence SKU pour l’éducation](../sku-reference-edu.md)
