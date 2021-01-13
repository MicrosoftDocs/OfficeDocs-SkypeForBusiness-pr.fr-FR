---
title: Gérer les stratégies d’autorisation d’application dans Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
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
description: Découvrez les stratégies d’autorisation d’application dans Microsoft Teams et comment les utiliser pour contrôler les applications disponibles pour les utilisateurs de votre organisation.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aa11b21405079ab26bf1fa9572eb203560c4e461
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802494"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gérer les stratégies d’autorisation d’application dans Microsoft Teams

En tant qu’administrateur, vous pouvez utiliser des stratégies d’autorisation d’application pour contrôler les applications auxquelles les utilisateurs de Microsoft Teams peuvent accéder au sein de votre organisation. Vous pouvez autoriser ou bloquer toutes les applications ou applications spécifiques publiées par Microsoft, des tiers et votre organisation. Lorsque vous bloquez une application, les utilisateurs qui disposent de la stratégie ne peuvent pas l’installer à partir de la boutique d’applications Teams. Vous devez être un administrateur général ou un administrateur du service Teams pour gérer ces stratégies.

Vous gérez les stratégies d’autorisation d’application dans le Centre d’administration Microsoft Teams. Vous pouvez utiliser la stratégie globale (à l’échelle de l’organisation par défaut) ou créer et attribuer des stratégies personnalisées. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée. Une fois que vous avez modifié ou attribué une stratégie, l’application des modifications peut prendre quelques heures.

![Capture d’écran de la stratégie d’autorisation d’application](media/app-permission-policies.png)

> [!NOTE]
> Les paramètres d’application à l’échelle de l’organisation remplacent la stratégie globale et toutes les stratégies personnalisées que vous créez et attribuez aux utilisateurs.

Si votre organisation est déjà sur Teams, les paramètres d’application que vous avez **configurés** dans les paramètres à l’échelle du client dans le Centre d’administration Microsoft 365 sont reflétés dans les paramètres des applications à l’échelle de l’organisation sur la [page](manage-apps.md) Gérer les applications. Si vous débutez dans Teams et que vous débutez, par défaut, toutes les applications sont autorisées dans la stratégie globale. Cela inclut les applications publiées par Microsoft, des tiers et votre organisation.

Par exemple, vous voulez bloquer toutes les applications tierces et autoriser des applications spécifiques de Microsoft pour l’équipe RH de votre organisation. Tout d’abord, vous devez vous rendre sur la [page](manage-apps.md) Gérer les applications et vous assurer que les applications que vous voulez autoriser pour l’équipe RH sont autorisées au niveau de l’organisation. Ensuite, créez une stratégie personnalisée nommée Stratégie d’autorisation d’application RH, définissez-la pour bloquer et autoriser les applications de votre souhaitez, puis affectez-la aux utilisateurs de l’équipe RH.

> [!NOTE]
> Si vous avez déployé Teams dans un environnement Microsoft 365 Government Community Cloud (GCC), consultez Gérer les paramètres des applications à l’échelle de l’organisation pour [Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) pour en savoir plus sur les paramètres d’applications tierces propres au CLOUD du cloud.

## <a name="create-a-custom-app-permission-policy"></a>Créer une stratégie d’autorisation d’application personnalisée

Si vous voulez contrôler les applications disponibles pour différents groupes d’utilisateurs de votre organisation, créez et affectez une ou plusieurs stratégies d’autorisation d’application personnalisées. Vous pouvez créer et attribuer des stratégies personnalisées distinctes si les applications sont publiées par Microsoft, des tiers ou votre organisation. Il est important de savoir qu’après avoir créé une stratégie personnalisée, vous ne pouvez pas la modifier si des applications tierces sont désactivées dans les paramètres de l’application à l’échelle de l’organisation.

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, allez aux stratégies **d’autorisation des applications Teams.**  >  
2. Cliquez sur **Ajouter**. <br>
    ![Capture d’écran de la nouvelle stratégie d’autorisation d’application](media/app-permission-policies-new-policy.png)
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. Sous **Applications Microsoft,** **Applications tierces** et Applications personnalisées, sélectionnez l’une des options suivantes :

    - **Autoriser toutes les applications**
    - **Autoriser des applications spécifiques et bloquer toutes les autres applications**
    - **Bloquer des applications spécifiques et autoriser tous les autres**
    - **Bloquer toutes les applications**

5. Si vous avez sélectionné Autoriser certaines applications et en **bloquer d’autres,** ajoutez les applications que vous voulez autoriser :

    1. Sélectionnez **Autoriser les applications.**
    1. Recherchez les applications que vous voulez autoriser, puis cliquez sur **Ajouter.** Les résultats de la recherche sont filtrés sur l’éditeur de l’application (applications **Microsoft,** applications **tierces** ou **applications personnalisées).**
    1. Une fois que vous avez choisi la liste d’applications, cliquez sur **Autoriser.** 

6. De même, si vous avez sélectionné Bloquer des applications spécifiques et autorisez toutes les autres **applications,** recherchez et ajoutez les applications que vous voulez bloquer, puis cliquez sur **Bloquer.**
7. Cliquez sur **Enregistrer**.

## <a name="edit-an-app-permission-policy"></a>Modifier une stratégie d’autorisation d’application

Vous pouvez utiliser le Centre d’administration Microsoft Teams pour modifier une stratégie, y compris la stratégie globale et les stratégies personnalisées que vous créez.

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, allez aux stratégies **d’autorisation des applications Teams.**  >  
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **Modifier.**
3. À partir de là, apportez les modifications souhaitées. Vous pouvez gérer les paramètres en fonction de l’éditeur de l’application et ajouter et supprimer des applications en fonction du paramètre d’autoriser/bloquer.
4. Cliquez sur **Enregistrer**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Affecter une stratégie d’autorisation d’application personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Gérer les paramètres d’application à l’échelle de l’organisation pour Microsoft 365 Pour le gouvernement  

Dans le cadre d’un déploiement Microsoft 365 Government - GCC de Teams, il est important de connaître les informations suivantes sur les paramètres des applications tierces, propres au GCC.

Dans le GCC, toutes les applications tierces sont bloquées par défaut. Vous verrez également la note suivante concernant la gestion des applications tierces sur la page stratégies d’autorisation d’application dans le Centre d’administration Microsoft Teams.

![Capture d’écran de la stratégie d’autorisation d’application dans le gcc](media/app-permission-policies-gcc.png)

Utilisez les paramètres d’application à l’échelle de l’organisation pour contrôler si les utilisateurs peuvent installer des applications tierces. Les paramètres d’application à l’échelle de l’organisation régissent le comportement de tous les utilisateurs et remplacent les autres stratégies d’autorisation d’application attribuées aux utilisateurs. Vous pouvez les utiliser pour contrôler des applications malveillantes ou problématiques.

1. Dans la page **Stratégies** d’autorisation, sélectionnez **Paramètres d’application à l’échelle de l’organisation.** Vous pouvez ensuite configurer les paramètres voulus dans le panneau.

    ![Capture d’écran des paramètres d’application à l’échelle de l’organisation](media/app-permission-policies-gcc-org-wide.png)
    
2. Sous **Applications tierces,** désactiver ou activer ces paramètres pour contrôler l’accès aux applications tierces :

    - **Autoriser les applications tierces**: cela contrôle si les utilisateurs peuvent utiliser des applications tierces. Si vous la désactiverez, vos utilisateurs ne pourront pas installer ou utiliser des applications tierces. Dans un déploiement Microsoft 365 Government - GCC de Teams, ce paramètre est off par défaut.
    - **Autoriser toutes les** nouvelles applications tierces publiées sur le Store par défaut : Cela contrôle si les nouvelles applications tierces publiées dans le magasin d’applications Teams deviennent automatiquement disponibles dans Teams. Vous ne pouvez définir cette option que si vous autorisez des applications tierces.

3. Sous **Applications bloquées,** ajoutez les applications que vous souhaitez bloquer dans votre organisation. Dans un déploiement Microsoft 365 Government - GCC de Teams, toutes les applications tierces sont ajoutées à cette liste par défaut. Pour une application tierce que vous souhaitez autoriser dans votre organisation, supprimez l’application de cette liste d’applications bloquées. Lorsque vous bloquez une application à l’échelle de l’organisation, l’application est automatiquement bloquée pour tous vos utilisateurs, qu’elle soit autorisée ou non dans les stratégies d’autorisation d’application.
4. Cliquez **sur Enregistrer** pour que les paramètres d’application à l’échelle de l’organisation prennent effet.

Comme indiqué précédemment, pour autoriser les applications tierces, vous pouvez modifier et utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées.

## <a name="faq"></a>FAQ

### <a name="working-with-app-permission-policies"></a>Fonctionnement des stratégies d’autorisation d’application

#### <a name="what-app-interactions-do-permission-policies-affect"></a>Quelles interactions d’application les stratégies d’autorisation affectent-elles ?
Les stratégies d’autorisation régissent l’utilisation des applications en contrôlant l’installation, la découverte et l’interaction pour les utilisateurs finaux. Les administrateurs peuvent toujours gérer les applications dans le Centre d’administration Microsoft Teams quelles que soient les stratégies d’autorisation qui leur sont affectées.

#### <a name="can-i-control-line-of-business-lob-apps"></a>Puis-je contrôler les applications métier ?
Oui, vous pouvez utiliser des stratégies d’autorisation d’application pour contrôler le déploiement et la distribution des applications personnalisées (LOB). Vous pouvez créer une stratégie personnalisée ou modifier la stratégie globale pour autoriser ou bloquer des applications personnalisées en fonction des besoins de votre organisation.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Comment les stratégies d’autorisation d’application sont-elles liées aux applications épinglées et aux stratégies de configuration d’applications ?

Vous pouvez utiliser des stratégies de configuration d’application avec des stratégies d’autorisation d’application. Les applications pré-épinglées sont sélectionnées dans l’ensemble des applications activées pour un utilisateur. De plus, si un utilisateur a une stratégie d’autorisation d’application qui bloque une application dans sa stratégie de configuration, cette application n’apparaîtra pas dans Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>Puis-je utiliser des stratégies d’autorisation d’application pour restreindre le téléchargement d’applications personnalisées ?

Vous pouvez utiliser des paramètres à l’échelle de l’organisation sur la **page** Gérer les applications ou des stratégies de configuration d’applications pour restreindre le téléchargement d’applications personnalisées pour votre organisation.  

Pour empêcher des utilisateurs spécifiques de télécharger des applications personnalisées, utilisez des stratégies d’application personnalisées. Pour plus d’informations, [voir Gérer les stratégies et paramètres d’application personnalisées dans Teams.](teams-custom-app-policies-and-settings.md)

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Le blocage d’une application s’applique-t-il aux clients mobiles Teams ?

Oui, lorsque vous bloquez une application, cette application est bloquée sur tous les clients Teams.  

### <a name="user-experience"></a>Expérience utilisateur

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>Qu’est-ce qu’une expérience utilisateur quand une application est bloquée ?

Les utilisateurs ne peuvent pas interagir avec une application bloquée ou ses fonctionnalités, telles que les bots, les onglets et les extensions de messagerie. Dans un contexte partagé, tel qu’une conversation d’équipe ou de groupe, les robots peuvent toujours envoyer des messages à tous les participants de ce contexte. Teams indique à l’utilisateur lorsqu’une application est bloquée.

Par exemple, lorsqu’une application est bloquée, les utilisateurs ne peuvent pas :

- Ajouter l’application personnellement ou à une conversation ou une équipe
- Envoyer des messages au robot de l’application
- Effectuer des actions de bouton qui renvoient des informations à l’application, tels que des messages actionnables  
- Afficher l’onglet de l’application
- Configurer des connecteurs pour recevoir des notifications
- Utiliser l’extension de messagerie de l’application

Le portail hérité permettait de contrôler les applications au niveau de l’organisation, ce qui signifie que lorsqu’une application est bloquée, elle est bloquée pour tous les utilisateurs de l’organisation. Le blocage d’une application sur la page [Gérer les](manage-apps.md) applications fonctionne exactement de la même manière.

Pour les stratégies d’autorisation d’application attribuées à des utilisateurs spécifiques, si une application avec la fonctionnalité bot ou connecteur était autorisée, puis bloquée, et si l’application est alors autorisée uniquement pour certains utilisateurs dans un contexte partagé, les membres d’une conversation de groupe ou d’un canal qui ne sont pas autorisés à cette application peuvent voir l’historique des messages et les messages publiés par le bot ou le connecteur , mais vous ne pouvez pas interagir avec.

## <a name="related-topics"></a>Sujets associés

[Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)
