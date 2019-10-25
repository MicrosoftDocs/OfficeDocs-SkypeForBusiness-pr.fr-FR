---
title: Gérer vos applications métier dans Microsoft teams
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
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment emporter vos applications teams personnalisées du développement au déploiement.
ms.openlocfilehash: cd64ff0a3307ada0f1fbfaf29b94cfcd1da3c0df
ms.sourcegitcommit: d6a0ff7f00defda2b58726f5f0f0fac871f46ab7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2019
ms.locfileid: "37682704"
---
# <a name="manage-your-line-of-business-apps-in-microsoft-teams"></a>Gérer vos applications métier dans Microsoft teams

Cet article fournit des instructions complètes sur la façon de mettre votre application teams en fin de développement. Ce guide est axé sur les aspects de l’application équipes et est destiné aux professionnels de l’informatique. Pour plus d’informations sur le développement d’applications Teams, voir [ici](https://docs.microsoft.com/microsoftteams/platform).

![Vue d’ensemble de votre application du développement au déploiement](media/manage-your-lob-apps.png)

## <a name="getting-started"></a>Prise en main

Pour créer et gérer des applications métier dans Teams, vous devez disposer de deux clients : un client de test pour le développement et un client de production.

> [!NOTE]
> Si vous n’avez pas encore de client de test, vous pouvez en créer un rapidement et le remplir avec des données de test à l’aide du programme développeurs d’Office 365. [En savoir plus ici](https://developer.microsoft.com/office/dev-program).

## <a name="step-1-develop-and-test"></a>Étape 1 : développement et test

### <a name="create-test-users"></a>Créer des utilisateurs test

Assurez-vous que vos développeurs, que vous soyez en interne ou en externe, disposent de comptes dans votre client de test. [En savoir plus sur l’ajout d’utilisateurs](https://docs.microsoft.com/office365/admin/add-users/add-users).

### <a name="allow-custom-apps-in-the-test-tenant"></a>Autoriser les applications personnalisées dans le client de test

Pour offrir aux développeurs l’accès nécessaires aux tests, autorisez tous les utilisateurs du client de test à télécharger des applications personnalisées (également appelées chargement indépendant). Cela permet aux développeurs de télécharger une application personnalisée à utiliser personnellement ou sur le client de test sans avoir à envoyer l’application au magasin des applications Teams. Le chargement d’une application personnalisée permet aux développeurs de tester une application avant de la distribuer plus fréquemment.

Pour autoriser les utilisateurs à télécharger des applications personnalisées, procédez comme suit :

1. Activez le paramètre **autoriser l’interaction avec les applications personnalisées** à l’échelle de l’organisation. Pour ce faire :
    1. Dans le volet de navigation de gauche du [Centre d’administration de Microsoft teams](https://admin.teams.microsoft.com/), accédez à**stratégies d’autorisations**des **applications** > Teams, puis cliquez sur **paramètres à l’échelle**de l’organisation.
    2. Sous **applications personnalisées**, activez **autoriser l’interaction avec les applications personnalisées**, puis cliquez sur **Enregistrer**.

    ![Capture d’écran du paramètre « autoriser l’interaction avec les applications personnalisées » en niveau de l’Organisation](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. Activez le paramètre **Télécharger des applications personnalisées** dans la stratégie de configuration de l’application globale. Pour ce faire :
    1. Dans le volet de navigation de gauche du [Centre d’administration de Microsoft teams](https://admin.teams.microsoft.com/), accédez à stratégies de configuration des **applications** > **d'** équipe, puis cliquez sur la stratégie **globale par défaut** de l’organisation.
    2. Activez **Télécharger les applications personnalisées**, puis cliquez sur **Enregistrer**.

    ![Capture d’écran du paramètre de stratégie « télécharger des applications personnalisées »](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> Il existe également un paramètre charger une application personnalisée au niveau de l’équipe. Par défaut, ce paramètre est activé. Toutefois, si les développeurs ne peuvent pas télécharger une application personnalisée dans une équipe, vérifiez le paramètre en suivant les [étapes ci-dessous.](teams-custom-app-policies-and-settings.md#configure-the-team-custom-app-setting)

### <a name="create-your-app"></a>Créer votre application

Les développeurs doivent maintenant avoir ce dont ils ont besoin pour créer votre application. Pour plus d’informations, consultez cette [page](https://docs.microsoft.commicrosoftteams/platform) .

## <a name="step-2-validate-in-production"></a>Étape 2 : valider en production

### <a name="get-the-app-package"></a>Télécharger le package de l’application

Lorsque l’application est prête à être utilisée en production, le développeur doit produire un package d’application. Ils peuvent utiliser [app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio) pour cela. Elle vous envoie le fichier au format. zip.

Microsoft utilise [ces instructions](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval) pour s’assurer de la conformité des applications avec les normes de qualité et de sécurité du magasin des applications globales Teams.

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a>Permettre aux utilisateurs approuvés de télécharger des applications personnalisées dans le client de production

Pour vérifier que l’application fonctionne correctement dans votre client de production, vous devez permettre aux utilisateurs approuvés de votre organisation de télécharger des applications personnalisées.  De la même façon que dans les [applications personnalisées allow auparavant de l’étape de test du client](#allow-custom-apps-in-the-test-tenant) , vous pouvez utiliser les stratégies de configuration d’application pour effectuer cette opération.

> [!NOTE]
> Si vous n’avez pas l’habitude de télécharger l’application sur votre client de production pour la validation, même pour les utilisateurs vous-même ou approuvés, vous pouvez ignorer cette étape et suivre les étapes 3 et 4 pour télécharger l’application non validée sur votre magasin d’applications clientes. Restreignez ensuite l’accès à cette application uniquement et aux utilisateurs approuvés. Ces utilisateurs peuvent ensuite télécharger l’application auprès du magasin des applications clientes pour effectuer la validation. Une fois l’application validée, utilisez les mêmes stratégies d’autorisation pour ouvrir Access et annuler l’application en vue d’une utilisation en production.

Pour permettre aux utilisateurs approuvés de télécharger des applications personnalisées, procédez comme suit :

1. Activez le paramètre **autoriser l’interaction avec les applications personnalisées** à l’échelle de l’organisation. Pour ce faire :
    1. Dans le volet de navigation de gauche du [Centre d’administration de Microsoft teams](https://admin.teams.microsoft.com/), accédez à**stratégies d’autorisations**des **applications** > Teams, puis cliquez sur **paramètres à l’échelle**de l’organisation.
    2. Sous **applications personnalisées**, activez **autoriser l’interaction avec les applications personnalisées**, puis cliquez sur **Enregistrer**.
2. Désactivez le paramètre **Télécharger des applications personnalisées** de la stratégie de configuration de l’application globale. Pour ce faire :
    1. Dans le volet de navigation de gauche du [Centre d’administration de Microsoft teams](https://admin.teams.microsoft.com/), accédez à stratégies de configuration des **applications** > **d'** équipe, puis cliquez sur la stratégie **globale par défaut** de l’organisation.
    2. Désactivez l’option **Télécharger les applications personnalisées**, puis cliquez sur **Enregistrer**.
3. Créez une stratégie de configuration de l’application qui permet le téléchargement d’applications personnalisées et l’attribution à votre ensemble d’utilisateurs approuvés. Pour ce faire :
    1. Dans le volet de navigation de gauche du [Centre d’administration de Microsoft teams](https://admin.teams.microsoft.com/), accédez à**stratégies de configuration**des **applications** > d’équipe, puis cliquez sur **Ajouter**. Donnez un nom et une description à la nouvelle stratégie, activez l' **application télécharger des applications personnalisées**, puis cliquez sur **Enregistrer**.
    2. Sélectionnez la nouvelle stratégie que vous avez créée, puis cliquez sur **gérer les utilisateurs**. Recherchez un utilisateur, cliquez sur **Ajouter**, puis sur **appliquer**. Répétez cette étape pour affecter la stratégie à l’ensemble de vos utilisateurs approuvés.

        ![Capture d’écran de la page « Ajouter une stratégie de configuration de l’application »](media/manage-your-lob-apps-new-app-setup-policy.png)

    Ces utilisateurs peuvent désormais télécharger le manifeste de l’application pour vérifier que l’application fonctionne correctement dans le client de production.

## <a name="step-3-upload-to-the-tenant-apps-catalog"></a>Étape 3 : Télécharger dans le catalogue des applications clientes

Pour mettre l’application à la disposition des utilisateurs dans le magasin d’applications clientes, téléchargez l’application. Vous pouvez le faire à l’aide du client de bureau Teams. Suivez les étapes [ci-dessous](tenant-apps-catalog-teams.md#go-to-the-tenant-apps-catalog).

![Capture d’écran de la page applications](media/manage-your-lob-apps-store.png)

## <a name="step-4-configure-and-assign-permissions"></a>Étape 4 : configurer et affecter des autorisations

### <a name="control-access-to-the-app"></a>Contrôler l’accès à l’application

Par défaut, tous les utilisateurs ont accès à cette application dans le magasin des applications Teams. Pour restreindre et contrôler les personnes autorisées à utiliser l’application, vous pouvez créer et affecter une nouvelle stratégie d’autorisation d’application. Suivez les étapes [ci-dessous](teams-app-permission-policies.md#create-a-custom-app-permission-policy).

![Capture d’écran de la page « stratégie d’autorisation d’ajout d’application »](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a>Épingler l’application à découvrir

Par défaut, pour que les utilisateurs puissent trouver cette application, ils doivent accéder au magasin d’applications teams et parcourir ou Rechercher le fichier. Pour permettre aux utilisateurs d’accéder facilement à l’application, vous pouvez épingler l’application à la barre de l’application dans Teams. Pour ce faire, créez une nouvelle stratégie de configuration d’application et attribuez-la à des utilisateurs. Suivez les étapes [ci-dessous](teams-app-setup-policies.md#create-a-custom-app-setup-policy).

![Capture d’écran du volet « ajouter des applications épinglées »](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a>Étape 5 : mettre à jour l’application

![Vue d’ensemble de votre application du développement au déploiement](media/manage-your-lob-apps-update.png)

Pour mettre à jour une application, les développeurs doivent continuer à suivre les [étapes 1](#step-1-develop-and-test) et [2](#step-2-validate-in-production).

Vous pouvez mettre à jour l’application par le biais du catalogue d’applications clientes. Pour ce faire, dans le client de bureau Teams, accédez à **applications** > **développées pour &lt;le&gt;nom de votre client**, puis cliquez sur **...** dans le coin supérieur droit de l’application, puis cliquez sur **mettre à jour**. Cette opération a pour effet de remplacer l’application existante dans le catalogue d’applications clientes, et toutes les stratégies d’autorisation et de configuration restent appliquées pour l’application mise à jour. 

![Capture d’écran de la mise à jour d’une application dans la page applications](media/manage-your-lob-apps-update-app.png)