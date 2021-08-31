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
description: Découvrez comment gérer l’accès des utilisateurs aux Teams en attribuant ou en supprimant une licence Teams aux utilisateurs de votre organisation.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4a83d0da32c11406f76b9bc355ceb666d4ea308
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728063"
---
# <a name="manage-user-access-to-teams"></a>Gérer l’accès des utilisateurs à Microsoft Teams

Vous gérez l’accès Teams utilisateur en attribuant ou en supprimant une Microsoft Teams produit. À l’exception de Teams anonymes, chaque utilisateur de votre organisation doit avoir une licence de Teams pour pouvoir utiliser Teams. Vous pouvez attribuer une licence Teams utilisateurs à de nouveaux utilisateurs lors de la création de comptes d’utilisateurs ou à des utilisateurs ayant déjà des comptes.

Par défaut, lorsqu’un plan de gestion des licences (par exemple, Microsoft 365 Entreprise E3 ou Microsoft 365 Business Premium) est attribué à un utilisateur, une licence Teams est attribuée automatiquement et l’utilisateur est activé pour les Teams. Vous pouvez désactiver ou activer Teams utilisateur en supprimant ou en attribuant une licence à tout moment.

Utilisez les stratégies de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a>messagerie, gérées à partir du Centre Teams’administration, pour contrôler les fonctionnalités de conversation et de messagerie de canal disponibles pour les utilisateurs Teams. Vous pouvez utiliser la stratégie par défaut ou créer une ou plusieurs stratégies de messagerie personnalisées pour les membres de votre organisation. Pour en savoir plus, lisez Gérer les stratégies de [messagerie dans Teams.](messaging-policies-in-teams.md)
Vous gérez Teams licences dans le Centre d’administration Microsoft 365 ou à l’aide de PowerShell. Pour gérer les licences, vous devez être administrateur global ou administrateur de gestion des utilisateurs.

> [!NOTE]
> Nous vous recommandons d’activer Teams pour tous les utilisateurs afin que les équipes soient formés de manière interne pour les projets et autres initiatives dynamiques. Même si vous exécutez un pilote, il peut s’avérer utile de garder les Teams activées pour tous les utilisateurs, mais de cibler uniquement les communications avec le groupe pilote d’utilisateurs.

## <a name="using-the-microsoft-365-admin-center"></a>Utilisation de la Centre d’administration Microsoft 365

Teams licences utilisateur sont gérées directement via les interfaces Centre d’administration Microsoft 365 gestion des utilisateurs. Un administrateur peut attribuer des licences aux nouveaux utilisateurs lors de la création de comptes d’utilisateurs, ou aux utilisateurs qui ont déjà des comptes. 

> [!IMPORTANT]
> L’administrateur doit avoir des privilèges d’administrateur général ou d’administrateur de gestion des utilisateurs pour Microsoft Teams licences.
Utilisez l’Centre d’administration Microsoft 365 pour gérer Teams licences utilisateur individuel ou petit groupe d’utilisateurs à la fois. Vous pouvez gérer Teams licences dans la page Licences (jusqu’à 20 utilisateurs à la **fois)** ou la page **Utilisateurs** actifs. La méthode que vous choisissez dépend de la gestion des licences de produits pour des utilisateurs spécifiques ou de la gestion des licences utilisateur de produits spécifiques.

Si vous devez gérer des licences Teams pour un grand nombre d’utilisateurs (par exemple, des centaines ou des milliers d’utilisateurs), utilisez [PowerShell](#using-powershell) ou des licences basées sur les groupes [dans Azure Active Directory (Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign) 

### <a name="assign-a-teams-license"></a>Attribuer une licence Teams licence

Les étapes diffèrent selon que vous utilisez la page Licences ou la **page** **Utilisateurs** actifs.  Pour obtenir des instructions détaillées, voir [Attribuer des licences aux utilisateurs.](/microsoft-365/admin/manage/assign-licenses-to-users)

|&nbsp;|&nbsp;|
|---------|---------|
|![Capture d’écran 1 Teams licence activée pour un utilisateur.](media/assign-teams-licenses-1.png)    | ![Capture d’écran 2 de Teams licence activée pour un utilisateur](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a>Supprimer une licence Teams licence

> [!IMPORTANT]
> La désactivation d’une référence Teams SKU prend environ 24 heures.

Lorsque vous supprimez la licence Teams d’un utilisateur, Teams est désactivé pour cet utilisateur et les Teams ne sont plus Teams dans le lanceur d’applications ou la page d’accueil. Pour obtenir la procédure détaillée, voir [Désaffecter les licences des utilisateurs.](/microsoft-365/admin/manage/remove-licenses-from-users)

|&nbsp;|&nbsp;|
|---------|---------|
|![Capture d’écran 1 de l Teams de licence désactivée pour un utilisateur.](media/remove-teams-licenses-1.png)    | ![Capture d’écran 2 de la Teams de licence désactivée pour un utilisateur](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a>Utiliser PowerShell

Utilisez PowerShell pour gérer les licences Teams utilisateurs en bloc. Vous activez et désactivez les Teams via PowerShell de la même façon que pour toute autre licence de plan de service. Vous aurez besoin des identificateurs des plans de service pour Teams, qui sont les suivants :

- Microsoft Teams : TEAMS1
- Microsoft Teams pour Cloud de la communauté du secteur public : TEAMS_GOV
- Microsoft Teams pour DoD : TEAMS_DOD

### <a name="assign-teams-licenses-in-bulk"></a>Attribuer Teams licences en bloc

Pour obtenir la procédure détaillée, voir Attribuer des licences à des comptes [d’utilisateurs avec PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="remove-teams-licenses-in-bulk"></a>Supprimer Teams licences en bloc

Pour obtenir la procédure détaillée, voir Désactiver l’accès aux services avec [PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) et Désactiver l’accès aux services lors de [l’attribution de licences utilisateur.](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)

#### <a name="example"></a>Exemple 

Voici un exemple d’utilisation des [cmdlets New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) et [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) pour désactiver les Teams pour les utilisateurs qui ont une offre de licence spécifique. Par exemple, suivez ces étapes pour désactiver l’Teams tous les utilisateurs qui ont un plan de gestion des licences particulier. Activez ensuite l Teams pour chaque utilisateur qui doit avoir accès à Teams.

> [!IMPORTANT]
> La [cmdlet New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) active tous les services précédemment désactivés, sauf s’ils sont explicitement identifiés dans votre script personnalisé. Par exemple, si vous souhaitez laisser Exchange et Sway désactivés tout en désactivant Teams, vous devez l’inclure dans le script, ou Exchange et Sway seront activés pour les utilisateurs que vous avez identifiés.

Exécutez la commande suivante pour afficher tous les plans de licence disponibles dans votre organisation. Pour en savoir plus, [consultez Afficher les licences et services avec PowerShell.](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)


```powershell
Get-MsolAccountSku
```

Exécutez les commandes suivantes, à savoir le nom de votre organisation et l’identificateur du plan de gestion des licences que vous avez récupéré à \<CompanyName:License> l’étape précédente. Par exemple, ContosoSchool:ENTERPRISEPACK_STUDENT.

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

Exécutez la commande suivante pour désactiver l Teams de tous les utilisateurs qui ont une licence active pour le plan de gestion des licences.

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a>Sujets associés

- [Teams licences de modules add-on](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Attribuer Teams licences de modules add-on](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [Afficher les licences et services avec PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Noms de produits et identificateurs de plans de service pour la gestion des licences](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Référence SKU pour l’éducation](sku-reference-edu.md)
