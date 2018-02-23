---
title: "Licence Office 365 pour Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen, ninadara
description: "Découvrez les différentes licences Office 365, celles qui activent Microsoft Teams pour les utilisateurs et comment les activer et les désactiver."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 401788f354ad57bded48d59a54646d6c10235662
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
<a name="office-365-licensing-for-microsoft-teams"></a>Licence Office 365 pour Microsoft Teams
========================================

Les abonnements Office 365 suivants activent Teams pour les utilisateurs :

|Plans Petite Entreprise  |Plans Entreprise  |Plans d'éducation  |
|---------|---------|---------|
|Office 365 Business Essentials     |Office 365 Entreprise E1         |Office 365 Éducation         |
|Office 365 Business Premium     |Office 365 Entreprise E3         |Office 365 Éducation Plus         |
|     |Office 365 Entreprise E4 (retiré)         |Office 365 Éducation E3 (retiré)         |
|     |Office 365 Entreprise E5         |Office 365 Éducation E5   
      |Office 365 Entreprise F1 |  |

> [!NOTE]
> Teams est également disponible pour les organisations à but non lucratif. Les accords de licence Gouvernement ne sont actuellement pas pris en charge, mais sont en cours d'étude à des fins de prise en charge future.
        


En termes de fonctionnalités **principales** de Microsoft Teams, il n'existe aucune différence entre les divers abonnements Office 365. La disponibilité des fonctionnalités de conformité dépend du niveau d'abonnement correct. (Pour plus d'informations, reportez-vous à l'article [Information Protection Licensing](https://support.office.com/en-us/article/Plan-for-Office-365-security-and-information-protection-capabilities-3d4ac4a1-3920-4ff9-918f-011f3ce60408).)

Tous les plans d'abonnement pris en charge permettent d’accéder au client Web, aux clients de bureau et aux applications mobiles Teams.

Teams n'est pas disponible en tant que service autonome.

<a name="teams-license"></a>Licence Teams
-------------

Par défaut, la licence Teams est activée pour tous les utilisateurs disposant d’un abonnement Office 365 éligible.

![Capture d'écran des paramètres dans la section de licence du Centre d'administration Office 365, indiquant Microsoft Teams comme activé.](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image2.png)


Teams peut être activé ou désactivé pour tout un type de licence dans une organisation ou être activé par défaut pour tous les types de licence, à l'exception des utilisateurs invités. **Vous ne pouvez pas activer Teams pour seulement une partie d'un type de licence à l'aide du commutateur Teams du Centre d'administration Office 365.** Si vous souhaitez activer Teams pour une partie de votre organisation et le désactiver pour une autre partie (par exemple, si vous prévoyez un pilote Teams avec un ensemble défini d'utilisateurs), activez le curseur de licence Teams pour tout le monde, puis désactivez-le pour des utilisateurs individuels.

![Capture d'écran du paramètre de type de licence/utilisateur Teams dans la section de licence du Centre d'administration Office 365, indiquant Microsoft Teams comme activé.](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image3.png)


**Conseil :** l'activation et la désactivation de Teams comme licence de charge de travail via PowerShell sont effectuées comme pour n'importe quelle charge de travail. Le nom du plan de service est TEAMS1 pour Microsoft Teams. (Voir [Désactiver l'accès aux services avec PowerShell Office 365](https://technet.microsoft.com/en-us/library/dn771769.aspx) pour plus d'informations.)

**Exemple :** voici un rapide exemple de la façon dont vous devez désactiver Microsoft Teams pour tous les utilisateurs disposant d'un type de licence spécifique. Vous devez commencer par cette opération. Ensuite, activez Microsoft Teams individuellement pour les utilisateurs devant y avoir accès à des fins de pilote.

*Pour afficher les types d'abonnement dont vous disposez dans votre organisation, utilisez la commande suivante :*

      Get-MsolAccountSku

*Indiquez un nom pour votre forfait qui inclut le nom de votre organisation et le forfait pour votre établissement (par exemple ContosoSchool:ENTERPRISEPACK_STUDENT), puis exécutez les commandes suivantes :*

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
*Pour désactiver Microsoft Teams pour tous les utilisateurs avec une licence active pour le forfait indiqué, exécutez la commande suivante :*

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x