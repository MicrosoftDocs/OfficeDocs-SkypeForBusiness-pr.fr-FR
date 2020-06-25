---
title: Attribution de licences de complément d’équipe aux utilisateurs
author: LanaChin
ms.author: v-lanac
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
description: Découvrez comment affecter des licences de complément d’équipe aux utilisateurs pour des fonctionnalités telles que l’audioconférence, le système téléphonique et les offres d’appels.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7faaf2e65330aafd809872ed19b5f2f16afc668
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868581"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Attribution de licences de complément d’équipe aux utilisateurs

Les licences de compléments sont des licences pour des fonctionnalités d’équipe spécifiques, telles que les conférences audio, le système téléphonique et les offres d’appels. Cet article décrit comment affecter des licences de complément à des utilisateurs individuels et à des groupes de personnes volumineux en bloc.

> [!NOTE]
> Pour plus d’options, voir [licences de complément teams](microsoft-teams-add-on-licensing.md) disponibles avec des licences de compléments. Vous trouverez également des informations sur les licences que vous devez acheter et sur la manière de les acheter (en fonction de votre plan), de sorte que les utilisateurs puissent obtenir des fonctions telles que les services d’audioconférence, les numéros gratuits et la possibilité d’appeler des numéros de téléphone en dehors de votre organisation. Une fois que vous avez décidé des fonctionnalités que vous voulez pour vos utilisateurs, attribuez-leur des licences.

Vous pouvez utiliser le centre d’administration 365 Microsoft ou PowerShell pour attribuer des licences aux utilisateurs de votre organisation. Vous devez être un administrateur général ou un administrateur de gestion des utilisateurs pour gérer les licences.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Ce que vous devez savoir avant d’affecter des licences de système téléphonique, de plan d’appels et de crédits de communication

Avant de commencer, vérifiez les points suivants :

- Si vous utilisez une connectivité de réseau téléphonique commuté (PSTN) locale pour les utilisateurs hybrides, il vous suffit d’affecter une licence de système téléphonique. Ne pas affecter de licence de plan d’appel.

- En raison de la latence entre Microsoft 365 et Microsoft Teams, il est possible que l’utilisateur dispose d’une offre de 24 heures après avoir affecté une licence. Si l’utilisateur ne dispose pas d’un plan d’appels après 24 heures, [Contactez le support technique des produits pour les entreprises-aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Vous recevez un message d’erreur si vous n’avez pas acheté le nombre de licences correct. Si vous avez besoin d’acheter d’autres licences de plan d’appel, choisissez l’option d’achat.

- Même si des licences entreprise E5 ont été affectées à vos utilisateurs, vous devez quand [même affecter des licences aux destinataires](../what-are-communications-credits.md) de vos appels pour passer ou recevoir des appels à partir du RTC.

- Dès lors que vous attribuez des licences à vos utilisateurs, vous devez obtenir des numéros de téléphone pour votre organisation, puis affecter ces numéros aux utilisateurs. Pour obtenir des instructions détaillées, consultez la rubrique [configurer les offres d’appels](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Utilisation du centre d’administration Microsoft 365

Utilisez le centre d’administration Microsoft 365 pour attribuer des licences à des utilisateurs individuels ou à des groupes d’utilisateurs de petites entreprises à la fois. Vous pouvez attribuer des licences dans la page **licences** (pour 20 utilisateurs maximum à la fois) ou la page **utilisateurs actifs** . La méthode que vous choisissez dépend de la façon dont vous souhaitez gérer les licences de produits pour des utilisateurs spécifiques ou gérer des licences utilisateur pour des produits spécifiques.

Pour obtenir des instructions détaillées, voir attribuer des [licences à des utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

Si vous devez attribuer des licences à un grand nombre d’utilisateurs, par exemple des centaines ou des milliers d’utilisateurs, utilisez PowerShell ou des [licences basées sur le groupe dans Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).  

## <a name="using-powershell"></a>Utiliser PowerShell

Utiliser PowerShell pour attribuer des licences en bloc aux utilisateurs.  Pour en savoir plus, voir [attribuer des licences à des comptes d’utilisateurs avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Exemple de script

Voici un exemple illustrant comment utiliser un script pour attribuer des licences à vos utilisateurs.

1. Installez la version 64 bits de l' [Assistant de connexion de Microsoft Online Services pour les informaticiens RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
2. Installez le module Microsoft Azure Active Directory pour Windows PowerShell :
    1. Ouvrez une invite de commandes Windows PowerShell avec élévation de privilèges (exécutez Windows PowerShell en tant qu’administrateur).
    2. Exécutez la commande suivante :
        ```powershell
        Install-Module MSOnline
        ```
    3. Si vous êtes invité à installer le fournisseur NuGet, tapez **o**, puis appuyez sur entrée.
    4. Si vous êtes invité à installer le module à partir de PSGallery, tapez **Y**, puis appuyez sur entrée.
3. Dans l’invite de commandes Windows PowerShell, exécutez le script suivant pour attribuer des licences à vos utilisateurs, où \<CompanyName:License> est le nom de votre organisation et l’identificateur de la licence que vous voulez attribuer. Par exemple, litwareinc : MCOMEETADV.

    L’identificateur est différent du nom convivial de la licence. Par exemple, l’identificateur pour audioconférence est MCOMEETADV. Pour en savoir plus, consultez la rubrique [noms des produits et identificateurs UGS pour les licences](#product-names-and-sku-identifiers-for-licensing).

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

    Par exemple, pour attribuer des licences Microsoft 365 entreprise 1 et audioconférence, utilisez la syntaxe suivante dans le script :

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Pour attribuer une licence Microsoft Business Voice (sans plan d’appel), utilisez la syntaxe suivante dans le script :

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Noms des produits et identificateurs UGS pour les licences

Voici une liste partielle des noms de produits et des noms de parties SKU correspondants que vous pouvez utiliser en tant que référence lorsque vous utilisez PowerShell pour gérer les licences dans Teams.

Pour en savoir plus, voir [afficher des licences et services avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [noms de produits et identificateurs de plan de service pour la gestion des licences](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)et référence des références [SKU éducation](../sku-reference-edu.md).

| Nom du produit| Référence |
|--------------|---------------|
| Microsoft entreprise E5 (avec système téléphonique) | ENTERPRISEPREMIUM |
| Microsoft entreprise E5 (sans conférence audio) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft entreprise E5 (avec audioconférence) | ENTERPRISEPREMIUM |
| Microsoft entreprise E3 | ENTERPRISEPACK |
| Microsoft entreprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Microsoft Business Voice (Canada)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Royaume-Uni) | BUSINESS_VOICE  |
| Microsoft Business Voice (États-Unis) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (sans plan d’appel) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (sans plan d’appel) pour les États-Unis| _MED BUSINESS_VOICE_DIRECTROUTING |
| Audioconférence | MCOMEETADV | 
| Payez à la minute (payer au fur et à mesure)</br>*Le crédit de communications doit être configuré et activé.* | MCOMEETACPEA |
| Système téléphonique | MCOEV |
| Forfait d’appels nationaux et internationaux | MCOPSTN2 |
| Forfait d’appels nationaux (3000 minutes par utilisateur/par mois pour les États-Unis/PR/CA, 1200 minutes par utilisateur et par mois pour les pays de l’Union européenne) | MCOPSTN1 |
| Forfait d’appels nationaux (120 minutes par utilisateur/mois pour chaque pays) </br>*Ce plan n’est pas disponible aux États-Unis.* | MCOPSTN5 |
| Forfait d’appels nationaux (240 minutes par utilisateur/mois pour chaque pays) </br>*Ce plan n’est pas disponible aux États-Unis.* | MCOPSTN6 |
| Crédits de communication | MCOPSTNPP |

## <a name="related-topics"></a>Voir aussi

- [Licences de module complémentaire Teams](microsoft-teams-add-on-licensing.md)
- [Gérer l’accès des utilisateurs à Microsoft Teams](../user-access.md)
- [Afficher les licences et services avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Noms de produits et identificateurs de plans de service pour la gestion des licences](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Référence SKU éducation](../sku-reference-edu.md)