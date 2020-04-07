---
title: Gérer vos applications dans le centre d’administration Microsoft teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Découvrez comment gérer vos applications teams dans la page gérer les applications du centre d’administration Microsoft teams
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 5e261dfd6f23ec298e354a7732a9a1afa9d6b22e
ms.sourcegitcommit: f3390e27bb63b66d1c4fb4f8afbda6b814fbbb5b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2020
ms.locfileid: "43170552"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Gérer vos applications dans le centre d’administration Microsoft teams
======================================================

En tant qu’administrateur, la page **gérer les applications** dans le centre d’administration Microsoft teams vous permet d’afficher et de gérer toutes les applications d’équipes dans le catalogue d’applications de votre organisation. Dans cet exemple, vous pouvez voir l’état de niveau de l’organisation et les propriétés des applications, télécharger de nouvelles applications personnalisées dans votre catalogue d’applications client, bloquer ou autoriser des applications au niveau de l’organisation, et gérer les paramètres de l’application à l’échelle de l’organisation.

La page **gérer les applications** vous donne une vue d’ensemble des applications disponibles dans votre catalogue de clients, en fournissant les informations dont vous avez besoin pour déterminer les applications à autoriser ou à bloquer au sein de votre organisation. Vous pouvez ensuite utiliser des [stratégies d’autorisation d’application](teams-app-permission-policies.md), des stratégies de [configuration d’application](teams-app-setup-policies.md)et des [stratégies et paramètres d’application personnalisés](teams-custom-app-policies-and-settings.md) pour configurer l’utilisation de l’application pour des utilisateurs spécifiques de votre organisation.

Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams** > **Manage**apps. Pour accéder à la page, vous devez être administrateur général ou administrateur de service Teams.

## <a name="view-apps-in-your-tenant-app-catalog"></a>Afficher les applications dans le catalogue d’applications de votre client

Vous pouvez afficher chaque application dans votre catalogue d’applications client, y compris les informations suivantes sur chaque application.

![Capture d’écran de la page des applications gérées](media/manage-apps.png)

- **Nom**: nom de l’application. Cliquez sur le nom de l’application pour afficher davantage d’informations sur celle-ci. Cela inclut une description de l’application, qu’elle soit autorisée ou bloquée, version, catégories qui s’appliquent à l’application, à l’état de la certification, aux fonctionnalités prises en charge et à l’ID de l’application. Voici un exemple :<br> 
![Capture d’écran de la page de détails sur les applications pour une application](media/manage-apps-app-details.png)
- **Certification**: si l’application n’a pas été **certifiée** , vous verrez soit la certification Microsoft 365, soit l' **attestation Publisher**. Cliquez sur le lien pour afficher les détails de certification de l’application. Si vous voyez «**--**», nous ne disposons pas des informations de certification de l’application. Pour en savoir plus sur les applications certifiées dans Teams, voir [programme de certification d’application Microsoft 365](https://docs.microsoft.com/teams-app-certification/all-apps).  
- **Catégories**: catégories qui s’appliquent à l’application.
- **État**de l’application : état de l’application au niveau de l’organisation, qui peut être l’un des éléments suivants :
    - **Autorisé**: l’application est disponible pour tous les utilisateurs de votre organisation.
    - **Bloqué**: l’application est bloquée et n’est pas disponible pour les utilisateurs de votre organisation.<br>
Il est important de savoir que cette colonne représente l’état autorisé et bloqué des applications qui se trouvaient auparavant dans le volet Paramètres à l’échelle de l' **organisation** . À présent, vous pouvez afficher, bloquer et autoriser des applications au niveau de l’organisation dans la page **gérer les applications** . 
- **Version**: version de l’application.

Pour afficher les informations que vous souhaitez inclure dans le tableau, cliquez sur **modifier la colonne** dans le coin supérieur droit pour ajouter ou supprimer des colonnes dans la table.

## <a name="upload-a-new-app"></a>Télécharger une nouvelle application

Vous pouvez utiliser votre catalogue d’applications pour tester et distribuer des applications métier qui sont spécifiquement conçues pour votre organisation. Un package d’application teams est créé à l’aide de [teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio). Lorsque vous disposez du package d’application, vous pouvez l’ajouter à votre catalogue d’applications. Même si tous les utilisateurs de votre organisation peuvent afficher le catalogue d’applications, seuls les administrateurs généraux et les administrateurs des services teams peuvent les publier et les gérer.

Pour télécharger une nouvelle application personnalisée dans le catalogue d’applications de votre client, cliquez sur **Télécharger une nouvelle application** pour télécharger votre package d’application au format. zip. Lorsque l’application n’est pas mise en surbrillance, vous devez effectuer une recherche dans le catalogue de votre application pour la trouver.

Pour mettre à jour une application après son téléchargement, dans la liste des applications sur la page **gérer les applications** , cliquez sur le nom de l’application, puis cliquez sur **mettre à jour**. Cela a pour effet de remplacer l’application existante dans votre catalogue d’applications et toutes les stratégies d’autorisations et les stratégies de configuration des applications qui ont été appliquées pour l’application mise à jour.

Pour en savoir plus, voir [gérer vos applications métier dans teams](manage-your-lob-apps.md).

## <a name="allow-and-block-apps"></a>Autoriser et bloquer des applications

Dans la page **gérer les applications** , vous pouvez autoriser ou bloquer des applications individuelles au niveau de l’organisation. Il affiche chaque application disponible et son état actuel d’application au niveau de l’organisation. (Le blocage et l’autorisation des applications au niveau de l’organisation sont déplacés du volet Paramètres de l’application à l’échelle de l' **organisation** .)

Pour autoriser ou bloquer une application, sélectionnez-la, puis cliquez sur **autoriser** ou **bloquer**. Lorsque vous bloquez une application, toutes les interactions avec cette application sont désactivées et l’application n’apparaît pas dans teams pour les utilisateurs de votre organisation.

Lorsque vous bloquez ou autorisez une application dans la page **gérer les applications** , cette application est bloquée ou autorisée pour tous les utilisateurs de votre organisation.  Lorsque vous bloquez ou autorisez une application dans une stratégie d’autorisation d’application Teams, elle est bloquée ou autorisée pour les utilisateurs qui ont attribué cette stratégie. Pour qu’un utilisateur puisse installer une application et interagir avec celle-ci, vous devez autoriser l’application au niveau de l’organisation sur la page **gérer les applications** et dans la stratégie d’autorisation d’application qui est affectée à l’utilisateur.

 > [!NOTE]
 > Pour désinstaller une application, cliquez avec le bouton droit sur l’application, puis cliquez sur **désinstaller** ou utilisez le menu **autres applications** du côté gauche. 

## <a name="manage-org-wide-app-settings"></a>Gérer les paramètres d’application à l’échelle de l’Organisation

Utilisez les paramètres d’application à l’échelle de l’Organisation pour contrôler si les utilisateurs peuvent installer des applications tierces et si les utilisateurs peuvent télécharger ou interutiliser des applications personnalisées au sein de votre organisation. Les paramètres de l’application à l’échelle de l’organisation régissent le comportement de tous les utilisateurs et remplacent toutes les autres stratégies d’autorisation d’application attribuées aux utilisateurs. Vous pouvez les utiliser pour contrôler les applications malveillantes ou problématiques.

1. Dans la page **gérer les applications** , sélectionnez Paramètres de l' **application à l’échelle de l’organisation**. Vous pouvez alors configurer les paramètres de votre choix dans le panneau.

    ![Capture d’écran des paramètres d’application à l’échelle de l’Organisation](media/manage-apps-org-wide-app-settings.png)
    
2. Sous **applications tierces**, désactivez ou activez ces paramètres pour contrôler l’accès aux applications tierces :

    - **Autoriser les applications tierces dans teams**: ce contrôle si les utilisateurs peuvent utiliser des applications tierces. Si vous désactivez ce paramètre, les utilisateurs ne pourront pas installer ou utiliser d’applications tierces. Pour les applications que vous avez autorisées, l’état indique As **allowed mais Disabled**de l’organisation.              

        > [!NOTE]
        > Dans Microsoft 365 Government-déploiement de Microsoft Teams, le paramètre **autoriser les applications tierces dans teams** est désactivé par défaut.

        Lorsque **l’option autoriser les applications tierces dans teams** est désactivée, les [webhook sortants](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) sont désactivés, ce qui signifie que les utilisateurs ne peuvent pas les créer. Lorsque ce paramètre est activé, l’option de raccordements Web sortants est activée pour tous les utilisateurs, qu’il soit activé ou désactivé dans la stratégie d’autorisation de l’utilisateur.
    - **Autorisez toutes les nouvelles applications tierces publiées dans le Windows Store par défaut**: ce contrôle si les nouvelles applications tierces publiées dans le Windows Store sont automatiquement disponibles dans Teams. Vous ne pouvez définir cette option que si vous autorisez des applications tierces.

3. Sous **applications personnalisées**, désactivez ou activez l’option **autoriser les interactions avec les applications personnalisées**. Ce paramètre détermine si les utilisateurs peuvent interagir avec les applications personnalisées. Pour plus d’informations, consultez [gérer les stratégies et les paramètres d’application personnalisés dans teams](teams-custom-app-policies-and-settings.md).
4. Cliquez sur **Enregistrer** pour appliquer les paramètres de l’application à l’échelle de l’organisation.

## <a name="related-topics"></a>Voir aussi

- [Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)
