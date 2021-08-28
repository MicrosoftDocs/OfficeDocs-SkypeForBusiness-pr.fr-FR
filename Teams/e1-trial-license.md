---
title: Gérer la version d’évaluation gratuite d’Office 365 E1
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aytange
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: Si vous ne disposez pas de Microsoft Teams et que vous en avez rapidement besoin, déployez la version d’évaluation d’Office 365 E1 pour les utilisateurs qui ont besoin de travailler à distance ou à partir de leur domicile (WFH) en réponse à l’épidémie COVID-19 (coronavirus).
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 875693e23b5e13f48a031a21f0037f1576dbd1ce
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611693"
---
# <a name="manage-the-office-365-e1-trial"></a>Gérer la version d’évaluation d’Office 365 E1

Depuis le 1er juillet 2020, la licence d’évaluation d’Office 365 E1 n’est plus disponible. Si vous avez besoin de fournir une licence à des utilisateurs pour Microsoft Teams, consultez la [Description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description) afin d’obtenir la liste des abonnements payants avec Teams inclus. Sinon, les organisations éligibles peuvent utiliser la **[version gratuite de Teams](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c)** ou les employés peuvent activer l’expérience **[Teams Exploratory](teams-exploratory.md)**.

Si vous êtes un client Teams pour l’éducation, jetez un œil à la [licence Office 365 A1](teams-edu-licensing.md)gratuite.

Lisez les instructions dans cet article pour gérer vos licences d’évaluation Office 365 E1 existantes, y compris [la mise à niveau vers un abonnement payant](#upgrade-users-from-the-office-365-e1-trial-license).

Ne manquez aucune de nos recommandations pour la [prise en charge des employés en télétravail avec Teams](support-remote-work-with-teams.md).

## <a name="manage-the-e1-trial"></a>Gérer l’évaluation E1

Une fois activée la version d’évaluation Office 365 E1, activez la licence pour les utilisations qui en ont besoin. Pour plus d'informations, lire la rubrique [Gestion de l'accès des utilisateurs à Microsoft Teams](user-access.md).


Une fois que vous avez activé la version d’évaluation E1 pour les utilisateurs qui en ont besoin, vous devez gérer ces utilisateurs de la même manière que les utilisateurs disposant d’une licence payante. Pour plus d’informations, voir [Gérer les paramètres de Teams pour votre organisation](enable-features-office-365.md).



### <a name="upgrade-users-from-the-office-365-e1-trial-license"></a>Mettre à niveau les utilisateurs à partir de la licence d’évaluation Office 365 E1

Pour migrer les utilisateurs de l'évaluation E1 vers une version payante :

1. Achetez un abonnement incluant Teams.

2. Supprimez l’abonnement d’évaluation Office 365 E1 chez l’utilisateur en question.

3. Affectez la licence nouvellement achetée.

Pour plus d’informations, voir [Description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description).

> [!NOTE]
> Si la licence d'essai E1se termine et qu'un utilisateur n’est pas immédiatement mis à jour vers un abonnement incluant Teams, les données des utilisateurs ne sont pas supprimées. L’utilisateur existe toujours dans Azure Active Directory et toutes les données au sein de Teams sont disponibles. Une fois qu’une nouvelle licence est attribuée à l’utilisateur pour activer la fonctionnalité Teams de nouveau, tout le contenu existera encore. 

### <a name="remove-an-office-365-e1-trial-license"></a>Supprimer une licence d’évaluation d’Office 365 E1

- Si vous souhaitez supprimer cette licence à l’aide PowerShell, voir [Supprimer des licences de comptes d’utilisateurs avec Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

- Si vous souhaitez supprimer cette licence via le portail d’administration, consultez : [Supprimer un utilisateur de votre organisation](/microsoft-365/admin/add-users/delete-a-user)

## <a name="related-topics"></a>Voir aussi

[Gérer l’accès des utilisateurs à Microsoft Teams](user-access.md)

[Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md)

[Gérer l’expérience exploratoire de Teams](teams-exploratory.md)

[Microsoft 365 ou Office 365 pour les associations](https://www.microsoft.com/microsoft-365/nonprofit/office-365-nonprofit)

[Obtenir de l’aide pour déployer des équipes](https://go.microsoft.com/fwlink/?linkid=780698)