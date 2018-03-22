---
title: Gérer l'accès des utilisateurs à Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Découvrez comment activer ou désactiver le niveau d'accès par utilisateur.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a612420808af06a773d206573f02d805aac06b15
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
<a name="manage-user-access-to-microsoft-teams"></a>Gérer l'accès des utilisateurs à Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Au niveau de l’utilisateur, les accès à Microsoft Teams peut être activé ou désactivé sur une base par utilisateur par affectation ou suppression de la licence de produit Microsoft Teams.

Actuellement, il n’y a aucune option de la stratégie pour activer équipes, ou un sous-ensemble des fonctionnalités des équipes, ou de désactiver au niveau de l’utilisateur individuel en dehors du Gestionnaire de licences.

> [!NOTE]
>Microsoft vous recommande d’activer les équipes pour tous les utilisateurs d’une entreprise afin que les équipes peuvent être formées biologique pour les projets et autres initiatives dynamiques. Même si vous décidez de pilote, il peut toujours être utile de conserver des équipes activés pour tous les utilisateurs, mais cible uniquement les communications avec le groupe pilote d’utilisateurs.

## <a name="manage-directly-through-the-office-365-admin-center"></a>Gérer directement via le centre d’administration Office 365

Licences d’équipes au niveau de l’utilisateur sont gérés directement via les interfaces de gestion des utilisateurs de Office 365 admin center. Un administrateur peut attribuer des licences à de nouveaux utilisateurs lors de la création de nouveaux comptes d’utilisateurs ou à des utilisateurs disposant de comptes existants. L’administrateur doit avoir des privilèges d’administrateur Global de Office 365 ou l’administrateur de gestion utilisateur pour gérer les licences de Teams de Microsoft.

Lorsqu'une référence (SKU) de licence telle que Entreprise E3 ou E5 est affectée à un utilisateur, une licence Microsoft Teams est automatiquement affectée et le produit est activé pour l'utilisateur. Les administrateurs peuvent disposer d'un contrôle précis sur les services et licences Office 365 ; la licence Microsoft Teams peut être activée ou désactivée pour un utilisateur ou un groupe d'utilisateurs.

![Capture d'écran de la section Licences de produit dans le Centre d'administration Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Une licence utilisateur d’équipes peut être désactivée à tout moment. Une fois que la licence est désactivée, l’accès des utilisateurs à Microsoft Teams ne peuvent pas et l’utilisateur ne seront plus en mesure de voir les équipes dans le Lanceur d’applications Office 365 et de la page d’accueil.

![Capture d'écran de la section Licences de produit dans le Centre d'administration Office 365, avec Microsoft Teams sélectionné.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Gérer via PowerShell

L’activation et la désactivation de Teams comme licence de charge de travail via PowerShell sont effectuées comme pour n'importe quelle charge de travail. Le nom du plan de service est TEAMS1 pour Microsoft Teams. (Voir [Désactiver l'accès aux services avec PowerShell Office 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) pour plus d'informations.)

**Exemple :** Voici juste un exemple rapide sur comment désactiver les équipes pour tout le monde dans un type de licence. Vous devez commencer par cette opération. Ensuite, activez Microsoft Teams individuellement pour les utilisateurs devant y avoir accès à des fins de pilote.

Pour afficher les types d'abonnement dont vous disposez dans votre organisation, utilisez la commande suivante :

      Get-MsolAccountSku

Indiquez un nom pour votre forfait qui inclut le nom de votre organisation et le forfait pour votre établissement (par exemple ContosoSchool:ENTERPRISEPACK_STUDENT), puis exécutez les commandes suivantes :

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Pour désactiver des équipes pour tous les utilisateurs disposant d’une licence active de votre plan de nommée, exécutez la commande suivante :

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Point de décision         |<ul><li>Quel est le plan de l’entreprise pour l’intégration des équipes au sein de l’organisation ?  (Pilote ou ouvrir)</li></ul>         |
|![Icône Étapes suivantes.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Étapes suivantes         |<ul><li>Si l'intégration est effectuée via un projet pilote fermé, choisissez entre l'affectation de licence ou une communication ciblée.</li><li>En fonction de la décision, prendre suit pour vous assurer seulement les utilisateurs qui sont autorisés à accéder aux équipes (si nécessaire) du pilote.</li><li>Les instructions pour les utilisateurs qui seront (ou pas) de documents ont accès aux équipes.</li></ul>         |

## <a name="manage-via-office-sku-level-switch"></a>Gérer via le commutateur au niveau du point de stock Office
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

1.  Connectez-vous au [Centre d'administration Office 365](https://go.microsoft.com/fwlink/?linkid=854614) avec un compte disposant de privilèges d'administrateur général.

2.  Accédez à **Paramètres** > **Services et compléments**.

    ![Capture d'écran de la section Paramètres dans le Centre d'administration Office 365 avec Services et compléments sélectionné. ](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image1.png)

3.  Sur la plage Services et compléments, cliquez sur **Microsoft Teams**.

    ![Capture d'écran de la plage Services et compléments avec Microsoft Teams sélectionné.](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image2.png)

4.  Pour activer Teams pour l'organisation, utilisez l'outil de sélection de licences et sélectionnez toutes les licences. Ensuite, définissez l'option sur **Activé** et cliquez sur **Enregistrer**.

    ![Captures d'écran de la page de paramètres Microsoft Teams affichant la bascule sur Activé pour activer Microsoft Teams.](media/Services-and-addins-control-Microsoft-Teams.PNG)
