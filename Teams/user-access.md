---
title: Gérer l'accès des utilisateurs à Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment activer ou désactiver le niveau d'accès par utilisateur.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 377e5ca917db9a0f628e8b045e179e1925e524f1
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493754"
---
<a name="manage-user-access-to-microsoft-teams"></a>Gérer l'accès des utilisateurs à Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Au niveau utilisateur, l’accès à Microsoft teams peut être activé ou désactivé en fonction de chaque utilisateur en attribuant ou en supprimant la licence de produit Microsoft Teams.

Utilisez des stratégies de messagerie gérées par le centre d’administration teams pour contrôler les fonctionnalités de messagerie et de messagerie instantanée disponibles pour les utilisateurs dans Teams. Vous pouvez utiliser la stratégie par défaut ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation. Pour en savoir plus, consultez [gérer les stratégies de messagerie dans teams](messaging-policies-in-teams.md).

> [!NOTE]
>Microsoft vous recommande de réactiver teams pour tous les utilisateurs d’une entreprise, de sorte que les équipes puissent être formées de manière biologique pour les projets et autres initiatives dynamiques. Même si vous décidez de procéder au programme pilote, il est possible que les équipes puissent rester utiles pour tous les utilisateurs, mais uniquement cibler les communications destinées au groupe pilote des utilisateurs.

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a>Gérer teams via le centre d’administration Microsoft 365

Les licences de niveau utilisateur d’équipes sont gérées directement via les interfaces de gestion des utilisateurs du centre d’administration Microsoft 365. Un administrateur peut affecter des licences à de nouveaux utilisateurs lors de la création de nouveaux comptes d’utilisateurs ou à des utilisateurs possédant des comptes existants. L’administrateur doit disposer de privilèges d’administrateur général Office 365 ou de gestion des utilisateurs pour gérer les licences Microsoft Teams.

Lorsqu'une référence (SKU) de licence telle que Entreprise E3 ou E5 est affectée à un utilisateur, une licence Microsoft Teams est automatiquement affectée et le produit est activé pour l'utilisateur. Les administrateurs peuvent disposer d'un contrôle précis sur les services et licences Office 365 ; la licence Microsoft Teams peut être activée ou désactivée pour un utilisateur ou un groupe d'utilisateurs.

![Capture d'écran de la section Licences de produit dans le Centre d'administration Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Une licence utilisateur d’équipes peut être désactivée à tout moment. Lorsque la licence est désactivée, les utilisateurs qui accèdent à Microsoft teams sont empêchés et l’utilisateur ne peut plus voir teams dans le lanceur d’applications et la page d’accueil d’Office 365.

![Capture d’écran montrant les équipes sélectionnées dans la section licences de produits.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Gérer via PowerShell

> [!IMPORTANT]
> Le nouveau-MsolLicenseOptions activera tous les services précédemment désactivés, à moins que explictitly identitied dans votre script personnalisé. Par exemple, si vous souhaitez laisser Exchange & Sway désactivé lors de la désactivation d’équipes, vous devrez inlcude cela dans le script ou Exchange & Sway sera activé pour les utilisateurs que vous avez identifiés. Si vous souhaitez utiliser une interface utilisateur pour gérer cette fonctionnalité, voir: [outil de création de rapports et de gestion des licences Office 365-attribuer supprimer des licences en bloc](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)

L’activation et la désactivation de Teams comme licence de charge de travail via PowerShell sont effectuées comme pour n'importe quelle charge de travail. Le nom du plan de service est TEAMS1 pour Microsoft Teams. Pour GCC, le nom du plan de services est TEAMS_GOV. Pour le nom de plan de service de GCC High, le nom du plan de services est TEAMS_GCCHIGH. Pour DoD, le nom du plan de service est TEAMS_DOD (pour plus d’informations, voir [désactiver l’accès aux services avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) .)

**Exemple:** Vous trouverez ci-dessous un exemple rapide de la manière dont vous allez désactiver teams pour tous les utilisateurs d’un type de licence particulier. Vous devez commencer par cette opération. Ensuite, activez Microsoft Teams individuellement pour les utilisateurs devant y avoir accès à des fins de pilote.

Pour afficher les types d'abonnement dont vous disposez dans votre organisation, utilisez la commande suivante :

      Get-MsolAccountSku

Indiquez un nom pour votre forfait qui inclut le nom de votre organisation et le forfait pour votre établissement (par exemple ContosoSchool:ENTERPRISEPACK_STUDENT), puis exécutez les commandes suivantes :

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Pour désactiver teams pour tous les utilisateurs disposant d’une licence active pour votre plan nommé, exécutez la commande suivante:

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icône représentant un point de décision](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Point de décision         |<ul><li>Quels sont les plans de votre organisation pour l’intégration d’équipes au sein de l’Organisation?  (Pilote ou ouvert)</li></ul>         |
|![Icône représentant les étapes suivantes](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Étapes suivantes         |<ul><li>S’il s’agit d’une intégration par le biais d’un pilote fermé, décidez si vous souhaitez le faire par le biais d’une licence ou d’une communication ciblée.</li><li>En fonction de la décision, prenez des mesures pour vous assurer que seuls les utilisateurs pilotes peuvent accéder aux équipes (si nécessaire).</li><li>Documenter les recommandations relatives aux utilisateurs qui (ou non) ont accès aux équipes.</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Gérer teams au niveau du client 365 Office
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

