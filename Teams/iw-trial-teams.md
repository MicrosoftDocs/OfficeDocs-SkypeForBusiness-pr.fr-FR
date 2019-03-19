---
title: Gérer l’offre d’essai du cloud commercial Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/10/2018
ms.topic: article
audience: Admin
ms.reviewer: annikaelias
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Les utilisateurs d’Office 365 qui ne disposent pas d’une licence Microsoft Teams peuvent commencer une période d’essai d’un an de Microsoft Teams.
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4fdeba0e4540d64e98eb2853b73e6d1edb5110e
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569614"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Gérer l’offre d’essai du cloud commercial Microsoft Teams
=======================================================

Microsoft Teams est un excellent outil de collaboration pour votre organisation. Il permet aux personnes et aux équipes de discuter, d’innover et de partager des idées grâce à la puissance d’Office 365. L’essai du cloud commercial Microsoft Teams offre aux utilisateurs d’Office 365 de votre entreprise qui ne sont pas titulaires d’une licence Microsoft Teams la possibilité de bénéficier d’une période d’évaluation d’un an du produit. Les administrateurs peuvent activer ou désactiver cette fonctionnalité pour les utilisateurs de leur organisation.

## <a name="whats-in-the-offer"></a>Nouveautés dans l’application Power BI

Cette offre inclut les plans de service suivants :

- Exchange Foundation
- Flow pour Office 365 (Plan 1)
- Microsoft Planner
- Microsoft Teams (Teams1, Teams IW)
- Office Online
- PowerApps pour Office 365 (Plan 1)
- SharePoint Online Kiosk
- Sway
- Yammer Entreprise

La période d’essai accorde un abonnement d’essai d’un an à l’ensemble de votre organisation. L’essai permet d’attribuer 500 000 licences. Pour chaque licence attribuée, la version d’évaluation alloue 2 Go de stockage en ligne SharePoint. 

## <a name="who-is-eligible"></a>Qui est éligible

Les utilisateurs doivent être autorisés à s’inscrire aux applications et aux essais (dans le Centre d’administration Office 365). Pour plus d’informations, voir [Gérer l’essai](#manage-the-trial) plus loin dans cet article. 

Les utilisateurs qui n’ont pas de licence Office 365 incluant Teams peuvent bénéficier de l’offre d’essai du cloud commercial Microsoft Teams. Par exemple, un utilisateur disposant d’une licence Office 365 Business (n’incluant pas Teams) est éligible à l’essai.

## <a name="who-is-not-eligible"></a>Qui n’est pas éligible

Votre organisation n’est pas éligible à l’essai dans les cas suivants : 

- Vous êtes un client partenaire de syndication
- Vous êtes un client partenaire revendeur
- Vous êtes un client EDU ou travaillez dans le secteur public

Si votre organisation n’est pas éligible à l’offre d’essai du cloud commercial Microsoft Teams, le bouton bascule **Laisser les utilisateurs installer les applications et services d’essai** ne s’affiche pas.

## <a name="how-users-sign-up-for-the-trial"></a>Comment les utilisateurs s’inscrivent à l’essai

Les utilisateurs éligibles peuvent s’inscrire à l’offre d’essai en se connectant à Teams ([teams.microsoft.com](https://teams.microsoft.com)). L’écran suivant leur est ensuite proposé pour commencer l’essai. 

![Capture d’écran de la page d’accueil de l’essai de Teams IW.](media/iw-trial-start-screen.png)

Tous les essais au sein de votre organisation partagent les mêmes dates de début et de fin, c’est-à-dire la date à laquelle le premier utilisateur s’est inscrit à l’essai. Par exemple, si l’utilisateur A commence la première évaluation le 25 janvier 2019 et que l’utilisateur B commence une évaluation le 3 juin 2019, l’évaluation expirera le 25 janvier 2020 pour les deux évaluations.

## <a name="manage-the-trial"></a>Gérer l’essai

Les administrateurs peuvent gérer les licences pour les utilisateurs qui se sont inscrits. 

De plus, les administrateurs peuvent désactiver la possibilité pour les utilisateurs finaux de réclamer des applications et services à l’essai au sein de leur organisation. Actuellement, l’essai décrit dans cet article est seul dans cette catégorie, mais il pourrait s’appliquer à d’autres programmes similaires à l’avenir. 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Empêcher les utilisateurs d’installer des applications et services à l’essai

Vous pouvez désactiver la possibilité pour un utilisateur d’installer des applications et services à l’essai.

1. Dans le [Centre d’administration Microsoft 365](https://portal.office.com/adminportal/home), accédez à **Paramètres** > **Services et compléments** > **Applications et services propriétaires**.

    ![Capture d’écran de la page Services et compléments dans le Centre d’administration d’Office 365.](media/iw-trial-enable-1.png)

2. Désactivez **Laisser les utilisateurs installer les applications et services à l’essai**.

    ![Capture d’écran de la page des applications et services appartenant à l’utilisateur dans le Centre d’administration Office 365.](media/iw-trial-enable-2.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>Gérer la disponibilité d’une version d’évaluation pour un utilisateur disposant d’une licence incluant Teams

Un utilisateur détenteur d’une licence incluant Team n’est pas admissible à l’évaluation. Lorsque le plan de service Teams est activé, l’utilisateur peut se connecter et utiliser Teams. Si le plan de service est désactivé, l’utilisateur ne peut pas se connecter et n’a donc pas accès à l’option d’essai.

Pour désactiver l’accès à Microsoft Teams :

1. Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.

2. Activez la case à cocher située en regard du nom de l’utilisateur.

3. Sur la droite, dans la ligne **Licences de produits**, sélectionnez **Modifier**.

4. Dans le volet **Licences de produit**, sélectionnez **Désactivé**.

    ![Capture d’écran de la section Licences des produits dans le Centre d’administration Office 365.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>Gérer la disponibilité de Teams pour les utilisateurs qui ont déjà réclamé l’essai

Si un utilisateur a réclamé une licence d’évaluation de Teams, vous pouvez la supprimer en supprimant la licence ou le plan de service.

Pour désactiver la licence d’évaluation :

1. Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.

2. Activez la case à cocher située en regard du nom de l’utilisateur.

3. Sur la droite, dans la ligne **Licences de produits**, sélectionnez **Modifier**.

4. Dans le volet **Licences de produit**, sélectionnez **Désactivé**.

    ![Capture d’écran du paramètre de licence d’évaluation de Teams dans le volet Licences des produits](media/iW-trial-enable-4.png)
    
>[!Note]
>Le bouton bascule de Version d’évaluation de Microsoft Teams apparaît une fois que le premier utilisateur s’est inscrit à l’évaluation dans l’organisation.

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>Gérer Teams pour les utilisateurs qui possèdent la licence d’évaluation

Vous pouvez gérer les utilisateurs qui ont une licence d’évaluation de la même façon que vous gérez ceux qui ont une licence payante régulière. Pour plus d’informations, consultez [Gérer les fonctionnalités de Microsoft Teams dans votre organisation Office 365](enable-features-office-365.md)

### <a name="upgrade-users-from-the-trial-license"></a>Mettre à niveau les utilisateurs à partir de la licence d’évaluation

Pour mettre à niveau les utilisateurs détenteurs de la licence d’évaluation, procédez comme suit :

1. Achetez un abonnement incluant Teams.

2. Supprimez l’abonnement d’évaluation de Teams pour l’utilisateur en question.

3. Affectez la licence nouvellement achetée.

Pour plus d’informations, voir [Gestion des licences Office 365 pour Microsoft Teams](Office-365-licensing.md).
