---
title: Gérer l'accès des utilisateurs à Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Découvrez comment gérer l’accès des utilisateurs à Teams en attribuant ou en supprimant une licence Teams aux utilisateurs de votre organisation.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4fdfddfe43fd977099a02df61bb74146afcb05d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804404"
---
# <a name="manage-user-access-to-teams"></a>Gérer l’accès des utilisateurs à Microsoft Teams

Vous gérez l’accès à Teams au niveau de l’utilisateur en attribuant ou en supprimant une licence de produit Microsoft Teams. À l’exception de participer à des réunions Teams de manière anonyme, chaque utilisateur de votre organisation doit avoir une licence Teams pour pouvoir utiliser Teams. Vous pouvez attribuer une licence Teams pour les nouveaux utilisateurs lors de la création de comptes d’utilisateurs ou pour les utilisateurs ayant des comptes existants.

Par défaut, lorsqu’un plan de gestion des licences (par exemple, Microsoft 365 Entreprise E3 ou Microsoft 365 Business Premium) est attribué à un utilisateur, une licence Teams est attribuée automatiquement et l’utilisateur est activé pour Teams. Vous pouvez désactiver ou activer Teams pour un utilisateur en supprimant ou en attribuant une licence à tout moment.

Utilisez les stratégies de messagerie, gérées à partir du Centre d’administration <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams,</a>pour contrôler les fonctionnalités de conversation et de messagerie de canal disponibles pour les utilisateurs dans Teams. Vous pouvez utiliser la stratégie par défaut ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation. Pour en savoir plus, lisez [Gérer les stratégies de messagerie dans Teams.](messaging-policies-in-teams.md)
Vous gérez les licences Teams dans le Centre d’administration Microsoft 365 ou à l’aide de PowerShell. Pour gérer les licences, vous devez être administrateur global ou administrateur de gestion des utilisateurs.

> [!NOTE]
> Nous vous recommandons d’activer Teams pour tous les utilisateurs afin que les équipes soient formés de manière interne pour les projets et autres initiatives dynamiques. Même si vous exécutez un pilote, il peut toujours être utile de garder Teams activé pour tous les utilisateurs, mais de cibler uniquement les communications avec le groupe pilote d’utilisateurs.

## <a name="using-the-microsoft-365-admin-center"></a>Utilisation du Centre d’administration Microsoft 365

Les licences utilisateur Teams sont gérées directement via les interfaces de gestion des utilisateurs du Centre d’administration Microsoft 365. Un administrateur peut attribuer des licences aux nouveaux utilisateurs lors de la création de comptes d’utilisateurs, ou aux utilisateurs qui ont déjà des comptes. 

> [!IMPORTANT]
> L’administrateur doit avoir des privilèges d’administrateur général ou d’administrateur de gestion des utilisateurs pour gérer les licences Microsoft Teams.
Le Centre d’administration Microsoft 365 permet de gérer les licences Teams pour des utilisateurs individuels ou des groupes d’utilisateurs de petite taille à la fois. Vous pouvez gérer les licences Teams sur la page **Licences** (jusqu’à 20 utilisateurs à la **fois)** ou la page Utilisateurs actifs. La méthode que vous choisissez dépend de la gestion des licences de produits pour des utilisateurs spécifiques ou de la gestion des licences utilisateur de produits spécifiques.

Si vous devez gérer les licences Teams pour un grand nombre d’utilisateurs(par exemple, des centaines ou des milliers d’utilisateurs), utilisez [PowerShell](#using-powershell) ou des licences basées sur des groupes dans [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) 

### <a name="assign-a-teams-license"></a>Attribuer une licence Teams

Les étapes diffèrent selon que vous utilisez la page Licences ou la **page** **Utilisateurs** actifs.  Pour obtenir des instructions détaillées, voir [Attribuer des licences aux utilisateurs.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

|||
|---------|---------|
|![Capture d’écran de la licence Teams activée pour un utilisateur](media/assign-teams-licenses-1.png)    | ![Capture d’écran de la licence Teams activée pour un utilisateur](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Supprimer une licence Teams

Lorsque vous supprimez la licence Teams d’un utilisateur, Teams est désactivé pour cet utilisateur et il ne verra plus Teams dans le lanceur d’applications ou la page d’accueil. Pour obtenir la procédure détaillée, voir [Désaffecter les licences des utilisateurs.](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)

|||
|---------|---------|
|![Capture d’écran de la licence Teams désactivée pour un utilisateur](media/remove-teams-licenses-1.png)    | ![Capture d’écran de la licence Teams désactivée pour un utilisateur](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Utiliser PowerShell

Utilisez PowerShell pour gérer les licences Teams pour les utilisateurs en bloc. Vous activez et désactivez Teams via PowerShell de la même façon que pour toute autre licence de plan de service. Vous aurez besoin des identificateurs pour les plans de service pour Teams, qui sont les suivants :

- Microsoft Teams : TEAMS1
- Microsoft Teams pour le GCC : TEAMS_GOV
- Microsoft Teams pour DoD : TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Attribuer des licences Teams en bloc

Pour obtenir la procédure détaillée, voir Attribuer des licences à des comptes [d’utilisateurs avec PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="remove-teams-licenses-in-bulk"></a>Supprimer des licences Teams en bloc

Pour obtenir la procédure détaillée, voir Désactiver l’accès aux services avec [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) et Désactiver l’accès aux services lors de [l’attribution de licences utilisateur.](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)

#### <a name="example"></a>Exemple 

Voici un exemple d’utilisation des [cmdlets New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) et [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) pour désactiver Teams pour les utilisateurs qui ont un plan de licence spécifique. Par exemple, suivez ces étapes pour désactiver d’abord Teams pour tous les utilisateurs qui ont un plan de gestion des licences particulier. Activez ensuite Teams pour chaque utilisateur individuel qui doit avoir accès à Teams.

> [!IMPORTANT]
> La [cmdlet New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) active tous les services précédemment désactivés, sauf s’ils sont explicitement identifiés dans votre script personnalisé. Par exemple, si vous voulez laisser Exchange et Sway désactivés tout en désactivant Teams, vous devez l’inclure dans le script, sinon Exchange et Sway seront activés pour les utilisateurs que vous avez identifiés.

Exécutez la commande suivante pour afficher tous les plans de licence disponibles dans votre organisation. Pour en savoir plus, [consultez Afficher les licences et services avec PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)


```powershell
Get-MsolAccountSku
```

Exécutez les commandes suivantes, à savoir le nom de votre organisation et l’identificateur du plan de gestion des licences que vous avez récupéré à \<CompanyName:License> l’étape précédente. Par exemple, ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Exécutez la commande suivante pour désactiver Teams pour tous les utilisateurs qui ont une licence active pour le plan de gestion des licences.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="manage-teams-at-the-organization-level"></a>Gérer les équipes au niveau de l’organisation

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a>Sujets associés

- [Licences de module ajouté Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Attribuer des licences de modules add-on Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Afficher les licences et services avec PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Noms de produits et identificateurs de plans de service pour la gestion des licences](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Référence SKU pour l’éducation](sku-reference-edu.md)
