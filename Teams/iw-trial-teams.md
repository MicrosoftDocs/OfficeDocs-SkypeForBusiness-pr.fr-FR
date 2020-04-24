---
title: Gérer l’offre d’évaluation Cloud commercial
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Les utilisateurs de Microsoft 365 ou Office 365 qui ne disposent pas d’une licence Microsoft Teams peuvent commencer une période d’essai d’un an de Microsoft Teams.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6a0ad5cf058b8dcc5567cfc706ed3edb2cc09adf
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778350"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Gérer l’offre d’essai du cloud commercial Microsoft Teams
=======================================================

L’essai du cloud commercial Microsoft Teams offre aux utilisateurs de Microsoft 365 ou Office 365 de votre entreprise qui ne sont pas titulaires d’une licence Microsoft Teams la possibilité de bénéficier d’une période d’évaluation d’un an du produit. Les administrateurs peuvent activer ou désactiver cette fonctionnalité pour les utilisateurs de leur organisation.

> [!IMPORTANT]
> L’essai du cloud commercial Microsoft Teams est remplacée par Microsoft Teams exploratoire à partir du 2020 janvier. Pour en savoir plus sur cette nouvelle offre, consultez [Gérer la licence exploratoire Teams](teams-exploratory.md).

## <a name="whats-in-the-offer"></a>Nouveautés dans l’application Power BI

Les plans de service inclus dans cette offre sont les suivants :

- Exchange Foundation
- Flow pour Office 365 (Plan 1)
- Formulaires
- Microsoft Planner
- Microsoft Teams (Teams1, Teams IW)
- Office 
- PowerApps pour Office 365 (Plan 1)
- SharePoint Online Kiosk
- Stream
- Sway
- Tableau blanc
- Yammer Entreprise 

La période d’essai accorde un abonnement d’essai d’un an à l’ensemble de votre organisation. Pour chaque licence attribuée, la version d’évaluation alloue 2 Go de stockage en ligne SharePoint. 

## <a name="who-is-eligible"></a>Qui est éligible

Les utilisateurs doivent être autorisés à s’inscrire aux applications et aux essais (dans le Centre d’administration Microsoft 365). Pour plus d’informations, voir [Gérer l’essai](#manage-the-trial) plus loin dans cet article. 

Les utilisateurs qui n’ont pas de licence Office 365 incluant Teams peuvent bénéficier de l’offre d’essai du cloud commercial Microsoft Teams. Par exemple, un utilisateur disposant d’une licence Applications Microsoft 365 pour les entreprises (n’incluant pas Teams) est éligible à l’essai.

## <a name="who-is-not-eligible"></a>Qui n’est pas éligible

Votre organisation n’est pas éligible pour l’essai si vous êtes un client partenaire de syndication ou si vous êtes un client GCC, GCC élevé, DoD ou EDU.

Si votre organisation n’est pas éligible à l’offre d’essai du cloud commercial Microsoft Teams, le bouton bascule **Laisser les utilisateurs installer les applications et services d’essai** ne s’affiche pas.

## <a name="how-users-sign-up-for-the-trial"></a>Comment les utilisateurs s’inscrivent à l’essai

Les utilisateurs éligibles peuvent s’inscrire à l’offre d’essai en se connectant à Teams ([teams.microsoft.com](https://teams.microsoft.com)). L’écran suivant leur est ensuite proposé pour commencer l’essai. 

![Capture d’écran de la page d’accueil de l’essai de Teams IW.](media/iw-trial-start-screen.png)

Tous les essais au sein de votre organisation partagent les mêmes dates de début et de fin, c'est-à-dire la date à laquelle le premier utilisateur s'est inscrit à l'essai. Par exemple, si l'utilisateur A commence la première évaluation le 2 janvier 2019 et que l'utilisateur B commence une évaluation le 3 juin 2019, l’évaluation expirera le 25 janvier 2020 pour les deux évaluations.

## <a name="manage-the-trial"></a><a name="manage-the-trial"></a>Gérer l’essai

La version d’évaluation de Teams est destinée aux utilisateurs finaux individuels et vous ne pouvez pas lancer l’offre d’évaluation de Teams pour le compte d’employés de l’utilisateur final.

Les administrateurs peuvent désactiver la possibilité pour les utilisateurs finaux de réclamer des évaluations des applications et services au sein de leur organisation. Actuellement, l’essai décrit dans cet article est seul dans cette catégorie, mais il pourrait s’appliquer à d’autres programmes similaires à l’avenir. 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Empêcher les utilisateurs d’installer des applications et services à l’essai

Vous pouvez désactiver la possibilité pour un utilisateur d’installer des applications et services à l’essai.

1. Dans le [Centre d’administration Microsoft 365](https://portal.office.com/adminportal/home), accédez à **Paramètres** > **Paramètres**, sélectionnez **Services**, puis choisissez **Services et applications propriétés de l'utilisateur**.

    ![Capture d’écran de la page Services dans le Centre d’administration](media/iw-trial-services.png)

2. Désactivez la cache à cocher **Permettre aux utilisateurs d'installer les applications et services à l’essai**.

    ![Capture d’écran de la page des applications et services appartenant à l’utilisateur dans le Centre d’administration](media/iw-trial-user-owned-apps-services.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>Gérer la disponibilité d’une version d’évaluation pour un utilisateur disposant d’une licence incluant Teams

Un utilisateur détenteur d’une licence incluant Team n’est pas admissible à l’évaluation. Lorsque le plan de service Teams est activé, l’utilisateur peut se connecter et utiliser Teams. Si le plan de service est désactivé, l’utilisateur ne peut pas se connecter et n’a donc pas accès à l’option d’essai.

Pour désactiver l’accès à Microsoft Teams :

1. Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.

2. Activez la case à cocher située en regard du nom de l’utilisateur.

3. Sur la droite, dans la ligne **Licences de produits**, sélectionnez **Modifier**.

4. Dans le volet **Licences de produit**, sélectionnez **Désactivé**.

    ![Capture d’écran de la section Licences dans le centre d’administration.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>Gérer la disponibilité de Teams pour les utilisateurs qui ont déjà réclamé l’essai

Si un utilisateur a réclamé une licence d’évaluation de Teams, vous pouvez la supprimer en supprimant la licence ou le plan de service.

Pour désactiver la licence d’évaluation :

1. Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.

2. Activez la case à cocher située en regard du nom de l’utilisateur.

3. Sur la droite, dans la ligne **Licences de produits**, sélectionnez **Modifier**.

4. Dans le volet **Licences de produit**, sélectionnez **Désactivé**.

    ![Capture d’écran du paramètre de licence d’évaluation de Teams dans le volet Licences](media/iW-trial-enable-4.png)
    
    >[!Note]
    >Le bouton bascule de Version d’évaluation de Microsoft Teams apparaît une fois que le premier utilisateur s’est inscrit à l’évaluation dans l’organisation.

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>Gérer Teams pour les utilisateurs qui possèdent la licence d’évaluation

Vous pouvez gérer les utilisateurs qui ont une licence d’évaluation de la même façon que vous gérez ceux qui ont une licence payante régulière. Pour plus d’informations[Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md).

### <a name="upgrade-users-from-the-trial-license"></a>Mettre à niveau les utilisateurs à partir de la licence d’évaluation

Pour mettre à niveau les utilisateurs détenteurs de la licence d’évaluation, procédez comme suit :

1. Achetez un abonnement incluant Teams.

2. Supprimez l’abonnement d’évaluation de Teams pour l’utilisateur en question.

3. Affectez la licence nouvellement achetée.

Pour plus d’informations, voir [Gestion des licences Office 365 pour Microsoft Teams](Office-365-licensing.md).

> [!NOTE]
> Si l’essai se termine et un utilisateur n’est pas immédiatement mis à niveau à un abonnement qui inclut Teams, les données des utilisateurs ne sont pas supprimées. L’utilisateur existe toujours dans Azure Active Directory et toutes les données au sein de Teams sont disponibles. Une fois qu’une nouvelle licence est attribuée à l’utilisateur pour activer la fonctionnalité Teams de nouveau, tout le contenu existera encore. 

### <a name="remove-a-legacy-microsoft-teams-trial-license"></a>Supprimer une licence d’évaluation de Microsoft Teams héritée

Depuis le 22 avril 2019, les utilisateurs peuvent commencer à demander la dernière licence d’évaluation Cloud commercial de Microsoft Teams. Si vous souhaitez migrer des membres de votre organisation de la licence d’évaluation héritée vers la dernière version de Microsoft Teams, vous devez commencer par supprimer la licence d’évaluation héritée pour chaque utilisateur concerné. Une fois la licence héritée supprimée, chaque utilisateur affecté peut réclamer la licence d’évaluation Cloud commercial de Microsoft Teams mise à jour.

- Si vous souhaitez supprimer cette licence via PowerShell, voir [Supprimer des licences de comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

- Si vous souhaitez supprimer cette licence via le portail d’administration, voir [Retirer des licences à des utilisateurs dans Office 365 pour les entreprises](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide).
