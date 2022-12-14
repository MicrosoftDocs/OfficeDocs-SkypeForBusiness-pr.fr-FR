---
title: Attribuer des licences de module complémentaire Teams aux utilisateurs
author: DaniEASmith
ms.author: danismith
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Découvrez comment attribuer des licences de module complémentaire Teams à des utilisateurs pour des fonctionnalités telles que l’audioconférence, le système téléphonique et les forfaits d’appels.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60bde63ab3cc499c022ef2d23b669b543d6f5dd9
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392084"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Attribuer des licences de module complémentaire Teams aux utilisateurs

Les licences d’extension sont des licences pour des fonctionnalités Teams spécifiques telles que l’audioconférence, le système téléphonique et les forfaits d’appels. Cet article explique comment attribuer des licences de module complémentaire à des utilisateurs individuels et à de grands ensembles d’utilisateurs en bloc.

> [!NOTE]
> Consultez [Licences de module complémentaire Teams](./microsoft-teams-add-on-licensing.md) pour les fonctionnalités Teams disponibles avec les licences d’extension. Vous trouverez également des informations sur les licences que vous devez acheter et sur la façon de les acheter, en fonction de votre offre. Une fois que vous avez choisi les fonctionnalités que vous souhaitez pour vos utilisateurs, attribuez-leur les licences.

Vous pouvez utiliser le Centre d'administration Microsoft 365 ou PowerShell pour attribuer des licences aux utilisateurs de votre organisation. Vous devez être administrateur général ou administrateur de gestion des utilisateurs pour gérer les licences.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Ce que vous devez savoir avant d’attribuer des licences système téléphonique, forfait d’appels et crédits de communication

Avant de commencer, passez en revue les conditions suivantes :

- Si vous utilisez la connectivité RTC (Public Switched Telephone Network) locale pour les utilisateurs, vous devez uniquement attribuer une licence Téléphonie Teams standard. N’attribuez PAS de licence de forfait d’appels.

- Après avoir affecté un Microsoft forfait d’appels à un utilisateur, il peut prendre jusqu’à 24 heures avant qu’il voit le pavé de numérotation dans son client Teams. Si le pavé de numérotation n’est pas affiché dans les 24 heures, vérifiez sa [configuration](../dial-pad-configuration.md). Si nécessaire, vous pouvez également [contacter le support technique](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Un message d’erreur s’affiche si vous n’avez pas acheté le nombre correct de licences. Si vous avez besoin d’acheter d’autres licences de forfait d’appels, choisissez l’option pour en acheter davantage.

- Même si vos utilisateurs se voient attribuer des licences Enterprise E5, vous devez toujours les connecter au RTC. Vous disposez de plusieurs [options de connectivité RTC](../pstn-connectivity.md), notamment Plans d'appel de Microsoft Teams, routage direct ou connexion d’opérateur.

- Une fois que vous avez attribué des licences de forfait d’appels ou de crédits de communication à vos utilisateurs, vous devez obtenir des numéros de téléphone pour votre organisation, puis attribuer ces numéros aux utilisateurs. Pour obtenir des instructions pas à pas, consultez [Configurer des forfaits d’appels](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Utilisation du Centre d'administration Microsoft 365

Utilisez la Centre d'administration Microsoft 365 pour attribuer des licences à des utilisateurs individuels ou à de petits ensembles d’utilisateurs à la fois.

Vous attribuez des licences sur la page **Licences** (jusqu’à 20 utilisateurs à la fois) ou sur la page **Utilisateurs actifs** (jusqu’à 40 utilisateurs à la fois). La méthode que vous choisissez varie selon que vous souhaitez gérer les licences de produit pour des utilisateurs spécifiques ou gérer les licences utilisateur pour des produits spécifiques.

Pour obtenir des instructions pas à pas, consultez [Attribuer des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users).

Si vous avez besoin d’attribuer des licences à un grand nombre d’utilisateurs, tels que des centaines ou des milliers d’utilisateurs, utilisez PowerShell ou des [licences basées sur les groupes dans Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)

## <a name="using-powershell"></a>Utiliser PowerShell

Utilisez PowerShell pour attribuer des licences aux utilisateurs en bloc. Pour plus d’informations, consultez [Attribuer des licences à des comptes d’utilisateur avec PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Exemple de script

Voici un exemple d’utilisation d’un script pour attribuer des licences à vos utilisateurs.

1. [Installez le module Microsoft Azure Active Directory pour Windows PowerShell](/powershell/azure/active-directory/install-msonlinev1).
2. À l’invite de commandes Windows PowerShell, exécutez le script suivant pour attribuer des licences à vos utilisateurs, où `CompanyName:License` est le nom de votre organisation et l’identificateur de la licence que vous souhaitez attribuer. Par exemple, `litwareinc:MCOMEETADV`.

    L’identificateur est différent du nom convivial de la licence. Par exemple, l’identificateur de l’audioconférence est `MCOMEETADV`. Pour plus d’informations, consultez [Noms de produits et identificateurs de référence SKU pour les licences](#product-names-and-sku-identifiers-for-licensing).

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

    Par exemple, pour attribuer Microsoft 365 Entreprise licences E1 et Audioconférence, utilisez la syntaxe suivante dans le script :

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Pour attribuer une licence Téléphone Teams avec forfait d’appels, utilisez la syntaxe suivante dans le script :

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Noms de produits et identificateurs de référence SKU pour les licences

Voici une liste partielle des noms de produits et de leurs noms de composants de référence SKU correspondants que vous pouvez référencer lorsque vous utilisez PowerShell pour gérer les licences dans Teams.

Pour plus d’informations, consultez [Afficher les licences et les services avec PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Noms de produits et identificateurs de plan de service pour les licences](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) et [Référence SKU Éducation](../sku-reference-edu.md).

| Nom du produit| Référence |
|--------------|---------------|
| Microsoft Enterprise E5 (avec système téléphonique) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (sans audioconférence) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (avec audioconférence) | ENTERPRISEPREMIUM |
| Microsoft Entreprise E3 | ENTERPRISEPACK |
| Microsoft Entreprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Audioconférence | MCOMEETADV |
| Paiement à la minute de l’audioconférence (paiement à l’utilisation) Nécessite que les crédits de communication soient configurés et activés.* | MCOMEETACPEA |
| Téléphonie Teams standard | MCOEV |
| Téléphone Teams avec forfait d'appel | MCOTEAMS_ESSENTIALS |
| Plan d’appels internationaux | MCOPSTN2 |
| Forfait d’appels nationaux (3 000 minutes par utilisateur/mois pour les États-Unis/PR/CA, 1 200 minutes par utilisateur/mois pour les pays de l’UE) | MCOPSTN1 |
| Forfait d’appels nationaux (120 minutes par utilisateur/mois pour chaque pays) </br>*Ce plan n’est pas disponible dans le États-Unis.* | MCOPSTN5 |
| Forfait d’appels nationaux (240 minutes par utilisateur/mois pour chaque pays) </br>*Ce plan n’est pas disponible dans le États-Unis.* | MCOPSTN6 |
| Crédits de communication | MCOPSTNPP |
| Forfaits d’appels avec paiement à l’utilisation (pays zone 1) | MCOPSTN_PAYG_1 |
| Forfaits d’appels avec paiement à l’utilisation (pays zone 2) | MCOPSTN_PAYG_2 |
| Salles Microsoft Teams Basique | Microsoft_Teams_Rooms_Basic |
| Salles Microsoft Teams Basique sans audioconférence | Microsoft_Teams_Rooms_Basic_without_Audio_Conferencing |
| Salles Microsoft Teams Pro | Microsoft_Teams_Rooms_Pro |
| Salles Microsoft Teams Pro sans audioconférence | Microsoft_Teams_Rooms_Pro_without_Audio_Conferencing |
| appareils partagés Microsoft Teams | MCOCAP |
| Microsoft Teams Premium | Microsoft_Teams_Premium |

## <a name="related-content"></a>Contenu associé

- [Licences de module complémentaire Teams](./microsoft-teams-add-on-licensing.md)
- [Gérer l’accès des utilisateurs à Microsoft Teams](../user-access.md)
- [Afficher les licences et les services avec PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Noms de produits et identificateurs de plans de service pour la gestion des licences](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Informations de référence sur la référence SKU Éducation](../sku-reference-edu.md)
