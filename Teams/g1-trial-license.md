---
title: Gérez la version d’évaluation gratuite d’Office 365 G1 pour le gouvernement américain
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aarimm
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: En ce qui concerne le gouvernement américain, si vous ne disposez pas de Microsoft Teams et que vous en avez rapidement besoin, déployez la version d’évaluation d’Office 365 G1 pour les utilisateurs qui ont besoin de travailler à distance ou à partir de leur domicile (WFH) en réponse à l’épidémie COVID-19 (coronavirus).
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d45869d015dc5486d3971bff5795cb0cc791dd5c
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377322"
---
# <a name="manage-the-office-365-g1-trial-for-us-government"></a>Gérez la version d’évaluation d’Office 365 G1 pour le gouvernement américain 

Depuis le 1er juillet 2020, la licence d’évaluation d’Office 365 E1 n’est plus disponible. Si vous avez besoin de fournir une licence à des utilisateurs pour Microsoft Teams, consultez la [Description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description) afin d’obtenir la liste des abonnements payants avec Teams inclus. 

Lisez les instructions dans cet article pour gérer vos licences d’évaluation Office 365 G1 existantes, y compris [la mise à niveau vers un abonnement payant](#upgrade-users-from-the-office-365-g1-trial-license). Pour en savoir plus, consultez les [Offres Microsoft 365 Government](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans) et les [fonctionnalités de Microsoft Teams disponibles dans le cloud de la communauté du secteur public](plan-for-government-gcc.md).

Ne manquez aucune de nos recommandations pour la [prise en charge des employés en télétravail avec Teams](support-remote-work-with-teams.md).

## <a name="manage-the-g1-trial"></a>Gérer la version d'évaluation G1

Une fois activée la version d’évaluation Office 365 G1, activez la licence pour les utilisations qui en ont besoin. Pour plus d'informations, lire la rubrique [Gestion de l'accès des utilisateurs à Microsoft Teams](user-access.md).

Une fois que vous avez activé la version d’évaluation G1 pour les utilisateurs qui en ont besoin, vous devez gérer ces utilisateurs de la même manière que ceux disposant d’une licence payante. Pour plus d’informations[Gérer les paramètres de Teams pour votre organisation](enable-features-office-365.md).

### <a name="upgrade-users-from-the-office-365-g1-trial-license"></a>Mettre à jour les utilisateurs à partir de la licence d’évaluation Office 365 G1

Pour migrer les utilisateurs de la version d'évaluation G1 vers une version payante :

1.  Achetez un abonnement incluant Teams.

2.  Supprimez l’abonnement en version d’évaluation Office 365 G1 chez l’utilisateur en question.

3.  Affectez la licence nouvellement achetée.

Pour plus d’informations, consultez [Teams pour le gouvernement](expand-teams-across-your-org/teams-for-government-landing-page.md).

> [!NOTE]
> Si la licence d'essai E1se termine et qu'un utilisateur n’est pas immédiatement migré vers un abonnement incluant Teams, les données des utilisateurs ne sont pas supprimées. L’utilisateur existe toujours dans Azure Active Directory et toutes les données au sein de Teams sont disponibles. Une fois qu’une nouvelle licence est attribuée à l’utilisateur pour activer la fonctionnalité Teams de nouveau, tout le contenu existera encore.
> 
### <a name="remove-an-office-365-g1-trial-license"></a>Supprimer une licence d’évaluation Office 365 G1

  - Si vous souhaitez supprimer cette licence à l’aide PowerShell, voir [Supprimer des licences de comptes d’utilisateurs avec Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

  - Si vous souhaitez supprimer cette licence via le portail d’administration, consultez : [Supprimer un utilisateur de votre organisation](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>Voir aussi

[Gérer l’accès des utilisateurs à Microsoft Teams](user-access.md)

[Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md)
