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
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef709e18627fb8a07f207f736440fa89f5110f0e
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203807"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>Gérer la licence exploratoire Microsoft Teams
=======================================================

L’expérience exploratoire Microsoft Teams permet aux utilisateurs au sein de votre organisation d’Azure Active Directory (AAD) et de ne pas être licenciés pour Teams de lancer une expérience exploratoire de Teams. Les administrateurs peuvent activer ou désactiver cette fonctionnalité pour les utilisateurs de leur organisation. La précédente [Version d'évaluation dans le cloud commercial Microsoft](iw-trial-teams.md) est désormais remplacée par l'expérience exploratoire Teams.

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

   <sup>1</sup> Les modifications apportées à l’utilisation de Microsoft Stream pour [OneDrive Entreprise et SharePoint pour les enregistrements de réunion](tmr-meeting-recording-change.md) auront une approche progressive. Au moment du lancement, vous pourrez choisir de participer à cette expérience. En novembre, vous devrez vous désengager si vous souhaitez continuer à utiliser Stream et début 2021, nous demanderons à tous les clients d'utiliser OneDrive Entreprise et SharePoint pour les nouveaux enregistrements de réunions.

## <a name="whos-eligible"></a>Qui est éligible ?

Tant que l'utilisateur possède une adresse e-mail de domaine géré AAD et qu'il ne dispose pas ou n'a pas encore reçu de licence Teams, il peut bénéficier de cette expérience. Par exemple, un utilisateur disposant d’une licence des Applications Microsoft 365 pour les entreprises (n’incluant pas Teams) est éligible à l’expérience exploratoire Teams.

Les utilisateurs doivent être autorisés à s’inscrire aux applications et aux essais (dans le Centre d’administration Microsoft 365). Pour plus d’informations, voir [Gérer l’expérience exploratoire Teams](#manage-the-teams-exploratory-experience) plus loin dans cet article.

## <a name="who-isnt-eligible"></a>Qui n'est pas éligible ?

Votre organisation n’est pas éligible pour cette offre si vous êtes un client partenaire de syndication ou un client GCC, GCC élevé, DoD ou EDU.

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>Comment les utilisateurs s’inscrivent pour l’expérience exploratoire Teams ?

Les utilisateurs éligibles peuvent s’inscrire à l’expérience exploratoire Teams en se connectant à Teams ([teams.microsoft.com](https://teams.microsoft.com)). Celle-ci se voit attribuer automatiquement cette licence et l’administrateur du client reçoit une notification par e-mail la première fois qu’une personne au sein de votre organisation démarre l’expérience exploratoire Teams.

## <a name="manage-the-teams-exploratory-experience"></a>Gérer l’expérience d’exploration de Teams

L’expérience exploratoire Teams est destinée aux utilisateurs finaux individuels et vous ne pouvez pas lancer cette offre pour le compte d’employés de l’utilisateur final.

L’expérience exploratoire Teams est fournie avec une licence Exchange Online, mais elle n’est pas attribuée à l’utilisateur tant que l’administrateur ne l’aura pas affecté. Si l’utilisateur ne dispose pas déjà d’une licence Exchange et que l’administrateur n’a pas encore attribué de licence Exchange Online, l’utilisateur ne peut pas planifier de réunions dans Teams et peut-être qu’il manque d’autres fonctionnalités Teams.

Les administrateurs peuvent désactiver la possibilité pour les utilisateurs finaux d’exécuter l’expérience exploratoire des équipes au sein de leur organisation à l’aide du commutateur des **applications et services d’essai**.

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Empêcher les utilisateurs d’installer des applications et services à l’essai

Vous pouvez désactiver la possibilité pour un utilisateur d’installer des applications et des services d’essai, ce qui l’empêche d’exécuter l’expérience exploratoire Teams.

1. Dans le Centre d’administration Microsoft 365, accédez à **Paramètres** > **Paramètres org**, sélectionnez **Services**, puis choisissez **Services et applications propriétés de l'utilisateur**.

    ![Capture d’écran de la page Services dans le Centre d’administration](media/iw-trial-services.png)

2. Désactivez la cache à cocher **Permettre aux utilisateurs d'installer les applications et services à l’essai**.

    ![Capture d’écran de la page des applications et services appartenant à l’utilisateur dans le Centre d’administration](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > Si votre organisation n’est pas éligible à l’expérience exploratoire Teams, l'option **Laisser les utilisateurs installer les applications et services d’essai** ne s’affiche pas.

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Gérer la disponibilité pour un utilisateur disposant d’une licence incluant Teams

Un utilisateur détenteur d’une licence incluant Team n’est pas admissible à l’expérience exploratoire Teams. Lorsque le plan de service Teams est activé, l’utilisateur peut se connecter et utiliser Teams. Si le plan de service est désactivé, l’utilisateur ne peut pas se connecter et l’expérience exploratoire Teams n’est pas disponible. Vous devez disposer de privilèges d’administrateur.

Pour désactiver l’accès à Microsoft Teams :

1. Dans le centre d’administration Microsoft 365, sélectionnez **Utilisateurs** > **Utilisateurs actifs**.

2. Activez la case à cocher située en regard du nom de l’utilisateur.

3. Sur la droite, dans la ligne **Licences de produits**, sélectionnez **Modifier**.

4. Dans le volet **Licences de produit**, sélectionnez **Désactivé**.

    ![Capture d’écran de la section Licences dans le centre d’administration.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Gérer la disponibilité Teams pour les utilisateurs qui utilisent déjà l’expérience exploratoire Teams

Si un utilisateur exécute l’expérience exploratoire Teams, vous pouvez la désactiver en supprimant la licence ou le plan de service. Vous devez disposer de privilèges d’administrateur.

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

Pour mettre à niveau des utilisateurs de la licence exploratoire Teams (vous devez disposer de privilèges d’administrateur), procédez comme suit :

1. Achetez un abonnement incluant Teams.

2. Supprimez l’abonnement exploratoire Teams pour l’utilisateur en question.

3. Affectez la licence nouvellement achetée.

Pour plus d’informations, voir [Description du service Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

> [!NOTE]
> Si la licence exploratoire Teams se termine et un utilisateur n’est pas immédiatement mis à jour vers un abonnement qui inclut Teams, les données des utilisateurs ne sont pas supprimées. L’utilisateur existe toujours dans Azure Active Directory et toutes les données au sein de Teams sont disponibles. Une fois qu’une nouvelle licence est attribuée à l’utilisateur pour activer la fonctionnalité Teams de nouveau, tout le contenu existera encore.

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>Qu’arrive-t-il aux licences d’évaluation cloud commercial de Microsoft Teams ?

À compter de février 2020, les utilisateurs qualifiés peuvent commencer à utiliser la dernière expérience exploratoire de Microsoft Teams. Toutes les versions d’évaluation du Cloud commercial sont automatiquement converties à la nouvelle offre avant l’expiration de la période d’évaluation.

Lorsqu'un utilisateur se connecte pour la première fois à sa version d'évaluation commerciale du cloud Teams qui a expiré, nous lui attribuons automatiquement une licence d'expérience Teams Exploratory. Les utilisateurs ne sont pas convertis avant de s'être inscrits.

### <a name="remove-a-teams-exploratory-license"></a>Supprimer une licence exploratoire Teams

- Si vous souhaitez supprimer cette licence à l’aide PowerShell, voir [Supprimer des licences de comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell).

- Si vous souhaitez supprimer cette licence via le portail d’administration, consultez : [Supprimer un utilisateur de votre organisation](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Combien de temps dure l’expérience d’exploration de Teams ?

L’expérience Microsoft Teams Exploratory est disponible sans frais supplémentaires jusqu’à la prochaine **date anniversaire** ou au prochain **renouvellement** de votre contrat d’entreprise survenant à compter du mois de janvier 2021. À ce stade, les utilisateurs finaux ayant une licence d’expérience exploratoire Microsoft doivent migrer vers une licence payante incluant Teams. Toutes les licences d’expérience exploratoire Microsoft commencées après cette période resteront valables sans frais supplémentaires jusqu’au prochain cycle **anniversaire** ou de **renouvellement**.

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a>Que se passe-t-il si un utilisateur final lance l'expérience Microsoft Teams Exploratory juste avant ma date d'anniversaire ou de renouvellement

Les licences de l’expérience Microsoft Teams Exploratory initiées dans le délai de 90 jours de la **date anniversaire** ou du **renouvellement** de votre contrat d’entreprise n’auront pas à migrer vers une licence payante avant le prochain cycle anniversaire ou de renouvellement.

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a>Que se passe-t-il si mon contrat ne possède pas de date de anniversaire ou de renouvellement annuel (par exemple, des contrats de mois à mois)

Pour les contrats qui n’ont pas de date de anniversaire ou de renouvellement annuel, l’année suivante après l’activation du premier utilisateur de la licence exploratoire Microsoft Teams est traitée comme la date anniversaire ou la date de renouvellement. Les utilisateurs de la licence exploratoire Microsoft Teams doivent être convertis en licence payante chaque année, conformément aux stratégies décrites ci-dessus.

Par exemple, si le premier utilisateur final active Microsoft Teams exploratoire le 19 juin 2020, les utilisateurs éligibles et tous les autres utilisateurs éligibles du locataire client doivent effectuer une conversion vers une licence payante avec Teams avant le 19 juin 2021.
