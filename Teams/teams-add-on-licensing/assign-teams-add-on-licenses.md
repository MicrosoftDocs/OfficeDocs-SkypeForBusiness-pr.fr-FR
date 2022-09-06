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
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Découvrez comment attribuer des licences de module complémentaire Teams aux utilisateurs pour des fonctionnalités telles que l’audioconférence, le système téléphonique et les forfaits d’appels.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c10ba390d906681434ae56272e4f112911bfcff
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606053"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Attribuer des licences de module complémentaire Teams aux utilisateurs

Les licences de module complémentaire sont des licences pour des fonctionnalités Teams spécifiques telles que l’audioconférence, le système téléphonique et les forfaits d’appels. Cet article explique comment attribuer des licences de module complémentaire à des utilisateurs individuels et à de grands ensembles d’utilisateurs en bloc.

> [!NOTE]
> Consultez [les licences de module complémentaire Teams](./microsoft-teams-add-on-licensing.md) pour les fonctionnalités Teams disponibles avec des licences de module complémentaire. Vous trouverez également des informations sur les licences que vous devez acheter et sur la façon de les acheter, en fonction de votre plan. Une fois que vous avez choisi les fonctionnalités souhaitées pour vos utilisateurs, attribuez-leur les licences.

Vous pouvez utiliser le Centre d'administration Microsoft 365 ou PowerShell pour attribuer des licences aux utilisateurs de votre organisation. Vous devez être administrateur général ou administrateur de gestion des utilisateurs pour gérer les licences.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Ce que vous devez savoir avant d’attribuer des licences système téléphonique, forfait d’appels et crédits de communication

Avant de commencer, passez en revue les exigences suivantes :

- Si vous utilisez la connectivité RTC (Public Switched Telephone Network) locale pour les utilisateurs, vous n’avez qu’à attribuer une licence Téléphonie Teams standard. N’affectez PAS de licence de plan d’appel.

- Après avoir affecté un plan d’appels Microsoft à un utilisateur, il peut prendre jusqu’à 24 heures avant qu’il ne voie le pavé de numérotation dans son client Teams. Si le pavé de numérotation n’est pas affiché dans les 24 heures, vérifiez la configuration de votre [pavé de numérotation](../dial-pad-configuration.md). Si nécessaire, vous pouvez également [contacter le support technique](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Un message d’erreur s’affiche si vous n’avez pas acheté le nombre correct de licences. Si vous avez besoin d’acheter d’autres licences de forfait d’appels, choisissez l’option d’en acheter davantage.

- Même si des licences Enterprise E5 sont attribuées à vos utilisateurs, vous devez toujours les connecter au RTC. Vous disposez de plusieurs [options de connectivité RTC](../pstn-connectivity.md), notamment Plans d'appel de Microsoft Teams, le routage direct ou Operator Connect.

- Une fois que vous avez attribué des licences de forfait d’appels ou de crédits de communication à vos utilisateurs, vous devez obtenir les numéros de téléphone de votre organisation, puis affecter ces numéros aux utilisateurs. Pour obtenir des instructions pas à pas, consultez [Configurer les forfaits d’appels](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Utilisation de la Centre d'administration Microsoft 365

Utilisez le Centre d'administration Microsoft 365 pour attribuer des licences à des utilisateurs individuels ou à de petits ensembles d’utilisateurs à la fois.

Vous attribuez des licences sur la page **Licences** (jusqu’à 20 utilisateurs à la fois) ou sur la page **Utilisateurs actifs** (jusqu’à 40 utilisateurs à la fois). La méthode que vous choisissez varie selon que vous souhaitez gérer les licences de produit pour des utilisateurs spécifiques ou gérer les licences utilisateur pour des produits spécifiques.

Pour obtenir des instructions pas à pas, consultez [Affecter des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users).

Si vous devez attribuer des licences à un grand nombre d’utilisateurs, tels que des centaines ou des milliers d’utilisateurs, utilisez PowerShell ou [des licences basées sur des groupes dans Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign)

## <a name="using-powershell"></a>Utiliser PowerShell

Utilisez PowerShell pour attribuer des licences aux utilisateurs en bloc. Pour plus d’informations, consultez [Affecter des licences à des comptes d’utilisateur avec PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Exemple de script

Voici un exemple d’utilisation d’un script pour attribuer des licences à vos utilisateurs.

1. [Installez le module Microsoft Azure Active Directory pour Windows PowerShell](/powershell/azure/active-directory/install-msonlinev1).
2. À l’invite de commandes Windows PowerShell, exécutez le script suivant pour attribuer des licences à vos utilisateurs, où `CompanyName:License` se trouvent le nom de votre organisation et l’identificateur de la licence que vous souhaitez attribuer. Par exemple, `litwareinc:MCOMEETADV`.

    L’identificateur est différent du nom convivial de la licence. Par exemple, l’identificateur de l’audioconférence est `MCOMEETADV`. Pour plus d’informations, consultez [les noms de produits et les identificateurs de référence SKU pour la gestion des licences](#product-names-and-sku-identifiers-for-licensing).

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

    Par exemple, pour attribuer Microsoft 365 Entreprise licences E1 et audioconférence, utilisez la syntaxe suivante dans le script :

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Pour affecter un téléphone Teams avec licence forfait d’appels, utilisez la syntaxe suivante dans le script :

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Noms de produits et identificateurs de référence SKU pour la gestion des licences

Voici une liste partielle des noms de produits et de leurs noms de composants de référence SKU correspondants que vous pouvez référencer lorsque vous utilisez PowerShell pour gérer les licences dans Teams.

Pour plus d’informations, consultez [Afficher les licences et les services avec PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [les noms de produits et les identificateurs de plan de service pour les licences](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) et les [références SKU Éducation](../sku-reference-edu.md).

| Nom du produit| Référence |
|--------------|---------------|
| Microsoft Enterprise E5 (avec système téléphonique) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (sans audioconférence) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (avec audioconférence) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | Spb|
| Audioconférence | MCOMEETADV |
| Paiement par minute de l’audioconférence (paiement à l’utilisation) Nécessite la configuration et l’activation des crédits de communication.* | MCOMEETACPEA |
| Téléphonie Teams standard | MCOEV |
| Téléphone Teams avec forfait d'appel | MCOTEAMS_ESSENTIALS |
| Plan d’appels internationaux | MCOPSTN2 |
| Forfait d’appels nationaux (3 000 minutes par utilisateur/mois pour les États-Unis/PR/CA, 1 200 minutes par utilisateur/mois pour les pays de l’UE) | MCOPSTN1 |
| Forfait d’appels nationaux (120 minutes par utilisateur/mois pour chaque pays) </br>*Ce plan n’est pas disponible dans le États-Unis.* | MCOPSTN5 |
| Forfait d’appels nationaux (240 minutes par utilisateur/mois pour chaque pays) </br>*Ce plan n’est pas disponible dans le États-Unis.* | MCOPSTN6 |
| Crédits de communication | MCOPSTNPP |
| Forfaits d’appels avec paiement à l’utilisation (pays de la zone 1) | MCOPSTN_PAYG_1 |
| Forfaits d’appels avec paiement à l’utilisation (pays de la zone 2) | MCOPSTN_PAYG_2 |
| Salles Microsoft Teams De base | Microsoft_Teams_Rooms_Basic |
| Salles Microsoft Teams De base sans audioconférence | Microsoft_Teams_Rooms_Basic_without_Audio_Conferencing |
| Salles Microsoft Teams Pro | Microsoft_Teams_Rooms_Pro |
| Salles Microsoft Teams Pro sans audioconférence | Microsoft_Teams_Rooms_Pro_without_Audio_Conferencing |

## <a name="related-content"></a>Contenu associé

- [Licences de module complémentaire Teams](./microsoft-teams-add-on-licensing.md)
- [Gérer l’accès des utilisateurs à Microsoft Teams](../user-access.md)
- [Afficher les licences et les services avec PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Noms de produits et identificateurs de plans de service pour la gestion des licences](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Informations de référence sur la référence SKU Éducation](../sku-reference-edu.md)
