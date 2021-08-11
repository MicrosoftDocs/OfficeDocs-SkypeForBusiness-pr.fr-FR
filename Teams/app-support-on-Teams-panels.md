---
title: Microsoft Teams prise en charge des applications métier sur les panneaux Teams métier
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Décrit la prise en charge de Teams applications/applications LOB.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56c26cef98e316a821f31d3baa014cd1e9f9695743c34493c8880ac85f232830
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2021
ms.locfileid: "54591218"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams prise en charge des applications métier sur les panneaux Teams métier

Teams panneaux ajoute la prise en charge Teams applications métier/applications métier. Cela permettra aux entreprises d’ajouter des expériences supplémentaires sur les panneaux pour répondre aux besoins de votre organisation. Cette version prend en charge le contenu web statique.

> [!IMPORTANT]
> Cette fonctionnalité est disponible uniquement après la mise à jour de Teams panneaux de sécurité. Vous devez avoir l’application Teams version 1449/1.0.97.2021070601 ou une version plus récente pour que l’application soit prise en charge dans Teams panneaux.

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>Configurer et gérer les applications Teams panneaux dans Teams centre d’administration 

Microsoft Teams applications apportent des informations clés, des outils courants et des processus de confiance dans l’endroit où les personnes se rassemblent, apprennent et travaillent. Teams applications [fonctionnent via des fonctionnalités intégrées.](/platform/concepts/capabilities-overview) À présent, en tant qu’administrateur informatique, vous avez le choix entre les applications à inclure dans l’appareil des panneaux Teams de votre organisation et personnaliser les autorisations via le Centre d’administration Teams.

Vous pouvez désormais utiliser les applications Teams sur les panneaux Teams et personnaliser l’expérience utilisateur en fonction des besoins de votre organisation. Vous pouvez choisir l’application web à laquelle vos utilisateurs peuvent accéder, utiliser et hiérarchiser les affichages d’application. Certaines options, telles que les fonctionnalités de bot et de messagerie, ne sont pas pris en charge pour le moment. En savoir plus sur les applications Teams et comment gérer vos appareils dans Microsoft Teams.

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>Gérer les applications sur les panneaux Teams dans Teams’administration centrale

**Remarque**: vous devez être un administrateur global ou un administrateur de service Teams pour accéder au centre d Teams’administration.

Les utilisateurs finaux peuvent afficher mais pas installer des applications sur Teams panneaux. En tant qu’administrateur, vous pouvez afficher et gérer toutes les applications Teams pour votre organisation via le centre d Teams’administration. Découvrez comment gérer vos applications dans le centre d’administration Microsoft Teams via la page Gérer **les applications.** La page **Gérer les applications** dans Teams centre d’administration est également l’endroit où vous pouvez télécharger des applications [personnalisées.](/manage-apps#publish-a-custom-app-to-your-organizations-app-store)

Après avoir configuré des [](/teams-app-permission-policies) applications, vous [](/teams-app-setup-policies) pouvez utiliser des stratégies d’autorisation d’application et des stratégies de configuration d’application pour configurer l’expérience d’application pour des comptes de salle spécifiques dans votre organisation.

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>Épingler des applications sur Teams panneaux avec des stratégies de configuration d’application

Étant donné que Teams offre la possibilité d’afficher un large éventail d’applications, les administrateurs peuvent choisir les  applications les plus essentielles pour l’organisation et épingler uniquement celles-ci pour l’écran d’accueil des panneaux Teams pour un accès rapide. S’il existe plus de cinq applications épinglées ou des applications non épinglées, elles apparaissent sous **l’écran Plus.** Microsoft recommande de créer une stratégie de configuration d’application personnalisée spécifique pour Teams panneaux.

![Capture d’écran de l’interface utilisateur de la page stratégies de configuration de l’application.](media/appsetup1.png) 

Pour gérer les applications épinglées affichées dans les panneaux Teams, connectez-vous au Centre d’administration Teams de votre organisation et accédez à **Teams apps** \> **Setup policies** Select or Create a new \> **policy** \> **Pinned apps**.

![Capture d’écran de la section des applications épinglées dans l’interface utilisateur.](media/appsetup2.png) 

Microsoft vous recommande  de désactiver les Télécharger personnalisées et d’autoriser l’épinglage des utilisateurs pour la meilleure expérience Teams’application sur Teams panneaux. 

Pour plus d’informations sur l’épinglage d’applications, voir [Gérer les stratégies de configuration des applications.](/teams-app-setup-policies)

## <a name="manage-apps-display-order-in-teams-panels"></a>Gérer l’ordre d’affichage des applications dans Teams panneaux 

![Capture d’écran de la section applications dans l’interface utilisateur.](media/appsetup3.png) 

Pour gérer l’ordre dans lequel les applications sont affichées dans les panneaux Teams, connectez-vous au Centre d’administration Teams de votre organisation et accédez aux stratégies d’installation des applications **Teams** Sélectionnez les applications épinglées de stratégie : \>  \>  \>  **Monter/descendre.**

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>Affectation de stratégies d’installation à un compte de ressource de salle

Après avoir créé la stratégie d’installation, l’administrateur doit affecter cette stratégie au compte de ressource de salle qui sera Teams panneaux de configuration. Pour plus d’informations, [reportez-vous à Attribuer des stratégies aux utilisateurs et aux groupes.](/assign-policies-users-and-groups)

## <a name="faq"></a>FAQ

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Combien de temps faut-il aux panneaux Teams pour obtenir les stratégies de configuration d’application nouvelles ou mises à jour ?

Après la modification ou l’affectation de nouvelles stratégies dans le Centre d’administration Teams, l’application des modifications peut prendre jusqu’à 24 heures. Les administrateurs peuvent essayer de se connecter à partir du panneau, d’appuyer  sur l’icône **Paramètres** et de revenir à l’écran d’accueil pour essayer d’actualiser les stratégies.

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>Quel est le ordre des applications sur l’écran « Plus » ?

Dans la page **Autres** applications, les applications épinglées apparaissent en premier. Ensuite, toutes les autres applications installées apparaissent dans l’ordre alphabétique.

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>Pourquoi les applications bot ne s’affichent-elles pas Teams panneaux ?

Seul le contenu web des onglets statiques est pris en charge pour le moment.

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>Pourquoi les applications Teams natives, telles que Calendrier et Tâches, n’apparaissent-elles pas dans Teams panneaux ?

Les applications Teams natives, telles que Calendrier et Tâches, ne sont pas affichées dans Teams panneaux.

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>Dans le Teams d’administration, sous la section Stratégies d’installation, quelle est la différence entre les applications installées et les applications épinglées ?

Pour Teams, Microsoft recommande l’utilisation d’applications épinglées, afin que l’administrateur puisse sélectionner l’application souhaitée et réorganiser son ordre.

**Remarque :** Certaines applications ne permettent pas l’épinglage d’application. Contactez le développeur de l’application pour activer la fonctionnalité d’épinglage de l’application.

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>Pourquoi d’autres applications apparaissent-elles dans l’écran « Plus » même si elles ne font pas partie des applications installées ou épinglées dans la section stratégie de configuration d’application Teams ?

Si des applications ont été précédemment installées via d’autres stratégies d’application ou manuellement dans les clients de bureau/web Teams pour le compte de ressource de salle utilisé sur les panneaux Teams, l’administrateur devra peut-être se connecter au compte de ressource de salle dans Teams et désinstaller manuellement les applications en cliquant avec le bouton droit sur l’application, puis en sélectionnant **Désinstaller.**

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Pourquoi ne puis-je pas trouver une application dans le volet « Ajouter des applications épinglées » ?

Toutes les applications ne peuvent pas être épinglées Teams via une stratégie de configuration d’application. Certaines applications peuvent ne pas prendre en charge cette fonctionnalité. Pour rechercher des applications qui peuvent être épinglées, recherchez l’application dans le volet Ajouter des **applications épinglées.** Pour plus d’informations, reportez-vous [au FAQ dans Working with app setup policies](/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane).

### <a name="why-am-i-seeing-an-allow-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-allow-user-pinning"></a>Pourquoi une fenêtre « Autoriser l’épinglage de l’utilisateur » apparaît-elle dans le panneau stratégies d’installation après avoir éteint « Autoriser l’épinglage de l’utilisateur ? »

![Capture d’écran de la section de stratégie d’installation dans l’interface utilisateur avec une fenêtre pop-up confirmant que l’épinglage utilisateur est actif.](media/appsetup4.png) 

Ce comportement est attendu pour un appareil dans un espace partagé et permet d’éviter l’épinglage involontaire d’application.
