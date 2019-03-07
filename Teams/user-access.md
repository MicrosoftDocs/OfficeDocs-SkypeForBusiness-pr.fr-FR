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
ms.openlocfilehash: f5c755c1dbcb62b01ab45772660b23524550e4e5
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458891"
---
<a name="manage-user-access-to-microsoft-teams"></a>Gérer l'accès des utilisateurs à Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Au niveau de l’utilisateur, l’accès à Microsoft Teams peut être activé ou désactivé sur par utilisateur à l’attribution ou la suppression de la licence de produit Microsoft Teams.

Actuellement, il n’existe aucune option de stratégie pour activer des équipes ou un sous-ensemble des fonctionnalités d’équipes, ou de désactiver au niveau utilisateur individuel en dehors de la gestion des licences.

> [!NOTE]
>Microsoft recommande que vous allumez équipes pour tous les utilisateurs d’une entreprise afin que les équipes peuvent être créées selon pour les projets et autres initiatives dynamiques. Même si vous décidez au pilote, il peut toujours être utile de conserver les équipes activés pour tous les utilisateurs, mais uniquement cibler communications dans le groupe pilote d’utilisateurs.

## <a name="manage-teams-through-the-office-365-admin-center"></a>Gérer les équipes via le centre d’administration Office 365

Licences d’équipes au niveau utilisateur sont gérés directement via les interfaces de gestion Office 365 admin center utilisateur. Un administrateur peut affecter des licences pour les nouveaux utilisateurs lors de la création de nouveaux comptes d’utilisateurs ou aux utilisateurs disposant de comptes existants. L’administrateur doit disposer de privilèges d’administrateur Global de Office 365 ou administrateur de gestion des utilisateurs pour gérer les licences Microsoft Teams.

Lorsqu'une référence (SKU) de licence telle que Entreprise E3 ou E5 est affectée à un utilisateur, une licence Microsoft Teams est automatiquement affectée et le produit est activé pour l'utilisateur. Les administrateurs peuvent disposer d'un contrôle précis sur les services et licences Office 365 ; la licence Microsoft Teams peut être activée ou désactivée pour un utilisateur ou un groupe d'utilisateurs.

![Capture d'écran de la section Licences de produit dans le Centre d'administration Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Une licence d’utilisateur équipes peut être désactivée à tout moment. Une fois que la licence est désactivée, l’accès des utilisateurs à Microsoft Teams n’est pas autorisée et l’utilisateur ne sera plus en mesure de voir les équipes dans la page d’accueil et lancement d’application Office 365.

![Capture d'écran de la section Licences de produit dans le Centre d'administration Office 365, avec Microsoft Teams sélectionné.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Gérer via PowerShell

> [!IMPORTANT]
> Nouvelle MsolLicenseOptions activer tous les services qui ont été précédemment désactivées à moins qu’explictitly identitied dans votre script personnalisé. Par exemple, si vous souhaitez laisser les deux & Exchange balancement désactivé pendant apporte désactivation des équipes, vous devrez incluent ce dans le script ou les deux & Exchange balancement sera deviennent activé pour les utilisateurs que vous avez identifié. Si vous souhaitez utilisent une interface utilisateur graphique pour gérer cette fonctionnalité, voir : [outil de gestion et de création de rapports de licence de Office 365-attribuer des licences supprimer en bloc](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)

L’activation et la désactivation de Teams comme licence de charge de travail via PowerShell sont effectuées comme pour n'importe quelle charge de travail. Le nom du plan de service est TEAMS1 pour Microsoft Teams. Pour GCC le nom de plan de service est TEAMS_GOV. High GCC le nom de plan de service est TEAMS_GCCHIGH. Le nom de plan de service est DoD TEAMS_DOD (voir [désactiver l’accès aux services Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) pour plus d’informations.)

**Exemple :** L’exemple suivant est simplement un rapide sur la façon dont vous pouvez le désactiver équipes pour tout le monde dans un type de licence. Vous devez commencer par cette opération. Ensuite, activez Microsoft Teams individuellement pour les utilisateurs devant y avoir accès à des fins de pilote.

Pour afficher les types d'abonnement dont vous disposez dans votre organisation, utilisez la commande suivante :

      Get-MsolAccountSku

Indiquez un nom pour votre forfait qui inclut le nom de votre organisation et le forfait pour votre établissement (par exemple ContosoSchool:ENTERPRISEPACK_STUDENT), puis exécutez les commandes suivantes :

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Pour désactiver les équipes pour tous les utilisateurs disposant d’une licence pour votre plan nommé active, exécutez la commande suivante :

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Point de décision         |<ul><li>Quel est le plan de votre organisation pour l’intégration des équipes au sein de l’organisation ?  (Pilote ou ouvrir)</li></ul>         |
|![Icône Étapes suivantes.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Étapes suivantes         |<ul><li>Si embarquement via un pilote fermé, décider si vous souhaitez faire par le biais de la gestion des licences ou ciblés de communication.</li><li>Selon la décision, procédez comme suit pour vous assurer que pilote uniquement les utilisateurs autorisés à accéder aux équipes (le cas échéant).</li><li>Les instructions pour les utilisateurs qui seront (ou pourront) de documents ont accès aux équipes.</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Gérer les équipes au niveau client Office 365
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

