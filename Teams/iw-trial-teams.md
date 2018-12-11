---
title: Gérer l'offre d’évaluation de cloud commercial Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/10/2018
ms.topic: article
audience: Admin
ms.reviewer: annikaelias
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
description: Les utilisateurs Office 365 qui ne sont pas une licence de Microsoft Teams peuvent lancer une version d’évaluation de 1 an d’équipes.
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: dc0b62ce0be0606ad4c31d3cee04347729fbbe32
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27214580"
---
<a name="manage-the-microsoft-teams-commercial-cloud-trial-offer"></a>Gérer l'offre d’évaluation de cloud commercial Microsoft Teams
=======================================================

Microsoft Teams est un excellent outil de collaboration pour votre organisation. Il permet aux personnes et aux équipes de discuter, innover et partager des idées à l’aide de la puissance d’Office 365. Les équipes commerciales Cloud version d’évaluation Microsoft offre Office 365 les utilisateurs existants dans votre organisation qui ne sont pas une licence de Microsoft Teams initier une version d’évaluation de 1 an du produit. Administrateurs peuvent passer cette fonctionnalité activé ou désactivé pour les utilisateurs dans leur organisation.

## <a name="whats-in-the-offer"></a>Nouveautés de l’offre

Les plans de service inclus dans cette offre sont les suivants :

- Foundation Exchange
- Flux pour Office 365 Plan 1
- Planificateur de Microsoft
- Équipes Microsoft (Teams1, équipes travailleur de l’information)
- Office Online
- PowerApps pour Office 365 Plan 1
- SharePoint Online Kiosk
- Balancement
- Yammer Enterprise

La version d’évaluation accorde à un abonnement d’évaluation d’un an dans toute l’organisation. La version d’évaluation permet de 500 000 licences disponibles pour l’affectation. Pour chaque licence est attribuée, la version d’évaluation alloue 2 Go de stockage SharePoint Online. 

## <a name="who-is-eligible"></a>Qui est éligible

Les utilisateurs doivent être activés pour s’inscrire pour les applications et versions d’évaluation (dans le centre d’administration Office 365). Pour plus d’informations, voir [Gérer la version d’évaluation](#manage-the-trial) plus loin dans cet article. 

Les utilisateurs qui ne possèdent pas d’une licence Office 365 qui inclut les équipes peuvent lancer l’offre d’évaluation de Cloud Microsoft équipes commerciale. Par exemple, si un utilisateur a Office 365 entreprise (qui n’inclut pas les équipes), ils sont éligibles pour la version d’évaluation.

## <a name="who-is-not-eligible"></a>Qui ne bénéficie pas

Votre organisation n’est pas éligible pour la version d’évaluation if : 

- Vous êtes un client de partenaire de Syndication
- Vous êtes un client de partenaire revendeur
- Vous êtes un client pour le gouvernement ou EDU

Si votre organisation n’est pour la Microsoft équipes commerciales Cloud d’évaluation, vous ne verrez pas le commutateur **aux utilisateurs d’installer les services et applications d’évaluation** .

## <a name="how-users-sign-up-for-the-trial"></a>Comment les utilisateurs s’inscrire à la version d’évaluation

Utilisateurs peuvent s’inscrire pour la version d’évaluation en vous connectant à équipes ([teams.microsoft.com](https://teams.microsoft.com)). Ils peuvent voir l’écran suivant pour démarrer la version d’évaluation. 

![Capture d’écran de la page de démarrage pour la version d’évaluation des équipes travailleur de l’information.](media/iw-trial-start-screen.png)

Toutes les versions d’évaluation de votre organisation partagent les mêmes début et les dates de fin qui correspond à la date du premier utilisateur inscrits pour la version d’évaluation. Par exemple, si l’utilisateur A commence à la première version d’évaluation sur le 25 janvier 2019 et l’utilisateur B une version d’évaluation sur 3 juin 2019, version d’évaluation de deux utilisateurs expire 2020 25 janvier.

## <a name="manage-the-trial"></a>Gérer la version d’évaluation

Administrateurs peuvent gérer les licences pour les utilisateurs qui ont été inscrits. 

En outre, les administrateurs peuvent désactiver la capacité pour les utilisateurs finaux demander des applications d’évaluation et services au sein de leur organisation. Actuellement, la version d’évaluation décrite dans cet article est uniquement trial dans cette catégorie, mais il peut s’appliquer à d’autres programmes similaires à l’avenir. 

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>Empêcher les utilisateurs d’installer les services et applications d’évaluation

Vous pouvez désactiver la capacité d’un utilisateur à installer les services et applications d’évaluation.

1. À partir du [Centre d’administration Microsoft 365](https://portal.office.com/adminportal/home), accédez à **paramètres** > **Services et compléments** > **utilisateur propriétaire des applications et Services**.

    ![Capture d’écran de la page Services et des compléments dans le centre d’administration d’Office 365.](media/iw-trial-enable-1.png)

2. Désactivez l’option **laisser les utilisateurs installer les services et applications d’évaluation**.

    ![Capture d’écran de l’utilisateur appartient la page Services et applications dans le centre d’administration d’Office 365.](media/iw-trial-enable-2.png)


### <a name="manage-trial-availability-for-a-user-with-a-license-that-includes-teams"></a>Gérer la disponibilité d’évaluation pour un utilisateur avec une licence qui inclut des équipes

Un utilisateur qui est attribué une licence qui inclut des équipes n’est pas éligible pour la version d’évaluation. Lorsque le plan de service équipes est activé, l’utilisateur peut se connecter et utiliser des équipes. Si le plan de service est désactivé, l’utilisateur ne peut pas se connecter et n’est pas présentée soit avec l’option d’évaluation.

Pour désactiver l’accès aux équipes :

1. Dans le centre d’administration Microsoft 365, sélectionnez **utilisateurs** > **utilisateurs actifs**.

2. Activez la case en regard du nom de l’utilisateur.

3. Sur la droite, dans la ligne de **licences** , choisissez **Modifier**.

4. Dans le volet de **licences de produits** , basculez la bascule à **désactiver**.

    ![Capture d’écran de la page licences de produits dans le centre d’administration d’Office 365.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-already-claimed-the-trial"></a>Administrer la disponibilité des équipes pour les utilisateurs ayant déjà demandé la version d’évaluation

Si un utilisateur a demandé une licence d’évaluation d’équipes, vous pouvez la supprimer en supprimant le plan de licence ou le service.

Pour désactiver la licence d’évaluation :

1. Dans le centre d’administration Microsoft 365, sélectionnez **utilisateurs** > **utilisateurs actifs**.

2. Activez la case en regard du nom de l’utilisateur.

3. Sur la droite, dans la ligne de **licences** , choisissez **Modifier**.

4. Dans le volet de **licences de produits** , basculez la bascule à **désactiver**.

    ![Capture d’écran du paramètre de licence d’évaluation d’équipes dans le volet de licences produit](media/iW-trial-enable-4.png)

### <a name="manage-teams-for-users-who-have-the-trial-license"></a>Gérer les équipes pour les utilisateurs qui disposent de la licence d’évaluation

Vous pouvez gérer les utilisateurs qui possèdent une licence d’évaluation comme vous gérez les utilisateurs qui possèdent une licence payante régulière. Pour plus d’informations, voir [fonctionnalités de gestion des équipes Microsoft dans votre organisation Office 365](enable-features-office-365.md).

### <a name="upgrade-users-from-the-trial-license"></a>Mise à niveau à partir de la licence d’évaluation

Pour mettre à niveau des utilisateurs à partir de la licence d’évaluation, procédez comme suit :

1. Acheter un abonnement qui inclut des équipes.

2. Supprimer l’abonnement d’évaluation équipes de l’utilisateur.

3. Attribuer la licence récemment acquis.

Pour plus d'informations, reportez-vous à la rubrique [Licence Office 365 pour Microsoft Teams](Office-365-licensing.md).