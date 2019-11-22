---
title: Publier des applications dans le catalogue d’applications client Microsoft teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Conseils pour la publication d’applications dans le catalogue d’applications client Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42fd9820f6f8ce11b245412a5ae99ed7b43dbc1e
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793530"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a>Publier des applications dans le catalogue d’applications client Microsoft teams
=======================================================

Vous pouvez utiliser le catalogue d’applications client Microsoft teams pour tester et distribuer des applications métier à votre organisation.

Le catalogue d’applications de locataire teams vous permet de distribuer des applications métier qui ont été spécifiquement développées pour votre organisation et dont vous avez l’assurance que vous vous bamettrez à effectuer les fonctions stratégiques de l’entreprise.

Pour publier des applications pour votre organisation, connectez-vous à votre client teams à l’aide d’un compte disposant des rôles d’administrateur général ou de service Teams, puis suivez les instructions ci-dessous.

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a>Publier une application dans le catalogue d’applications client à partir du client teams

> [!NOTE]
> Vous devez être connecté au client Microsoft teams avec un compte pour lequel le rôle d’administrateur général ou de service teams a été activé pour publier des applications pour votre organisation. En savoir plus sur [l’utilisation des rôles d’administrateur pour gérer teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).

### <a name="get-a-teams-app-package"></a>Obtenir un package d’application teams

Un package d’application teams est créé à l’aide de [teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Une fois le package d’application installé, vous pouvez l’ajouter au catalogue d’applications de l’entreprise. Même si tous les utilisateurs du client peuvent afficher le catalogue d’applications, seuls les administrateurs généraux et les administrateurs des services teams ont la possibilité de les publier et de les gérer.

### <a name="go-to-the-tenant-apps-catalog"></a>Accédez au catalogue des applications clientes.

Démarrez le client Microsoft Teams, puis connectez-vous à l’aide de vos informations d’identification d’administrateur de service global ou Teams. Sélectionnez **applications** dans la partie gauche de l’application, puis sélectionnez la nouvelle section intitulée pour votre organisation spécifique (dans cet exemple, contoso). Les utilisateurs de votre organisation peuvent afficher les applications dans le catalogue et les installer pour les équipes dont ils sont membres.

![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a>Ajouter une application au catalogue d’applications locataire

1. Dans la page **applications** , sélectionnez **Télécharger un** > **chargement d’application personnalisé pour Contoso**.

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image02.png)

    (Vous pouvez également choisir **Télécharger pour moi ou mes équipes**, qui s’appelle *chargement indépendant*. Chargement indépendant rend l’application disponible uniquement pour vos équipes ou pour les équipes que vous sélectionnez.)

2. Accédez au package d’application et sélectionnez-le, puis cliquez sur **ouvrir**.

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image03.png)

Lorsque vous revenez au catalogue d’applications de votre client, la nouvelle application d’entreprise est disponible. N’oubliez pas que seuls les membres de votre organisation et vous avez accès à ce catalogue d’applications.

### <a name="update-an-app-in-the-tenant-apps-catalog"></a>Mise à jour d’une application dans le catalogue des applications clientes

1. Dans le catalogue d’applications de votre client, sélectionnez «**...**» dans le coin supérieur droit de l’application que vous voulez mettre à jour.

2. Accédez au package d’application mis à jour, sélectionnez-le, puis cliquez sur **ouvrir**.

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image04.png)

L’application sera révisée vers la version 2,0. Vous pouvez également supprimer l’application pour votre entreprise dans le menu.

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a>Utiliser le portail d’administration Office 365 pour gérer le catalogue des applications clientes

Si vous avez des applications qui nécessitent des corrections de bogues, vous pouvez désactiver temporairement les applications par le biais du > Centre d’administration 365 de Microsoft **teams** > , ainsi que les**stratégies d’autorisations** **applications** >  > <le nom de la stratégie, par exemple, « global (par défaut de l’organisation par défaut) » > les **applications clientes** > bloquer certaines applications et ajouter votre application à la liste.

![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image05.png)

La désactivation d’une application empêche les utilisateurs d’interagir avec celle-ci, sans supprimer entièrement l’application. Ces contrôles vous offrent une plus grande souplesse et contrôle lors de la gestion des applications dans votre entreprise.
