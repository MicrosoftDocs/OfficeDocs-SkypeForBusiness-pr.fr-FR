---
title: Publier des applications dans le catalogue d’applications client Microsoft teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Conseils pour la publication d’applications dans le catalogue d’applications client Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161613"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a>Publier des applications dans le catalogue d’applications client Microsoft teams
=======================================================

Vous pouvez utiliser le catalogue d’applications client de Microsoft teams pour tester et distribuer des applications métier à votre organisation.

Le catalogue d’applications client teams vous permet de distribuer des applications métier qui ont été spécifiquement développées pour votre organisation et dont vous avez l’assurance que vous vous fierez aux fonctions stratégiques de l’entreprise.

Pour publier des applications pour votre organisation, connectez-vous au client teams en utilisant un compte doté du rôle administrateur général ou service d’équipe, puis suivez les étapes décrites ci-dessous.

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a>Publier une application dans le catalogue d’applications client à partir du client teams

> [!NOTE]
> Ces étapes décrivent la publication d’une application à l’aide du client Teams. Vous pouvez également publier une application sur la page **gérer les applications** dans le centre d’administration Microsoft Teams. Pour en savoir plus, voir [gérer les applications dans teams](manage-apps.md).

### <a name="get-a-teams-app-package"></a>Obtenir un package d’application teams

Un package d’application teams est créé à l’aide de [teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Une fois le package d’application installé, vous pouvez l’ajouter au catalogue d’applications du client. Même si tous les utilisateurs de votre organisation peuvent afficher le catalogue d’applications, seuls les administrateurs généraux et les administrateurs des services teams ont la possibilité de les publier et de les gérer.

### <a name="go-to-the-tenant-app-catalog"></a>Accédez au catalogue d’applications du client.

Démarrez teams et connectez-vous à l’aide de vos informations d’identification d’administrateur de service ou d’équipe globale. Sélectionnez **applications** dans la partie gauche de l’application, puis sélectionnez la nouvelle section intitulée pour votre organisation spécifique (dans cet exemple, contoso). Les utilisateurs de votre organisation peuvent afficher les applications dans le catalogue et les installer pour les équipes dont ils sont membres.

![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a>Ajouter une application au catalogue d’applications du client

1. Dans la page **applications** , sélectionnez **Télécharger un** > **chargement d’application personnalisé pour Contoso**.

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image02.png)

    (Vous pouvez également choisir **Télécharger pour moi ou mes équipes**, qui s’appelle *chargement indépendant*. Chargement indépendant rend l’application disponible uniquement pour vos équipes ou pour les équipes que vous sélectionnez.)

2. Accédez au package d’application et sélectionnez-le, puis cliquez sur **ouvrir**.

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image03.png)

Lorsque vous revenez à votre catalogue d’applications client, la nouvelle application d’entreprise est disponible. N’oubliez pas que seuls les membres de votre organisation et vous avez accès à ce catalogue d’applications.

### <a name="update-an-app-in-the-tenant-app-catalog"></a>Mise à jour d’une application dans le catalogue d’applications du client

1. Dans le catalogue d’applications de votre client, sélectionnez «**...**» dans le coin supérieur droit de l’application que vous voulez mettre à jour.

2. Accédez au package d’application mis à jour, sélectionnez-le, puis cliquez sur **ouvrir**.

    ![Capture d’écran du magasin d’applications teams montrant le catalogue d’applications.](media/private-app-store-teams-image04.png)

L’application sera révisée vers la version 2,0. Vous pouvez également supprimer l’application pour votre entreprise dans le menu.

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a>Utiliser le centre d’administration de Microsoft teams pour gérer le catalogue d’applications locataire

Si vous avez des applications qui ont besoin de résolutions de bogues, vous pouvez désactiver temporairement les applications pour les utilisateurs dans une stratégie d’autorisation d’application.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à > **stratégies d’autorisations**des **applications teams**.
2. Sélectionnez la stratégie d’autorisation d’application que vous voulez modifier, puis cliquez sur **modifier**.
3. Sous **applications clientes**, sélectionnez **bloquer des applications spécifiques et autoriser tous les autres**, puis ajoutez les applications que vous souhaitez bloquer.

La désactivation d’une application interdit aux utilisateurs d’interagir avec celle-ci, sans supprimer entièrement l’application. Ces contrôles vous offrent une plus grande souplesse et contrôle lors de la gestion des applications au sein de votre organisation.

Pour en savoir plus, voir [gérer les stratégies d’autorisation d’applications dans Microsoft teams](teams-app-permission-policies.md).