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
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Découvrez comment gérer vos applications teams dans la page gérer les applications du centre d’administration Microsoft teams
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 23ff7cc90d30dc931b0677ce5ec5aa8db98981fb
ms.sourcegitcommit: e0e089f0ab217d920e128377af653f7dbfdedacf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818183"
---
<a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Gérer vos applications dans le centre d’administration Microsoft teams
======================================================

En tant qu’administrateur, la page gérer les applications dans le centre d’administration Microsoft teams vous permet d’afficher et de gérer toutes les applications d’équipe pour votre organisation. Dans cet exemple, vous pouvez voir l’état de niveau de l’organisation et les propriétés des applications, approuver ou télécharger de nouvelles applications personnalisées dans le magasin d’applications de votre organisation, bloquer ou autoriser des applications au niveau de l’organisation, acheter des services pour des applications tierces et gérer les paramètres de l’application à l’échelle de l’organisation.

La page gérer les applications vous donne une vue d’ensemble des applications disponibles et vous fournit les informations dont vous avez besoin pour déterminer les applications à autoriser ou à bloquer au sein de votre organisation. Vous pouvez ensuite utiliser des [stratégies d’autorisation d’application](teams-app-permission-policies.md), des stratégies de [configuration d’application](teams-app-setup-policies.md)et des [stratégies et paramètres d’application personnalisés](teams-custom-app-policies-and-settings.md) pour configurer l’utilisation de l’application pour des utilisateurs spécifiques de votre organisation.

Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage**apps. Pour accéder à la page, vous devez être administrateur général ou administrateur de service Teams.

> [!NOTE]
> La page gérer les applications n’est pas encore disponible dans les déploiements de Microsoft 365 Government Community Cloud.

## <a name="view-apps"></a>Afficher des applications

Vous pouvez afficher chaque application, y compris les informations suivantes sur chaque application.

![Capture d’écran de la page des applications gérées](media/manage-apps.png)

- **Nom**: nom de l’application. Cliquez sur le nom de l’application pour afficher davantage d’informations sur celle-ci. Cela inclut une description de l’application, qu’elle soit autorisée ou bloquée, version, catégories qui s’appliquent à l’application, à l’état de la certification, aux fonctionnalités prises en charge et à l’ID de l’application. Voici un exemple :

  ![Capture d’écran de la page de détails sur les applications pour une application](media/manage-apps-app-details.png)
  
- **Certification**: si l’application n’a pas été **certifiée** , vous verrez soit la certification Microsoft 365, soit l' **attestation Publisher**. Cliquez sur le lien pour afficher les détails de certification de l’application. Si vous voyez « **--** », nous ne disposons pas des informations de certification de l’application. Pour en savoir plus sur les applications certifiées dans Teams, voir [programme de certification d’application Microsoft 365](https://docs.microsoft.com/teams-app-certification/all-apps).  
- **Publisher**: nom de l’éditeur.
- **État de publication**: état de publication des applications personnalisées.
- **État**: état de l’application au niveau de l’organisation, qui peut être l’un des éléments suivants :

    - **Autorisé**: l’application est disponible pour tous les utilisateurs de votre organisation.
    
    - **Bloqué**: l’application est bloquée et n’est pas disponible pour les utilisateurs de votre organisation.
    
    - **Bloqué à l’échelle**de l’Organisation : l’application est bloquée dans les paramètres de l’application à l’échelle de l’organisation.
    
      Il est important de savoir que cette colonne représente l’état autorisé et bloqué des applications qui se trouvaient auparavant dans le volet Paramètres à l’échelle de l' **organisation** . À présent, vous pouvez afficher, bloquer et autoriser des applications au niveau de l’organisation dans la page **gérer les applications** . 
- **Licences**: indique si une application propose un abonnement logiciel en tant que service (SaaS) à des fins d’achat. Cette colonne s’applique uniquement aux applications tierces. Chaque application tierce utilise l’une des valeurs suivantes :
    - **Achat immédiat**: l’application propose un abonnement SaaS et est disponible à l’achat.  
    - **Acheté**: l’application propose un abonnement SaaS et vous avez acheté des licences.
    - **--**: L’application n’a pas d’abonnement Saas.
- **Application personnalisée**: si l’application est une application personnalisée.
- **Catégories**: catégories qui s’appliquent à l’application.
- **Version**: version de l’application.

Pour afficher les informations que vous souhaitez inclure dans le tableau, cliquez sur **modifier la colonne** dans le coin supérieur droit pour ajouter ou supprimer des colonnes dans la table.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Publier une application personnalisée dans le magasin d’applications de votre organisation

Utilisez la page gérer les applications pour publier des applications qui sont conçues spécifiquement pour votre organisation. Après avoir publié une application personnalisée, celle-ci est disponible pour les utilisateurs du magasin d’applications de votre organisation. Il existe deux façons de publier une application personnalisée dans le magasin d’applications de votre organisation. La façon dont vous utilisez dépend de la manière dont vous obtenez l’application.

- [Approuver une application personnalisée](#approve-a-custom-app): utilisez cette méthode si le développeur envoie directement l’application à la page gérer les applications à l’aide de l’API de soumission d’applications Teams. Vous pouvez ensuite passer en revue et publier (ou rejeter) l’application directement à partir de la page des détails de l’application.
- [Télécharger un package d’application](#upload-an-app-package): utilisez cette méthode si le développeur vous envoie le package d’application au format. zip. Vous publiez l’application en chargeant le package de l’application.

###  <a name="approve-a-custom-app"></a>Approuver une application personnalisée

Le widget **approbations en attente** sur la page gérer les applications vous avertit lorsqu’un développeur soumet une application à l’aide de l’API de soumission d’applications Teams. Une application nouvellement soumise est associée à un **État de publication** de **soumis** et un **statut** de **blocage**. Accédez à la page Détails de l’application pour afficher des informations supplémentaires sur celle-ci, puis pour la publier, définissez l' **État de publication** sur **publier**.

Vous êtes également averti lorsqu’un développeur envoie une mise à jour à une application personnalisée. Vous pouvez ensuite vérifier et publier (ou rejeter) la mise à jour sur la page Détails de l’application. Toutes les stratégies d’autorisation d’application et les stratégies de configuration des applications restent appliquées pour l’application mise à jour.

Pour en savoir plus, voir [publier une application personnalisée soumise par le biais de l’API de soumission d’applications teams](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Télécharger un package d’application

Le développeur crée un package d’application teams à l’aide de [teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio), puis l’envoie au format. zip. Lorsque vous disposez du package d’application, vous pouvez le télécharger dans le magasin d’applications de votre organisation.

Pour télécharger une nouvelle application personnalisée, sélectionnez **charger** pour télécharger le package de l’application. Lorsque l’application n’est pas mise en surbrillance, vous devez effectuer une recherche dans la liste des applications sur la page gérer les applications pour la trouver.

Pour mettre à jour une application après son téléchargement, dans la liste des applications sur la page gérer les applications, cliquez sur le nom de l’application, puis cliquez sur **mettre à jour**. Le fait de procéder au remplacement de l’application existante et de toutes les stratégies d’autorisation d’application et de configuration des applications reste appliqué pour l’application mise à jour.

Pour en savoir plus, voir [publier une application personnalisée en chargeant un package d’application](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Autoriser et bloquer des applications

Dans la page gérer les applications, vous pouvez autoriser ou bloquer des applications individuelles au niveau de l’organisation. Il affiche chaque application disponible et son état actuel d’application au niveau de l’organisation. (Le blocage et l’autorisation des applications au niveau de l’organisation sont déplacés du volet Paramètres de l’application à l’échelle de l' **organisation** .)

Pour autoriser ou bloquer une application, sélectionnez-la, puis cliquez sur **autoriser** ou **bloquer**. Lorsque vous bloquez une application, toutes les interactions avec cette application sont désactivées et l’application n’apparaît pas dans teams pour les utilisateurs de votre organisation.

Lorsque vous bloquez ou autorisez une application dans la page gérer les applications, cette application est bloquée ou autorisée pour tous les utilisateurs de votre organisation.  Lorsque vous bloquez ou autorisez une application dans une stratégie d’autorisation d’application Teams, elle est bloquée ou autorisée pour les utilisateurs qui ont attribué cette stratégie. Pour qu’un utilisateur puisse installer une application et interagir avec celle-ci, vous devez autoriser l’application au niveau de l’organisation sur la page gérer les applications et dans la stratégie d’autorisation d’application qui est affectée à l’utilisateur.

 > [!NOTE]
 > Pour désinstaller une application, cliquez avec le bouton droit sur l’application, puis cliquez sur **désinstaller** ou utilisez le menu **plus d’applications** sur le côté gauche.

## <a name="purchase-services-for-third-party-apps"></a>Acheter des services pour des applications tierces

Vous pouvez rechercher et acheter des licences de services proposées par des applications tierces pour les utilisateurs de votre organisation directement à partir de la page gérer les applications. La colonne **licences** du tableau indique si une application propose un abonnement Saas payant. Cliquez sur **acheter maintenant** pour afficher les offres et les informations de tarification et acheter des licences pour vos utilisateurs. Pour en savoir plus, voir [acheter des services pour les applications tierces dans le centre d’administration Microsoft teams](purchase-third-party-apps.md).

## <a name="manage-org-wide-app-settings"></a>Gérer les paramètres d’application à l’échelle de l’Organisation

Utilisez les paramètres d’application à l’échelle de l’Organisation pour contrôler si les utilisateurs peuvent installer des applications tierces et si les utilisateurs peuvent télécharger ou interutiliser des applications personnalisées au sein de votre organisation. Les paramètres de l’application à l’échelle de l’organisation régissent le comportement de tous les utilisateurs et remplacent toutes les autres stratégies d’autorisation d’application attribuées aux utilisateurs. Vous pouvez les utiliser pour contrôler les applications malveillantes ou problématiques.

> [!NOTE]
> Pour plus d’informations sur l’utilisation des paramètres d’application à l’échelle de l’organisation dans Microsoft 365 Government-déploiements de Microsoft Teams, voir [gérer les stratégies d’autorisation d’application dans teams](teams-app-permission-policies.md).

1. Dans la page gérer les applications, sélectionnez Paramètres de l' **application à l’échelle de l’organisation**. Vous pouvez alors configurer les paramètres de votre choix dans le panneau.

    ![Capture d’écran des paramètres d’application à l’échelle de l’Organisation](media/manage-apps-org-wide-app-settings.png)
    
2. Sous **applications tierces**, désactivez ou activez ces paramètres pour contrôler l’accès aux applications tierces :

    - **Autoriser les applications**tierces : ce contrôle si les utilisateurs peuvent utiliser des applications tierces. Si vous désactivez ce paramètre, vos utilisateurs ne seront pas en mesure d’installer ou d’utiliser des applications tierces et l’état de l’application de ces applications est affiché en tant qu' **entreprise bloquée** dans le tableau.

        > [!NOTE]
        > Lorsque l’option **autoriser les applications tierces** est désactivée, les [webhook sortant](https://docs.microsoft.com/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) sont désactivés, ce qui signifie que les utilisateurs ne peuvent pas les créer. Lorsque ce paramètre est activé, les webhook sortants sont activés pour tous les utilisateurs et vous pouvez les contrôler au niveau utilisateur en autorisant ou en bloquant l’application webhook sortante par le biais de [stratégies d’autorisation d’application](teams-app-permission-policies.md). <br><br>Notez que si vous disposez de [stratégies d’autorisation d’application](teams-app-permission-policies.md) existantes pour les **applications Microsoft** qui utilisent le paramètre **autoriser des applications spécifiques et bloquer toutes les autres** , et que vous souhaitez activer les webhook sortant pour les utilisateurs, ajoutez l’application webhook sortant à la liste.
    - **Autorisez toutes les nouvelles applications tierces publiées dans le Windows Store par défaut**: ce contrôle si les nouvelles applications tierces publiées dans le Windows Store sont automatiquement disponibles dans Teams. Vous ne pouvez définir cette option que si vous autorisez des applications tierces.

3. Sous **applications personnalisées**, désactivez ou activez l’option **autoriser les interactions avec les applications personnalisées**. Ce paramètre détermine si les utilisateurs peuvent interagir avec les applications personnalisées. Pour plus d’informations, consultez [gérer les stratégies et les paramètres d’application personnalisés dans teams](teams-custom-app-policies-and-settings.md).
4. Cliquez sur **Enregistrer** pour appliquer les paramètres de l’application à l’échelle de l’organisation.

## <a name="related-topics"></a>Sujets associés

- [Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)