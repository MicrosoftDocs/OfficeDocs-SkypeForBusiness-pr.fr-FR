---
title: Gérer vos applications personnalisées dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment emporter vos applications teams personnalisées du développement au déploiement.
ms.openlocfilehash: 8166ba6b46853510a9f4e966ddca4e5b8686b551
ms.sourcegitcommit: a09334ef1a6b0a877839c3b46165eb5a6aad1ba9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/02/2020
ms.locfileid: "44006053"
---
# <a name="manage-your-custom-apps-in-microsoft-teams"></a>Gérer vos applications personnalisées dans Microsoft teams

Cet article fournit des instructions complètes sur la façon de mettre votre application teams en fin de développement. Ce guide est axé sur les aspects de l’application équipes et est destiné aux professionnels de l’informatique. Pour plus d’informations sur le développement d’applications Teams, voir <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">ici</a>.

![Vue d’ensemble de votre application du développement au déploiement](media/manage-your-lob-apps.png)

## <a name="getting-started"></a>Prise en main

Pour créer et gérer des applications personnalisées dans Teams, vous devez disposer de deux clients : un client de test pour le développement et un client de production.

> [!NOTE]
> Si vous n’avez pas encore de client de test, vous pouvez en créer un rapidement et le remplir avec des données de test à l’aide du programme développeurs d’Office 365. <a href="https://developer.microsoft.com/office/dev-program" target="_blank">En savoir plus ici</a>.

## <a name="step-1-develop-and-test"></a>Étape 1 : développement et test

### <a name="create-test-users"></a>Créer des utilisateurs test

Assurez-vous que vos développeurs, que vous soyez en interne ou en externe, disposent de comptes dans votre client de test. <a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">En savoir plus sur l’ajout d’utilisateurs</a>.

### <a name="allow-custom-apps-in-the-test-tenant"></a>Autoriser les applications personnalisées dans le client de test

Pour offrir aux développeurs l’accès nécessaires aux tests, autorisez tous les utilisateurs du client de test à télécharger des applications personnalisées (également appelées chargement indépendant). Cela permet aux développeurs de télécharger une application personnalisée à utiliser personnellement ou sur le client de test sans avoir à envoyer l’application au magasin des applications Teams. Le chargement d’une application personnalisée permet aux développeurs de tester une application avant de la distribuer plus fréquemment.

Pour autoriser les utilisateurs à télécharger des applications personnalisées, procédez comme suit :

1. Activez le paramètre **autoriser l’interaction avec les applications personnalisées** à l’échelle de l’organisation. Pour ce faire :
    1. Dans le volet de navigation de gauche du <a href="https://admin.teams.microsoft.com/" target="_blank">Centre d’administration de Microsoft teams</a>, accédez à **teams** > **Manage Apps**, puis cliquez sur **paramètres de l’application à l’échelle**de l’organisation.
    2. Sous **applications personnalisées**, activez **autoriser l’interaction avec les applications personnalisées**, puis cliquez sur **Enregistrer**.

    ![Capture d’écran du paramètre « autoriser l’interaction avec les applications personnalisées » dans l’Organisation](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. Activez le paramètre **Télécharger des applications personnalisées** dans la stratégie de configuration de l’application globale. Pour ce faire :
    1. Dans le volet de navigation de gauche du <a href="https://admin.teams.microsoft.com/" target="_blank">Centre d’administration de Microsoft teams</a>, accédez à stratégies de configuration des **applications** > **d'** équipe, puis cliquez sur la stratégie **globale par défaut** de l’organisation.
    2. Activez **Télécharger les applications personnalisées**, puis cliquez sur **Enregistrer**.

    ![Capture d’écran du paramètre de stratégie « télécharger des applications personnalisées »](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> Il existe également un paramètre charger une application personnalisée au niveau de l’équipe. Par défaut, ce paramètre est activé. Toutefois, si les développeurs ne peuvent pas télécharger une application personnalisée dans une équipe, vérifiez le paramètre en suivant les <a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">étapes ci-dessous.</a>

### <a name="create-your-app"></a>Créer votre application

Les développeurs doivent maintenant avoir ce dont ils ont besoin pour créer votre application. Pour plus d’informations, consultez cette <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">page</a> .

## <a name="step-2-validate-in-production"></a>Étape 2 : valider en production

### <a name="get-the-app-package"></a>Télécharger le package de l’application

Lorsque l’application est prête à être utilisée en production, le développeur doit produire un package d’application. Ils peuvent utiliser <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">app Studio</a> pour cela. Elle vous envoie le fichier au format. zip.

Microsoft utilise <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">ces instructions</a> pour s’assurer de la conformité des applications avec les normes de qualité et de sécurité du magasin des applications globales Teams.

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a>Permettre aux utilisateurs approuvés de télécharger des applications personnalisées dans le client de production

Pour vérifier que l’application fonctionne correctement dans votre client de production, vous devez permettre aux utilisateurs approuvés de votre organisation de télécharger des applications personnalisées.  À l’instar de l' <a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">étape</a>précédente, vous utilisez des stratégies de configuration d’application pour cela.

> [!NOTE]
> Si vous n’avez pas l’habitude de télécharger l’application sur votre client de production pour la validation, même pour les utilisateurs vous-même ou approuvés, vous pouvez ignorer cette étape et suivre les étapes 3 et 4 pour télécharger l’application non validée sur votre magasin d’applications client. Restreignez ensuite l’accès à cette application uniquement et aux utilisateurs approuvés. Ces utilisateurs peuvent ensuite obtenir l’application à partir du magasin d’applications du client pour effectuer la validation. Une fois l’application validée, utilisez les mêmes stratégies d’autorisation pour ouvrir Access et annuler l’application en vue d’une utilisation en production.

Pour permettre aux utilisateurs approuvés de télécharger des applications personnalisées, procédez comme suit :

1. Activez le paramètre **autoriser l’interaction avec les applications personnalisées** à l’échelle de l’organisation. Pour ce faire :
    1. Dans le volet de navigation de gauche du <a href="https://admin.teams.microsoft.com/" target="_blank">Centre d’administration de Microsoft teams</a>, accédez à **teams** > **Manage Apps**, puis cliquez sur **paramètres de l’application à l’échelle**de l’organisation.
    2. Sous **applications personnalisées**, activez **autoriser l’interaction avec les applications personnalisées**, puis cliquez sur **Enregistrer**.
2. Désactivez le paramètre **Télécharger des applications personnalisées** de la stratégie de configuration de l’application globale. Pour ce faire :
    1. Dans le volet de navigation de gauche du <a href="https://admin.teams.microsoft.com/" target="_blank">Centre d’administration de Microsoft teams</a>, accédez à stratégies de configuration des **applications** > **d'** équipe, puis cliquez sur la stratégie **globale par défaut** de l’organisation.
    2. Désactivez l’option **Télécharger les applications personnalisées**, puis cliquez sur **Enregistrer**.
3. Créez une stratégie de configuration de l’application qui permet le téléchargement d’applications personnalisées et l’attribution à votre ensemble d’utilisateurs approuvés. Pour ce faire :
    1. Dans le volet de navigation de gauche du <a href="https://admin.teams.microsoft.com/" target="_blank">Centre d’administration de Microsoft teams</a>, accédez à**stratégies de configuration**des **applications** > d’équipe, puis cliquez sur **Ajouter**. Donnez un nom et une description à la nouvelle stratégie, activez l' **application télécharger des applications personnalisées**, puis cliquez sur **Enregistrer**.
    2. Sélectionnez la nouvelle stratégie que vous avez créée, puis cliquez sur **gérer les utilisateurs**. Recherchez un utilisateur, cliquez sur **Ajouter**, puis sur **appliquer**. Répétez cette étape pour affecter la stratégie à l’ensemble de vos utilisateurs approuvés.

        ![Capture d’écran de la page « Ajouter une stratégie de configuration de l’application »](media/manage-your-lob-apps-new-app-setup-policy.png)

    Ces utilisateurs peuvent désormais télécharger le manifeste de l’application pour vérifier que l’application fonctionne correctement dans le client de production.

## <a name="step-3-upload-to-the-tenant-app-catalog"></a>Étape 3 : charger vers le catalogue d’applications du client

Pour mettre l’application à la disposition des utilisateurs dans le magasin d’applications du client, téléchargez l’application. Vous pouvez le faire dans la page [gérer les applications](manage-apps.md) du centre d’administration Microsoft Teams.

![Capture d’écran de la page gérer les applications dans le centre d’administration](media/manage-your-lob-apps-upload-new-app.png)

## <a name="step-4-configure-and-assign-permissions"></a>Étape 4 : configurer et affecter des autorisations

### <a name="control-access-to-the-app"></a>Contrôler l’accès à l’application

Par défaut, tous les utilisateurs ont accès à cette application dans le magasin des applications Teams. Pour restreindre et contrôler les personnes autorisées à utiliser l’application, vous pouvez créer et affecter une nouvelle stratégie d’autorisation d’application. Suivez les étapes <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">ci-dessous</a>.

![Capture d’écran de la page « stratégie d’autorisation d’ajout d’application »](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a>Épingler l’application à découvrir

Par défaut, pour que les utilisateurs puissent trouver cette application, ils doivent accéder au magasin d’applications teams et parcourir ou Rechercher le fichier. Pour permettre aux utilisateurs d’accéder facilement à l’application, vous pouvez épingler l’application à la barre de l’application dans Teams. Pour ce faire, créez une nouvelle stratégie de configuration d’application et attribuez-la à des utilisateurs. Suivez les étapes <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">ci-dessous</a>.

![Capture d’écran du volet « ajouter des applications épinglées »](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a>Étape 5 : mettre à jour l’application

![Vue d’ensemble de votre application du développement au déploiement](media/manage-your-lob-apps-update.png)

Pour mettre à jour une application, les développeurs doivent continuer à suivre les [étapes 1](#step-1-develop-and-test) et [2](#step-2-validate-in-production).

Vous pouvez mettre à jour l’application via le catalogue d’applications du client. Pour ce faire, dans le centre d’administration de Microsoft Teams, accédez à **teams** > **Manage**apps. Dans la liste des applications, cliquez sur le nom de l’application, puis sur **mettre à jour**. Le fait de procéder au remplacement de l’application existante dans le catalogue d’applications du client et à l’ensemble des stratégies d’autorisation et de configuration de l’application reste en vigueur pour l’application mise à jour.

### <a name="end-user-update-experience"></a>Mise à jour des utilisateurs finaux

Dans la plupart des cas, une fois que vous avez effectué une mise à jour de l’application, la nouvelle version s’affiche automatiquement pour les utilisateurs finaux. Il y a toutefois des mises à jour du <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">manifeste Microsoft teams</a> qui nécessitent l’acceptation de l’utilisateur :

* un bot a été ajouté ou supprimé
* modification de la propriété « botId » d’une bot existante
* modification de la propriété « isNotificationOnly » d’une bot existante
* la propriété « supportsFiles » du bot a changé
* ajout ou suppression d’une extension de messagerie
* un nouveau connecteur a été ajouté.
* un nouvel onglet statique a été ajouté.
* un nouvel onglet configurable a été ajouté.
* Propriétés dans « webApplicationInfo » modifiées

## <a name="related-apps"></a>Applications associées

- [Gérer vos applications dans le centre d’administration Microsoft teams](manage-apps.md)
