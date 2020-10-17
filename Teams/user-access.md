---
title: Gérer l'accès des utilisateurs à Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment gérer l’accès des utilisateurs aux équipes en attribuant ou en supprimant une licence d’équipe aux utilisateurs de votre organisation.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d877a4c6534c76b894583401dc5dba0936c3c75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521381"
---
# <a name="manage-user-access-to-teams"></a>Gérer l’accès des utilisateurs à Microsoft Teams

Vous pouvez gérer l’accès aux équipes au niveau utilisateur en attribuant ou en supprimant une licence de produit Microsoft Teams. Pour pouvoir utiliser Teams, chaque utilisateur de votre organisation doit disposer d’une licence Teams. Vous pouvez affecter une licence d’équipe aux nouveaux utilisateurs lors de la création de nouveaux comptes d’utilisateurs ou à des utilisateurs possédant des comptes existants.

Par défaut, lorsque vous disposez d’un plan de gestion des licences (par exemple, Microsoft 365 entreprise E3 ou Microsoft 365 Business Premium) affecté à un utilisateur, une licence d’équipe est automatiquement affectée et l’utilisateur est activé pour Teams. Vous pouvez désactiver ou activer les équipes pour un utilisateur en le supprimant ou en lui attribuant une licence à tout moment.

Utilisez des stratégies de messagerie gérées par le <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centre d’administration teams</a>pour contrôler les fonctionnalités de messagerie et de messagerie instantanée disponibles pour les utilisateurs dans Teams. Vous pouvez utiliser la stratégie par défaut ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation. Pour en savoir plus, consultez [gérer les stratégies de messagerie dans teams](messaging-policies-in-teams.md).
Vous pouvez gérer les licences d’équipes dans le centre d’administration 365 Microsoft ou en utilisant PowerShell. Vous devez être un administrateur général ou un administrateur de gestion des utilisateurs pour gérer les licences.

> [!NOTE]
> Nous vous recommandons d’activer teams pour tous les utilisateurs de sorte que les équipes puissent être formées de manière biologique pour les projets et autres initiatives dynamiques. Même si vous exécutez une version d’essai, il est possible que les équipes puissent rester opérationnelles pour tous les utilisateurs, mais uniquement cibler les communications avec le groupe pilote d’utilisateurs.

## <a name="using-the-microsoft-365-admin-center"></a>Utilisation du centre d’administration Microsoft 365

Les licences de niveau utilisateur d’équipes sont gérées directement via les interfaces de gestion des utilisateurs du centre d’administration Microsoft 365. Un administrateur peut affecter des licences à de nouveaux utilisateurs lors de la création de nouveaux comptes d’utilisateurs ou à des utilisateurs possédant des comptes existants. 

> [!IMPORTANT]
> L’administrateur doit disposer de privilèges d’administrateur général ou de gestion des utilisateurs pour gérer les licences Microsoft Teams.
Le centre d’administration Microsoft 365 permet de gérer les licences d’équipes pour des utilisateurs individuels ou des petits groupes d’utilisateurs à la fois. Vous pouvez gérer les licences teams dans la page **licences** (pour 20 utilisateurs au maximum) ou la page **utilisateurs actifs** . La méthode que vous choisissez dépend de la façon dont vous souhaitez gérer les licences de produits pour des utilisateurs spécifiques ou gérer des licences utilisateur pour des produits spécifiques.

Si vous avez besoin de gérer les licences d’équipes pour un grand nombre d’utilisateurs, par exemple des centaines voire des milliers d’utilisateurs, utilisez la gestion des licences [PowerShell](#using-powershell) ou par [groupe dans Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign). 

### <a name="assign-a-teams-license"></a>Attribution d’une licence d’équipe

Les étapes diffèrent selon que vous utilisez la page **licences** ou **utilisateurs actifs** .  Pour obtenir des instructions détaillées, voir attribuer des [licences à des utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

|||
|---------|---------|
|![Capture d’écran de la licence teams activée pour un utilisateur](media/assign-teams-licenses-1.png)    | ![Capture d’écran de la licence teams activée pour un utilisateur](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Supprimer une licence d’équipe

Lorsque vous supprimez une licence teams d’un utilisateur, teams est désactivé pour cet utilisateur et ne verra plus teams dans le lanceur d’applications ou sur la page d’accueil. Pour obtenir la procédure détaillée, voir [Annuler l’attribution de licences aux utilisateurs](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).

|||
|---------|---------|
|![Capture d’écran de la licence teams désactivée pour un utilisateur](media/remove-teams-licenses-1.png)    | ![Capture d’écran de la licence teams désactivée pour un utilisateur](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Utiliser PowerShell

Utiliser PowerShell pour gérer les licences teams des utilisateurs en bloc. Vous pouvez activer et désactiver teams via PowerShell de la même manière que pour n’importe quelle licence d’autre plan de service. Vous aurez besoin des identificateurs pour les plans de services pour les équipes, qui sont les suivantes :

- Microsoft teams : TEAMS1
- Microsoft teams pour GCC : TEAMS_GOV
- Microsoft teams pour DoD : TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Attribution de licences équipe en bloc

Pour obtenir la procédure détaillée, voir [attribuer des licences à des comptes d’utilisateurs avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="remove-teams-licenses-in-bulk"></a>Supprimer des licences d’équipe en bloc

Pour obtenir la procédure détaillée, voir [désactiver l’accès aux services avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) et [désactiver l’accès aux services lorsque vous attribuez des licences utilisateur](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

#### <a name="example"></a>Exemple 

Voici un exemple d’utilisation des applets de commande [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) et [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) pour désactiver teams pour les utilisateurs disposant d’un plan de gestion des licences spécifique. Par exemple, suivez ces étapes pour désactiver d’abord teams pour tous les utilisateurs disposant d’un plan de gestion des licences particulier. Activez ensuite teams pour chaque utilisateur individuel qui doit avoir accès à Teams.

> [!IMPORTANT]
> L’applet [de action New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) active tous les services précédemment désactivés, sauf s’ils sont explicitement identifiés dans votre script personnalisé. Par exemple, si vous souhaitez que Microsoft Exchange et votre Sway soient désactivés, vous devez le faire dans le script ou Exchange et Sway seront activés pour les utilisateurs identifiés.

Exécutez la commande suivante pour afficher l’ensemble des plans de licence disponibles dans votre organisation. Pour en savoir plus, voir [afficher des licences et services avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).

      Get-MsolAccountSku

Exécutez les commandes suivantes, où \<CompanyName:License> est le nom de votre organisation et l’identificateur correspondant au plan de gestion des licences que vous avez récupéré lors de l’étape précédente. Par exemple, ContosoSchool : ENTERPRISEPACK_STUDENT.

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

Exécutez la commande suivante pour désactiver teams pour tous les utilisateurs disposant d’une licence active pour le plan de gestion des licences.

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a>Gérer teams au niveau de l’Organisation

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a>Voir aussi

- [Licences de compléments teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Attribution de licences de complément d’équipes](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Afficher les licences et services avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Noms de produits et identificateurs de plans de service pour la gestion des licences](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Référence SKU éducation](sku-reference-edu.md)