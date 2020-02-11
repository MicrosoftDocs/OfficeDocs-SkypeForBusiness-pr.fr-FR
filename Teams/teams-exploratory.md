---
title: Gérer l’expérience exploratoire de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Les utilisateurs d’Office 365 qui ne disposent pas d’une licence Microsoft Teams peuvent initier une licence exploratoire.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb0998579c29cd7405319600c436468bac2ec4e8
ms.sourcegitcommit: 73376693670d12f3d9038d4ed604e6685ee21984
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41917019"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>Gérer la licence exploratoire Microsoft Teams
=======================================================

L’expérience exploratoire Microsoft Teams permet aux utilisateurs au sein de votre organisation d’Azure Active Directory (AAD) et de ne pas être licenciés pour Teams de lancer une expérience exploratoire de Teams. Les administrateurs peuvent activer ou désactiver cette fonctionnalité pour les utilisateurs de leur organisation. Le précédent [essai de cloud commercial Microsoft](iw-trial-teams.md) est désormais appelée expérience exploratoire Teams.

## <a name="whats-in-the-teams-exploratory-experience"></a>Qu’est-ce que l’expérience exploratoire Teams ?

Les offres de service incluses dans l’expérience exploratoire Teams sont les suivantes :
 - Exchange Online (plan 1)
 - Flow pour Office 365
 - Informations obtenues par MyAnalytics
 - Microsoft Forms (plan E1)
 - Microsoft Planner
 - Recherche Microsoft
 - Microsoft StaffHub
 - Microsoft Stream pour O365 E1 SKU
 - Microsoft Teams
 - Gestion des appareils mobiles pour Office 365
 - Applications Office Mobile pour Office 365 
 - Office Online
 - PowerApps pour Office 365
 - SharePoint Online (plan 1)
 - Sway
 - Tâches (plan 1)
 - Tableau blanc (plan 1)
 - Yammer Enterprise


## <a name="whos-eligible"></a>Utilisateurs éligibles ?

Les utilisateurs doivent être autorisés à s’inscrire aux applications et aux essais (dans le Centre d’administration Microsoft 365). Pour plus d’informations, voir [Gérer l’expérience exploratoire Teams](#manage-the-teams-exploratory-experience) plus loin dans cet article. 

Les utilisateurs qui n’ont pas de licence Office 365 et qui incluent Teams peuvent initier une expérience exploratoire Teams. Par exemple, un utilisateur disposant d’une licence Office 365 Business (n’incluant pas Teams) est éligible à l’expérience exploratoire Teams.

## <a name="who-isnt-eligible"></a>Personnes non éligibles

Votre organisation n’est pas éligible pour cette offre si vous êtes un client partenaire de syndication ou un client GCC, GCC élevé, DoD ou EDU.


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>Comment les utilisateurs s’inscrivent pour l’expérience exploratoire Teams ?

Les utilisateurs éligibles peuvent s’inscrire à l’expérience exploratoire Teams en se connectant à Teams ([teams.microsoft.com](https://teams.microsoft.com)). Celle-ci se voit attribuer automatiquement cette licence et l’administrateur du client reçoit une notification par e-mail la première fois qu’une personne au sein de votre organisation démarre l’expérience exploratoire Teams.

## <a name="manage-the-teams-exploratory-experience"></a>Gérer l’expérience d’exploration de Teams

L’expérience exploratoire Teams est destinée aux utilisateurs finaux individuels et vous ne pouvez pas lancer cette offre pour le compte d’employés de l’utilisateur final.

L’expérience exploratoire Teams est fournie avec une licence Exchange Online, mais elle n’est pas attribuée à l’utilisateur tant que l’administrateur ne l’aura pas affecté. Si l’utilisateur ne dispose pas déjà d’une licence Exchange et que l’administrateur n’a pas encore attribué de licence Exchange Online, l’utilisateur ne peut pas planifier de réunions dans Teams et peut-être qu’il manque d’autres fonctionnalités Teams.

Les administrateurs peuvent désactiver la possibilité pour les utilisateurs finaux d’exécuter l’expérience exploratoire des équipes au sein de leur organisation à l’aide du commutateur des **applications et services d’essai**.


### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Empêcher les utilisateurs d’installer des applications et services à l’essai

Vous pouvez désactiver la possibilité pour un utilisateur d’installer des applications et des services d’essai, empêchant l’utilisateur d’exécuter l’expérience exploratoire Teams.

1. Dans le [Centre d’administration Microsoft 365](https://portal.office.com/adminportal/home), accédez à **Paramètres** > **Paramètres**, sélectionnez **Services**, puis choisissez **Services et applications propriétés de l'utilisateur**.

    ![Capture d’écran de la page Services dans le Centre d’administration](media/iw-trial-services.png)

2. Désactivez la cache à cocher **Permettre aux utilisateurs d'installer les applications et services à l’essai**.

    ![Capture d’écran de la page des applications et services appartenant à l’utilisateur dans le Centre d’administration](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Si votre organisation n’est pas éligible à l’expérience exploratoire Teams, l'option **Laisser les utilisateurs installer les applications et services d’essai** ne s’affiche pas.

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Gérer la disponibilité pour un utilisateur disposant d’une licence incluant Teams

Un utilisateur détenteur d’une licence incluant Team n’est pas admissible à l’expérience exploratoire Teams. Lorsque le plan de service Teams est activé, l’utilisateur peut se connecter et utiliser Teams. Si le plan de service est désactivé, l’utilisateur ne peut pas se connecter et l’expérience exploratoire Teams n’est pas disponible.

Pour désactiver l’accès à Microsoft Teams :

1. Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.

2. Activez la case à cocher située en regard du nom de l’utilisateur.

3. Sur la droite, dans la ligne **Licences de produits**, sélectionnez **Modifier**.

4. Dans le volet **Licences de produit**, sélectionnez **Désactivé**.

    ![Capture d’écran de la section Licences dans le centre d’administration.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Gérer la disponibilité Teams pour les utilisateurs qui utilisent déjà l’expérience exploratoire Teams

Si un utilisateur exécute l’expérience exploratoire Teams, vous pouvez la désactiver en supprimant la licence ou le plan de service.

Pour désactiver la licence l’expérience exploratoire Teams :

1. Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.

2. Activez la case à cocher située en regard du nom de l’utilisateur.

3. Sur la droite, dans la ligne **Licences de produits**, sélectionnez **Modifier**.

4. Dans le volet **Licences de produit**, sélectionnez **Désactivé** pour cette licence exploratoire.
   
    >[!Note]
    >Le commutateur de bascule exploratoire Teams apparaît une fois que le premier utilisateur de l’organisation a lancé l’expérience exploratoire Teams.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Gérer Teams pour les utilisateurs disposant d’une licence exploratoire Teams

Vous pouvez gérer les utilisateurs qui ont une licence exploratoire Teams de la même façon que vous gérez ceux qui ont une licence payante régulière. Pour plus d’informations[Gérer les paramètres de Teams pour votre organisation](enable-features-office-365.md).

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>Mettre à niveau les utilisateurs de la licence exploratoire Teams

Pour mettre à niveau les utilisateurs de la licence exploratoire Teams, procédez comme suit :

1. Achetez un abonnement incluant Teams.

2. Supprimez l’abonnement exploratoire Teams pour l’utilisateur en question.

3. Affectez la licence nouvellement achetée.

Pour plus d’informations, voir [Gestion des licences Office 365 pour Microsoft Teams](Office-365-licensing.md).

> [!NOTE]
> Si la licence exploratoire Teams se termine et un utilisateur n’est pas immédiatement mis à niveau à un abonnement qui inclut Teams, les données des utilisateurs ne sont pas supprimées. L’utilisateur existe toujours dans Azure Active Directory et toutes les données au sein de Teams sont disponibles. Une fois qu’une nouvelle licence est attribuée à l’utilisateur pour activer la fonctionnalité Teams de nouveau, tout le contenu existera encore. 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>Qu’arrive-t-il aux licences d’évaluation cloud commercial de Microsoft Teams ?

Depuis la mi-janvier 2020, les utilisateurs éligibles peuvent commencer à utiliser la dernière expérience exploratoire de Microsoft Teams. Toutes les versions d’évaluation du Cloud commercial sont automatiquement converties à la nouvelle offre avant l’expiration de la période d’évaluation.

### <a name="remove-a-teams-exploratory-license"></a>Supprimer une licence exploratoire Teams

- Si vous souhaitez supprimer cette licence à l’aide PowerShell, voir [Supprimer des licences de comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

- Si vous souhaitez supprimer cette licence via le portail d’administration, voir [Retirer des licences à des utilisateurs dans Office 365 pour les entreprises](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide).
