---
title: Gérer l’expérience exploratoire de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Les utilisateurs de Microsoft 365 ou Office 365 qui ne disposent pas d’une licence Microsoft Teams peuvent initier une licence exploratoire.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 368c4dace7a7ba14cb13f3a027b9d04ee63dc17b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119203"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a>Gérer la licence exploratoire Microsoft Teams

L’expérience Microsoft Teams Exploratory permet aux utilisateurs de Azure Active Directory (AAD) de votre organisation qui n’ont pas de licence Teams de lancer l’expérience de l’exploration de Teams. Les administrateurs peuvent activer ou désactiver cette fonctionnalité pour les utilisateurs de leur organisation. La précédente [Version d'évaluation dans le cloud commercial Microsoft]() est désormais remplacée par l'expérience exploratoire Teams.

> [!NOTE]
> La limite est de 100 licences Microsoft Teams pour chaque client.

## <a name="whats-in-the-teams-exploratory-experience"></a>Qu’est-ce que l’expérience exploratoire Teams ?

Les plans de service qu’un administrateur peut voir dans le cadre de l’expérience exploratoire Teams sont les suivants :

- Exchange Online (plan 1)
- Flux pour Microsoft 365 ou Office 365
- Informations obtenues par MyAnalytics
- Microsoft Forms (plan E1)
- Microsoft Planner
- Recherche Microsoft
- Microsoft StaffHub
- Microsoft Stream pour Microsoft 365 et Office 365 E1 SKU <sup>1</1>
- Microsoft Teams
- Gestion des appareils mobiles pour Microsoft 365 ou Office 365
- Applications Office Mobile pour Office 365
- Office Online
- PowerApp pour Microsoft 365 ou Office 365
- SharePoint Online (plan 1)
- Sway
- Tâches (plan 1)
- Tableau blanc (plan 1)
- Yammer Enterprise

  <sup>1</sup> Les modifications apportées à l’utilisation de Microsoft Stream pour [OneDrive Entreprise et SharePoint pour les enregistrements de réunion](tmr-meeting-recording-change.md) auront une approche progressive. Au démarrage, vous pourrez choisir cette expérience. En novembre, vous devrez abandonner cette option si vous souhaitez continuer à utiliser Stream. Au début de 2021, nous demanderons à tous les clients d’utiliser OneDrive Entreprise et SharePoint pour les nouveaux enregistrements de réunion.

## <a name="whos-eligible"></a>Critères d’éligibilité

Les utilisateurs éligibles à l’expérience Teams Exploratory sont les utilisateurs qui:

- Disposent d’une adresse e-mail du domaine Azure AD gérée.
- Appartiennent à un client disposant d’un abonnement payant.
- N’avez pas de licence Teams active.
- Ne se trouve pas dans un client où une stratégie d’attribution de licence a été créée.

Les utilisateurs doivent être autorisés à s’inscrire aux applications et aux essais (dans le Centre d’administration Microsoft 365). Pour plus d’informations, voir [Gérer l’expérience exploratoire Teams](#manage-the-teams-exploratory-experience) plus loin dans cet article.

## <a name="who-isnt-eligible"></a>Qui n'est pas éligible ?

Les utilisateurs inéligibles sont les utilisateurs qui :

- disposent ou ont disposé de Teams grâce à une licence payée, non payée ou d’évaluation ;
- se trouvent dans un client qui utilise ou a reçu au moins une offre spéciale COVID.

Votre organisation n’est pas éligible pour cette offre si vous êtes un client partenaire de syndication ou un client GCC, GCC élevé, DoD ou EDU.

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>Comment les utilisateurs s’inscrivent pour l’expérience exploratoire Teams ?

Les utilisateurs éligibles peuvent s’inscrire à l’expérience exploratoire Teams en se connectant à Teams à partir de l’ordinateur de bureau ou web ([teams.microsoft.com](https://teams.microsoft.com)). Pour l’instant, l’activation de exploratoire via mobile n’est pas prise en charge. Lorsqu’il s’inscrivent, la licence leur est attribuée automatiquement et l’administrateur client reçoit une notification par e-mail la première fois qu’une personne au sein de votre organisation démarre l’expérience Teams Exploratory.

## <a name="manage-the-teams-exploratory-experience"></a>Gérer l’expérience Teams Exploratory

L’expérience Teams Exploratory est destinée aux utilisateurs finaux individuels et vous ne pouvez pas lancer cette offre pour le compte d’employés de l’utilisateur final.

L’expérience Teams Exploratory est offerte avec une licence Exchange Online, mais elle ne peut être attribuée à l’utilisateur que par l’administrateur. Si l’utilisateur ne dispose pas déjà d’une licence Exchange et que l’administrateur ne lui a pas encore attribué la licence Exchange Online, l’utilisateur ne peut pas planifier de réunions dans Teams et pourrait manquer d’autres fonctionnalités Teams.

Les administrateurs peuvent désactiver la possibilité pour les utilisateurs finaux d’exécuter l’expérience exploratoire des équipes au sein de leur organisation à l’aide du commutateur des **applications et services d’essai**.

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Empêcher les utilisateurs d’installer des applications et services à l’essai

Vous pouvez désactiver la possibilité pour un utilisateur d’installer des applications et des services d’essai, ce qui l’empêche d’exécuter l’expérience exploratoire Teams.

1. Dans le Centre d’administration Microsoft 365, accédez à **Paramètres** > **Paramètres org**, sélectionnez **Services**, puis choisissez **Services et applications propriétés de l'utilisateur**.

    ![La page Services dans le Centre d’administration](media/iw-trial-services.png)

2. Désactivez la cache à cocher **Permettre aux utilisateurs d'installer les applications et services à l’essai**.

    ![L’Utilisateur dispose d’une page des applications et services dans le Centre d’administration](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Si votre organisation n’est pas éligible à l’expérience exploratoire Teams, l'option **Laisser les utilisateurs installer les applications et services d’essai** ne s’affiche pas.

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Gérer la disponibilité pour un utilisateur disposant d’une licence incluant Teams

Un utilisateur détenteur d’une licence incluant Team n’est pas admissible à l’expérience exploratoire Teams. Lorsque le plan de service Teams est activé, l’utilisateur peut se connecter et utiliser Teams. Si le plan de service est désactivé, l’utilisateur ne peut pas se connecter et l’expérience exploratoire Teams n’est pas disponible. Vous devez disposer de privilèges d’administrateur.

Pour désactiver l’accès à Microsoft Teams :

1. Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.

2. Activez la case à cocher située en regard du nom de l’utilisateur.

3. Sur la ligne **Licences de produits**, sélectionnez **Modifier**.

4. Dans le volet **Licences de produit**, sélectionnez **Désactivé**.

    ![la page Licences de produit dans le centre d’administration.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Gérer la disponibilité Teams pour les utilisateurs qui utilisent déjà l’expérience exploratoire Teams

Si un utilisateur exécute l’expérience exploratoire Teams, vous pouvez la désactiver en supprimant la licence ou le plan de service. Vous devez disposer de privilèges d’administrateur.

Pour désactiver la licence de l’expérience Teams Exploratory:

1. Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.

2. Activez la case à cocher située en regard du nom de l’utilisateur.

3. Sur la ligne **Licences de produits**, sélectionnez **Modifier**.

4. Dans le volet **Licences de produit**, sélectionnez **Désactivé** pour cette licence exploratoire.

    > [!NOTE]
    > Le commutateur de bascule exploratoire Teams apparaît une fois que le premier utilisateur de l’organisation a lancé l’expérience exploratoire Teams.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Gérer Teams pour les utilisateurs disposant d’une licence exploratoire Teams

Vous pouvez gérer les utilisateurs qui ont une licence exploratoire Teams de la même façon que vous gérez ceux qui ont une licence payante régulière. Pour plus d’informations[Gérer les paramètres de Teams pour votre organisation](enable-features-office-365.md).

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>Mettre à niveau les utilisateurs de la licence exploratoire Teams

Pour mettre à niveau les utilisateurs à partir de la licence Teams Exploratory, vous devez disposer de privilèges d’administrateur et procédez comme suit:

1. Achetez un abonnement incluant Teams.

2. Supprimez l’abonnement exploratoire Teams pour l’utilisateur en question.

3. Affectez la licence nouvellement achetée.

Pour plus d’informations, voir [Description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description).

> [!NOTE]
> Si la licence Teams Exploratory expire et l’utilisateur n’est pas immédiatement mis à niveau vers un abonnement comprenant Teams, ils disposent de 30 jours de délai de grâce, puis de 30 jours supplémentaires. Après ce délai les données sont supprimées. L’utilisateur demeure dans Azure Active Directory. Une fois qu’une nouvelle licence est attribuée à l’utilisateur pour réactiver la fonctionnalité Teams, tout le contenu reste en l’état si l’utilisateur est ajouté dans le cadre du délai de grâce.

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>Qu’arrive-t-il aux licences d’évaluation cloud commercial de Microsoft Teams?

À partir de février 2020, les utilisateurs éligibles peuvent commencer à utiliser l’expérience la plus récente de Microsoft Teams Exploratory. Toutes les versions d’évaluation du Cloud commercial sont automatiquement converties à la nouvelle offre avant l’expiration de la période d’évaluation.

Lorsqu'un utilisateur se connecte pour la première fois à la version d'évaluation cloud commercial de Teams expiré, nous lui attribuons automatiquement une licence d'expérience Teams Exploratory. Les utilisateurs ne sont pas convertis avant de s'être inscrits.

### <a name="remove-a-teams-exploratory-license"></a>Supprimer une licence exploratoire Teams

- Si vous souhaitez supprimer cette licence à l’aide PowerShell, voir [Supprimer des licences de comptes d’utilisateurs avec Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

- Si vous souhaitez supprimer cette licence via le portail d’administration, consultez : [Supprimer un utilisateur de votre organisation](/microsoft-365/admin/add-users/delete-a-user)

## <a name="what-is-the-data-retention-policy"></a>En quoi consiste la stratégie de conservation des données ?

Consultez [informations d’abonnement 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Combien de temps dure l’expérience d’exploration de Teams ?

A partir de début 2021, Teams exploratoire est disponible sous la forme d'un abonnement de 12 mois (à partir de l'inscription initiale de l'utilisateur) pour tous les nouveaux clients. Le nouvel abonnement Teams exploratoire démarre lorsque le premier utilisateur d’une organisation s’est abonné à Teams exploratoire et expirera au bout de 12 mois. La date d’expiration s’applique à tous les utilisateurs du même client. La période de 12 mois commence à la date d’inscription du premier utilisateur.

> [!NOTE]
> La date de fin de l’expérience est configurée au niveau de l’organisation, ce qui signifie qu’elle s’applique à tous les utilisateurs d’une même organisation. Par exemple, l’utilisateur 1 s’est abonné à l’abonnement le 1er janvier 2021. Cela déclenche la date de fin de l’abonnement le 31 décembre 2021. Un autre utilisateur, Utilisateur 2, s’est abonné à l’abonnement le 1er octobre 2021. L’utilisateur 2 peut utiliser Teams exploratoire pour deux mois, sa date de fin étant le 31 décembre 2021, car il est dans le cadre de l’abonnement de la même organisation que Utilisateur 1.

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a>Que doivent faire les administrateurs à la fin des 12 mois d’expérience Teams exploratoire

À la fin de l'abonnement de 12 mois, les administrateurs doivent convertir tous les utilisateurs de Teams exploratoire en une licence payante qui inclut Teams. Il est essentiel de s’assurer que cette opération se termine avant l’expiration de l’abonnement Teams exploratoire Pour éviter toute interruption de l’expérience de l’utilisateur.


> [!NOTE]
> Les clients seront désactivés et bloqués pour le démarrage d’une nouvelle licence d’évaluation de Exploratory pendant 3 mois après l’expiration de la licence d’évaluation Exploratory précédente.

Pour plus d’informations, consultez la rubrique [Mise à niveau des utilisateurs à partir de licence Teams exploratoire](#upgrade-users-from-the-teams-exploratory-license), plus haut dans cet article.