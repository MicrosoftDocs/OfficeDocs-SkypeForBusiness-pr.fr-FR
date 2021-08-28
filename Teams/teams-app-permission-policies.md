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
ms.localizationpriority: medium
search.appverid: MET150
description: En savoir plus sur les stratégies d’autorisation d’application dans Microsoft Teams et comment les utiliser pour contrôler les applications disponibles pour les utilisateurs de votre organisation.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 841f471d548e26d9eb7eb876433330d3ecd20f67
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627446"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gérer les stratégies d’autorisation d’application dans Microsoft Teams

En tant qu’administrateur, vous pouvez utiliser des stratégies d’autorisation d’application pour contrôler les applications auxquelles les utilisateurs de Microsoft Teams peuvent accéder au sein de votre organisation. Vous pouvez autoriser ou bloquer toutes les applications ou des applications spécifiques publiées par Microsoft, par des tiers et par votre organisation. Lorsque vous bloquez une application, les utilisateurs qui disposent de la stratégie ne peuvent pas l’installer à partir de la boutique d’applications Teams. Vous devez être un administrateur général ou un administrateur du service Teams pour gérer ces stratégies.

Vous gérez les stratégies d’autorisation d'applications dans le Centre d'administration Microsoft Teams. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Les utilisateurs de votre organisation recevront automatiquement la stratégie globale, sauf si vous créez et leur attribuez une stratégie personnalisée. Après avoir modifié ou attribué une stratégie, l’application des modifications peut prendre quelques heures.

![Capture d’écran de la stratégie d’autorisation d’application](media/app-permission-policies.png)

> [!NOTE]
> Les paramètres de l’application à l’échelle de l’organisation remplacent la stratégie globale et les stratégies personnalisées que vous créez et affectez aux utilisateurs.

Si votre organisation utilise déjà Teams, les paramètres de l’application que vous avez configurés dans **Paramètres à l’échelle du client** dans le Centre d’administration Microsoft 365 sont reflétés dans les paramètres des applications à l’échelle de l’organisation sur la page [Gérer les applications](manage-apps.md). Si vous êtes nouveau dans Teams et que vous débutez, par défaut, toutes les applications sont autorisées dans la stratégie globale. Cela inclut les applications publiées par Microsoft, des tiers et votre organisation.

Par exemple, vous voulez bloquer toutes les applications tierces et autoriser des applications spécifiques de Microsoft pour l’équipe RH de votre organisation. Tout d’abord, vous devez vous rendre sur la page [Gérer les applications](manage-apps.md) et vous assurer que les applications que vous voulez autoriser pour l’équipe RH sont autorisées au niveau de l’organisation. Ensuite, créez une stratégie personnalisée appelée Stratégie d'autorisation des applications RH, définissez-la pour bloquer et autoriser les applications que vous souhaitez, et affectez-la aux utilisateurs de l'équipe RH.

> [!NOTE]
> Si vous avez déployé Teams dans un environnement MICROSOFT 365 CLOUD DE LA COMMUNAUTÉ DU SECTEUR PUBLIC High (GCCH) et Department of Defense (DoD), voir Gérer les [paramètres](#manage-org-wide-app-settings-for-microsoft-365-government) d’application à l’échelle de l’organisation pour Microsoft 365 Government pour en savoir plus sur les paramètres d’applications tierces propres à GCCH et DoD.

## <a name="create-a-custom-app-permission-policy"></a>Créer une stratégie d’autorisation d’application personnalisée

Si vous voulez contrôler les applications disponibles pour différents groupes d’utilisateurs au niveau de votre organisation, créez et affectez une ou plusieurs stratégies d’autorisation d’application personnalisées. Vous pouvez créer et attribuer des stratégies personnalisées distinctes sur la base de la publication d’applications par Microsoft, des tiers ou votre organisation. Il est important de savoir qu’après avoir créé une stratégie personnalisée, vous ne pouvez pas la modifier si les applications tierces sont désactivées dans les paramètres de l’application à l’échelle de l’organisation.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Stratégies d’autorisation**.
2. Cliquez sur **Ajouter**.<br>
    ![Capture d’écran de la nouvelle stratégie d’autorisation d’application](media/app-permission-policies-new-policy.png)
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. Sous **Applications Microsoft**, **Applications tierces** et **Applications personnalisées**, sélectionnez l’une des options suivantes :

    - **Autoriser toutes les applications**
    - **Autoriser des applications spécifiques et bloquer toutes les autres**
    - **Bloquer des applications spécifiques et autoriser toutes les autres**
    - **Bloquer toutes les applications**.

5. Si vous avez sélectionné **Autoriser des applications spécifiques et bloquer d’autres utilisateurs**, ajoutez les applications que vous voulez autoriser :

    1. Sélectionnez **Autoriser des applications**.
    1. Recherchez les applications que vous voulez autoriser, puis cliquez sur **Ajouter**. Les résultats de la recherche sont filtrés sur l’éditeur de l’application (**Applications Microsoft**, **Applications tierces** ou **Applications personnalisées**).
    1. Lorsque vous avez choisi la liste d’applications, cliquez sur **Autoriser**. 

6. De même, si vous avez sélectionné **Bloquer des applications spécifiques et autorisez tous les autres**, recherchez et ajoutez les applications que vous voulez bloquer, puis cliquez sur **Bloquer**.
7. Cliquez sur **Enregistrer**.

## <a name="edit-an-app-permission-policy"></a>Modifier une stratégie d’autorisation à l’application

Vous pouvez utiliser le Centre d’administration Microsoft Teams pour modifier une stratégie, y compris la stratégie globale et les stratégies personnalisées que vous créez.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Stratégies d’autorisation**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. À partir de là, apportez les modifications souhaitées. Vous pouvez gérer les paramètres en fonction de l’éditeur de l’application et ajouter et supprimer des applications en fonction du paramètre Autoriser/Bloquer.
4. Cliquez sur **Enregistrer**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Affecter une stratégie d’autorisation d’application personnalisée aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Gérer les paramètres d’application à l’échelle de l’organisation pour Microsoft 365 secteur public  

Dans le cadre d’un déploiement Microsoft 365 Government - GCCH et DoD de Teams, il est important de connaître les informations suivantes sur les paramètres des applications tierces, qui sont propres à GCCH et DoD.

Dans GCCH et DoD, toutes les applications tierces sont bloquées par défaut. En outre, vous trouverez la note suivante sur la gestion des applications tierces sur la page des stratégies de permission des applications dans le Centre d'administration de Microsoft Teams.

![Capture d’écran de la stratégie d’autorisation d’application dans GCCH et DoD](media/app-permission-policies-gcc.png)

Utilisez les paramètres de l’application à l’échelle de l’organisation pour contrôler si les utilisateurs peuvent installer des applications tierces. Les paramètres de l’application à l’échelle de l’organisation contrôlent le comportement de tous les utilisateurs et remplacent les autres stratégies d’autorisation d’application attribuées à des utilisateurs. Vous pouvez les utiliser pour contrôler des applications malveillantes ou problématiques.

1. Dans la page **Stratégies d’autorisations** , sélectionnez **Paramètres de l’application à l'échelle de l'organisation**. Vous pouvez ensuite configurer les paramètres voulus dans le panneau.

    ![Capture d’écran des paramètres de l’application à l’échelle de l’organisation](media/app-permission-policies-gcc-org-wide.png)
    
2. Sous **Applications tierces**, désactiver ou activer ces paramètres pour contrôler l’accès à des applications tierces :

    - **Autoriser les applications tierces** : cette commande contrôle si les utilisateurs peuvent utiliser des applications tierces. Si vous avez désactiver ce paramètre, vos utilisateurs ne pourront pas installer ou utiliser des applications tierces. Dans le cadre Microsoft 365 -GCCH et DoD du déploiement de Teams, ce paramètre est off par défaut.
    - **Autoriser toute nouvelle application tierce publiée sur le magasin par défaut** : cette option contrôle la publication automatique des nouvelles applications tierces publiées dans le magasin d’applications Teams dans Teams. Vous ne pouvez définir cette option que si vous autorisez des applications tierces.

3. Sous **Applications bloquées**, ajoutez les applications que vous voulez bloquer au sein de votre organisation. Dans un Microsoft 365 - Déploiement gccH et DoD de Teams, toutes les applications tierces sont ajoutées à cette liste par défaut. Pour une application tierce que vous voulez autoriser dans votre organisation, supprimez l’application de cette liste d’applications bloquées. Lorsque vous bloquez une application à l’échelle de l’organisation, l’application est automatiquement bloquée pour tous vos utilisateurs, qu’elles soient autorisées ou non dans les stratégies d’autorisation d’application.
4. Cliquez sur **Enregistrer** pour que les paramètres de l’application à l’échelle de l’organisation prennent effet.

Comme indiqué précédemment, pour autoriser des applications tierces, vous pouvez modifier et utiliser la stratégie globale (à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées.

## <a name="faq"></a>FAQ

### <a name="working-with-app-permission-policies"></a>Fonctionnement des stratégies d’autorisation d’application

#### <a name="what-app-interactions-do-permission-policies-affect"></a>Quelles interactions affectent les stratégies d’autorisation ?
Les stratégies d’autorisation contrôlent l’utilisation des applications en contrôlant l’installation, la découverte et l’interaction pour les utilisateurs finaux. Les administrateurs peuvent toujours gérer les applications dans le Centre d’administration Microsoft Teams quelles que soient les stratégies d’autorisation qui leur sont affectées.

#### <a name="can-i-control-line-of-business-lob-apps"></a>Puis-je contrôler les applications métier (LOB) ?
Oui, vous pouvez utiliser les stratégies d'autorisation des applications pour contrôler le déploiement et la distribution des applications personnalisées (LOB). Vous pouvez créer une stratégie personnalisée ou modifier la stratégie globale pour autoriser ou bloquer des applications personnalisées en fonction des besoins de votre organisation.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Quel est le lien entre les stratégies d'autorisation des applications et les stratégies de configuration des applications ?

Vous pouvez utiliser les stratégies de configuration des applications en même temps que les stratégies de permission des applications. Les applications pré-épinglées sont sélectionnées dans l’ensemble des applications activées pour un utilisateur. Par ailleurs, si un utilisateur a une stratégie d’autorisation d’application qui bloque une application dans sa stratégie de configuration d’application, cette application n’apparaît pas dans Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>Puis-je utiliser des stratégies d’autorisation d’application pour restreindre le chargement d’applications personnalisées ?

Vous pouvez utiliser les paramètres à l’échelle de l’organisation sur la page **Gérer les applications**, ou des stratégies de configuration d’applications pour restreindre le chargement d’applications personnalisées pour votre organisation.  

Pour empêcher des utilisateurs spécifiques de télécharger des applications personnalisées, utilisez des stratégies d’application personnalisées. Pour plus d’informations, consultez [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-custom-app-policies-and-settings.md).

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Le blocage d’une application s’applique-t-il aux clients mobiles Teams ?

Oui, lorsque vous bloquez une application, cette application est bloquée dans tous les clients Teams.  

### <a name="user-experience"></a>Expérience utilisateur

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>Qu'est-ce qu'un utilisateur ressent lorsqu'une application est bloquée ?

Les utilisateurs ne peuvent pas interagir avec une application bloquée ou ses fonctionnalités, telles que les bots, les onglets et les extensions de messagerie. Dans un contexte partagé, tel qu’une conversation d’équipe ou de groupe, les bots peuvent toujours envoyer des messages à tous les participants de ce contexte. Teams indique à l’utilisateur lorsqu’une application est bloquée.

Par exemple, lorsqu’une application est bloquée, les utilisateurs ne peuvent pas :

- Ajouter l’application personnellement ou à une conversation ou une équipe
- Envoyer des messages au bot de l’application
- Exécuter des actions de bouton qui renvoient des informations à l’application, telles que des messages actionnables  
- Afficher l’onglet de l’application
- Configurer des connecteurs pour recevoir des notifications
- Utiliser l’extension de messagerie de l’application

L'ancien portail permettait de contrôler les applications au niveau de l'organisation, ce qui signifie que lorsqu'une application est bloquée, elle l'est pour tous les utilisateurs de l'organisation. Le blocage d’une application sur page [Gérer les applications](manage-apps.md) fonctionne exactement de la même manière.

Pour les stratégies d’autorisation d’application affectées à des utilisateurs spécifiques, si une application avec une fonctionnalité bot ou de connecteur était autorisée, puis bloquée, et si l’application n’est ensuite autorisée que pour certains utilisateurs dans un contexte partagé, les membres d’une conversation de groupe ou d’un canal qui ne sont pas autorisés à cette application peuvent voir l’historique des messages et les messages publiés par le bot ou le connecteur, mais ne peut pas interagir avec.

## <a name="related-topics"></a>Sujets associés

[Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)
